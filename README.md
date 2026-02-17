[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.0+-orange.svg)](https://scikit-learn.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

#  Portfolio Return Prediction & Risk Management using Machine Learning

This project develops a complete Machine Learning system to **predict portfolio returns** and **analyze investment risk**, combining financial theory with data science techniques.

>  Important: The project (notebook, comments, and report) is written in **Spanish**, but this README is provided in English for accessibility.

---

##  Project Overview

The objective of this project is to design a predictive system capable of:

- Forecasting **daily portfolio returns**
- Analyzing **risk-adjusted performance**
- Supporting **investment decision-making**

The system uses **historical financial data (synthetic but statistically realistic)** and applies **supervised Machine Learning models** to identify patterns and generate predictions.

---

##  Key Features

- 📊 Generation of a synthetic financial dataset based on **Geometric Brownian Motion**
- 📉 Calculation of **technical indicators** (moving averages, momentum, volatility, RSI, etc.)
- 🤖 Training and comparison of **10 Machine Learning models**
- 🌳 Final model selection using **Random Forest**
- 🔁 Time-series **cross-validation**
- 📈 Financial risk metrics:
  - Sharpe Ratio
  - Value at Risk (VaR 95%)
  - Maximum Drawdown
- 💡 Investment decision support based on predicted returns

---

##  Project Structure
├── TFM_Portfolio_Alexandra.ipynb   # Main Jupyter Notebook (analysis + models)
├── TFM_IA_Alexandra.pdf            # Final report (full explanation)
└── README.md                        # Project documentation

---

##  Dataset

The dataset was **synthetically generated** to replicate real market behavior using:

- 10 large-cap US companies
- 5 economic sectors (Tech, Banking, Healthcare, Energy, Consumer)
- 5 years of daily data (~1260 trading days)

This approach ensures:

- Full reproducibility
- Statistical realism
- No external API dependency

---

##  Tech Stack

- **Python 3**
- **pandas** – data manipulation
- **NumPy** – numerical computations
- **scikit-learn** – machine learning models
- **matplotlib & seaborn** – data visualization

---

##  Machine Learning Models Used

The project evaluates multiple regression algorithms, including:

- Linear Regression
- Ridge & Lasso
- KNN
- Decision Trees
- Random Forest  (final model)
- Gradient Boosting
- Extra Trees

Models are compared using:

- RMSE
- MAE
- R² Score

---

##  Methodology

The project follows the **CRISP-DM framework**:

1. Business Understanding  
2. Data Understanding  
3. Data Preparation  
4. Modeling  
5. Evaluation  
6. (Simulated) Deployment  

---

##  Financial Metrics Implemented

To evaluate portfolio performance:

- **Sharpe Ratio** → risk-adjusted return
- **Value at Risk (VaR 95%)** → expected worst loss
- **Maximum Drawdown** → largest historical drop

---

##  Results

- The final model achieves a prediction error (RMSE) of approx **1.75%**
- The system is capable of identifying patterns in market behavior
- It provides **actionable insights for portfolio allocation**

---

##  Disclaimer

This project is for **educational purposes only**.

Financial markets are inherently unpredictable, and this system **does not guarantee profits**.  
It should be used as a complementary tool alongside fundamental analysis and proper risk management.



## References

1. Markowitz, H. (1952). "Portfolio Selection". *Journal of Finance*
2. Black, F. & Scholes, M. (1973). "The Pricing of Options and Corporate Liabilities"
3. Breiman, L. (2001). "Random Forests". *Machine Learning*
4. Engle, R. (1982). "Autoregressive Conditional Heteroscedasticity" (Volatility Clustering)
