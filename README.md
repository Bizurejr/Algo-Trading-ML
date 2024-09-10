# Algo-Trading-ML


## Overview

This project develops an unsupervised learning trading strategy to analyze S&P 500 stocks. Unlike supervised learning, this approach does not use labeled data or predefined target variables. Instead, the model focuses on extracting insights from financial data through clustering techniques and feature calculations to build and optimize a stock portfolio.

## Project Steps

1. **Download/Load S&P 500 Stock Prices Data**
   - Fetch historical price data for S&P 500 stocks using `yfinance`.

2. **Calculate Features and Technical Indicators**
   - **Garman-Klass Volatility**: Measures volatility using high, low, open, and adjusted close prices.
   - **RSI (Relative Strength Index)**: Momentum oscillator calculated over a 20-day period.
   - **Bollinger Bands**: Includes lower, middle, and upper bands calculated over 20 periods.
   - **ATR (Average True Range)**: Measures volatility over a 14-day period.
   - **MACD (Moving Average Convergence Divergence)**: Trend-following momentum indicator.

3. **Aggregate Data to Monthly Level and Filter Top 150 Most Liquid Stocks**
   - Convert daily data to monthly frequency.
   - Filter stocks based on Dollar Volume to retain the top 150 most liquid stocks.

4. **Calculate Monthly Returns for Different Time Horizons**
   - Compute returns over various periods (e.g., 1-month, 2-month) to capture momentum patterns.

5. **Download Fama-French Factors and Calculate Rolling Factor Betas**
   - Use Fama-French factors to estimate asset exposure to risk factors.
   - Perform rolling linear regression to compute factor betas.

6. **Fit K-Means Clustering Algorithm Monthly**
   - Group stocks into clusters based on their features using K-Means clustering.
   - Use predefined centroids for clustering initialization if needed.

7. **Form Portfolio Based on Efficient Frontier Optimization**
   - Select stocks from the chosen cluster (e.g., cluster 3) based on your hypothesis.
   - Optimize portfolio weights to maximize the Sharpe ratio using `PyPortfolioOpt`.

8. **Download Fresh Daily Prices Data**
   - Fetch daily price data for selected stocks.
   - Calculate daily returns and optimize portfolio weights monthly.

9. **Visualize Portfolio Returns and Compare to S&P 500**
   - Compare the performance of the optimized portfolio against the S&P 500 index.

## Required Packages

- `pandas`
- `numpy`
- `matplotlib`
- `statsmodels`
- `pandas_datareader`
- `datetime`
- `yfinance`
- `sklearn`
- `PyPortfolioOpt`

## Usage

1. **Clone the Repository**

   ```bash
   git clone https://github.com/Bizurejr/Algo-Trading-ML)
