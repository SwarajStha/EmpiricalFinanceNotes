<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# Practice Questions - Solutions Guide

## Methods and Databases in Empirical Finance WS 2025/2026


***

## Section 1: CAPM Formula

### Question 1

**Problem:** A stock has a beta of 1.25. The risk-free rate is 3%, and the expected market return is 11%. Calculate the expected return for this stock using the CAPM.

**Solution:**

Using the CAPM formula: E(R) = Rf + β[E(Rm) - Rf]

E(R) = 0.03 + 1.25 × (0.11 - 0.03)
E(R) = 0.03 + 1.25 × 0.08
E(R) = 0.03 + 0.10
**E(R) = 0.13 or 13.00%**

***

### Question 2

**Problem:** An investor is evaluating a portfolio with a beta of 0.80. If the risk-free rate is 2.5% and the market risk premium is 7%, what is the expected return of the portfolio according to the CAPM? If the actual return is 8%, is the portfolio overperforming or underperforming relative to CAPM predictions?

**Solution:**

E(R) = Rf + β × MRP
E(R) = 0.025 + 0.80 × 0.07
E(R) = 0.025 + 0.056
**E(R) = 0.081 or 8.10%**

Actual return = 8.00%
Expected return = 8.10%

**The portfolio is underperforming** relative to CAPM predictions (8.00% < 8.10%)

***

## Section 2: Beta Calculation

### Question 1

**Problem:** Given the following variance-covariance matrix, calculate the beta for Stock X:

- Covariance of Stock X with Market = 0.0450
- Variance of Market = 0.0625

**Solution:**

β = Cov(X, Market) / Var(Market)
β = 0.0450 / 0.0625
**β = 0.72**

***

### Question 2

**Problem:** A stock has a covariance with the market of 0.0280. The standard deviation of the market is 18%. Calculate the beta of the stock.

**Solution:**

First, calculate variance of market:
Var(Market) = σm² = 0.18² = 0.0324

Then calculate beta:
β = Cov(Stock, Market) / Var(Market)
β = 0.0280 / 0.0324
**β = 0.8642**

***

## Section 3: Minimum Variance Portfolio (2 assets)

### Question 1

**Problem:** An investor is considering two assets with the following characteristics:

- Asset 1: σ₁ = 22%, Asset 2: σ₂ = 16%
- Correlation ρ₁₂ = 0.25

Calculate the weights of the minimum variance portfolio.

**Solution:**

w₁ = (σ₂² - ρ₁₂σ₁σ₂) / (σ₁² + σ₂² - 2ρ₁₂σ₁σ₂)

w₁ = (0.16² - 0.25 × 0.22 × 0.16) / (0.22² + 0.16² - 2 × 0.25 × 0.22 × 0.16)
w₁ = (0.0256 - 0.0088) / (0.0484 + 0.0256 - 0.0176)
w₁ = 0.0168 / 0.0564
**w₁ = 0.2979 or 29.79%**
**w₂ = 0.7021 or 70.21%**

***

### Question 2

**Problem:** You have two stocks in your portfolio:

- Stock A: Standard deviation = 30%
- Stock B: Standard deviation = 20%
- Covariance between A and B = 0.045

Find the weight allocation for the minimum variance portfolio and calculate its variance.

**Solution:**

w_A = (σ_B² - Cov(A,B)) / (σ_A² + σ_B² - 2×Cov(A,B))
w_A = (0.20² - 0.045) / (0.30² + 0.20² - 2×0.045)
w_A = (0.04 - 0.045) / (0.09 + 0.04 - 0.09)
w_A = -0.005 / 0.04
**w_A = -0.125 or -12.50%** (short position)
**w_B = 1.125 or 112.50%** (long position)

Portfolio Variance:
σp² = w_A²σ_A² + w_B²σ_B² + 2w_Aw_BCov(A,B)
σp² = (-0.125)² × 0.30² + (1.125)² × 0.20² + 2 × (-0.125) × 1.125 × 0.045
σp² = 0.00140625 + 0.050625 + (-0.012656)
**σp² = 0.0394 or 3.94%**
**σp = 0.1984 or 19.84%**

***

## Section 4: Portfolio Expected Return

### Question 1

**Problem:** A portfolio consists of three stocks with the following weights and expected returns:

- Stock 1: w₁ = 0.40, E(R₁) = 12%
- Stock 2: w₂ = 0.35, E(R₂) = 9%
- Stock 3: w₃ = 0.25, E(R₃) = 15%

