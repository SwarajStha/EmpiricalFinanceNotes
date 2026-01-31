# Calculative Formulas Comprehensive Guide
## Methods and Databases in Empirical Finance WS 2025/2026

---

## Section 1: CAPM Formula

### Formula
The Capital Asset Pricing Model (CAPM) formula:

$$
E(R_i) = R_f + \beta_i[E(R_m) - R_f]
$$

Where:
- $E(R_i)$ = Expected return of asset $i$
- $R_f$ = Risk-free rate
- $\beta_i$ = Beta of asset $i$
- $E(R_m)$ = Expected return of the market
- $[E(R_m) - R_f]$ = Market risk premium

### Beta Calculation Formula

$$
\beta_i = \frac{Cov(R_i, R_m)}{Var(R_m)}
$$

### Mentions from Slides

**From Exercise 4 (Exercise-4-CAPM-and-Factor-Models.pdf), Slide 11:**

"Revisiting Capital Asset Pricing Model

Left-hand side of the regression is the return of a given portfolio or stock minus the risk-free rate

The right hand side is the component of systematic risk β, 

The reminder of the function is the idiosyncratic risk component epsilon and alpha. According to the CAPM, the only factor which should drive returns is the component of systematic risk.

$R_{i,t} - R_{f,t} = \alpha_i + \beta_i(R_{m,t} - R_{f,t}) + \epsilon_{i,t}$"

**From Exercise 4, Task 2 Question 1 (Slide 13):**

"What must be the beta of a portfolio with an expected return of 18%, a risk-free rate of 6%, and a market return of 14%?

Formula CAPM for a portfolio:

$0.18 = 0.06 + \beta(0.14 - 0.06)$

$0.18 = 0.06 + \beta \cdot 0.08$

$\beta = \frac{0.18 - 0.06}{0.08} = 1.5$"

**From Exercise 4, Task 2 Question 2 (Slide 14-15):**

"A security currently costs $50 and has an expected return of 14%. If its correlation with the market portfolio doubles (all else equal)?
(Risk-free rate = 6%, market risk premium = 8.5%)

Formula CAPM for a portfolio:

$0.14 = 0.06 + \beta \cdot 0.085$

$\beta = \frac{0.14 - 0.06}{0.085} = 0.941$

Correlation doubles → beta doubles:

$\beta_{new} = 2 \times 0.941 = 1.882$

$E(R) = 0.06 + 1.882 \times 0.085 = 0.22$ or 22%"

**From Exercise 4, Task 2 Question 3 (Slide 16-17):**

"Using the CAPM, what is the fair return for each company given the following information? Based on the CAPM fair returns calculated, is each company underpriced, overpriced, or properly priced?

Risk-free rate = 4%, Market risk premium = 6%

Company A: β = 1.5

$E(R_A) = 0.04 + 1.5 \times 0.06 = 0.13$ or 13%

Company B: β = 1.0

$E(R_B) = 0.04 + 1.0 \times 0.06 = 0.10$ or 10%

Company A: Forecasted return 12% < CAPM fair return 13%. Investors require 13% but the stock offers only 12%. The return is too low for its risk level. Company A is overpriced.

Company B: Forecasted return 11% > CAPM fair return 10%. Investors require 10% but the stock offers 11%. The return is higher than required for its risk level. Company B is underpriced."

**From Lecture 5 (Lecture-5.pdf), Slide 11:**

"Empirical implementation using excess returns:

$R_{i,t} - R_{f,t} = \alpha_i + \beta_i(R_{m,t} - R_{f,t}) + \epsilon_{i,t}$"

**From Mock Exam (Question 2):**

"Based on the information provided below, calculate the expected CAPM return for firm A and B assuming α = 0 and a market excess return of 2%.

Sample Variance-Covariance Matrix shows:
- Covariance of A with Market = 0.0320
- Variance of Market = 0.0625

β(A) = 0.0320/0.0625 = 0.512

CAPM return = 0.512 × 2% = 1.024%"

### Practice Questions

**Question 1:**
A stock has a beta of 1.25. The risk-free rate is 3%, and the expected market return is 11%. Calculate the expected return for this stock using the CAPM.

**Question 2:**
An investor is evaluating a portfolio with a beta of 0.80. If the risk-free rate is 2.5% and the market risk premium is 7%, what is the expected return of the portfolio according to the CAPM? If the actual return is 8%, is the portfolio overperforming or underperforming relative to CAPM predictions?

---

## Section 2: Minimum Variance Portfolio (MVP)

### Formulas

**For 2 assets:**

$$
w_1^{MVP} = \frac{\sigma_2^2 - \rho_{1,2}\sigma_1\sigma_2}{\sigma_1^2 + \sigma_2^2 - 2\rho_{1,2}\sigma_1\sigma_2}
$$

Or equivalently:

$$
w_1^{MVP} = \frac{\sigma_2^2 - Cov(1,2)}{\sigma_1^2 + \sigma_2^2 - 2Cov(1,2)}
$$

$$
w_2^{MVP} = 1 - w_1^{MVP}
$$

**For n assets (matrix form):**

$$
w^{MVP} = \frac{\Sigma^{-1}\mathbf{1}}{\mathbf{1}^T\Sigma^{-1}\mathbf{1}}
$$

Where:
- $w$ = column vector of weights $(w_1, w_2, ..., w_n)^T$
- $\mathbf{1}$ = column vector of ones $(1,1,...,1)^T$
- $\Sigma^{-1}$ = inverse of covariance matrix

