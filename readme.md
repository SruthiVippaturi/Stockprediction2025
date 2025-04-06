## Stock Market Crash Prediction Using SPY & VIX with yfinance
### Objective
This project aims to predict the likelihood of a 2-day stock market crash (≥4% drop in SPY) by analyzing historical SPY and VIX data, using the yfinance library for data retrieval. The goal is to help investors and traders forecast potential market crashes, enabling them to make proactive decisions about hedging or exiting the market. The model utilizes XGBoost, a powerful machine learning algorithm, to make these predictions based on historical trends and market volatility.

### Data Sources
The data used in this project is sourced from Yahoo Finance through the yfinance library:

SPY: Closing prices of the S&P 500 ETF (SPY).

VIX: Closing prices of the Volatility Index (VIX).

### Key Features Used in the Model:
SPY_Close: Closing price of SPY.

VIX_Close: Closing price of VIX.

SPY_Return: Daily return of SPY.

VIX_Return: Daily return of VIX.

SPY_3d_Volatility: 3-day rolling standard deviation of SPY returns.

VIX_3d_Change: 3-day percent change in VIX.

SPY_5d_Return: 5-day return of SPY.

VIX_5d_Change: 5-day percent change in VIX.

### Key Findings
The model successfully identifies high-risk periods where the market might experience significant declines (≥4% drop in SPY).

On April 4th, 2025, the model predicted a 26% chance of a market crash, indicating a moderate level of risk. This prediction came ahead of the significant market downturn that occurred, as the S&P 500 saw a 6% drop due to escalating tariff tensions between the U.S. and China, erasing $6.4 trillion in market value.

The 26% probability predicted by the model suggests a "Watch" action, meaning that the market was showing signs of increased volatility, but not yet signaling a clear crash. This prediction aligned with real-world events, where global trade fears led to an accelerated selloff.

Despite the relatively low probability, the model’s "Watch" recommendation highlighted the need for caution, as it was enough to signal potential risk in the market, aligning with the actual market events that followed.

### Methods Used
Data Preprocessing:

Engineered features that capture market volatility, returns, and rolling changes for both SPY and VIX.

Labeled the data with binary outcomes (1 for a crash, 0 for no crash), based on historical market drops.

XGBoost Classifier:

Trained an XGBoost model using SPY and VIX features to predict whether the market would experience a crash in the next 2 days.

Utilized class balancing to address the imbalanced nature of the dataset, as crashes are rare events.

Model Evaluation:

Used a Confusion Matrix and Classification Report to assess the performance of the model, with an emphasis on detecting crashes (i.e., high recall).

Crash Probability Forecasting:

Forecasted the likelihood of market crashes for the years 2024–2025 based on the model’s predictions.

Provided actionable labels: Exit, Hedge, Watch, and Hold based on predicted crash probabilities.

Visualization:

Created visualizations of the Crash Probability Forecast to help users visualize market risk and plan accordingly.

Displayed actions for the next 7 days based on crash probabilities.

### How to Run this File 
### Clone the repository
```
git clone https://github.com/SruthiVippaturi/StockPrediction_2025 
```
### Install dependencies
```
pip install -r requirements.txt
```
(Ensure to create a requirements.txt file with the necessary libraries listed.)

### Further Development
Real-Time Data Integration:

Integrate live market data from sources like IEX Cloud or Alpaca to provide up-to-date crash predictions, enabling quicker responses to market changes.

Interactive Dashboard:

Create an interactive dashboard using Streamlit or Dash to visualize crash probabilities and provide actionable insights in real-time, making it easier for users to track and manage risk.