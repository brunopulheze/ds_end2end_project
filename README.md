# Gold & Silver Price Forecasting with Machine Learning

A beginner-friendly machine learning project that analyzes and forecasts gold and silver prices using historical futures data.

You can view the slideshow presentation [here](https://www.canva.com/design/DAG-bdvH--Q/N6BvJ3XpflKFcMUcaJziNQ/edit?utm_content=DAG-bdvH--Q&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton).

![Python](https://img.shields.io/badge/Python-3.11-blue)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.3-orange)
![yFinance](https://img.shields.io/badge/yFinance-0.2-green)

## 📋 Project Overview

This project demonstrates an end-to-end machine learning workflow:
1. **Data Collection**: Download real-time gold and silver futures prices using yFinance
2. **Feature Engineering**: Create technical indicators (moving averages, volatility, returns)
3. **Exploratory Data Analysis**: Visualize price trends and patterns
4. **Model Training**: Train and compare multiple ML models
5. **Evaluation**: Assess model performance using RMSE, R², MAPE, and TimeSeriesSplit CV

## 📁 Project Structure

```
ds_end2end_project/
├── gold_silver_simple_notebook.ipynb   # Main analysis notebook
├── news_sentiment_nlp_notebook.ipynb   # NLP sentiment analysis (bonus)
├── presentation_speech.md               # Presentation notes
├── README.md                            # This file
├── config.py                            # Configuration settings
└── data/
    └── google_news_stock_rss.csv        # News data for NLP analysis
```

## 🚀 Quick Start

### Prerequisites

```bash
pip install pandas numpy yfinance matplotlib scikit-learn xgboost
```

### Run the Notebook

1. Open `gold_silver_simple_notebook.ipynb` in Jupyter or VS Code
2. Run all cells to:
   - Download the latest gold/silver price data
   - Generate features and visualizations
   - Train and compare ML models

## 📊 Data

| Asset | Ticker | Source | Period |
|-------|--------|--------|--------|
| Gold Futures | GC=F | Yahoo Finance | Jan 2025 - Present |
| Silver Futures | SI=F | Yahoo Finance | Jan 2025 - Present |

**Why Futures instead of Spot Prices?**
- Better data quality from regulated exchanges
- Higher liquidity = more reliable pricing
- Cleaner prices without storage/insurance costs

## 🔧 Features Created

| Feature | Description |
|---------|-------------|
| `daily_return` | Percentage change from previous day |
| `ma10` | 10-day moving average |
| `ma20` | 20-day moving average |
| `volatility` | 20-day rolling standard deviation of returns |
| `gold_silver_ratio` | Gold price / Silver price |

## 🤖 Models Compared

| Model | Description |
|-------|-------------|
| **Linear Regression** | Simple baseline model |
| **Ridge Regression** | Linear regression with L2 regularization |
| **Random Forest** | Ensemble of decision trees |
| **XGBoost** | Gradient boosting algorithm |

## 📈 Results

### Best Model: Ridge Regression

| Metric | Gold | Silver |
|--------|------|--------|
| R² Score | 0.55 | 0.45 |
| RMSE | $113 | $8 |
| MAPE | 2.14% | 8.91% |
| CV RMSE | $105 | $2.62 |

### Key Findings

- ✅ **Simple models outperformed complex ones** with limited data (~250 days)
- ✅ **Ridge Regression** best for both assets due to regularization
- ❌ **Tree-based models** (RF, XGBoost) overfit with small datasets
- 📊 **TimeSeriesSplit CV** provides more realistic performance estimates

## 📏 Evaluation Metrics

| Metric | What it Measures | Interpretation |
|--------|------------------|----------------|
| **RMSE** | Average prediction error in dollars | Lower is better |
| **R²** | Variance explained by model (0-1) | Closer to 1 is better |
| **MAPE** | Average percentage error | Lower is better |
| **CV RMSE** | Cross-validated error (TimeSeriesSplit) | More robust estimate |

## 🔬 Bonus: NLP Sentiment Analysis

The `news_sentiment_nlp_notebook.ipynb` analyzes stock market news headlines:
- **Sentiment Analysis**: Classifies news as positive/negative/neutral using VADER
- **Text Clustering**: Groups similar articles using TF-IDF + K-Means
- **Word Frequency**: Identifies most common terms in financial news

## 🛠️ Technologies Used

- **Python 3.11**
- **pandas** - Data manipulation
- **numpy** - Numerical computing
- **yfinance** - Financial data download
- **matplotlib** - Visualization
- **scikit-learn** - Machine learning
- **XGBoost** - Gradient boosting
- **NLTK** - Natural language processing

## 📚 What I Learned

1. How to download and process financial time series data
2. Feature engineering for price prediction
3. Importance of using TimeSeriesSplit for time series data
4. Why simpler models can outperform complex ones with limited data
5. How to evaluate and compare multiple ML models

## 🔮 Future Improvements

- [ ] Collect more historical data (2+ years)
- [ ] Add external features (interest rates, inflation, USD index)
- [ ] Implement LSTM or other deep learning models
- [ ] Add real-time prediction pipeline
- [ ] Include more commodities (platinum, copper)

## 👤 Author

Created as part of the Ironhack Data Science & AI Bootcamp

## 📄 License

This project is for educational purposes.