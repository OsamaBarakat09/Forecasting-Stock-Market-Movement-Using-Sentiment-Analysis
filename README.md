# Forecasting stock market movement using Sentiment Analysis
This project discusses how fundamental analysis affects the stock market and how news has a significant impact on stock movement.
# News_Data
This file contain three data sets:
- News_Data: That contain:
  * Links: URLs of websites.
  * Text: article that we extract it from link.
  * Sentiment: Labeling data for (Positive & Natural & Negative).
  * Date: Date of each new.
  * Labeling_Sentiment: Convert labeling to (0 & 1 & 2).
    
- News_Links: That contain:
  * Links: General links that we will scrap links news that we will scrap text from it.
    
- Finance_Key_Words:
  * Key: Contain almost all acronyms companies in exchanges and finance terms to filter data.

# Project Summary: Forecasting Stock Market Movement Using News Data¶
* This Jupyter Notebook provides a comprehensive pipeline for forecasting stock market movements by analyzing news data scraped from multiple sources. The project integrates web scraping, natural language processing (NLP), sentiment analysis, and financial indicators to predict stock price trends. Below is a guide to help users understand and utilize the project effectively.

# Key Features¶
* Web Scraping: The project scrapes news articles from financial websites like Yahoo Finance, CNN, and CNBC. It extracts relevant links and processes them to gather news text and publication dates.

* Text Preprocessing: The news text is cleaned by removing HTML tags, special characters, and stopwords. Duplicate patterns and irrelevant content are filtered out to ensure high-quality data.

* Sentiment Analysis: The project uses the FinBERT model, a pre-trained NLP model specifically designed for financial sentiment analysis. News articles are classified into positive, negative, or neutral sentiments, which are then encoded for further analysis.

* Date Extraction and Formatting: Publication dates are extracted from the news articles and standardized into a consistent format (YYYY-MM-DD).

* Financial Indicators: The project calculates key financial indicators such as Moving Averages and Relative Strength Index (RSI) to analyze stock price trends.

* Visualization: The results are visualized using Matplotlib, showing stock price trends, RSI, and sentiment analysis over time. A Gradio interface is provided for users to input stock names and view the analysis interactively.

# How to Use the Project¶
* Setup: Ensure you have the required Python libraries installed (pandas, nltk, transformers, yfinance, gradio, etc.). Download the necessary NLTK resources using nltk.download().

* Data Collection: Run the web scraping scripts to collect news data from financial websites. The scraped data is stored in News_Data.csv and News_Links.csv.

* Text Processing: Clean and preprocess the text data to remove noise and irrelevant content. Filter the data to retain only finance-related news articles.

* Sentiment Analysis: Use the FinBERT model to classify the sentiment of each news article. Encode the sentiment labels for further analysis.

* Date Extraction: Extract and format publication dates from the news articles.

* Financial Analysis: Calculate moving averages and RSI for the stock data. Combine sentiment analysis with financial indicators to predict stock price movements.

* Visualization: Use the Gradio interface to input a stock name and visualize the analysis. The output includes plots for stock price trends, RSI, and sentiment analysis.

# File Structure¶
* News_Data: Contains the scraped news data, including links, text, sentiment, and dates.

* News_Links: Stores the links to the news articles.

* Finance_Key_Words: Contains a list of financial keywords used for filtering finance-related news.






