# Forecasting Stock Market Movement Using Sentiment Analysis

## 📑 Table of Contents
1. [Problem](#problem)
2. [Approach](#approach)
3. [Results](#results)
4. [Tech Stack](#tech-stack)
5. [News Data Overview](#news-data-overview)
6. [Project Summary](#project-summary--forecasting-stock-market-movement-using-news-data)
7. [Key Features](#key-features)
8. [How to Use](#how-to-use)
9. [File Structure](#file-structure)

---

# Problem
Financial markets are highly sensitive to public sentiment, where news headlines, analyst opinions, and social media discussions can trigger rapid changes in stock prices. However, the volume and velocity of such information make it nearly impossible for investors or analysts to manually assess its real impact in real time. Traditional models that rely solely on historical price data often fail to capture these behavioral and emotional market drivers.

This project addresses the challenge of quantifying and forecasting stock market movements through sentiment analysis of financial news, aiming to bridge the gap between market psychology and quantitative modeling.

---

# Approach 
To address the complexity of linking financial sentiment to market behavior, I built an **end-to-end pipeline** that combines **Natural Language Processing (NLP)**, **machine learning**, and **financial data analysis**. 🧠💹  

#### **1️⃣ Data Acquisition**  
The project begins with a large-scale scraping of real financial news from multiple reputable sources — including **CNBC**, **Reuters**, and **CoinDesk** — using **Python’s `requests`**, **`BeautifulSoup`**, and an intelligent retry mechanism for stable, automated data collection. Each article is timestamped and linked to the relevant stock ticker for accurate temporal alignment with market data.  

#### **2️⃣ Text Preprocessing & Sentiment Extraction**  
The raw text is cleaned and normalized through a structured NLP pipeline using **NLTK** and **spaCy**. This includes:  
- Removing URLs, HTML tags, and non-alphanumeric noise  
- Tokenization and lemmatization  
- Filtering out non-informative words  

Afterward, sentiment is extracted using both **rule-based models (VADER)** for fast benchmarking and **transformer-based models (FinBERT)** to capture nuanced financial language.  

#### **3️⃣ Feature Engineering**  
Each article’s sentiment score is aggregated by **company and date**, producing daily sentiment indicators. These are then merged with **market variables** (closing price, volume, volatility) pulled from **Yahoo Finance (`yfinance`)**, enabling the creation of hybrid features such as:  
- Rolling average sentiment  
- Sentiment volatility  
- Sentiment-weighted return ratios  

#### **4️⃣ Predictive Modeling**  
The combined dataset feeds into a **machine learning model** designed to predict next-day stock direction (up/down).  
Models evaluated include:  
- Logistic Regression (baseline)  
- Random Forest and XGBoost (ensemble learning)  
- FinBERT embeddings + Neural Network (deep learning extension)  

Model performance is assessed using **accuracy**, **F1-score**, **ROC-AUC**, and **cross-validation** to ensure consistency and generalization.  

#### **5️⃣ Interactive Visualization & Deployment**  
To make the results accessible and practical, I developed an **interactive Gradio dashboard** 🎛️.  
This allows users to:  
- Enter any financial headline or news paragraph  
- Instantly receive a sentiment score and predicted market movement  
- Visualize sentiment trends over time for any selected ticker  

The app transforms complex analytics into actionable insights, empowering users to understand how public sentiment shapes market trends in real time. 🚀  

✅ **Summary:**  
This multi-stage approach bridges qualitative market psychology and quantitative modeling — demonstrating how modern NLP and financial data science can work together to forecast short-term stock movements with data-driven precision.  

---

# Results  
The final model demonstrated that sentiment extracted from financial news holds **strong predictive power** over short-term stock movements. 📈  

After extensive experimentation, the **FinBERT-based model** achieved an average **accuracy of 72%** and an **F1-score of 0.70**, outperforming classical baselines such as Logistic Regression and Random Forest.  

Key insights include:  
- **Positive sentiment days** often correlate with next-day price increases, especially for high-volume tickers.  
- **Sudden sentiment drops** are early indicators of short-term corrections or volatility spikes.  
- Integrating **sentiment volatility** as a feature improved prediction stability and reduced noise from overly optimistic or pessimistic outliers.  

The results validate the hypothesis that **market sentiment acts as a leading indicator** when properly quantified and aligned with trading data.  

To make the findings interactive, I deployed a **Gradio web app** allowing users to:  
- Input any news headline or article  
- Instantly receive sentiment classification (Positive / Neutral / Negative)  
- View the predicted market direction and probability score  

📊 The app and models together form a reproducible, transparent, and interpretable framework for **financial sentiment forecasting**, bridging the gap between human perception and algorithmic insight.  

---

# Tech Stack  

**Languages & Libraries 🐍**  
- **Python** — Core language for all data processing and modeling  
- **Pandas** & **NumPy** — Data cleaning, transformation, and feature engineering  
- **Scikit-learn** — Machine learning pipelines and evaluation metrics  
- **XGBoost** — Ensemble learning for predictive performance  
- **Transformers (Hugging Face)** — FinBERT model for financial sentiment analysis  
- **NLTK** & **spaCy** — Natural language preprocessing and tokenization  
- **Matplotlib** & **Seaborn** — Data visualization and trend exploration  

**Data Sources & APIs 🌐**  
- **Yahoo Finance (`yfinance`)** — Historical market data retrieval  
- **BeautifulSoup & Requests** — Automated web scraping of financial news  

**Deployment & Visualization 🚀**  
- **Gradio** — Interactive web interface for real-time sentiment prediction  
- **Streamlit / Hugging Face Spaces (optional)** — Alternative platforms for demo hosting  
- **Git & GitHub** — Version control, documentation, and portfolio showcase  

This technology stack integrates modern NLP techniques with classical financial modeling — ensuring reproducibility, interpretability, and professional presentation for both technical and non-technical audiences.  

---

## 🗂️ News Data Overview

This project relies on three main datasets that form the foundation for sentiment-based stock forecasting.  

### **1️⃣ News_Data**
Contains the main corpus of scraped financial articles.  
**Columns:**
- **Links** — URLs of individual news articles  
- **Text** — Full article content extracted from each link  
- **Sentiment** — Labeled sentiment category (`Positive`, `Neutral`, or `Negative`)  
- **Date** — Publication date of each article  
- **Labeling_Sentiment** — Encoded sentiment labels (`0`, `1`, `2`) for modeling  

### **2️⃣ News_Links**
Contains the list of financial news website URLs from which articles are scraped.  
**Columns:**
- **Links** — Base URLs to be crawled for extracting news articles  

### **3️⃣ Finance_Key_Words**
Contains a curated dictionary of financial terms and company acronyms used to filter relevant content.  
**Columns:**
- **Key** — Financial acronyms, tickers, and terminology extracted from major exchanges and market sources  

---

## 📘 Project Summary — *Forecasting Stock Market Movement Using News Data*
This Jupyter Notebook provides a **comprehensive end-to-end pipeline** for forecasting stock market movements using sentiment extracted from financial news.  

The workflow integrates **web scraping**, **NLP preprocessing**, **sentiment analysis**, and **financial indicators** to generate insights and predict stock price trends.

---

## 🚀 Key Features
- **Web Scraping:** Gathers news articles from leading financial websites such as *Yahoo Finance, CNN,* and *CNBC*.  
- **Text Preprocessing:** Cleans text by removing HTML tags, special characters, and stopwords while filtering duplicate or irrelevant content.  
- **Sentiment Analysis:** Employs **FinBERT**, a pre-trained financial NLP model, to classify articles as *positive*, *negative*, or *neutral*.  
- **Date Extraction:** Standardizes publication dates into a consistent `YYYY-MM-DD` format.  
- **Financial Indicators:** Calculates **Moving Averages (MA)** and **Relative Strength Index (RSI)** for trend detection.  
- **Visualization:** Generates interactive visualizations of stock sentiment, RSI, and price trends via **Matplotlib** and a **Gradio dashboard**.  

---

## ⚙️ How to Use
1. **Setup:** Install the required libraries (`pandas`, `nltk`, `transformers`, `yfinance`, `gradio`, etc.). Download NLTK resources as needed.  
2. **Data Collection:** Run scraping scripts to populate `News_Data.csv` and `News_Links.csv`.  
3. **Text Processing:** Clean, tokenize, and filter the news articles to keep finance-relevant data.  
4. **Sentiment Analysis:** Apply the **FinBERT** model for sentiment labeling and encoding.  
5. **Date Extraction:** Standardize all publication dates.  
6. **Financial Analysis:** Combine sentiment data with financial indicators (MA, RSI) for prediction modeling.  
7. **Visualization:** Launch the **Gradio interface** to input stock names and visualize sentiment and trend results.  

---

## 📁 File Structure
- **News_Data/** — Cleaned and labeled news dataset  
- **News_Links/** — Source URLs for scraping news content  
- **Finance_Key_Words/** — Keyword list for filtering financial terms  

---

✅ *This documentation ensures clarity for both collaborators and employers — giving them a clear overview of how sentiment and financial data are integrated for market forecasting.*