### Mentions from Slides

**From Exercise 4, Slide 3:**

"Minimum Variance Portfolio (MVP) Recap

The MVP is the portfolio with the lowest possible volatility on the Efficient Frontier

With 2 assets the weights of the MVP is given by:

$w_1^{MVP} = \frac{\sigma_2^2 - \rho_{1,2}\sigma_1\sigma_2}{\sigma_1^2 + \sigma_2^2 - 2\rho_{1,2}\sigma_1\sigma_2}$

$w_1^{MVP} = \frac{\sigma_2^2 - Cov(1,2)}{\sigma_1^2 + \sigma_2^2 - 2Cov(1,2)}$

$w_2^{MVP} = 1 - w_1^{MVP}$

With more than 2 assets the weights of the MVP is given by:

$w^{MVP} = \frac{\Sigma^{-1}\mathbf{1}}{\mathbf{1}^T\Sigma^{-1}\mathbf{1}}$

Where w = column vector of weights, 1 = column vector of ones, Σ⁻¹ = inverse of covariance matrix"

**From Exercise 4, Task 1 Solution 1 (Slide 7-8):**

"Find the Minimum-Variance Portfolio (MVP)

Given: σ₁ = 15%, σ₂ = 20%, ρ₁₂ = 0.3

$w_1 = \frac{\sigma_2^2 - \rho_{1,2}\sigma_1\sigma_2}{\sigma_1^2 + \sigma_2^2 - 2\rho_{1,2}\sigma_1\sigma_2}$

$w_1 = \frac{0.04 - (0.15 \times 0.20 \times 0.3)}{0.0225 + 0.04 - 2(0.15 \times 0.20 \times 0.3)}$

$w_1 = \frac{0.04 - 0.009}{0.0225 + 0.04 - 0.018} = \frac{0.031}{0.0445} = 0.6966$ or 69.66%

$w_2 = 1 - 0.6966 = 0.3034$ or 30.34%"

**From Lecture 4 (Lecture-4.pdf), Slide 13:**

"The MVP is the portfolio with the lowest possible volatility on the Efficient Frontier

With 2 assets the weights of the MVP is given by:

$w_1^{MVP} = \frac{\sigma_2^2 - \rho_{1,2}\sigma_1\sigma_2}{\sigma_1^2 + \sigma_2^2 - 2\rho_{1,2}\sigma_1\sigma_2}$

$w_1^{MVP} = \frac{\sigma_2^2 - Cov(1,2)}{\sigma_1^2 + \sigma_2^2 - 2Cov(1,2)}$

$w_2^{MVP} = 1 - w_1^{MVP}$

With more than 2 assets the weights of the MVP is given by:

$w^{MVP} = \frac{\Sigma^{-1}\mathbf{1}}{\mathbf{1}^T\Sigma^{-1}\mathbf{1}}$"

### Practice Questions

**Question 1:**
An investor is considering two assets with the following characteristics:
- Asset 1: σ₁ = 22%, Asset 2: σ₂ = 16%
- Correlation ρ₁₂ = 0.25

Calculate the weights of the minimum variance portfolio.

**Question 2:**
You have two stocks in your portfolio:
- Stock A: Standard deviation = 30%
- Stock B: Standard deviation = 20%
- Covariance between A and B = 0.045

Find the weight allocation for the minimum variance portfolio and calculate its variance.

---

## Section 3: Portfolio Expected Return and Variance

### Formulas

**Expected Return:**

$$
E(R_p) = \sum_{i=1}^{n} w_i E(R_i)
$$

**For 2 assets:**

$$
E(R_p) = w_1 E(R_1) + w_2 E(R_2)
$$

**Portfolio Variance (2 assets):**

$$
\sigma_p^2 = w_1^2\sigma_1^2 + w_2^2\sigma_2^2 + 2w_1w_2\rho_{1,2}\sigma_1\sigma_2
$$

Or equivalently:

$$
\sigma_p^2 = w_1^2\sigma_1^2 + w_2^2\sigma_2^2 + 2w_1w_2Cov(1,2)
$$

### Mentions from Slides

**From Exercise 4, Task 1 Solution 2 (Slide 8):**

"Compute the MVP expected return and variance

Expected return:

$E(R_{MVP}) = w_1 \mu_1 + w_2 \mu_2$

$E(R_{MVP}) = 0.6966 \times 0.08 + 0.3034 \times 0.12 = 0.0921$ or 9.21%

Variance:

$\sigma_{MVP}^2 = w_1^2\sigma_1^2 + w_2^2\sigma_2^2 + 2w_1w_2\rho_{1,2}\sigma_1\sigma_2$

$\sigma_{MVP}^2 = 0.6966^2 \times 0.0225 + 0.3034^2 \times 0.04 + 2 \times 0.6966 \times 0.3034 \times 0.15 \times 0.20 \times 0.3$

$\sigma_{MVP}^2 = 0.0184$

$\sigma_{MVP} = \sqrt{0.0184} = 0.1356$ or 13.56%"

**From Lecture 4, Slide 6:**

"The expected return of that portfolio is simply the average return of all stocks in that portfolio:

$E(R_p) = \sum_{i=1}^{n} w_i E(R_i)$

Where:
- $E(R_p)$ = Expected return of the portfolio
- $w_i$ = Weight of stock i in the portfolio
- $E(R_i)$ = Expected return of stock i

