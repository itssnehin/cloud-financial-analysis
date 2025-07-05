# Stock and ETF Performance Analysis with Spark SQL

## Overview

This project analyzes the performance of stocks and Exchange-Traded Funds (ETFs) using a large historical dataset from the NASDAQ stock exchange. The primary focus is on leveraging the power of Apache Spark and Spark SQL to process and query big data, uncovering meaningful trends and insights from the financial markets.

The analysis is documented in the `Individual Project Notebook.ipynb` Jupyter Notebook, which includes detailed steps for data loading, preprocessing, analysis, and visualization.

## Dataset

The project utilizes the "Stock Market Dataset" from Kaggle, which contains historical data for a wide range of stocks and ETFs listed on the NASDAQ.

- **Data Source**: [Stock Market Dataset on Kaggle](https://www.kaggle.com/datasets/jacksoncrow/stock-market-dataset)
- **Contents**: The dataset includes daily price information (Open, High, Low, Close, Adjusted Close) and trading volume.

## Technologies Used

- **Data Processing**: Apache Spark, PySpark, HDFS
- **Data Analysis & Manipulation**: Spark SQL, Pandas
- **Data Visualization**: Matplotlib, Seaborn

## Key Analyses and Insights

The notebook explores several key areas of financial analysis:

### 1. Moving Average Crossover Analysis
- **Objective**: To identify long-term trend signals using the 50-day and 200-day moving averages.
- **Concepts**:
    - **Golden Cross**: A bullish signal where the short-term moving average (50-day) crosses above the long-term moving average (200-day).
    - **Death Cross**: A bearish signal where the short-term moving average crosses below the long-term one.
- **Findings**: The analysis of stocks like Apple (AAPL) and Microsoft (MSFT) revealed that while they experienced "Death Crosses" during major economic downturns like the 2008 financial crisis, they have predominantly maintained a bullish "Golden Cross" trend, indicating strong long-term growth.

### 2. Volatility During the 2008 Financial Crisis
- **Objective**: To compare the weekly price volatility of individual large-cap stocks (AAPL, MSFT, AMZN) against a market index ETF (SPY) during the 2007-2009 financial crisis.
- **Findings**: The analysis showed that while all assets experienced significant volatility spikes, the SPY ETF had smoother fluctuations and lower peaks. This highlights the diversification benefits of index funds, which can reduce the risk associated with the extreme price swings of a single stock.

### 3. Sharpe Ratio Analysis for ETFs
- **Objective**: To evaluate the risk-adjusted return of the top-performing ETFs using the Sharpe Ratio.
- **Concept**: The Sharpe Ratio measures how much excess return an investor receives for taking on additional risk. A higher ratio indicates a better risk-adjusted return.
- **Findings**: By calculating and plotting the weekly Sharpe Ratio for the top 5 ETFs, the analysis identified which funds provided the best performance for the level of risk taken during the analyzed period.

### 4. High and Low Breakout Analysis
- **Objective**: To identify significant price movements in retail stocks (e.g., BBBY, AEO) by detecting breakouts above 12-week highs or below 12-week lows.
- **Findings**: The analysis of normalized stock prices clearly visualized the sharp, systemic shock to the retail sector caused by the COVID-19 pandemic in early 2020, with all analyzed stocks suffering a dramatic drop in price.

## Setup and Usage

This project is designed to run in an environment with Apache Spark and HDFS.

1.  **Prerequisites**:
    - A running Spark cluster.
    - Access to HDFS for storing the dataset.
    - Python environment with Jupyter, PySpark, Pandas, Matplotlib, and Seaborn installed.

2.  **Data Loading**:
    - Download the dataset from the Kaggle link provided above.
    - Unzip and place the `stocks` and `etfs` folders into your HDFS directory (e.g., `hdfs://namenode:9000/data/`).

3.  **Running the Analysis**:
    - Launch the Jupyter Notebook server.
    - Open and run the cells in `Individual Project Notebook.ipynb` to see the full analysis. The notebook is self-contained and includes all the Spark SQL queries and Python code for visualization.