Calculate the expected return of the portfolio.

**Solution:**

E(Rp) = w₁E(R₁) + w₂E(R₂) + w₃E(R₃)
E(Rp) = 0.40 × 0.12 + 0.35 × 0.09 + 0.25 × 0.15
E(Rp) = 0.048 + 0.0315 + 0.0375
**E(Rp) = 0.117 or 11.70%**

***

### Question 2

**Problem:** An investor allocates 60% to bonds with an expected return of 5% and 40% to stocks with an expected return of 14%. What is the expected return of this portfolio?

**Solution:**

E(Rp) = 0.60 × 0.05 + 0.40 × 0.14
E(Rp) = 0.03 + 0.056
**E(Rp) = 0.086 or 8.60%**

***

## Section 5: Portfolio Variance (2 assets)

### Question 1

**Problem:** Calculate the variance of a portfolio with:

- w₁ = 0.60, σ₁ = 25%
- w₂ = 0.40, σ₂ = 18%
- ρ₁₂ = 0.40

**Solution:**

σp² = w₁²σ₁² + w₂²σ₂² + 2w₁w₂ρ₁₂σ₁σ₂
σp² = 0.60² × 0.25² + 0.40² × 0.18² + 2 × 0.60 × 0.40 × 0.40 × 0.25 × 0.18
σp² = 0.0225 + 0.005184 + 0.00864
**σp² = 0.0363 or 3.63%**
**σp = 0.1906 or 19.06%**

***

### Question 2

**Problem:** Two assets have the following properties:

- Asset A: weight = 0.70, standard deviation = 20%
- Asset B: weight = 0.30, standard deviation = 35%
- Covariance(A,B) = 0.035

Calculate the portfolio variance and standard deviation.

**Solution:**

σp² = w_A²σ_A² + w_B²σ_B² + 2w_Aw_BCov(A,B)
σp² = 0.70² × 0.20² + 0.30² × 0.35² + 2 × 0.70 × 0.30 × 0.035
σp² = 0.0196 + 0.011025 + 0.0147
**σp² = 0.0453 or 4.53%**
**σp = 0.2129 or 21.29%**

***

## Section 6: Tangency Portfolio

### Question 1

**Problem:** Given two risky assets with the following characteristics:

- Asset 1: μ₁ = 10%, σ₁ = 18%
- Asset 2: μ₂ = 14%, σ₂ = 25%
- ρ₁₂ = 0.20, Risk-free rate = 4%

Calculate the weights for the tangency portfolio.

**Solution:**

w₁ = [(μ₁-rf)σ₂² - (μ₂-rf)ρ₁₂σ₁σ₂] / [(μ₁-rf)σ₂² + (μ₂-rf)σ₁² - (μ₁-rf+μ₂-rf)ρ₁₂σ₁σ₂]

Numerator = (0.10-0.04)×0.25² - (0.14-0.04)×0.20×0.18×0.25
Numerator = 0.06×0.0625 - 0.10×0.009
Numerator = 0.00375 - 0.0009 = 0.00285

Denominator = (0.10-0.04)×0.25² + (0.14-0.04)×0.18² - (0.10-0.04+0.14-0.04)×0.20×0.18×0.25
Denominator = 0.06×0.0625 + 0.10×0.0324 - 0.16×0.009
Denominator = 0.00375 + 0.00324 - 0.00144 = 0.00555

w₁ = 0.00285 / 0.00555 = **0.5135 or 51.35%**
**w₂ = 0.4865 or 48.65%**

***

### Question 2

**Problem:** An investor can choose between:

- Stock A: Expected return = 9%, Standard deviation = 15%
- Stock B: Expected return = 13%, Standard deviation = 22%
- Correlation = 0.35, Risk-free rate = 3%

Find the optimal portfolio weights using the tangency portfolio formula.

**Solution:**

w_A = [(μ_A-rf)σ_B² - (μ_B-rf)ρσ_Aσ_B] / [(μ_A-rf)σ_B² + (μ_B-rf)σ_A² - (μ_A-rf+μ_B-rf)ρσ_Aσ_B]

Numerator = (0.09-0.03)×0.22² - (0.13-0.03)×0.35×0.15×0.22
Numerator = 0.06×0.0484 - 0.10×0.01155
Numerator = 0.002904 - 0.001155 = 0.001749