If a portfolio has 2 stocks with weight 0.2, return 10% and weight 0.8 and return 8% then:

$E(R_p) = 0.20 \times 0.10 + 0.80 \times 0.08 = 0.084$ or 8.4%"

### Practice Questions

**Question 1:**
A portfolio consists of three stocks with the following weights and expected returns:
- Stock 1: w₁ = 0.40, E(R₁) = 12%
- Stock 2: w₂ = 0.35, E(R₂) = 9%
- Stock 3: w₃ = 0.25, E(R₃) = 15%

Calculate the expected return of the portfolio.

**Question 2:**
Calculate the variance of a portfolio with:
- w₁ = 0.60, σ₁ = 25%
- w₂ = 0.40, σ₂ = 18%
- ρ₁₂ = 0.40

---

## Section 4: Tangency Portfolio (Optimal Portfolio)

### Formula

**For 2 assets:**

$$
w_1^{tangency} = \frac{(\mu_1 - r_f)\sigma_2^2 - (\mu_2 - r_f)\rho_{1,2}\sigma_1\sigma_2}{(\mu_1 - r_f)\sigma_2^2 + (\mu_2 - r_f)\sigma_1^2 - (\mu_1 - r_f + \mu_2 - r_f)\rho_{1,2}\sigma_1\sigma_2}
$$

$$
w_2^{tangency} = 1 - w_1^{tangency}
$$

### Mentions from Slides

**From Exercise 4, Slide 4:**

"Calculating the optimal portfolio

The tangency portfolio is the portfolio of risky assets that has the highest Sharpe ratio

It represents the optimal risky portfolio that all rational investors should hold combined with the risk-free asset in proportions based on their risk tolerance

The risk-free rate determines which portfolio is tangent - a different risk-free rate would result in a different tangency portfolio

Formula shown with subscript notation for two assets"

**From Exercise 4, Task 1 Solution 3 (Slide 9):**

"Calculate the Optimal Portfolio

$w_1^{opt} = \frac{(\mu_1 - r_f)\sigma_2^2 - (\mu_2 - r_f)\rho_{1,2}\sigma_1\sigma_2}{(\mu_1 - r_f)\sigma_2^2 + (\mu_2 - r_f)\sigma_1^2 - (\mu_1 - r_f + \mu_2 - r_f)\rho_{1,2}\sigma_1\sigma_2}$

Given: μ₁ = 8%, μ₂ = 12%, σ₁ = 15%, σ₂ = 20%, ρ₁₂ = 0.3, rf = 6%

$w_1^{opt} = \frac{(0.08 - 0.06) \times 0.20^2 - (0.12 - 0.06) \times 0.15 \times 0.20 \times 0.3}{(0.08 - 0.06) \times 0.20^2 + (0.12 - 0.06) \times 0.15^2 - (0.08 - 0.06 + 0.12 - 0.06) \times 0.15 \times 0.20 \times 0.3}$

$w_1^{opt} = 0.5171$

$w_2^{opt} = 1 - 0.5171 = 0.4829$"

**From Lecture 4, Slide 15:**

"Calculating the optimal portfolio

The tangency portfolio is the portfolio of risky assets that has the highest Sharpe ratio

It represents the optimal risky portfolio that all rational investors should hold combined with the risk-free asset in proportions based on their risk tolerance

The risk-free rate determines which portfolio is tangent - a different risk-free rate would result in a different tangency portfolio

Volatility of the Tangency portfolio represents risk and the return of the Tangency portfolio minus the risk free rate is the risk premium"

### Practice Questions

**Question 1:**
Given two risky assets with the following characteristics:
- Asset 1: μ₁ = 10%, σ₁ = 18%
- Asset 2: μ₂ = 14%, σ₂ = 25%
- ρ₁₂ = 0.20, Risk-free rate = 4%

Calculate the weights for the tangency portfolio.

**Question 2:**
An investor can choose between:
- Stock A: Expected return = 9%, Standard deviation = 15%
- Stock B: Expected return = 13%, Standard deviation = 22%
- Correlation = 0.35, Risk-free rate = 3%

Find the optimal portfolio weights using the tangency portfolio formula.

---

## Section 5: Sharpe Ratio

### Formula

$$
\text{Sharpe Ratio} = \frac{E(R) - R_f}{\sigma}
$$

Or for annualized returns:

$$
\text{Sharpe Ratio (annual)} = \frac{\mu_{annual} - r_{f,annual}}{\sigma_{annual}} = \frac{\mu_{daily} \times 252 - r_{f,annual}}{\sigma_{daily} \times \sqrt{252}}
$$

### Mentions from Slides

**From Exercise 2 (Exercise-2-Financial-Data-structures.pdf), Task 4:**

"Formula: Sharpe Ratio = $\frac{R - r_f}{\sigma}$ (assuming rf = 0)

Asset A: $R_A = 0.7167$, $s_A = 0.9745$

$\text{Sharpe}_A = \frac{0.7167}{0.9745} = 0.7354$

Asset B: $R_B = 0.55$, $s_B = 0.6221$

$\text{Sharpe}_B = \frac{0.55}{0.6221} = 0.8841$"

**From Lecture 4, Slide 5:**

"Sharpe Ratio measures risk-adjusted return: how much excess return is achieved per unit of risk.

$SR = \frac{R - r_f}{\sigma}$"

**From Lecture 1, Slide 10:**

