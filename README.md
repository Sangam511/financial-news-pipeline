Financial Data ETL Pipeline
This project implements an automated pipeline to extract, transform, and load financial data from multiple sources. It combines stock price data from Yahoo Finance and news sentiment analysis from NewsAPI. The pipeline is automated using Prefect, with SQLite as the storage backend and interactive visualizations for insights.

Data Sources:
	1.	Yahoo Finance (yfinance):
	•	Provides stock price data (AAPL, GOOGL, AMZN).
	•	Metrics: Open, High, Low, Close, Volume.
	2.	NewsAPI:
	•	Provides financial news articles based on the query "stock market".
	•	Metrics: Title, description, published date.

Transformation Steps:
	1.	News Data:
	•	Sentiment analysis using TextBlob to compute polarity scores for each article.
	2.	Stock Data:
	•	Compute percentage price change (price_change).
	•	Calculate rolling volatility using a 3-hour window.

Data Destination:
	1.	SQLite Database:
	•	news_data table: Stores news articles and sentiment scores.
	•	stock_data table: Stores stock prices, price changes, and volatility.

Pipeline Automation:
	1.	Orchestration:
	•	Prefect orchestrates the ETL pipeline with tasks for:
	•	Data extraction from Yahoo Finance and NewsAPI.
	•	Data transformation with pandas and TextBlob.
	•	Data loading into SQLite.
	•	Visualization using plotly.
	2.	Scheduling:
	•	Prefect schedules the pipeline to run automatically at fixed intervals (e.g., every 24 hours).
	3.	Error Handling:
	•	Logs and exception handling ensure reliability.