Denominator = (0.09-0.03)×0.22² + (0.13-0.03)×0.15² - (0.09-0.03+0.13-0.03)×0.35×0.15×0.22
Denominator = 0.06×0.0484 + 0.10×0.0225 - 0.16×0.01155
Denominator = 0.002904 + 0.00225 - 0.001848 = 0.003306

w_A = 0.001749 / 0.003306 = **0.5290 or 52.90%**
**w_B = 0.4710 or 47.10%**

***

## Section 7: Sharpe Ratio

### Question 1

**Problem:** A mutual fund has an annual return of 12% with a standard deviation of 18%. If the risk-free rate is 3%, calculate the Sharpe ratio of this fund.

**Solution:**

Sharpe Ratio = (E(R) - Rf) / σ
Sharpe Ratio = (0.12 - 0.03) / 0.18
Sharpe Ratio = 0.09 / 0.18
**Sharpe Ratio = 0.50**

***

### Question 2

**Problem:** Portfolio X has a mean return of 15% and volatility of 22%. Portfolio Y has a mean return of 11% and volatility of 14%. The risk-free rate is 2.5%. Which portfolio has a better risk-adjusted return?

**Solution:**

Portfolio X:
SR_X = (0.15 - 0.025) / 0.22 = 0.125 / 0.22 = **0.5682**

Portfolio Y:
SR_Y = (0.11 - 0.025) / 0.14 = 0.085 / 0.14 = **0.6071**

**Portfolio Y has the better risk-adjusted return** with a Sharpe Ratio of 0.6071 compared to Portfolio X's 0.5682.

***

## Section 8: Covariance

### Question 1

**Problem:** Calculate the covariance between two assets given the following monthly returns:


| Month | Asset A | Asset B |
| :-- | :-- | :-- |
| 1 | 0.05 | 0.03 |
| 2 | -0.02 | -0.01 |
| 3 | 0.04 | 0.05 |
| 4 | 0.01 | 0.02 |
| 5 | 0.03 | 0.04 |

**Solution:**

Step 1: Calculate means
Mean(A) = (0.05 - 0.02 + 0.04 + 0.01 + 0.03) / 5 = 0.11 / 5 = 0.022
Mean(B) = (0.03 - 0.01 + 0.05 + 0.02 + 0.04) / 5 = 0.13 / 5 = 0.026

Step 2: Calculate products of deviations


| Month | (A - Ā) | (B - B̄) | Product |
| :-- | :-- | :-- | :-- |
| 1 | 0.028 | 0.004 | 0.000112 |
| 2 | -0.042 | -0.036 | 0.001512 |
| 3 | 0.018 | 0.024 | 0.000432 |
| 4 | -0.012 | -0.006 | 0.000072 |
| 5 | 0.008 | 0.014 | 0.000112 |

Sum of products = 0.00224

Cov(A,B) = 0.00224 / (5-1) = 0.00224 / 4
**Cov(A,B) = 0.00056**

***

### Question 2

**Problem:** Two stocks have the following deviations from their mean returns over 6 periods:


| Period | (Rₐ - R̄ₐ) | (Rᵦ - R̄ᵦ) |
| :-- | :-- | :-- |
| 1 | 0.02 | 0.015 |
| 2 | -0.015 | -0.010 |
| 3 | 0.010 | 0.020 |
| 4 | -0.005 | 0.005 |
| 5 | 0.020 | 0.012 |
| 6 | -0.010 | -0.008 |

Calculate the sample covariance.

**Solution:**

Calculate products:


| Period | Product |
| :-- | :-- |
| 1 | 0.02 × 0.015 = 0.000300 |
| 2 | -0.015 × -0.010 = 0.000150 |
| 3 | 0.010 × 0.020 = 0.000200 |
| 4 | -0.005 × 0.005 = -0.000025 |
| 5 | 0.020 × 0.012 = 0.000240 |
| 6 | -0.010 × -0.008 = 0.000080 |

Sum of products = 0.000945

Cov(A,B) = 0.000945 / (6-1) = 0.000945 / 5
**Cov(A,B) = 0.000189**

***

## Section 9: Correlation

### Question 1

**Problem:** Stock X has a standard deviation of 24%, Stock Y has a standard deviation of 19%, and their covariance is 0.0342. Calculate the correlation coefficient.

**Solution:**

ρ = Cov(X,Y) / (σ_X × σ_Y)
ρ = 0.0342 / (0.24 × 0.19)
ρ = 0.0342 / 0.0456
**ρ = 0.75**

