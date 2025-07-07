
# ML-Based Equity Momentum Strategy using LightGBM

This project implements a machine learning-driven momentum strategy for stock selection using technical indicators and LightGBM. It focuses on monthly ranking of NSE-100 stocks to generate actionable buy/sell signals, with custom backtesting and performance analytics.

---

## Project Overview

- **Objective**: Predict top-performing stocks based on recent momentum and technical indicators.
- **Universe**: NSE-100 stocks, 2019–2024 data.
- **Approach**: Use LightGBM to rank stocks by predicted forward returns.
- **Backtest Logic**: Buy top-N ranked stocks monthly, equal-weighted, with transaction cost and cumulative capital tracking.

---

## Features & Engineering

- 12+ Technical Indicators:
  - RSI, MACD, ATR, EMA, Momentum, etc.
- Forward return labeling:
  - Based on 21-day future return.
- Monthly cross-sectional classification:  
  - Stocks are labeled as outperforming (+1), underperforming (−1), or neutral (0, optionally dropped).

---

## Model

- **Model**: LightGBM Classifier
- **Task**: Multiclass classification (−1, 0, +1) or binary (dropping 0)
- **Hyperparameter Tuning**: RandomizedSearchCV
- **Validation**: Time-aware train-test split (by month)

---

## Results

| Metric           | Value       |
|------------------|-------------|
| Sharpe Ratio     | 2.06        |
| Max Drawdown     | −13.61%     |
| Monthly Win Rate | 76.67%      |

- Model beat average market return over 5 years.
- Returns calculated using cumulative capital and transaction costs.

---

## Visuals

- Cumulative Returns vs Market
- Monthly Portfolio Performance
- SHAP Value Plots (optional)
- Drawdown Curve

---

## Backtesting Framework

Custom vectorized backtest engine includes:

- Capital compounding logic
- Transaction cost handling
- Monthly signal execution
- Cumulative return calculation

---

## Tools Used

- Python, Pandas, NumPy
- LightGBM, Scikit-learn
- Matplotlib, Seaborn
- SHAP (optional)
- Jupyter Notebook

---

## Future Improvements

- Live simulation with 2025+ data
- Confidence-weighted position sizing
- Regression-based return prediction
- Integration with macro indicators (VIX, rates)
- Streamlit dashboard for interactive picks

---