"Key Risk and Performance Metrics

Sharpe ratio: $\frac{\mu - r_f}{\sigma}$

- Sharpe ratio measures return per unit of risk
- Allows comparison across different strategies and asset classes"

### Practice Questions

**Question 1:**
A mutual fund has an annual return of 12% with a standard deviation of 18%. If the risk-free rate is 3%, calculate the Sharpe ratio of this fund.

**Question 2:**
Portfolio X has a mean return of 15% and volatility of 22%. Portfolio Y has a mean return of 11% and volatility of 14%. The risk-free rate is 2.5%. Which portfolio has a better risk-adjusted return?

---

## Section 6: Covariance and Correlation

### Formulas

**Sample Covariance:**

$$
Cov(A, B) = \frac{\sum_{i=1}^{n}(A_i - \bar{A})(B_i - \bar{B})}{n - 1}
$$

**Correlation Coefficient:**

$$
\rho_{A,B} = \frac{Cov(A,B)}{\sigma_A \sigma_B}
$$

Where $-1 \leq \rho_{A,B} \leq 1$

### Mentions from Slides

**From Exercise 2, Task 4 Solution Step 5:**

"Formula: $Cov(A, B) = \frac{\sum(A_i - \bar{A})(B_i - \bar{B})}{n - 1}$

| Month | A - R̄ₐ | B - R̄ᵦ | Product |
|-------|--------|--------|---------|
| 1 | 0.4833 | 0.35 | 0.1692 |
| 2 | -0.2167 | -0.75 | 0.1625 |
| 3 | -1.5167 | -0.15 | 0.2275 |
| 4 | 1.3833 | 0.95 | 1.3141 |
| 5 | 0.2833 | 0.15 | 0.0425 |
| 6 | -0.4167 | -0.55 | 0.2292 |

Sum of products = 0.1692 + 0.1625 + 0.2275 + 1.3141 + 0.0425 + 0.2292 = 2.1450

$Cov(A, B) = \frac{2.1450}{6 - 1} = \frac{2.1450}{5} = 0.4290$"

**From Lecture 4, Slide 10:**

"Correlation is standardized covariance, which is easier to interpret:

$\rho_{i,j} = \frac{Cov(i,j)}{\sigma_i \sigma_j}$

Correlation ranges from -1 (perfect negative correlation) to +1 (perfect positive correlation)"

### Practice Questions

**Question 1:**
Calculate the covariance between two assets given the following monthly returns:

| Month | Asset A | Asset B |
|-------|---------|---------|
| 1 | 0.05 | 0.03 |
| 2 | -0.02 | -0.01 |
| 3 | 0.04 | 0.05 |
| 4 | 0.01 | 0.02 |
| 5 | 0.03 | 0.04 |

**Question 2:**
Stock X has a standard deviation of 24%, Stock Y has a standard deviation of 19%, and their covariance is 0.0342. Calculate the correlation coefficient.

---

## Section 7: Standard Deviation (Volatility)

### Formula

**Sample Standard Deviation:**

$$
s = \sqrt{\frac{\sum_{i=1}^{n}(x_i - \bar{x})^2}{n - 1}}
$$

**Sample Variance:**

$$
s^2 = \frac{\sum_{i=1}^{n}(x_i - \bar{x})^2}{n - 1}
$$

### Mentions from Slides

**From Exercise 2, Task 4 Solution Step 3:**

"Formula: $s = \sqrt{\frac{\sum(x_i - \bar{x})^2}{n - 1}}$

Asset A:

Sum of squared deviations = 0.2336 + 0.0469 + 2.3003 + 1.9135 + 0.0803 + 0.1736 = 4.7482

$s_A^2 = \frac{4.7482}{6 - 1} = \frac{4.7482}{5} = 0.9496$

$s_A = \sqrt{0.9496} = 0.9745$

Asset B:

Sum of squared deviations = 0.1225 + 0.5625 + 0.0225 + 0.9025 + 0.0225 + 0.3025 = 1.9350

$s_B^2 = \frac{1.9350}{6 - 1} = \frac{1.9350}{5} = 0.3870$

$s_B = \sqrt{0.3870} = 0.6221$"

**From Lecture 4, Slide 5:**

"Volatility: How far the return deviates from the mean return, often measured as the standard deviation of returns.

$\sigma = \sqrt{\frac{1}{N-1}\sum_{t=1}^{N}(r_t - \bar{r})^2}$"

### Practice Questions

**Question 1:**
Calculate the sample standard deviation of the following monthly returns:
1.5%, -0.8%, 2.2%, 0.5%, -1.2%, 1.8%

**Question 2:**
A stock has the following returns over 5 months: 5%, 3%, -2%, 7%, 2%. Calculate the sample variance and standard deviation.

---

## Section 8: Returns (Simple and Log)

### Formulas

**Simple (Arithmetic) Return:**

$$
R_t = \frac{P_t - P_{t-1}}{P_{t-1}} = \frac{P_t}{P_{t-1}} - 1
$$

**Log (Continuously Compounded) Return:**

$$
r_t = \ln\left(\frac{P_t}{P_{t-1}}\right) = \ln(P_t) - \ln(P_{t-1})
$$

**Total Return (with dividends):**

$$
R_t^{total} = \frac{P_t + D_t - P_{t-1}}{P_{t-1}}
$$

### Mentions from Slides

**From Lecture 1, Slide 8-9:**

"Return Definitions

