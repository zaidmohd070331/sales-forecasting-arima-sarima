# Sales Forecasting — ARIMA & SARIMA

## 📌 Project Overview
Built a complete time-series forecasting pipeline on retail sales data
from 2015–2018 using ARIMA and SARIMA models. The project covers
data preparation, decomposition, stationarity testing, model building,
anomaly detection, and a 12-month future forecast.

## 🛠️ Tools & Libraries
- Python, Pandas, NumPy
- Statsmodels (ARIMA, SARIMAX, STL)
- Scikit-learn (MAE, RMSE metrics)
- Matplotlib, Seaborn

## 📊 Model Performance

| Model | MAPE | Accuracy | MAE | RMSE |
|---|---|---|---|---|
| ARIMA(1,2,1) | 32.92% | 67.08% | $29,292 | $35,299 |
| SARIMA(1,2,1)×(1,1,1,12) | 21.80% | 78.20% | $18,066 | $22,600 |

🏆 **Best Model: SARIMA(1,2,1)×(1,1,1,12)**
- SARIMA improved accuracy by 11.12% over ARIMA
- Seasonal component (period=12) successfully captured Q4 spikes
- Ljung-Box test confirmed residuals are white noise

## 📈 12-Month Future Forecast (2019)

| Metric | Value |
|---|---|
| Peak Month | November 2019 |
| Peak Sales | $101,487 |
| Lowest Month | February 2019 |
| Lowest Sales | $30,765 |
| Total Forecast | $746,327 |
| Avg Per Month | $62,194 |

## 🔍 Key Insights
- Strong seasonal pattern detected — seasonal strength > 0.6
- Q4 (Oct–Dec) consistently highest sales every year
- Q1 (Jan–Mar) consistently lowest — post-holiday slump
- ARIMA failed to capture seasonal spikes — SARIMA solved this
- 3 anomalous months detected across Z-Score, IQR and SARIMA residual methods
- Sales show moderate trend strength (0.4) with smooth year-over-year growth

## ⚙️ Project Pipeline

1. **Load & Prepare** — aggregate daily sales to monthly time series
2. **EDA & Decomposition** — STL decomposition, seasonality heatmap, rolling statistics
3. **Stationarity Testing** — ADF test + KPSS test → d=2 confirmed
4. **ACF & PACF Analysis** — determined p=1, q=1 for ARIMA order
5. **ARIMA Model** — ARIMA(1,2,1) → 67.08% accuracy
6. **SARIMA Model** — SARIMA(1,2,1)×(1,1,1,12) → 78.20% accuracy
7. **Anomaly Detection** — Z-Score, IQR, SARIMA residual methods
8. **Future Forecast** — 12-month forecast with 95% confidence intervals

## 🖼️ Key Visualizations

### Monthly Sales Trend
![Monthly Sales](plots/monthly_sales_raw.png)

### Seasonality Heatmap
![Seasonality Heatmap](plots/seasonality_heatmap.png)

### STL Decomposition
![STL Decomposition](plots/stl_decomposition.png)

### ARIMA vs SARIMA Forecast
![ARIMA vs SARIMA](plots/arima_vs_sarima.png)

### 12-Month Future Forecast
![Future Forecast](plots/future_forecast.png)

### Final Model Comparison Dashboard
![Final Dashboard](plots/final_comparison_dashboard.png)

### Anomaly Detection
![Anomaly IQR](plots/anomaly_iqr.png)

## 📁 Repository Structure
