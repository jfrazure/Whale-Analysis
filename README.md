# Whale-Analysis

A Whale off the Port(folio)

In this assignment, you'll get to use what you've learned this week to evaluate the performance among various algorithmic, hedge, and mutual fund portfolios and compare them against the S&P 500 Index.


# Initial imports
import pandas as pd
import numpy as np
import datetime as dt
from pathlib import Path
​
%matplotlib inline
Data Cleaning

In this section, you will need to read the CSV files into DataFrames and perform any necessary data cleaning steps. After cleaning, combine all DataFrames into a single DataFrame.

Files:

whale_returns.csv: Contains returns of some famous "whale" investors' portfolios.

algo_returns.csv: Contains returns from the in-house trading algorithms from Harold's company.

sp500_history.csv: Contains historical closing prices of the S&P 500 Index.

Whale Returns

Read the Whale Portfolio daily returns and clean the data


# Reading whale returns
​

# Count nulls
​

# Drop nulls
​
Algorithmic Daily Returns

Read the algorithmic daily returns and clean the data


# Reading algorithmic returns
​

# Count nulls
​

# Drop nulls
​
S&P 500 Returns

Read the S&P 500 historic closing prices and create a new daily returns DataFrame from the data.


# Reading S&P 500 Closing Prices
​

# Check Data Types
​

# Fix Data Types
​

# Calculate Daily Returns
​

# Drop nulls
​

# Rename `Close` Column to be specific to this portfolio.
​
Combine Whale, Algorithmic, and S&P 500 Returns

# Join Whale Returns, Algorithmic Returns, and the S&P 500 Returns into a single DataFrame with columns for each portfolio's returns.
​
Conduct Quantitative Analysis

In this section, you will calculate and visualize performance and risk metrics for the portfolios.

Performance Anlysis

Calculate and Plot the daily returns.

# Plot daily returns of all portfolios
​
Calculate and Plot cumulative returns.

# Calculate cumulative returns of all portfolios
​
# Plot cumulative returns
​
Risk Analysis

Determine the risk of each portfolio:

Create a box plot for each portfolio.
Calculate the standard deviation for all portfolios
Determine which portfolios are riskier than the S&P 500
Calculate the Annualized Standard Deviation
Create a box plot for each portfolio

# Box plot to visually show risk
​
Calculate Standard Deviations

# Calculate the daily standard deviations of all portfolios
​
Determine which portfolios are riskier than the S&P 500

# Calculate  the daily standard deviation of S&P 500
​
# Determine which portfolios are riskier than the S&P 500
​
Calculate the Annualized Standard Deviation

# Calculate the annualized standard deviation (252 trading days)
​
Rolling Statistics

Risk changes over time. Analyze the rolling statistics for Risk and Beta.

Calculate and plot the rolling standard deviation for all portfolios using a 21-day window
Calculate the correlation between each stock to determine which portfolios may mimick the S&P 500
Choose one portfolio, then calculate and plot the 60-day rolling beta between it and the S&P 500
Calculate and plot rolling std for all portfolios with 21-day window

# Calculate the rolling standard deviation for all portfolios using a 21-day window
​
# Plot the rolling standard deviation
​
Calculate and plot the correlation

# Calculate the correlation
​
# Display de correlation matrix
​
Calculate and Plot Beta for a chosen portfolio and the S&P 500

# Calculate covariance of a single portfolio
​
# Calculate variance of S&P 500
​
# Computing beta
​
# Plot beta trend
​
Rolling Statistics Challenge: Exponentially Weighted Average

An alternative way to calculate a rolling window is to take the exponentially weighted moving average. This is like a moving window average, but it assigns greater importance to more recent observations. Try calculating the ewm with a 21-day half life for each portfolio, using standard deviation (std) as the metric of interest.


# Use `ewm` to calculate the rolling window
​
Sharpe Ratios

In reality, investment managers and thier institutional investors look at the ratio of return-to-risk, and not just returns alone. After all, if you could invest in one of two portfolios, and each offered the same 10% return, yet one offered lower risk, you'd take that one, right?

Using the daily returns, calculate and visualize the Sharpe ratios using a bar plot

# Annualized Sharpe Ratios
​

# Visualize the sharpe ratios as a bar plot
​
Determine whether the algorithmic strategies outperform both the market (S&P 500) and the whales portfolios.

Write your answer here!

Create Custom Portfolio

In this section, you will build your own portfolio of stocks, calculate the returns, and compare the results to the Whale Portfolios and the S&P 500.

Choose 3-5 custom stocks with at last 1 year's worth of historic prices and create a DataFrame of the closing prices and dates for each stock.
Calculate the weighted returns for the portfolio assuming an equal number of shares for each stock
Join your portfolio returns to the DataFrame that contains all of the portfolio returns
Re-run the performance and risk analysis with your portfolio to see how it compares to the others
Include correlation analysis to determine which stocks (if any) are correlated
Choose 3-5 custom stocks with at last 1 year's worth of historic prices and create a DataFrame of the closing prices and dates for each stock.

# Reading data from 1st stock
​

# Reading data from 2nd stock
​

# Reading data from 3rd stock
​

# Combine all stocks in a single DataFrame
​

# Reset Date index
​

# Reorganize portfolio data by having a column per symbol
​

# Calculate daily returns
​
# Drop NAs
​
# Display sample data
​
Calculate the weighted returns for the portfolio assuming an equal number of shares for each stock

# Set weights
weights = [1/3, 1/3, 1/3]
​
# Calculate portfolio return
​
# Display sample data
​
Join your portfolio returns to the DataFrame that contains all of the portfolio returns

# Join your returns DataFrame to the original returns DataFrame
​

# Only compare dates where return data exists for all the stocks (drop NaNs)
​
Re-run the risk analysis with your portfolio to see how it compares to the others
Calculate the Annualized Standard Deviation

# Calculate the annualized `std`
​
Calculate and plot rolling std with 21-day window

# Calculate rolling standard deviation
​
# Plot rolling standard deviation
​
Calculate and plot the correlation

# Calculate and plot the correlation
​
Calculate and Plot Rolling 60-day Beta for Your Portfolio compared to the S&P 500

# Calculate and plot Beta
​
Using the daily returns, calculate and visualize the Sharpe ratios using a bar plot

# Calculate Annualized Sharpe Ratios
​

# Visualize the sharpe ratios as a bar plot
​
How does your portfolio do?

Write your answer here!


​

Simple
0
16
Python 3 (ipykernel) | Idle
0
whale_analysis.ipynb
