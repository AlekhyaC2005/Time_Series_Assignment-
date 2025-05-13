# 📈 Stock Price Forecasting Using ARIMA and XGBoost

## 📝 Project Overview
This project aims to forecast stock prices using both statistical and machine learning techniques—specifically ARIMA (AutoRegressive Integrated Moving Average) and XGBoost (Extreme Gradient Boosting). By leveraging historical data and engineered features, the study provides a comparative analysis of both models in terms of accuracy and reliability.

## 🎯 Objectives
- Collect and preprocess historical stock data (AAPL) using the yfinance API.
- Perform exploratory data analysis (EDA) and feature engineering (moving averages, lagged returns, etc.).
- Build forecasting models using ARIMA and XGBoost.
- Evaluate model performance using RMSE, MAE, and R² Score.
- Compare the effectiveness of traditional statistical and modern machine learning models.
- Derive actionable insights for trading strategy implications.

## 📊 Data Collection & Preprocessing
- **Source**: `yfinance` API (1-year historical data of AAPL)
- **Preprocessing**: 
  - Handled missing values
  - Applied ADF & KPSS stationarity tests
  - First-order differencing for ARIMA
  - Feature creation: Lag returns, % changes, moving averages, volume deltas

## 🔧 Models Used
### 1. ARIMA
- Parameter tuning using ACF, PACF, and GridSearch
- Applied on differenced series
- `(p, d, q) = (7, 1, 12)`

### 2. XGBoost
- Feature Engineering: Lagged prices, 5-day MA, volatility, % change
- Hyperparameter tuning with Optuna
- Key Parameters:
  - `n_estimators=857`
  - `max_depth=8`
  - `learning_rate=0.4419`
  - `subsample=0.73199`, etc.

## 📈 Evaluation Metrics
| Metric | ARIMA | XGBoost |
|--------|--------|----------|
| MAE    | 3.1521 | 2.8341   |
| RMSE   | 4.1892 | 3.5096   |
| R²     | 0.0552 | 0.3369   |

✅ **Conclusion**: XGBoost outperformed ARIMA on all metrics, making it a more suitable model for stock price forecasting in this case.

## 📌 Technologies Used
- Python, Pandas, Numpy, Matplotlib, Seaborn
- yfinance, statsmodels (ARIMA), scikit-learn
- XGBoost, Optuna
- ADF and KPSS tests for stationarity

## 📚 Key Learnings
- Time series preprocessing and model building
- Comparative model analysis
- Feature importance and engineering for financial data
- Model evaluation using real-world metrics