Simple (arithmetic) return:

$R_t = \frac{P_t - P_{t-1}}{P_{t-1}} = \frac{P_t}{P_{t-1}} - 1$

- Intuitive percentage change in investment value
- Used for single-period analysis and cross-sectional comparisons

Log (continuously compounded) return:

$r_t = \ln\left(\frac{P_t}{P_{t-1}}\right)$

- Time-additive: $r_{t-1,t+1} = r_{t-1,t} + r_{t,t+1}$
- Better statistical properties for time-series analysis
- Approximately equal to simple returns for small changes: $r_t \approx R_t$ when $|R_t| < 0.1$"

**From Lecture 3, Slide 14:**

"Price return (Only capital appreciation):

$R_t^{price} = \frac{P_t - P_{t-1}}{P_{t-1}}$

Total return (Price appreciation + dividends):

$R_t^{total} = \frac{P_t + D_t - P_{t-1}}{P_{t-1}}$

Why this matters for empirical work:
- Total return gives complete picture of investment performance
- High-dividend stocks look better with total return
- Historical backtests must include dividend reinvestment"

### Practice Questions

**Question 1:**
A stock's price increases from $45 to $52 over one month. Calculate both the simple return and the log return.

**Question 2:**
An investor bought a stock at $80, received a $2 dividend, and sold it at $87. Calculate the total return. Also calculate what the price return would have been ignoring dividends.

---

## Section 9: Fama-MacBeth Regression

### Methodology

**Step 1: Periodic Cross-sectional regressions (each month t)**

$$
R_{i,t} - R_{f,t} = \lambda_{0,t} + \lambda_{1,t}X_{i,t-1}^{(1)} + \lambda_{2,t}X_{i,t-1}^{(2)} + ... + \lambda_{K,t}X_{i,t-1}^{(K)} + \epsilon_{i,t}
$$

- Regress returns of all stocks on lagged characteristics
- Obtain coefficient estimates $\lambda_{k,t}$ for each month
- Repeat for every month in sample

**Step 2: Average Time-series results**

$$
\bar{\lambda}_k = \frac{1}{T}\sum_{t=1}^{T}\lambda_{k,t}
$$

- Average coefficient across all months
- Compute standard error: $SE(\bar{\lambda}_k) = \frac{\sigma(\lambda_{k,t})}{\sqrt{T}}$
- Test significance: $t = \frac{\bar{\lambda}_k}{SE(\bar{\lambda}_k)}$

### Mentions from Slides

**From Exercise 7 (Exercise_7.pdf), Slide 5:**

"Fama-MacBeth Regression Methodology

Step 1: Periodic Cross-sectional regressions (each month)

$R_{i,t} - R_{f,t} = \lambda_{0,t} + \lambda_{1,t}X_{i,t-1}^{(1)} + \lambda_{2,t}X_{i,t-1}^{(2)} + \lambda_{K,t}X_{i,t-1}^{(K)} + \epsilon_{i,t}$

Regress returns of all stocks on lagged characteristics
Obtain coefficient estimates $\lambda_{i,t}$ for each month
Repeat for every month in sample

Step 2: Average Time-series results

$\bar{\lambda}_k = \frac{1}{T}\sum_{t=1}^{T}\lambda_{k,t}$

Average coefficient across all months
Compute standard error $SE(\bar{\lambda}_k) = \frac{\sigma(\lambda_{k,t})}{\sqrt{T}}$
Test significance $t = \frac{\bar{\lambda}_k}{SE(\bar{\lambda}_k)}$

The Two-Step Procedure"

**From Exercise 7, Task 1 (Slide 6-7):**

"Given model: $\hat{ret} = \alpha + \lambda_1 Beta + \lambda_2 Size + \lambda_3 Value + \lambda_4 Profitability$

$\alpha = 0.020, \lambda_1 = 0.050, \lambda_2 = 0.120, \lambda_3 = -0.030, \lambda_4 = 0.080$

A firm has the following characteristics:
Market Beta = 1.3, Size = 0.7, Value = 0.4, Profitability = 0.05

1. Compute the predicted monthly return, $\hat{ret}$.

Solution:

$\hat{ret} = 0.020 + 0.050(1.3) + 0.120(0.7) + (-0.030)(0.4) + 0.080(0.05)$

$\hat{ret} = 0.020 + 0.065 + 0.084 - 0.012 + 0.004 = 0.161$

$\hat{ret} = 0.161$ or 16.1%

2. If the actual return is ret = 0.025, compute the residual.

$u = ret - \hat{ret} = 0.025 - 0.161 = -0.136$

$u = -0.136$ or -13.6%"

**From Lecture 7 (Lecture-7.pdf), Slide 25-26:**

"Fama-MacBeth Regression Methodology

Why This Particular Procedure?

The problem:
- Stock returns have time-varying volatility and correlation
- We cannot simply run one large panel regression, as residuals are correlated over time.
- Standard errors would be wrong, t-statistics misleading
- Violates key regression assumption of independent errors

The solution:
- Separate time-series from cross-section
- Step 1: Cross-section (each month) → Avoids time-series correlation issues
- Step 2: Average across months → Averages out month-specific noise"

### Practice Questions

**Question 1:**
In a Fama-MacBeth regression, the following coefficients are obtained for Size over 60 months:
Month 1: -0.15, Month 2: -0.18, ..., Average across all 60 months: -0.12
The standard deviation of these 60 coefficients is 0.048.

