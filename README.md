# GARCH Volatility Forecasting on Financial Time Series

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![Model](https://img.shields.io/badge/Model-GARCH(1,1)-green.svg)

A **time series analysis project** focused on modeling and forecasting financial volatility using the **GARCH (1,1)** model.

This project uses daily return data from financial time series to analyze:
- volatility clustering
- stationarity
- ARCH effects
- conditional variance modeling
- future volatility forecasting

The notebook applies **ADF Test, Engle’s ARCH Test, and GARCH(1,1)** to build a complete volatility modeling pipeline.

---

## Project Overview

Financial return series often show periods of high volatility followed by high volatility, and low volatility followed by low volatility. This phenomenon is called **volatility clustering** and is one of the main reasons GARCH models are widely used in financial econometrics.

The objective of this project is to:

- test stationarity of return series
- detect ARCH effects
- estimate a GARCH(1,1) model
- evaluate standardized residuals
- forecast future volatility for the next 10 days

This project is suitable for:
- financial econometrics
- volatility forecasting
- investment risk analysis
- academic time series assignments

---

## Repository Structure

```bash
UTS-Analisis-Runtun-Waktu/
│
├── 2404220026_Dimas_Pasha_Akrilian_UTS_Analisis_Runtun_Waktu.ipynb
├── garch_dataset_400.xlsx
├── LICENSE
└── README.md
