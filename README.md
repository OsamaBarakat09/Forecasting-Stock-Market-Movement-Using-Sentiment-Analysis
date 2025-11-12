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
8. [How to Use](#how-to-use)
9. [File Structure](#file-structure)
10. [Screenshots](#screenshots)
11. [Future Work](#future-work)
12. [References](#references)
13. [Author](#author)

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

## 🔹 Approach
To address this challenge, I built an **end-to-end pipeline** combining **Natural Language Processing (NLP)**, **machine learning**, and **financial data analysis**. 🧠💹  

### **1️⃣ Data Acquisition**
- Scraped financial news from **CNBC**, **Reuters**, and **CoinDesk** using **Python `requests`** and **`BeautifulSoup`**  
- Implemented automated retry and error-handling mechanisms  
- Linked articles to stock tickers and timestamps for accurate market alignment  

### **2️⃣ Text Preprocessing & Sentiment Extraction**
- Cleaned and normalized text using **NLTK** and **spaCy**  
- Removed HTML tags, special characters, stopwords, and duplicates  
- Extracted sentiment with **VADER** (baseline) and **FinBERT** (transformer-based) models  

### **3️⃣ Feature Engineering**
- Aggregated sentiment by company and date to create daily indicators  
- Combined with **market variables** from **Yahoo Finance (`yfinance`)**  
- Created hybrid features such as:
  - Rolling average sentiment  
  - Sentiment volatility  
  - Sentiment-weighted return ratios  

### **4️⃣ Predictive Modeling**
- Machine learning models used to predict next-day stock direction:  
  - Logistic Regression (baseline)  
  - Random Forest & XGBoost (ensemble learning)  
  - FinBERT embeddings + Neural Network (deep learning extension)  
- Evaluated with **accuracy**, **F1-score**, **ROC-AUC**, and **cross-validation**  

### **5️⃣ Interactive Visualization & Deployment**
- Developed an **interactive Gradio dashboard** 🎛️  
- Users can:
  - Enter any financial headline or article  
  - Receive sentiment score and predicted stock movement  
  - Visualize sentiment trends over time  
- Transforming complex analytics into actionable insights 🚀  

✅ **Summary:**  
This approach bridges market psychology and quantitative modeling, demonstrating how modern NLP and financial data science can forecast short-term stock movements with data-driven precision.

---

## 🔹 Results
The **FinBERT-based model** achieved:  
- **Accuracy:** 72%  
- **F1-Score:** 0.70  

Key insights:  
- Positive sentiment days correlate with next-day price increases, especially for high-volume tickers  
- Sudden sentiment drops can indicate short-term corrections or volatility spikes  
- Sentiment volatility improves prediction stability and reduces noise  

Interactive Gradio app enables:  
- Real-time sentiment classification (Positive / Neutral / Negative)  
- Predicted market direction with probability  
- Visualization of sentiment trends over time  

📊 The system forms a reproducible, transparent, and interpretable framework for **financial sentiment forecasting**.

---

## 🔹 Tech Stack

**Languages & Libraries 🐍**
- Python, Pandas, NumPy, Scikit-learn, XGBoost  
- NLTK, spaCy, Transformers (FinBERT)  
- Matplotlib, Seaborn  

**Data Sources & APIs 🌐**
- Yahoo Finance (`yfinance`)  
- BeautifulSoup & Requests  

**Deployment & Visualization 🚀**
- Gradio (interactive interface)  
- Streamlit / Hugging Face Spaces (optional)  
- Git & GitHub  

---

## 🗂️ News Data Overview

### **1️⃣ News_Data**
- URLs, article text, sentiment labels, date, encoded sentiment  

### **2️⃣ News_Links**
- Base URLs for scraping financial news  

### **3️⃣ Finance_Key_Words**
- Financial acronyms and terms for filtering news  

---

## 🚀 Key Features
- Web scraping from major financial websites  
- Text preprocessing & filtering for finance relevance  
- Sentiment classification using **FinBERT**  
- Financial indicators (MA, RSI) integrated with sentiment  
- Interactive visualization via Gradio  

---

## ⚙️ How to Use
1. Install required Python libraries (`pandas`, `nltk`, `transformers`, `yfinance`, `gradio`)  
2. Run scraping scripts to collect news data (`News_Data.csv`, `News_Links.csv`)  
3. Preprocess and clean text  
4. Apply FinBERT for sentiment analysis  
5. Standardize publication dates  
6. Combine sentiment with financial indicators for modeling  
7. Launch Gradio interface for interactive visualization  

---

## 📁 File Structure
- **News_Data/** — Scraped and cleaned news dataset  
- **News_Links/** — URLs for scraping  
- **Finance_Key_Words/** — Financial terms for filtering  

---

## 🖼️ Screenshots
*(Replace the placeholder images with your actual project screenshots)*

![Dashboard Screenshot](https://via.placeholder.com/600x300?text=Gradio+Dashboard)
![Stock Trend Visualization](https://via.placeholder.com/600x300?text=Stock+Trend+Charts)

---

## 🔮 Future Work
- Extend model to multi-day forecasts  
- Include social media sentiment (Twitter, Reddit)  
- Deploy as a fully hosted web app for public use  
- Explore deep learning transformers for full text sequence analysis  

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