***

### Question 2

**Problem:** The covariance between two assets is 0.0156. Asset 1 has a volatility of 20% and Asset 2 has a volatility of 13%. What is the correlation between these assets?

**Solution:**

ρ = Cov(1,2) / (σ₁ × σ₂)
ρ = 0.0156 / (0.20 × 0.13)
ρ = 0.0156 / 0.026
**ρ = 0.60**

***

## Section 10: Standard Deviation

### Question 1

**Problem:** Calculate the sample standard deviation of the following monthly returns:
1.5%, -0.8%, 2.2%, 0.5%, -1.2%, 1.8%

**Solution:**

Step 1: Calculate mean
Mean = (0.015 - 0.008 + 0.022 + 0.005 - 0.012 + 0.018) / 6 = 0.04 / 6 = 0.00667

Step 2: Calculate squared deviations


| Return | Deviation | Squared Dev |
| :-- | :-- | :-- |
| 0.015 | 0.00833 | 0.00006939 |
| -0.008 | -0.01467 | 0.00021521 |
| 0.022 | 0.01533 | 0.00023509 |
| 0.005 | -0.00167 | 0.00000279 |
| -0.012 | -0.01867 | 0.00034857 |
| 0.018 | 0.01133 | 0.00012839 |

Sum = 0.00099944

Variance = 0.00099944 / 5 = 0.00019989
**Standard Deviation = √0.00019989 = 0.01414 or 1.414%**

***

### Question 2

**Problem:** A stock has the following returns over 5 months: 5%, 3%, -2%, 7%, 2%. Calculate the sample variance and standard deviation.

**Solution:**

Step 1: Calculate mean
Mean = (0.05 + 0.03 - 0.02 + 0.07 + 0.02) / 5 = 0.15 / 5 = 0.03

Step 2: Calculate squared deviations


| Return | Deviation | Squared Dev |
| :-- | :-- | :-- |
| 0.05 | 0.02 | 0.0004 |
| 0.03 | 0.00 | 0.0000 |
| -0.02 | -0.05 | 0.0025 |
| 0.07 | 0.04 | 0.0016 |
| 0.02 | -0.01 | 0.0001 |

Sum = 0.0046

**Variance = 0.0046 / 4 = 0.00115 or 0.115%**
**Standard Deviation = √0.00115 = 0.03391 or 3.391%**

***

## Section 11: Returns (Simple and Log)

### Question 1

**Problem:** A stock's price increases from \$45 to \$52 over one month. Calculate both the simple return and the log return.

**Solution:**

Simple Return:
R = (P_t - P_{t-1}) / P_{t-1}
R = (52 - 45) / 45
R = 7 / 45
**R = 0.1556 or 15.56%**

Log Return:
r = ln(P_t / P_{t-1})
r = ln(52 / 45)
r = ln(1.1556)
**r = 0.1445 or 14.45%**

***

### Question 2

**Problem:** An investor bought a stock at \$80, received a \$2 dividend, and sold it at \$87. Calculate the total return. Also calculate what the price return would have been ignoring dividends.

**Solution:**

Total Return:
R^total = (P_t + D_t - P_{t-1}) / P_{t-1}
R^total = (87 + 2 - 80) / 80
R^total = 9 / 80
**R^total = 0.1125 or 11.25%**

Price Return (ignoring dividends):
R^price = (P_t - P_{t-1}) / P_{t-1}
R^price = (87 - 80) / 80
R^price = 7 / 80
**R^price = 0.0875 or 8.75%**

The dividend contributed 2.5% to the total return.

***

## Section 12: Fama-MacBeth Regression

### Question 1

**Problem:** In a Fama-MacBeth regression, the following coefficients are obtained for Size over 60 months:
Month 1: -0.15, Month 2: -0.18, ..., Average across all 60 months: -0.12
The standard deviation of these 60 coefficients is 0.048.

Calculate the t-statistic for the average Size coefficient.

**Solution:**

Step 1: Calculate standard error
SE(λ̄) = σ(λ) / √T
SE(λ̄) = 0.048 / √60
SE(λ̄) = 0.048 / 7.746
SE(λ̄) = 0.006197

Step 2: Calculate t-statistic
t = λ̄ / SE(λ̄)
t = -0.12 / 0.006197
**t = -19.37**

This is highly statistically significant (|t| > 2.66 for 1% level with df = 59).

