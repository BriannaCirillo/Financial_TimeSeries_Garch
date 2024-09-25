# Financial_TimeSeries_Garch

# Modeling and Forecasting Volatility in Financial Time Series

This project focuses on analyzing and forecasting volatility in financial time series data using ARIMA and GARCH models. The analysis compares the behavior of two datasets: the Federal Reserve Economic Data (FRED) on U.S. retail sales and Apple’s stock closing prices. The goal is to develop a robust model for understanding the time-varying volatility and providing accurate future forecasts for each dataset.

## Project Overview

This study applies time series analysis techniques to both seasonal retail sales data and non-seasonal stock price data, aiming to forecast future values. The models applied include:
- **ARIMA** (AutoRegressive Integrated Moving Average) models for capturing trends and seasonality.
- **GARCH** (Generalized Autoregressive Conditional Heteroskedasticity) models for modeling and forecasting volatility in the data.

### Key Objectives:
- Explore the seasonal and non-seasonal characteristics of the datasets.
- Identify and apply ARIMA models for trend and seasonality.
- Capture volatility using GARCH models and evaluate their performance.
- Use statistical tests such as the ADF test and Ljung-Box test to validate stationarity and autocorrelation.

## Datasets

1. **FRED Monthly Retail Sales**: 
   - Data from the U.S. Census Bureau capturing consumer demand for goods and services.
   - Period: January 1992 to July 2024 (32 years, 391 observations).
   - The data exhibits an upward trend and seasonal spikes, notably around the financial crisis of 2008 and the COVID-19 pandemic.

2. **Apple Stock Prices**: 
   - Monthly closing prices of Apple Inc. from January 2016 to May 2024.
   - The data shows an upward trend with increasing volatility over time.

## Methodology

1. **Time Series Analysis**:
   - Conducted ACF (Autocorrelation Function) and PACF (Partial Autocorrelation Function) analysis to determine the order of the ARIMA models.
   - Seasonal decomposition was applied to the retail sales data to isolate trend, seasonality, and residual components.

2. **ARIMA Model**:
   - A range of ARIMA models was tested for both datasets, with model selection based on Akaike Information Criterion (AIC) and Bayesian Information Criterion (BIC).
   - ARIMA(3,0,3)×(0,0,3)12 was selected for retail sales, while ARIMA(2,1,1) was chosen for Apple stock prices.

3. **GARCH Model**:
   - After fitting ARIMA models, GARCH(1,1) models were applied to the residuals to capture the time-varying volatility.
   - Both normal and Student-t distributions were considered for the GARCH models, with the Student-t distribution providing better flexibility for heavy tails often seen in financial data.

4. **Model Validation**:
   - The Ljung-Box test was applied to ensure the residuals of the fitted models resembled white noise.
   - AIC and BIC scores were compared across models to select the most robust.

## Results

- **Retail Sales**: 
   - ARIMA(3,0,3) × (0,0,3)12 with GARCH(1,1) (Student-t distribution) best captured the volatility patterns in the retail sales data.
   - The model captured the seasonal spikes and periods of increased volatility (e.g., during the financial crisis and the pandemic).

- **Apple Stock**: 
   - ARIMA(2,1,1) combined with GARCH(1,1) performed well in modeling Apple’s stock price volatility.
   - The volatility in the stock prices was successfully captured, and the forecasts aligned with historical trends.

## Conclusion

The ARIMA-GARCH combination models effectively captured both the seasonal and non-seasonal dynamics present in the retail sales and Apple stock data, respectively. GARCH models significantly improved volatility forecasting, a critical aspect of financial time series.
