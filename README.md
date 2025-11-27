# 📈 SBI Stock Price Prediction

This project focuses on predicting the **State Bank of India (SBI)** stock prices (`SBIN.NS`) using historical data from Yahoo Finance. The workflow includes feature engineering with moving averages, volatility, returns, and volume-based indicators, followed by model training using **SGDRegressor** and exploratory steps with TensorFlow.

---

## 🚀 Project Overview
- Fetches SBI stock price history using **Yahoo Finance API (`yfinance`)**.
- Performs extensive **feature engineering**:
  - Moving averages (weekly, monthly, yearly).
  - Ratios between different moving averages.
  - Standard deviation of moving averages (volatility).
  - Volume-based moving averages and ratios.
  - Daily, weekly, monthly, and yearly returns.
- Builds a dataset with **30+ engineered features**.
- Splits data into training (80%) and testing (20%).
- Trains a **linear regression model (SGDRegressor)** for prediction.
- Visualizes **actual vs predicted stock prices**.

---

## 📊 Dataset
- Source: Yahoo Finance (`SBIN.NS`).
- Time period: 1996 – 2025.
- Final dataset size: ~7,000 rows × 31 columns.
- Target variable: `Close` price.
- Features: 30 engineered indicators (moving averages, volatility, returns, volume ratios, etc.).

---

## 🛠️ Feature Engineering
Key transformations applied:
- **Moving Averages**:
  - Weekly (5-day), Monthly (21-day), Yearly (252-day).
  - Ratios: Weekly/Monthly, Monthly/Yearly, Weekly/Yearly.
- **Volatility (Std Dev)**:
  - Weekly, Monthly, Yearly rolling standard deviations.
  - Ratios between different volatility measures.
- **Volume Indicators**:
  - Weekly, Monthly, Yearly rolling averages of trading volume.
  - Ratios between volume averages.
- **Returns**:
  - Daily, Weekly, Monthly, Yearly percentage changes.
  - Rolling averages of returns.

---

## ⚙️ Model Training
- **Model**: `SGDRegressor` (scikit-learn).
- Parameters:
  - Loss: `squared_error`
  - Penalty: `l2`
  - Max iterations: `1000`
  - Learning rate: constant (`eta0=0.01`)
  - Regularization: `alpha=0.1`
- Training set: 80% of data.
- Testing set: 20% of data.
- Evaluation: Visual comparison of predicted vs actual prices.

---

## 📈 Results
- The model captures general trends in SBI stock prices.
- Visualization shows predicted values closely following actual closing prices, though with some variance due to model simplicity.

---

## 📦 Dependencies
Install required libraries:
```bash
pip install yfinance pandas matplotlib scikit-learn tensorflow
```

---

## ▶️ Usage
1. Clone the repository.
2. Run the notebook in **Google Colab** or locally.
3. Execute cells step by step:
   - Data fetching
   - Feature engineering
   - Train/test split
   - Model training
   - Visualization

---

## 🔮 Future Work
- Experiment with **deep learning models** (e.g., LSTM, GRU).
- Add **hyperparameter tuning** for SGDRegressor.
- Explore **ensemble methods** (Random Forest, XGBoost).
- Improve feature selection using correlation analysis.

---

## 📌 License
This project is open-source under the MIT License.

---

Would you like me to make this README **more formal (academic-style)** with equations and methodology, or **developer-friendly** with quick-start instructions and code snippets?
