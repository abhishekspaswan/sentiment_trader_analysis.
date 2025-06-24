Bitcoin Trader Performance and Market Sentiment Analysis
This repository contains a Python script (sentiment_trader_analysis.py) that analyzes the relationship between Bitcoin trader performance and market sentiment. It leverages two datasets: the Bitcoin Fear & Greed Index (fear_greed_index.csv) and historical trader data from Hyperliquid (historical_data.csv). Designed for Jupyter Notebook, the script provides visualizations, correlations, and actionable trading strategy insights to help traders make data-driven decisions in volatile cryptocurrency markets.
Project Overview
The script merges daily trader metrics (e.g., profit/loss, trade size, leverage) with market sentiment data to uncover patterns in how sentiment (e.g., Extreme Fear, Greed) influences trading outcomes. It generates interactive visualizations and computes key metrics like sentiment streaks and correlations, offering strategies such as buying during Extreme Fear or selling during Greed. The project is ideal for traders, data analysts, or researchers interested in cryptocurrency market psychology and performance analysis.
Datasets
The analysis uses two datasets, which must be placed in a data/ subdirectory:

Bitcoin Fear & Greed Index (fear_greed_index.csv):

Description: Daily market sentiment indicator for cryptocurrencies, sourced from providers like alternative.me.
Columns:
timestamp: Unix timestamp.
value: Sentiment score (0–100; 0 = Extreme Fear, 100 = Extreme Greed).
classification: Sentiment category (Extreme Fear, Fear, Neutral, Greed, Extreme Greed).
date: Date in YYYY-MM-DD format.


Date Range: February 1, 2018, to May 2, 2025 (2,557 entries).


Historical Trader Data from Hyperliquid (historical_data.csv):

Description: Transaction records for Bitcoin trades on the Hyperliquid platform.
Columns: account, symbol, time, closedPnL, size, leverage, execution_price, side, start_position, event, etc.
Note: The script filters for Bitcoin trades (e.g., symbols containing "BTC" or "bitcoin").



Functionality
The sentiment_trader_analysis.py script performs the following:

Data Processing:

Loads and cleans datasets, converting dates and ensuring numeric values.
Standardizes sentiment classification to lowercase.
Aggregates trader data daily (mean closedPnL, trade count, total size, leverage).
Merges datasets with a left join, filling missing sentiment with mean value and 'neutral'.


Visualizations:

Sentiment Distribution: Bar chart of sentiment classification counts.
Average PnL by Sentiment: Bar chart of mean daily profit/loss (avg_pnl) by sentiment.
PnL Distribution: Box plot of avg_pnl distribution by sentiment.
Sentiment vs. PnL Over Time: Line plot comparing Fear & Greed value and avg_pnl.
Trade Size vs. PnL: Scatter plot of trade size (total_size) vs. avg_pnl, colored by sentiment, sized by trade count.


Analysis:

Correlation matrix for value, avg_pnl, trade_count, pnl_std, total_size, avg_leverage.
Longest streaks of Extreme Fear (value <= 25) and Extreme Greed (value >= 75).
Leverage and trade size trends by sentiment.


Insights:

Buy during Extreme Fear for potential oversold markets.
Sell or hold during Greed/Extreme Greed for bullish trends.
Manage risk in Fear periods with high PnL volatility.
Adjust leverage based on sentiment-driven performance.


