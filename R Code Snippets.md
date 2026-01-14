
**[Exercise 2]**

#Setting the timeperiod (Only change the end_date)
start_date <- ymd("1970-01-01")  %% #variable = "start_date" %%
end_date <- ymd("2023-12-31")

#CRSP monthly security file,
msf_db <- tbl(wrds, in_schema("crsp", "msf_v2")) 
%% ['wrds'] is the name of connection, [in_schema(library, datasets)] %%

#select
  select(
    permno, %% Security identifier %%
    date, %% Month of the observation %%
    ret = mthret, %% Return %%
    shrout, %% Shares outstanding (in thousands) %%
    prc = mthprc, %% Last traded price in a month %%
    primaryexch, %% Primary exchange code %%
    siccd, %% Industry code %%
    ticker %% Ticker Information %%
  )

# Correct filter 
crsp_monthly <- msf_db |>
  filter(mthcaldt >= start_date & mthcaldt <= end_date) |>
  select(-c(siccd, primaryexch, conditionaltype, tradingstatusflg)) |> 
  inner_join(
    stksecurityinfohist_db |>
      filter(sharetype == "NS" & 
               securitytype == "EQTY" & 
               securitysubtype == "COM" & 
               usincflg == "Y" & 
               issuertype %in% c("ACOR", "CORP") & 
               primaryexch %in% c("N", "A", "Q") &
               conditionaltype %in% c("RW", "NW") &
               tradingstatusflg == "A") |> 
      select(permno, secinfostartdt, secinfoenddt,
             primaryexch, siccd),
    join_by(permno)
  ) |> 
  filter(mthcaldt >= secinfostartdt & mthcaldt <= secinfoenddt) |>
  mutate(date = floor_date(mthcaldt, "month")) |>
  select(
    permno, %% Security identifier %%
    date, %% Month of the observation %%
    ret = mthret, %% Return %%
    shrout, %% Shares outstanding (in thousands) %%
    prc = mthprc, %% Last traded price in a month %%
    primaryexch, %% Primary exchange code %%
    siccd, %% Industry code %%
    ticker %% Ticker Information %%
  ) |>
  collect() |>
  mutate(
    date = ymd(date),
    shrout = shrout * 1000
  )

#Important tbl() does not download data collect is necessary to actually have it in the environment 
#crsp_monthly <- msf_db |> collect() saves entire msf_db as crsp_monthly

![[Pasted image 20251115130334.png]]


# Compustat

funda_db <- tbl(wrds, in_schema("comp","funda"))

compustat <- funda_db |>
  filter(
    indfmt == "INDL" &
      datafmt == "STD" & 
      consol == "C" &
      curcd == "USD" &
      datadate >= start_date & datadate <= end_date
  ) |>
  select(
    gvkey, %% Firm identifier %%
    datadate, %% Date of the accounting data %%
    seq, %% Stockholders' equity %%
    ceq, %% Total common/ordinary equity %%
    at, %% Total assets %%
    lt, %% Total liabilities %%
    txditc, %% Deferred taxes and investment tax credit %%
    txdb, %% Deferred taxes %%
    itcb, %% Investment tax credit %%
    pstkrv, %% Preferred stock redemption value %%
    pstkl, %% Preferred stock liquidating value %%
    pstk, %% Preferred stock par value %%
    capx, %% Capital investment %%
    oancf, %% Operating cash flow %%
    sale,  %% Revenue %%
    cogs, %% Costs of goods sold %%
    xint, %% Interest expense %%
    xsga %% Selling, general, and administrative expenses %%
  ) |>
  collect()

![[Pasted image 20251115134022.png]]


**Task 3.**
Calculating using R:

%% The following blocks construct three different portfolios from the 'crsp_monthly' data.%%
%% It uses the pipe operator (%>%) for sequential data manipulation with dplyr functions.%%

%% 1. CONSTRUCT PORTFOLIOS%%

%% --- Consumer Staples Portfolio ---%%
Consumer_Staples <- crsp_monthly %>%
  %% Start filtering data from January 1st, 1980.%%
  filter(date >= "1980-01-01") %>%
  %% Select securities based on their Ticker symbols (KO: Coca-Cola, WMT: Walmart, PG: Procter & Gamble).%%
  filter(ticker == "KO" | ticker == "WMT" | ticker == "PG") %>%
  %% Group the data by month (or time period represented by 'date').%%
  group_by(date) %>%
  %% Calculate the portfolio return (RET_Port) as the simple average of the excess returns ('ret_excess')%%
  %% of the selected stocks for that period. 'na.rm=TRUE' ignores missing returns.%%
  summarize(RET_Port = mean(ret_excess, na.rm = TRUE))

%% --- Tech Portfolio ---%%
Tech <- crsp_monthly %>%
  %% Filter data from 1980-01-01.%%
  filter(date >= "1980-01-01") %>%
  %% Select major Tech stocks (AAPL: Apple, MSFT: Microsoft, INTC: Intel).%%
  filter(ticker == "AAPL" | ticker == "MSFT" | ticker == "INTC") %>%
  %% Group by date.%%
  group_by(date) %>%
  %% Calculate the simple average of excess returns for the Tech stocks.%%
  summarize(RET_Port = mean(ret_excess, na.rm = TRUE))