Calculate the t-statistic for the average Size coefficient.

**Question 2:**
A researcher runs monthly cross-sectional regressions for 120 months. The average coefficient on the book-to-market ratio is 0.045 with a time-series standard error of 0.015. Test whether this coefficient is statistically significant at the 5% level.

---

## Section 10: Linear Factor Model (Predicted Return)

### Formula

$$
\hat{r}_i = \alpha + \beta_1 Factor1_i + \beta_2 Factor2_i + \beta_3 Factor3_i + ... + \beta_k Factork_i
$$

**Residual:**

$$
\epsilon_i = r_i - \hat{r}_i
$$

### Mentions from Slides

**From Mock Exam, Question 3:**

"Consider the linear factor model:

$\hat{r}_i = \alpha + \beta_1 Beta_i + \beta_2 Size_i + \beta_3 Value_i + \beta_4 Profitability_i$

with

$\alpha = 0.015, \beta_1 = 0.045, \beta_2 = 0.100, \beta_3 = -0.020, \beta_4 = 0.060$

A firm has the following characteristics:

Beta = 1.4, Size = 0.6, Value = 0.5, Profitability = 0.10

1. Compute the predicted monthly return $\hat{r}$.

Solution: (plug and play)

$\hat{r} = 0.015 + 0.045(1.4) + 0.100(0.6) + (-0.020)(0.5) + 0.060(0.10)$

$\hat{r} = 0.015 + 0.063 + 0.060 - 0.010 + 0.006 = 0.134$

2. If the realized return is r = 0.05, compute the residual.

Solution: residual = diff. between predicted and actual (actual)

$\epsilon = r - \hat{r} = 0.05 - 0.134 = -0.084$

3. Suppose the realized return equals the predicted return. What does this imply about how well the model explains this firm's return in that month?

