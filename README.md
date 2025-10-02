# Gold Price Forecasting Using Time Series Analysis

## Project Overview
This project analyzes historical gold price data (2014-2023) and builds time series forecasting models to predict future prices. The analysis compares ARIMA and Facebook Prophet models to determine the most effective approach for gold price prediction.

## Dataset
- **Source**: Historical gold price data
- **Records**: 2,227 daily observations
- **Time Period**: January 2014 to August 2023
- **Features**: Date, Price, Open, High, Low, Volume, Change%

## Tech Stack
- **Python 3.x**
- **Libraries**: 
  - pandas - Data manipulation
  - numpy - Numerical operations
  - matplotlib, seaborn - Data visualization
  - statsmodels - ARIMA modeling and statistical tests
  - prophet - Facebook Prophet forecasting
  - scikit-learn - Model evaluation metrics

## Methodology

### 1. Exploratory Data Analysis (EDA)
- Missing value analysis
- Correlation heatmap analysis
- Time series visualization
- Moving averages (7-day, 14-day, 21-day)
- Pairwise scatter plot matrix

### 2. Data Preprocessing
- Date formatting and indexing
- Train-test split (80/20) - chronological split for time series
- Stationarity testing using Augmented Dickey-Fuller (ADF) test
- First-order differencing to achieve stationarity

### 3. Model Building

#### ARIMA Model
- Parameter selection using ACF/PACF plots
- Tested multiple configurations: (1,1,0), (1,1,1), (2,1,1), etc.
- Best model: ARIMA(1,1,0)

#### Prophet Model
- Facebook Prophet with yearly and weekly seasonality
- Confidence interval predictions

### 4. Model Evaluation
- Root Mean Squared Error (RMSE)
- Mean Absolute Error (MAE)
- Mean Absolute Percentage Error (MAPE)

## Results

| Model | RMSE | MAE | Performance |
|-------|------|-----|-------------|
| ARIMA(1,1,0) | $3,071.56 | $2,558.64 | Best |
| Prophet | $17,622.85 | - | Failed (overestimated trend) |

**Winner**: ARIMA(1,1,0)

The ARIMA model achieved significantly better performance by predicting price stability, while Prophet incorrectly extrapolated an aggressive upward trend.

## Key Findings
- Gold prices show strong upward trend from 2014-2020
- High volatility in 2020-2023 period
- Price, Open, High, Low columns are highly correlated (0.99+)
- Volume shows weak correlation with price
- ARIMA outperformed Prophet for this dataset due to Prophet's over-aggressive trend extrapolation

## Limitations
- Time series models struggle with financial data due to unpredictable external factors
- ~6% prediction error is typical for financial forecasting
- Models cannot account for geopolitical events, policy changes, or market sentiment
- Short-term forecasting (30 days) is more reliable than long-term

## Author
Bhavana