***

### Question 2

**Problem:** A researcher runs monthly cross-sectional regressions for 120 months. The average coefficient on the book-to-market ratio is 0.045 with a time-series standard error of 0.015. Test whether this coefficient is statistically significant at the 5% level.

**Solution:**

t-statistic = λ̄ / SE(λ̄)
t = 0.045 / 0.015
**t = 3.00**

Critical value at 5% level (two-tailed) with df = 119 ≈ 1.98

Since **|t| = 3.00 > 1.98**, the coefficient is **statistically significant at the 5% level**.

**Interpretation:** The book-to-market ratio has a positive and statistically significant relationship with returns. On average, a one-unit increase in the book-to-market ratio is associated with a 4.5% higher return.

***

## Section 13: Linear Factor Model

### Question 1

**Problem:** A linear factor model has the following specification:
α = 0.012, β₁(Market) = 0.055, β₂(Size) = 0.085, β₃(Value) = -0.025

A firm has: Market Beta = 1.1, Size = 0.50, Value = 0.35

Calculate the predicted monthly return. If the actual return is 0.08, what is the residual?

**Solution:**

Predicted return:
r̂ = α + β₁×Beta + β₂×Size + β₃×Value
r̂ = 0.012 + 0.055×1.1 + 0.085×0.50 + (-0.025)×0.35
r̂ = 0.012 + 0.0605 + 0.0425 - 0.00875
**r̂ = 0.106 or 10.6%**

Residual:
ε = r - r̂
ε = 0.08 - 0.106
**ε = -0.026 or -2.6%**

The firm underperformed its predicted return by 2.6%.

***

### Question 2

**Problem:** Consider a 4-factor model:
α = 0.018, β₁ = 0.040, β₂ = 0.110, β₃ = -0.015, β₄ = 0.070

For a firm with Factor1 = 1.2, Factor2 = 0.8, Factor3 = 0.6, Factor4 = 0.15, calculate the expected return according to the model.

**Solution:**

r̂ = α + β₁×Factor1 + β₂×Factor2 + β₃×Factor3 + β₄×Factor4
r̂ = 0.018 + 0.040×1.2 + 0.110×0.8 + (-0.015)×0.6 + 0.070×0.15
r̂ = 0.018 + 0.048 + 0.088 - 0.009 + 0.0105
**r̂ = 0.1555 or 15.55%**

***

## Section 14: Event Study - Abnormal Returns

### Question 1

**Problem:** A stock has α = 0.0005 and β = 1.35 (estimated from pre-event data). On the event day, the market return is 0.015 and the stock return is 0.035. Calculate the abnormal return for the event day.

**Solution:**

Step 1: Calculate expected return
E(R) = α + β × R_m
E(R) = 0.0005 + 1.35 × 0.015
E(R) = 0.0005 + 0.02025
E(R) = 0.02075

Step 2: Calculate abnormal return
AR = R_actual - E(R)
AR = 0.035 - 0.02075
**AR = 0.01425 or 1.425%**

The stock had a positive abnormal return of 1.425% on the event day.

***

### Question 2

**Problem:** An event study finds the following abnormal returns around an announcement:

- Day -1: AR = 0.002
- Day 0: AR = 0.018
- Day +1: AR = 0.005
- Day +2: AR = -0.003

Calculate the cumulative abnormal return (CAR) for the window [-1, +2].

**Solution:**

CAR[-1, +2] = Σ AR_t
CAR[-1, +2] = 0.002 + 0.018 + 0.005 + (-0.003)
**CAR[-1, +2] = 0.022 or 2.2%**

**Interpretation:** Over the 4-day event window, the stock experienced a cumulative abnormal return of 2.2%. The largest positive reaction occurred on Day 0 (announcement day) with an AR of 1.8%, suggesting the market reacted positively to the new information.

***

## Section 15: Fixed Effects Regression

### Question 1

**Problem:** Consider the following panel data for two firms over 3 years:


| Firm | Year | Y | X |
| :-- | :-- | :-- | :-- |
| A | 1 | 5.2 | 10 |
| A | 2 | 4.8 | 12 |
| A | 3 | 5.5 | 11 |
| B | 1 | 7.0 | 15 |
| B | 2 | 6.5 | 17 |
| B | 3 | 7.2 | 16 |

Calculate the firm means, demean the data, and estimate the fixed effects coefficient β using the within transformation.

**Solution:**

Step 1: Calculate firm means

