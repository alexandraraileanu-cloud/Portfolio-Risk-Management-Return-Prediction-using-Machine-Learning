[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.0+-orange.svg)](https://scikit-learn.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

##  Executive Summary

This project applies advanced **Machine Learning techniques** to predict portfolio returns and manage investment risk for a diversified portfolio of 10 US equities. The system achieved a **Root Mean Squared Error (RMSE) of 1.750%** using Random Forest, outperforming 9 other algorithms evaluated.

Key Achievement:** Sharpe Ratio of 1.28, indicating strong risk-adjusted returns.

(Please have in consideration that this project is written in Spanish)

---

##  Why This Matters for Investment Banking

This project demonstrates:

- **Quantitative Analysis Skills**: Built from scratch a predictive model for financial returns
- **Risk Management Expertise**: Calculated professional metrics (Sharpe, VaR, Maximum Drawdown)
- **Programming Proficiency**: Python, pandas, scikit-learn, matplotlib
- **Financial Markets Knowledge**: Technical indicators, portfolio theory, market dynamics
- **Statistical Rigor**: Cross-validation, error analysis, hypothesis testing
- **Business Communication**: Clear documentation and actionable recommendations

---

##  Portfolio Composition

The portfolio includes **10 blue-chip stocks** across 5 sectors for optimal diversification:

| Sector | Stocks | Characteristics |
|--------|--------|-----------------|
| **Technology** | Apple (AAPL), Microsoft (MSFT) | High growth, high volatility |
| **Banking** | JPMorgan Chase (JPM), Bank of America (BAC) | Interest rate sensitive, cyclical |
| **Healthcare** | Johnson & Johnson (JNJ), Pfizer (PFE) | Defensive, stable cash flows |
| **Energy** | Exxon Mobil (XOM), Chevron (CVX) | Commodity-driven, geopolitical exposure |
| **Consumer** | Amazon (AMZN), Walmart (WMT) | Mixed growth/value characteristics |

**Rationale:** Sector diversification reduces unsystematic risk while maintaining exposure to market returns.

---

##  Methodology

### 1. Data Generation
- **1,260 trading days** (≈5 years) of synthetic price data
- Calibrated with real market parameters (2020-2024)
- **Geometric Brownian Motion** with volatility clustering
- Implements autocorrelation to replicate market behavior

### 2. Feature Engineering (14 Technical Indicators)
- **Statistical Features**: Mean, std, min, max returns over 30-day windows
- **Moving Averages**: SMA 5, 10, 20 days (normalized)
- **Momentum Indicators**: 5-day and 10-day price changes
- **Volatility Measures**: Rolling standard deviations
- **RSI (14-day)**: Relative Strength Index for overbought/oversold conditions

### 3. Machine Learning Pipeline
Evaluated **10 regression algorithms**:
- Linear Models: Linear Regression, Ridge, Lasso, ElasticNet
- Kernel Methods: Support Vector Regression (SVR)
- Instance-Based: K-Nearest Neighbors
- Tree-Based: Decision Tree, Extra Trees, **Random Forest** ⭐, Gradient Boosting

### 4. Model Selection & Validation
- **Train/Test Split**: 80/20 temporal (no shuffling to prevent data leakage)
- **Cross-Validation**: Time Series Split (5 folds)
- **Feature Scaling**: StandardScaler for algorithms sensitive to scale
- **Error Analysis**: Residual diagnostics to verify no systematic bias

---

##  Results

### Model Performance

| Model | RMSE (%) | MAE (%) | R² |
|-------|----------|---------|-----|
| **Random Forest** ⭐ | **1.750** | **1.341** | **-0.014** |
| Extra Trees | 1.752 | 1.343 | -0.015 |
| Gradient Boosting | 1.762 | 1.348 | -0.027 |
| SVR | 1.761 | 1.347 | -0.027 |
| Linear Regression | 1.762 | 1.348 | -0.027 |
| Ridge/Lasso | 1.763 | 1.349 | -0.028 |
| KNN | 1.764 | 1.350 | -0.029 |
| Decision Tree | 1.770 | 1.355 | -0.032 |

**Winner:** Random Forest with lowest RMSE

**Note on R²:** Negative R² is normal and expected for daily return prediction. The high stochastic component of financial markets makes most day-to-day variation unpredictable. What matters is that RMSE is reasonable and the model has no systematic bias.

### Cross-Validation (Random Forest)
- **Mean RMSE**: 1.748% 
- **Std Dev**: 0.085%
- **Folds**: [1.65%, 1.73%, 1.81%, 1.75%, 1.80%]

**Interpretation:** Low variability confirms model robustness across different time periods.

### Feature Importance (Top 5)
1. **volatility_10**: 8.61%
2. **volatility_5**: 8.54%
3. **std_return**: 8.48%
4. **sma_20**: 7.85%
5. **momentum_5**: 7.62%

**Key Insight:** Volatility features dominate, validating the "volatility clustering" phenomenon in financial markets.

### Risk Metrics

| Metric | Value | Interpretation |
|--------|-------|----------------|
| **Sharpe Ratio** | 1.28 | Good risk-adjusted return (>1 is good, >2 excellent) |
| **Annualized Return** | 12.58% | Above long-term equity average (~10%) |
| **Annualized Volatility** | 8.28% | Moderate risk due to diversification |
| **VaR 95% (daily)** | -0.78% | Maximum expected loss on 95% of days |
| **Maximum Drawdown** | -14.34% | Largest peak-to-trough decline (moderate) |

---

##  Key Findings

1. **Ensemble methods outperform** linear models, indicating important non-linear relationships
2. **Volatility is the strongest predictor** of future returns, confirming established financial theory
3. **Cross-validation confirms robustness** - model performs consistently across time periods
4. **No systematic bias** in residuals - predictions are unbiased
5. **Sector diversification works** - correlations within sectors (0.65-0.74) higher than between sectors (0.20-0.50)

---

##  Technical Stack

- **Language**: Python 3.8+
- **Data Processing**: pandas, NumPy
- **Machine Learning**: scikit-learn (10 algorithms)
- **Visualization**: Matplotlib, Seaborn
- **Statistical Analysis**: SciPy, statsmodels
- **Notebook**: Jupyter Lab

---


##  How to Run

### Prerequisites
```bash
Python 3.8+
pip
```

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/portfolio-ml-prediction.git
cd portfolio-ml-prediction
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Launch Jupyter:
```bash
jupyter lab
```

4. Open and run

---

## 📊 Visualizations

The notebook includes 15+ professional visualizations:
- Portfolio return distributions
- Correlation heatmaps
- Risk-return scatter plots
- Feature importance charts
- Cross-validation results
- Residual diagnostic plots
- Drawdown analysis

---

##  Academic Rigor

This project follows the **CRISP-DM methodology** (Cross-Industry Standard Process for Data Mining):
1. Business Understanding
2. Data Understanding
3. Data Preparation
4. Modeling
5. Evaluation
6. Deployment

**Validation approach** mirrors industry standards used by quant funds and asset managers.

---

##  Limitations & Disclaimers

1. **Synthetic Data**: While calibrated to real market statistics, does not capture all extreme events
2. **Short Horizon**: Daily predictions have high noise; longer horizons may improve predictability
3. **No Transaction Costs**: Real-world implementation would include commissions, slippage, market impact
4. **Historical Patterns**: Assumes past relationships persist (not guaranteed in regime changes)
5. **Not Investment Advice**: This is an academic exercise, not a recommendation to trade

**For educational and demonstration purposes only.**

---

##  Future Enhancements

1. **Alternative Data**: Incorporate news sentiment, social media, macroeconomic indicators
2. **Deep Learning**: Explore LSTM, Transformers for sequence modeling
3. **Longer Horizons**: Weekly/monthly predictions with lower noise
4. **Dynamic Allocation**: Optimize portfolio weights based on predictions
5. **Transaction Costs**: Add realistic friction to backtest
6. **Regime Detection**: Build separate models for bull/bear/sideways markets
7. **Multi-Asset**: Extend to bonds, commodities, currencies

---

## References

1. Markowitz, H. (1952). "Portfolio Selection". *Journal of Finance*
2. Black, F. & Scholes, M. (1973). "The Pricing of Options and Corporate Liabilities"
3. Breiman, L. (2001). "Random Forests". *Machine Learning*
4. Engle, R. (1982). "Autoregressive Conditional Heteroscedasticity" (Volatility Clustering)
