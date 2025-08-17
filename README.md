# Modeling and Forecasting Total Gross Gas Consumption in France - Time Series Forecasting

## Dataset 📊

Our study is based on the dataset provided by **ODRE: Open Data Réseaux Énergie**, a consortium that includes, among others, GRTgaz and Teréga. These groups operate within the natural gas supply chain, with GRTgaz handling transportation and Teréga managing gas storage. Their clients are players in the gas market who intervene at various stages of the production, distribution, and commercialization of natural gas, as well as industrial consumers. Link to public dataset : https://urlz.fr/oAG7.

## Overview 🌟

We study the total gross gas consumption in France. It is measured in Megawatts (MW), using the convention of a Higher Heating Value (HHV) at 0 degrees Celsius. This corresponds to the total amount of heat released at constant volume by the combustion of one kilogram of fuel. The measurements cover the period 2012–2023.

We chose to train our model on 80% of the available data, which corresponds to the period from 2012 to mid-2020. We then attempt to predict the daily total gross gas consumption in France from October 2021 to December 2022.

--- 

Key steps of the project include:
- Decomposition of the time series into trend, seasonality, and residuals
- Implementation and benchmarking of several models: AR, MA, ARMA
- Residual analysis to assess model adequacy
- Forecasting daily gas consumption in France from October 2021 to December 2022

## Models Implemented 🧮

- **Moving Average** (MA)
- **Autoregressive** (AR)
- **Autoregressive Moving Average** (ARMA)

## Benchmarking Metrics 📈

The benchmarking of the time series models (MA, AR, ARMA) relied on several evaluation tools:

- **Akaike Information Criterion** (AIC): Used to compare model fit while penalizing complexity, with the best model selected based on the lowest AIC value.
- **Durbin-Watson Test**: Applied to residuals to detect the presence of autocorrelation, ensuring they behaved like white noise.
- **Q-Q Plot** & **Residual Histogram**: Used to assess the normality of residuals and verify whether they followed a Gaussian distribution centered around zero.
- **Autocorrelation Function** (ACF) of Residuals: Checked for the absence of correlation between residuals, validating the white noise assumption.
- **Root Mean Square Error** (RMSE): Quantified the prediction accuracy, with lower values indicating better performance.

---

🔎 These combined metrics allowed the selection of the ARMA(11,3) model as the best-performing one for forecasting total gas consumption in France:
- RMSE ≈ 0.53, consistent with the scale of observed data.
- The ARMA(11,3) model provided the most reliable forecasts.
- Adding external variables (e.g., temperature, energy crisis data) could further improve accuracy.