Firm A:
Ȳ_A = (5.2 + 4.8 + 5.5) / 3 = 5.167
X̄_A = (10 + 12 + 11) / 3 = 11.00

Firm B:
Ȳ_B = (7.0 + 6.5 + 7.2) / 3 = 6.900
X̄_B = (15 + 17 + 16) / 3 = 16.00

Step 2: Demean the data


| Firm | Year | Y - Ȳ | X - X̄ |
| :-- | :-- | :-- | :-- |
| A | 1 | 0.033 | -1.00 |
| A | 2 | -0.367 | 1.00 |
| A | 3 | 0.333 | 0.00 |
| B | 1 | 0.100 | -1.00 |
| B | 2 | -0.400 | 1.00 |
| B | 3 | 0.300 | 0.00 |

Step 3: Calculate β̂_FE

β̂ = Σ(X - X̄)(Y - Ȳ) / Σ(X - X̄)²

Numerator:
(-1.00)(0.033) + (1.00)(-0.367) + (0.00)(0.333) + (-1.00)(0.100) + (1.00)(-0.400) + (0.00)(0.300)
= -0.033 - 0.367 + 0 - 0.100 - 0.400 + 0
= -0.900

Denominator:
(-1.00)² + (1.00)² + (0.00)² + (-1.00)² + (1.00)² + (0.00)²
= 1 + 1 + 0 + 1 + 1 + 0
= 4

**β̂_FE = -0.900 / 4 = -0.225**

**Interpretation:** Within a firm, a one-unit increase in X is associated with a 0.225 decrease in Y, controlling for time-invariant firm characteristics.

***

### Question 2

**Problem:** In a fixed effects model studying the relationship between R\&D intensity and firm growth, the following demeaned data is obtained:


| Observation | (X - X̄) | (Y - Ȳ) |
| :-- | :-- | :-- |
| 1 | -0.02 | -0.15 |
| 2 | 0.03 | 0.20 |
| 3 | -0.01 | -0.05 |
| 4 | 0.01 | 0.08 |
| 5 | -0.01 | -0.08 |

Calculate the fixed effects estimator β̂.

**Solution:**

β̂_FE = Σ(X - X̄)(Y - Ȳ) / Σ(X - X̄)²

Numerator:
(-0.02)(-0.15) + (0.03)(0.20) + (-0.01)(-0.05) + (0.01)(0.08) + (-0.01)(-0.08)
= 0.003 + 0.006 + 0.0005 + 0.0008 + 0.0008
= 0.0111

Denominator:
(-0.02)² + (0.03)² + (-0.01)² + (0.01)² + (-0.01)²
= 0.0004 + 0.0009 + 0.0001 + 0.0001 + 0.0001
= 0.0016

**β̂_FE = 0.0111 / 0.0016 = 6.9375**

**Interpretation:** Within a firm, a one percentage point increase in R\&D intensity is associated with a 6.94 percentage point increase in firm growth, after controlling for time-invariant firm characteristics (such as industry, corporate culture, baseline capabilities).

***

**End of Solutions Guide**
<span style="display:none">[^1][^10][^11][^12][^13][^14][^15][^16][^17][^18][^19][^2][^20][^21][^3][^4][^5][^6][^7][^8][^9]</span>

<div align="center">⁂</div>

[^1]: Exercise_9.pdf

[^2]: Exercise_8.pdf

[^3]: Exercise_7.pdf

[^4]: Exercise 6.pdf

[^5]: Exercise 5 -Trading.pdf

[^6]: Exercise 4 -CAPM and Factor Models.pdf

[^7]: Exercise 2 -Financial Data structures.pdf

[^8]: Exercise 1 - Introduction to programming with R.pdf

[^9]: Lecture 12 - Gen AI and NLP in Finance II.pdf

[^10]: Lecture 11 - Gen AI and NLP in Finance I.pdf

[^11]: Lecture 10.pdf

[^12]: Lecture 9.pptx - Schreibgeschützt.pdf

[^13]: Lecture 8.pdf

[^14]: Lecture 7.pdf

[^15]: Lecture 6.pdf

[^16]: Lecture 5.pdf

[^17]: Lecture 4.pdf

[^18]: Lecture 3.pdf

[^19]: Lecture 2.pdf

[^20]: Lecture 1 - Introduction to Empirical Finance.pdf

[^21]: Exam_MDEF_WS25_26_Mock-4.pdf

