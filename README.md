# GARCH Volatility Forecasting on Financial Time Series

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![Model](https://img.shields.io/badge/Model-GARCH(1,1)-green.svg)

A **time series analysis project** focused on modeling and forecasting financial volatility using the **GARCH (1,1)** model.

This project uses daily return data from financial time series to analyze volatility clustering, stationarity, ARCH effects, conditional variance modeling, and future volatility forecasting.

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
```

---

## Workflow

```text
Load return data
      ↓
Visualize volatility clustering
      ↓
ADF Test (Stationarity)
      ↓
Engle’s ARCH Test
      ↓
GARCH(1,1) Model Estimation
      ↓
Conditional Volatility Extraction
      ↓
Residual Diagnostics
      ↓
ARCH Re-Test
      ↓
10-Day Volatility Forecast
      ↓
Visualization and Interpretation
```

---

## Methodology

## 1. Load Data

The dataset used is:

```text
garch_dataset_400.xlsx
```

The main variable analyzed is:

```text
Return
```

This represents daily return values of a financial asset and is scaled by multiplying by 100 for GARCH estimation stability.

---

## 2. Volatility Clustering Visualization

A line plot is created to observe volatility behavior.

### Key Observation

Periods of high volatility are followed by high volatility, while low volatility tends to follow low volatility.

This indicates the presence of:

```text
Volatility Clustering
```

which supports the use of GARCH modeling.

---

## 3. Stationarity Test

The project uses:

```text
ADF Test (Augmented Dickey-Fuller)
```

### Interpretation

If:

```text
p-value < 0.05
```

then the return series is considered stationary.

This is an important assumption before applying GARCH.

---

## 4. ARCH Effect Test

The project uses:

```text
Engle's ARCH Test
```

to determine whether conditional heteroskedasticity exists.

### Interpretation

If:

```text
p-value < 0.05
```

then ARCH effects exist and GARCH modeling is justified.

---

## 5. GARCH Model

The volatility model used is:

```text
GARCH(1,1)
```

with specification:

```python
mean='Constant'
vol='GARCH'
p=1
q=1
dist='Normal'
```

This model captures:

- short-term volatility shocks
- long-term volatility persistence

---

## 6. Residual Diagnostics

After fitting the model:

- conditional volatility is extracted
- standardized residuals are calculated

Then the project performs:

```text
ARCH Re-Test
```

to verify whether the model successfully removes ARCH effects.

### Expected Result

```text
p-value > 0.05
```

which indicates the model is adequate.

---

## 7. Volatility Forecasting

The model forecasts:

```text
10 days ahead volatility
```

using:

```python
results.forecast(horizon=10)
```

The forecasted variance is converted into volatility using:

```python
sqrt(variance)
```

This helps evaluate future market uncertainty.

---

## Example Usage

```python
from arch import arch_model

model = arch_model(
    returns,
    mean='Constant',
    vol='GARCH',
    p=1,
    q=1,
    dist='Normal'
)

results = model.fit(disp='off')
print(results.summary())
```

---

## Tech Stack

- Python
- pandas
- NumPy
- matplotlib
- statsmodels
- arch
- scipy

---

## Key Outputs

The notebook produces:

- volatility clustering plot
- ADF test results
- ARCH test results
- GARCH summary table
- conditional volatility plot
- standardized residual diagnostics
- 10-day volatility forecast plot

---

## Use Cases

This project is highly relevant for:

- stock market volatility analysis
- financial risk management
- portfolio decision support
- Value-at-Risk baseline modeling
- econometrics coursework
- time series forecasting studies

---

## License

This project is licensed under the **MIT License**.

You are free to use, modify, distribute, and adapt this work with proper attribution.

---

## MIT License

Copyright (c) 2026 Dimas Pasha Akrilian

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the “Software”), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---

## Author

**Dimas Pasha Akrilian**

This repository is part of my **financial time series and statistical modeling portfolio**, focusing on volatility forecasting, econometric analysis, and applied GARCH modeling.
