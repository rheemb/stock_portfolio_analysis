
# **Stock Portfolio Analysis**
This project analyzes historical stock data from the Consumer Staples, Industrials, and Utilities sectors of the S&P 500 (2017-2022) to optimize portfolio performance. Using data preparation, statistical modeling, and optimization techniques, it evaluates investment strategies, assesses risk, and compares portfolio returns against the S&P 500 benchmark.

## What I Did
1. **Data Preparation:**
+ Retrieved S&P 500 stock tickers and sectors from Wikipedia.
+ Filtered for Consumer Staples (36 stocks), Industrials (77 stocks), and Utilities (30 stocks) as assigned to Group 8.
+ Fetched daily adjusted close prices (2017-01-01 to 2022-12-31) using the Yahoo Finance API.
+ Cleaned data by removing tickers with insufficient history (BF.B, GEV, KVUE, VLTO) and null values.
+ Created sector-specific DataFrames for analysis.
  
2. **Linear Regression:**
+ Applied linear regression to identify trends and predict 2022 performance for top stocks in each sector.
+ Selected top performers: EL (Consumer Staples), FE (Utilities), LDOS (Industrials) based on time series visualization.
  
3. **Modern Portfolio Theory (MPT):**
+ Built an optimization model to balance risk and return, using historical returns and covariance.
+ Determined optimal risk threshold and stock allocations.

4. **Buy-and-Hold Strategy:**
+ Simulated a $100,000 investment in the MPT portfolio and compared it to the S&P 500 over 2022.

5. **Monte Carlo Simulation:**
+ Ran simulations (1000-10000 iterations) to estimate loss probabilities for individual stocks and the portfolio.

## **Libraries Used**
+ **Pandas:** Data manipulation (e.g., DataFrames for stock prices, filtering sectors).
+ **Matplotlib:** Visualization (e.g., time series plots, efficient frontier).
+ **NumPy:** Numerical operations (e.g., covariance calculations).
+ **yahoo_fin:** Fetched historical stock data from Yahoo Finance.
+ **Pyomo:** Formulated and solved the MPT optimization problem.
+ **IPOPT Solver:** Optimized portfolio allocations (installed via custom binary).

## Conclusions with Metrics/Values
1. **Linear Regression:**
    + **Top Stocks Identified:**
       + Consumer Staples: EL (strong upward trend in adjusted close prices).
        + Utilities: FE (consistent growth pattern).
        + Industrials: LDOS (robust performance over time).
     + **Why:** Chosen based on time series visualizations showing higher stability and growth compared to peers like TSN or WBA.

2. **Modern Portfolio Theory (MPT):**
    + **Risk Threshold:** 0.00035 (optimal point for stable stock allocations)).
    + **Reward Plateau:** 0.0014 (consistent returns beyond risk of 0.000325).
    + **Key Insight:** Higher allocation to EL, indicating potential risk concentration, necessitating risk management and balanced risk-return at the chosen threshold.
    + **Why:** Selected 0.00035 after experimentation to balance risk and reward; neglected higher thresholds due to diminishing returns.
3. **Buy-and-Hold Strategy:**
    + Performance: MPT portfolio with a $100,000 initial investment outperformed the S&P 500 throughout 2022. 
    + Outcome: Visualized in investment strategy plots, confirming MPT’s superior growth over the market benchmark.
4. **Monte Carlo Simulation:**
    + **Loss Probabilities:**
       + Individual Stocks: TSN (36.6%), EL (12.0%), LDOS (30.6%), FE (35.9%).
       + Overall Portfolio: 6.9%.
    + **Stability:** Increasing simulations from 1000 to 10000 showed no significant change, confirming reliability.
    + **Why:** MPT reduced portfolio risk (6.9%) compared to individual stocks (~30% average), highlighting diversification benefits; neglected higher simulation counts as results stabilized.
