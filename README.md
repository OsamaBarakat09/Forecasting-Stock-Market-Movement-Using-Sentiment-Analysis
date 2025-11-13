# Forecasting Stock Market Movement Using Sentiment Analysis

![Python](https://img.shields.io/badge/Python-3.11-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## 📑 Table of Contents
1. [Project Overview](#project-overview)
2. [Problem](#problem)
3. [Approach](#approach)
4. [Results](#results)
5. [Tech Stack](#tech-stack)
6. [News Data Overview](#news-data-overview)
7. [Key Features](#key-features)
8. [References](#references)
9. [Author](#author)

---

## 📘Project Overview
This project presents a **comprehensive, end-to-end pipeline** for forecasting stock market movements using sentiment analysis of financial news. Financial markets are inherently influenced by public perception — including news headlines, analyst opinions, and social media discussions. By quantifying sentiment from diverse textual sources, this project bridges the gap between qualitative market psychology and quantitative financial modeling.  

The pipeline integrates **web scraping, natural language processing (NLP), feature engineering, machine learning, and financial indicators**, providing a robust framework for short-term market trend prediction. It is designed to be **scalable, reproducible, and interpretable**, allowing both researchers and practitioners to replicate the results or extend the methodology to other markets.  

Key aspects of this project include:  
- **Multi-source data integration:** Collects news from major financial platforms such as *CNBC, Reuters,* and *CoinDesk*, ensuring coverage of global market events.  
- **Advanced NLP processing:** Uses transformer-based models (FinBERT) alongside classical sentiment analysis for high-accuracy financial sentiment classification.  
- **Feature-rich modeling:** Combines textual sentiment with technical financial indicators such as Moving Averages (MA) and Relative Strength Index (RSI) to capture both qualitative and quantitative signals.  
- **Interactive deployment:** Provides a Gradio-based dashboard for real-time input of news headlines and instant sentiment-based market predictions, making the insights actionable for decision-makers.  

Overall, this project demonstrates how modern AI techniques can be applied to the financial domain to extract meaningful signals from unstructured textual data, supporting data-driven investment decisions and predictive analytics. It highlights a **practical application of NLP in finance**, with a focus on interpretability, accuracy, and usability for both technical and non-technical audiences.

---

## 💡Problem
Financial markets are highly sensitive to public sentiment. News headlines, analyst opinions, and social media discussions can trigger rapid fluctuations in stock prices, often within minutes. However, the **sheer volume, velocity, and diversity of information** make it extremely challenging for investors, analysts, and automated systems to accurately interpret and respond to market-moving news in real time.

Traditional stock prediction models rely predominantly on historical price data and technical indicators. While effective for trend analysis, these models often **fail to capture the behavioral and emotional drivers** behind market movements. This gap results in missed opportunities, delayed reactions to market events, and suboptimal investment decisions.

The central challenge addressed in this project is:  

- **Quantifying market sentiment** from unstructured textual sources at scale  
- **Linking sentiment to stock performance** for predictive modeling  
- **Providing actionable insights** for decision-makers in a timely, interpretable, and reproducible manner  

By tackling this problem, the project demonstrates how modern **Natural Language Processing (NLP)** and **financial data science** techniques can complement traditional modeling approaches, enabling more accurate forecasts of short-term stock price movements and a deeper understanding of market psychology.

---
## 🛠️ Approach
To tackle the challenge of linking financial sentiment to stock market movements, this project implements a **multi-stage, end-to-end pipeline** combining **Natural Language Processing (NLP)**, **machine learning**, and **financial data analysis**. The approach ensures both **accuracy** and **interpretability**, making it suitable for practical use in trading and investment analysis.  

### **1️⃣ Data Acquisition**
- Scraped financial news from **CNBC**, **Reuters**, **CoinDesk**, and other major sources 🌐  
- Used **Python `requests`** and **`BeautifulSoup`** with intelligent retry and error-handling mechanisms for reliable, automated collection  
- Timestamped and linked each article to relevant **stock tickers** to maintain alignment with market data  

### **2️⃣ Text Preprocessing & Sentiment Extraction**
- Applied **structured NLP pipeline** using **NLTK** and **spaCy** for text cleaning:  
  - Removed HTML tags, URLs, special characters, and non-alphanumeric noise  
  - Tokenized and lemmatized text for standardization  
  - Filtered out stopwords and non-informative words  
- Extracted sentiment using both **rule-based models (VADER)** for fast evaluation and **transformer-based models (FinBERT)** for nuanced financial language understanding 💹  

### **3️⃣ Feature Engineering**
- Aggregated daily sentiment scores by **company and date** to create interpretable indicators  
- Merged sentiment features with **market variables** from **Yahoo Finance (`yfinance`)**, including:  
  - Closing price  
  - Trading volume  
  - Volatility  
- Created hybrid features such as:  
  - Rolling average sentiment  
  - Sentiment volatility  
  - Sentiment-weighted return ratios  

### **4️⃣ Predictive Modeling**
- Built machine learning models to predict next-day stock direction (up/down) 📈  
- Models evaluated include:  
  - **Logistic Regression** (baseline)  
  - **Random Forest** and **XGBoost** (ensemble learning)  
  - **Neural Network** using **FinBERT embeddings** for deep learning extension  
- Performance metrics: **accuracy**, **F1-score**, **ROC-AUC**, and **cross-validation** for robust evaluation  

### **5️⃣ Interactive Visualization & Deployment**
- Developed an **interactive Gradio dashboard** 🎛️ to allow real-time analysis  
- Users can:  
  - Input any financial headline or article  
  - Instantly receive **sentiment score** and **predicted stock movement**  
  - Visualize sentiment trends over time for selected tickers  
- This transforms complex analytics into **actionable insights** for investors and analysts  

✅ **Summary:**  
This structured, multi-stage approach **bridges market psychology and quantitative modeling**, demonstrating how modern NLP and financial data science techniques can forecast short-term stock movements with **interpretable, actionable results**. It highlights **scalability, reproducibility, and usability**, making the methodology suitable for both research and practical investment applications.

---

## 📊 Results
The pipeline demonstrates that **sentiment extracted from financial news** can be a strong predictor of short-term stock movements. The final **FinBERT-based model** achieved:

- **Accuracy:** 72%  
- **F1-Score:** 0.70  
- **Consistency:** Verified through **cross-validation** to ensure robustness  

### Key Insights
- **Positive sentiment days** often correlate with **next-day price increases**, particularly for high-volume tickers 🚀  
- **Sudden sentiment drops** can signal **short-term corrections** or increased volatility ⚡  
- Incorporating **sentiment volatility** as a feature improves model stability and reduces noise from overly optimistic or pessimistic outliers 🔍  

### Interactive Visualization
- Deployed a **Gradio dashboard** to make findings accessible in real time 🎛️  
- Users can:  
  - Input any financial headline or article  
  - Receive **instant sentiment classification** (Positive / Neutral / Negative)  
  - View **predicted stock direction** along with probability scores  
  - Track **sentiment trends over time** for selected tickers  

### Summary
These results validate the hypothesis that **market sentiment acts as a leading indicator** when quantified properly and aligned with financial data. The combination of **advanced NLP**, **feature-rich modeling**, and **interactive visualization** provides a **reproducible, interpretable, and actionable framework** for short-term stock forecasting.

---

## 🧰 Tech Stack
This project integrates **modern NLP techniques** with **classical financial modeling** to create a robust, interpretable pipeline for stock market forecasting.  

### **Languages & Libraries 🐍**
- **Python** — Core programming language for data processing, modeling, and deployment  
- **Pandas & NumPy** — Efficient data manipulation, cleaning, and feature engineering  
- **Scikit-learn** — Machine learning pipelines, model training, and evaluation  
- **XGBoost** — High-performance ensemble learning for predictive modeling  
- **Transformers (Hugging Face)** — Pre-trained **FinBERT** model for financial sentiment analysis  
- **NLTK & spaCy** — Advanced natural language processing, tokenization, lemmatization, and stopword removal  
- **Matplotlib & Seaborn** — Data visualization, trend analysis, and exploratory insights  

### **Data Sources & APIs 🌐**
- **Yahoo Finance (`yfinance`)** — Historical market data retrieval for price trends, volume, and indicators  
- **BeautifulSoup & Requests** — Automated web scraping for collecting financial news  

### **Deployment & Visualization 🚀**
- **Gradio** — Interactive web interface for real-time sentiment prediction and market trend visualization  
- **Streamlit / Hugging Face Spaces (optional)** — Alternative platforms for hosting the interactive dashboard  
- **Git & GitHub** — Version control, documentation, and portfolio showcase  

### **Why This Stack?**
This combination of tools ensures:  
- **Reproducibility:** Anyone can replicate the results using the same libraries and datasets  
- **Interpretability:** Features, predictions, and sentiment outputs are easy to understand  
- **Scalability:** The pipeline can handle growing news data and extend to other markets or asset classes  
- **Professional Presentation:** Interactive dashboards make complex analysis actionable for both technical and non-technical users
---

## 🗂️ News Data Overview
This project relies on three primary datasets, forming the foundation for sentiment-based stock forecasting. Each dataset is carefully structured to enable **robust modeling** and **reproducible results**.

### **1️⃣ News_Data**
Contains the main corpus of financial articles collected from multiple sources.  
**Purpose:** Provides textual content for sentiment analysis and links it with stock tickers and dates for market prediction.  

| Column | Description |
|--------|--------------|
| `Links` | URLs of individual news articles |
| `Text` | Full content of the article |
| `Sentiment` | Labeled sentiment category (`Positive`, `Neutral`, `Negative`) |
| `Date` | Publication date of each article   |
| `Labeling_Sentiment` | Encoded sentiment labels (`0`, `1`, `2`) for modeling purposes |

### **2️⃣ News_Links**
Contains the list of financial news website URLs from which articles are scraped.  
**Purpose:** Serves as a source for automated web scraping and ensures coverage of diverse financial news sources.  

| Column | Description |
|--------|--------------|
| `Links` | Base URLs to be crawled for extracting news articles |

### **3️⃣ Finance_Key_Words**
Contains a curated dictionary of **financial terms, acronyms, and company tickers**.  
**Purpose:** Filters scraped articles to retain only finance-relevant content, improving model accuracy and efficiency.  

| Column | Description |
|--------|--------------|
| `Key` | Financial acronyms, tickers, and terminology extracted from major exchanges and market sources |

✅ **Summary:**  
These datasets collectively enable the **extraction, preprocessing, and modeling of sentiment-driven stock predictions**, ensuring a reliable and interpretable pipeline for forecasting financial market movements.

---

## 🚀 Key Features
This project integrates **advanced NLP, financial analysis, and machine learning** to provide a comprehensive solution for sentiment-based stock forecasting. Key features include:

- **🌐 Multi-Source Web Scraping:** Collects financial news articles from top platforms such as *Yahoo Finance, CNN, CNBC, Reuters,* and *CoinDesk* for broad market coverage.  
- **🧹 Text Preprocessing:** Cleans and standardizes news text by removing HTML tags, URLs, special characters, and stopwords, while filtering duplicate or irrelevant content.  
- **💹 Financial Sentiment Analysis:** Uses **FinBERT**, a pre-trained transformer model tailored for financial text, to classify articles as *Positive*, *Neutral*, or *Negative*.  
- **📅 Date Standardization:** Ensures all publication dates are formatted consistently (`YYYY-MM-DD`) for accurate temporal alignment with market data.  
- **📊 Financial Indicators Integration:** Calculates key indicators such as **Moving Averages (MA)** and **Relative Strength Index (RSI)** and merges them with sentiment scores to generate hybrid features.  
- **🎛️ Interactive Visualization:** Provides a **Gradio dashboard** for real-time sentiment analysis and stock trend visualization, transforming complex analytics into actionable insights.  
- **🧠 Predictive Modeling:** Implements multiple machine learning models, including **Logistic Regression, Random Forest, XGBoost,** and **Neural Networks with FinBERT embeddings**, evaluated with metrics like accuracy, F1-score, and ROC-AUC.  

✅ **Summary:**  
These features combine **qualitative and quantitative insights**, creating a **reproducible, interpretable, and practical framework** for forecasting short-term stock movements.

---

## 📚 References
- Hugging Face Transformers Documentation  
- FinBERT: Financial Sentiment Analysis  
- Yahoo Finance API Documentation  
- NLTK & spaCy NLP Libraries  

---

## 👤 Author
**Osama Barakat**  
- Email: `Osamabarakat021@gmail.com`  
- LinkedIn: [linkedin.com/in/osamabarakat](https://www.linkedin.com/in/osama-barakat-9b1b511b8/)  
- GitHub: [github.com/osamabarakat](https://github.com/OsamaBarakat09)  