%% --- Market Portfolio ---%%
Market <- crsp_monthly %>%
  %% Filter data from 1980-01-01.%%
  filter(date >= "1980-01-01") %>%
  %% No Ticker filter, so it includes all available securities.%%
  group_by(date) %>%
  %% Calculate the Market return (proxy) as the average of ALL excess returns for that period.%%
  summarize(RET_Port = mean(ret_excess, na.rm = TRUE))


%% 2. DESCRIPTIVE STATISTICS FOR INITIAL PORTFOLIOS%%

%% Load the 'moments' package, which is typically used for calculating skewness and kurtosis%%
%% (though only mean, StDev, and Sharpe are used here).%%
library(moments)

%% Calculate descriptive statistics for each of the three created portfolios.%%
descriptive_stats <- tibble(
  Portfolio = c("Consumer Staples", "Tech", "Market"),
  %% Calculate the Mean return for each portfolio.%%
  Mean = c(mean(Consumer_Staples$RET_Port, na.rm = TRUE),
           mean(Tech$RET_Port, na.rm = TRUE),
           mean(Market$RET_Port, na.rm = TRUE)),
  %% Calculate the Standard Deviation (Volatility) for each portfolio.%%
  StDev = c(sd(Consumer_Staples$RET_Port, na.rm = TRUE),
             sd(Tech$RET_Port, na.rm = TRUE),
             sd(Market$RET_Port, na.rm = TRUE)),
  %% Calculate the Sharpe Ratio (Mean / StDev), which measures risk-adjusted return.%%
  %% This implicitly assumes the risk-free rate is zero, since 'ret_excess' is used.%%
  Sharpe_Ratio = Mean / StDev
)


%% 3. PREPARING DATA FOR PORTFOLIO OPTIMIZATION%%

%% Create a single matrix/data frame of portfolio returns, aligned by date.%%
portfolio_returns <- Consumer_Staples %>%
  %% Rename the return column for clarity before joining.%%
  rename(Consumer_Staples = RET_Port) %>%
  %% Merge with the Tech returns based on the 'date' column.%%
  left_join(Tech %>% rename(Tech = RET_Port), by = "date") %>%
  %% Merge with the Market returns based on the 'date' column.%%
  left_join(Market %>% rename(Market = RET_Port), by = "date") %>%
  %% Remove the 'date' column, leaving only the return series.%%
  select(-date) %>%
  %% Remove any rows where one or more return series are missing (NA).%%
  na.omit()

%% Calculate the covariance matrix (Σ) of the three portfolio returns.%%
cov_matrix <- cov(portfolio_returns)
%% Calculate the mean return vector (μ) of the three portfolios.%%
mean_returns <- colMeans(portfolio_returns)


%% 4. CALCULATING TANGENCY PORTFOLIO WEIGHTS%%

%% The Tangency Portfolio is the portfolio on the efficient frontier with the highest Sharpe Ratio.%%
%% Its weight vector (w) is calculated as: w = (Σ^-1 * μ) / (1' * Σ^-1 * μ)%%

%% Create a vector of ones for the denominator calculation (used for summing components).%%
ones <- rep(1, ncol(portfolio_returns))
%% Calculate the inverse of the covariance matrix (Σ^-1).%%
inv_cov <- solve(cov_matrix)
%% Calculate the final Tangency Portfolio weights (w).%%
tangency_weights <- (inv_cov %*% mean_returns) / as.numeric(t(ones) %*% inv_cov %*% mean_returns)


%% 5. CONSTRUCTING TANGENCY AND NAIVE PORTFOLIOS%%

%% Calculate the return of the Tangency Portfolio using the optimal weights.%%
tangency_portfolio <- portfolio_returns %>%
  mutate(Tangency = Consumer_Staples * tangency_weights[1] + 
           Tech * tangency_weights[2] + 
           Market * tangency_weights[3])

%% Calculate the return of a Naive (Equal-Weight) Portfolio (1/3 for each asset).%%
naive_portfolio <- portfolio_returns %>%
  mutate(Naive = (Consumer_Staples + Tech + Market) / 3)


%% 6. COMPARING TANGENCY AND NAIVE PORTFOLIOS%%

%% Calculate summary statistics for the two new diversified portfolios.%%
comparison_stats <- tibble(
  Portfolio = c("Tangency", "Naive Equal-Weight"),
  Mean = c(mean(tangency_portfolio$Tangency, na.rm = TRUE),
           mean(naive_portfolio$Naive, na.rm = TRUE)),
  StDev = c(sd(tangency_portfolio$Tangency, na.rm = TRUE),
             sd(naive_portfolio$Naive, na.rm = TRUE)),
  %% Calculate the Sharpe Ratio for comparison.%%
  Sharpe_Ratio = Mean / StDev
)

%% Display the comparison of performance metrics.%%
print(comparison_stats)

%% Display the calculated optimal weights for the Tangency Portfolio.%%
tangency_weights_df <- tibble(
  Portfolio = c("Consumer Staples", "Tech", "Market"),
  Weight = as.numeric(tangency_weights)
)