If realized = predicted, then residual = 0, meaning the model perfectly explains the return for that specific month (though this is rare and doesn't necessarily mean the model is perfect overall)."

### Practice Questions

**Question 1:**
A linear factor model has the following specification:
α = 0.012, β₁(Market) = 0.055, β₂(Size) = 0.085, β₃(Value) = -0.025

A firm has: Market Beta = 1.1, Size = 0.50, Value = 0.35

Calculate the predicted monthly return. If the actual return is 0.08, what is the residual?

**Question 2:**
Consider a 4-factor model:
α = 0.018, β₁ = 0.040, β₂ = 0.110, β₃ = -0.015, β₄ = 0.070

For a firm with Factor1 = 1.2, Factor2 = 0.8, Factor3 = 0.6, Factor4 = 0.15, calculate the expected return according to the model.

---

## Section 11: Event Study - Abnormal Returns

### Formulas

**Market Model (Estimation):**

$$
R_{i,t} = \alpha_i + \beta_i R_{m,t} + \epsilon_{i,t}
$$

Where:
- $\beta_i = \frac{Cov(R_i, R_m)}{Var(R_m)}$
- $\alpha_i = \bar{R}_i - \beta_i \bar{R}_m$

**Expected Return:**

$$
E(R_{i,t}) = \alpha_i + \beta_i R_{m,t}
$$

**Abnormal Return (AR):**

$$
AR_{i,t} = R_{i,t} - E(R_{i,t}) = R_{i,t} - (\alpha_i + \beta_i R_{m,t})
$$

**Cumulative Abnormal Return (CAR):**

$$
CAR_{i}(t_1, t_2) = \sum_{t=t_1}^{t_2} AR_{i,t}
$$

### Mentions from Slides

**From Exercise 8 (Exercise_8.pdf), Task 1 (Slide 5-7):**

"Given the following stock market data, estimate the market model for an event study:

| Day | Market(Rm) | Stock (R) |
|-----|-----------|-----------|
| -6 | 0.0020 | 0.0030 |
| -5 | -0.0010 | -0.0015 |
| -4 | 0.0010 | 0.0017 |
| -3 | 0.0000 | 0.0002 |
| -2 | 0.0030 | 0.0042 |
| -1 | -0.0020 | -0.0031 |

Market Model: $R_{i,t} = \alpha_i + \beta_i R_{m,t} + \epsilon_{i,t}$

The estimation of the model requires knowledge about beta and alpha

Beta can be estimated using return data:

$\beta = \frac{Cov(R, R_m)}{Var(R_m)}$

Alpha can be estimated:

$\alpha = \bar{R} - \beta \bar{R}_m$

Solution:

1. Sample Means:

$\bar{R}_m = \frac{\sum R_m}{6} = \frac{0.0030}{6} = 0.0005$

$\bar{R} = \frac{\sum R}{6} = \frac{0.0045}{6} = 0.00075$

2. Estimate Beta:

$Cov(R, R_m) = \frac{\sum(R - \bar{R})(R_m - \bar{R}_m)}{n-1} = 0.0000273$

$Var(R_m) = \frac{\sum(R_m - \bar{R}_m)^2}{n-1} = 0.000019$

$\beta = \frac{0.0000273}{0.000019} = 1.43$

3. Estimate Alpha:

$\alpha = 0.00075 - 1.43(0.0005) = 0.000034$"

**From Exercise 8, Task 2 (Slide 8-10):**

"Given the model estimated in Task 1, compute abnormal returns in the event window:

| Day | Market | Stock |
|-----|--------|-------|
| 0 | 0.0010 | 0.0120 |
| 1 | 0.0020 | 0.0040 |
| 2 | -0.0010 | -0.0005 |

Solution:

Day 0:

$E(R_0) = 0.0000343 + 1.4314(0.0010) = 0.0014657$

$AR_0 = 0.0120 - 0.0014657 = 0.0105343$ (expected return)

Day 1:

$E(R_1) = 0.0000343 + 1.4314(0.0020) = 0.0028971$

$AR_1 = 0.0040 - 0.0028971 = 0.0011029$

Day 2:

$E(R_2) = 0.0000343 + 1.4314(-0.0010) = -0.0013971$

$AR_2 = -0.0005 - (-0.0013971) = 0.0008971$

$CAR_{[0,2]} = 0.0105343 + 0.0011029 + 0.0008971 = 0.0125343$ or 1.25%

Interpretation:

The event window shows positive abnormal returns on all three days (0 to 2), with a particularly large abnormal return on the announcement day (Day 0). This indicates that the market reacted immediately and positively to the announcement. The cumulative abnormal return of approximately 1.25% over [0, 2] suggests that the announcement conveyed new, value-relevant information to investors."

### Practice Questions

**Question 1:**
A stock has α = 0.0005 and β = 1.35 (estimated from pre-event data). On the event day, the market return is 0.015 and the stock return is 0.035. Calculate the abnormal return for the event day.

**Question 2:**
An event study finds the following abnormal returns around an announcement:
- Day -1: AR = 0.002
- Day 0: AR = 0.018
- Day +1: AR = 0.005
- Day +2: AR = -0.003

Calculate the cumulative abnormal return (CAR) for the window [-1, +2].

---

## Section 12: Fixed Effects Regression (Panel Data)

### Formula

**Fixed Effects Model:**

$$
Y_{it} = \alpha_i + \beta X_{it} + \epsilon_{it}
$$

**Within Transformation (De-meaning):**

$$
(Y_{it} - \bar{Y}_i) = \beta(X_{it} - \bar{X}_i) + (\epsilon_{it} - \bar{\epsilon}_i)
$$

Where $\bar{Y}_i$ and $\bar{X}_i$ are firm-specific time averages.

**Fixed Effects Estimator:**

$$
\hat{\beta}_{FE} = \frac{\sum_{i,t}(X_{it} - \bar{X}_i)(Y_{it} - \bar{Y}_i)}{\sum_{i,t}(X_{it} - \bar{X}_i)^2}
$$

### Mentions from Slides

**From Exercise 8, Task 3 (Slide 11-15):**

"Given the following model:

$Investment_{it} = \alpha_i + \beta Leverage_{it} + \epsilon_{it}$

Where:
- i = firm
- t = year
- $\alpha_i$ = firm fixed effect
- β = effect of leverage on investment

Study the question: When a firm becomes more or less leveraged over time, does its level of investment change?

Panel data (2 firms, 2 periods):

| Firm | Year | Investment | Leverage |
|------|------|-----------|----------|
| A | 1 | 0.10 | 0.30 |
| A | 2 | 0.08 | 0.40 |
| B | 1 | 0.20 | 0.50 |
| B | 2 | 0.18 | 0.60 |

Why would estimating using pooled OLS lead to biased or misleading results in this setting?

Answer: Firms differ in time-invariant characteristics (e.g. managerial quality, risk, corporate culture). These characteristics affect both leverage and investment. Pooled OLS ignores this unobserved heterogeneity. As a result, leverage is correlated with the error term leading to omitted variable bias. Fixed effects address this by comparing each firm to itself over time.

Fixed Effects Estimation Steps:

Step 1: Compute firm means

Firm A:
$\bar{Investment}_A = \frac{0.10 + 0.08}{2} = 0.09$
$\bar{Leverage}_A = \frac{0.30 + 0.40}{2} = 0.35$

Firm B:
$\bar{Investment}_B = \frac{0.20 + 0.18}{2} = 0.19$
$\bar{Leverage}_B = \frac{0.50 + 0.60}{2} = 0.55$

Step 2: Demean variables (Within-firm deviations)

| Firm | Year | Investment_it - Investment_i | Leverage_it - Leverage_i |
|------|------|----------------------------|--------------------------|
| A | 1 | 0.01 | -0.05 |
| A | 2 | -0.01 | 0.05 |
| B | 1 | 0.01 | -0.05 |
| B | 2 | -0.01 | 0.05 |

Step 3: Estimating using de-meaned version

The fixed effects estimator is OLS on the demeaned data:

$\hat{\beta} = \frac{\sum(Leverage_{it} - \bar{Leverage}_i)(Investment_{it} - \bar{Investment}_i)}{\sum(Leverage_{it} - \bar{Leverage}_i)^2}$

$\hat{\beta} = \frac{(-0.05)(0.01) + (0.05)(-0.01) + (-0.05)(0.01) + (0.05)(-0.01)}{(-0.05)^2 + (0.05)^2 + (-0.05)^2 + (0.05)^2}$

$\hat{\beta} = \frac{-0.001 - 0.001 - 0.001 - 0.001}{0.0025 + 0.0025 + 0.0025 + 0.0025} = \frac{-0.004}{0.01} = -0.20$

Interpretation: The fixed effects estimate of -0.20 implies that within a given firm, an increase in leverage is associated with a decrease in investment. Because the fixed effects estimator removes time-invariant firm characteristics (e.g. managerial ability, firm culture, baseline risk), this result is not driven by cross-firm differences, but by changes within the same firm over time."

### Practice Questions

**Question 1:**
Consider the following panel data for two firms over 3 years:

| Firm | Year | Y | X |
|------|------|---|---|
| A | 1 | 5.2 | 10 |
| A | 2 | 4.8 | 12 |
| A | 3 | 5.5 | 11 |
| B | 1 | 7.0 | 15 |
| B | 2 | 6.5 | 17 |
| B | 3 | 7.2 | 16 |

Calculate the firm means, demean the data, and estimate the fixed effects coefficient β using the within transformation.

**Question 2:**
In a fixed effects model studying the relationship between R&D intensity and firm growth, the following demeaned data is obtained:

| Observation | (X - X̄) | (Y - Ȳ) |
|-------------|---------|---------|
| 1 | -0.02 | -0.15 |
| 2 | 0.03 | 0.20 |
| 3 | -0.01 | -0.05 |
| 4 | 0.01 | 0.08 |
| 5 | -0.01 | -0.08 |

Calculate the fixed effects estimator β̂.

---

## Summary Table of All Formulas

| Formula Name | Formula | Page Reference |
|-------------|---------|----------------|
| CAPM | $E(R_i) = R_f + \beta_i[E(R_m) - R_f]$ | Exercise 4, Slide 11 |
| Beta | $\beta_i = \frac{Cov(R_i, R_m)}{Var(R_m)}$ | Exercise 4, Slide 13 |
| Minimum Variance Portfolio (2 assets) | $w_1^{MVP} = \frac{\sigma_2^2 - Cov(1,2)}{\sigma_1^2 + \sigma_2^2 - 2Cov(1,2)}$ | Exercise 4, Slide 3 |
| Minimum Variance Portfolio (n assets) | $w^{MVP} = \frac{\Sigma^{-1}\mathbf{1}}{\mathbf{1}^T\Sigma^{-1}\mathbf{1}}$ | Exercise 4, Slide 3 |
| Portfolio Expected Return | $E(R_p) = \sum_{i=1}^{n} w_i E(R_i)$ | Lecture 4, Slide 6 |
| Portfolio Variance (2 assets) | $\sigma_p^2 = w_1^2\sigma_1^2 + w_2^2\sigma_2^2 + 2w_1w_2Cov(1,2)$ | Exercise 4, Slide 8 |
| Tangency Portfolio (2 assets) | $w_1^{tangency} = \frac{(\mu_1 - r_f)\sigma_2^2 - (\mu_2 - r_f)\rho_{1,2}\sigma_1\sigma_2}{(\mu_1 - r_f)\sigma_2^2 + (\mu_2 - r_f)\sigma_1^2 - (\mu_1 - r_f + \mu_2 - r_f)\rho_{1,2}\sigma_1\sigma_2}$ | Exercise 4, Slide 9 |
| Sharpe Ratio | $SR = \frac{E(R) - R_f}{\sigma}$ | Lecture 4, Slide 5 |
| Covariance | $Cov(A, B) = \frac{\sum_{i=1}^{n}(A_i - \bar{A})(B_i - \bar{B})}{n - 1}$ | Exercise 2, Task 4 |
| Correlation | $\rho_{A,B} = \frac{Cov(A,B)}{\sigma_A \sigma_B}$ | Lecture 4, Slide 10 |
| Standard Deviation | $s = \sqrt{\frac{\sum_{i=1}^{n}(x_i - \bar{x})^2}{n - 1}}$ | Exercise 2, Task 4 |
| Simple Return | $R_t = \frac{P_t - P_{t-1}}{P_{t-1}}$ | Lecture 1, Slide 8 |
| Log Return | $r_t = \ln\left(\frac{P_t}{P_{t-1}}\right)$ | Lecture 1, Slide 9 |
| Total Return | $R_t^{total} = \frac{P_t + D_t - P_{t-1}}{P_{t-1}}$ | Lecture 3, Slide 14 |
| Fama-MacBeth (Step 1) | $R_{i,t} - R_{f,t} = \lambda_{0,t} + \sum_{k}\lambda_{k,t}X_{i,t-1}^{(k)} + \epsilon_{i,t}$ | Exercise 7, Slide 5 |
| Fama-MacBeth (Step 2) | $\bar{\lambda}_k = \frac{1}{T}\sum_{t=1}^{T}\lambda_{k,t}$ | Exercise 7, Slide 5 |
| Linear Factor Model | $\hat{r}_i = \alpha + \sum_{k}\beta_k Factor_{k,i}$ | Mock Exam, Q3 |
| Abnormal Return | $AR_{i,t} = R_{i,t} - (\alpha_i + \beta_i R_{m,t})$ | Exercise 8, Slide 9 |
| Cumulative Abnormal Return | $CAR_{i}(t_1, t_2) = \sum_{t=t_1}^{t_2} AR_{i,t}$ | Exercise 8, Slide 10 |
| Fixed Effects Estimator | $\hat{\beta}_{FE} = \frac{\sum_{i,t}(X_{it} - \bar{X}_i)(Y_{it} - \bar{Y}_i)}{\sum_{i,t}(X_{it} - \bar{X}_i)^2}$ | Exercise 8, Slide 15 |

---

**End of Document**

*Created for Methods and Databases in Empirical Finance (WS 2025/2026)*  
*TUM Center for Digital Transformation*  
*Prof. Dr. Sebastian Müller*
