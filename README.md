# Instructions for files:
* First, go through the presentation for an overview of the project
* Then, go through SnP500Analysis.ipynb
* Next, go through EDA_1.ipynb, which contains all the exploratory data for macro finance
* Finally, go through Indicators & Analysis Prediction but run it in an IDE such as (VSCode preferred for group members) as some results are truncated in the browser view of GitHub, which contains all the predictions and data for out economy predictions which contains further information for how to view the notebook

# Predicting U.S. Economic Stability Using Macroeconomic and Financial Indicators

DSCI 521 – Drexel University
2026

**Team Members**

* Marko Melishchuk
* Muhammad Imran Mushtaq
* Zain Al Bassam
* Christos Jovanovic
* Leili Massoum Zadeh

Presentation Slides:
Final Presentation.pptx

---

# Project Overview

This project analyzes macroeconomic and financial indicators to evaluate **U.S. economic stability and predict inflation trends**. By combining macroeconomic data with financial market indicators, we develop a data-driven framework for understanding relationships between key economic variables.

The analysis integrates:

* Inflation
* Unemployment
* Federal Funds Rate
* Housing prices
* Oil prices
* U.S. Dollar Index
* S&P 500 market behavior

Machine learning and statistical models are used to evaluate whether these indicators can help predict future inflation and detect structural changes in the economy.

---

# Objective

The objective of this project is to build a **market analysis system** that:

* Measures structural properties of the S&P 500
* Extracts key macroeconomic indicators
* Analyzes financial trends
* Develops predictive models for inflation

### Key Research Question

**How can macroeconomic and financial indicators be used to quantitatively characterize and predict economic stability over time?**

---

# Data Sources

The project uses publicly available economic datasets.

| Dataset             | Source                               | Description                        |
| ------------------- | ------------------------------------ | ---------------------------------- |
| CPI / Inflation     | Federal Reserve Economic Data (FRED) | Measures consumer price changes    |
| Unemployment Rate   | U.S. Bureau of Labor Statistics      | Percentage of unemployed workforce |
| Federal Funds Rate  | Federal Reserve Board                | Monetary policy interest rate      |
| Housing Prices      | U.S. Census Bureau                   | Median home sale prices            |
| S&P 500 Market Data | Yahoo Finance                        | Market performance and volatility  |
| Oil Prices          | Energy Market Data                   | Brent and WTI crude oil prices     |
| U.S. Dollar Index   | Financial Market Data                | Strength of the U.S. dollar        |

---

# Economic Indicators Analysis

## Inflation Rate

Inflation generally remains close to the Federal Reserve’s long-term target of around **2%**, but major economic shocks cause significant fluctuations.

Two major disruptions appear:

* **2008–2009 financial crisis**
* **2020 COVID-19 pandemic**

Both periods resulted in sharp changes in inflation due to reduced economic activity.

Because inflation reflects changes in overall price levels, it is a key indicator used in this project to evaluate **economic stability and future economic trends**.

---

## Unemployment Rate

Unemployment provides insight into the health of the labor market.

Economic crises typically increase unemployment, which reduces consumer spending and lowers inflation pressure.

The relationship between unemployment and inflation is often explained by the **Phillips Curve**, which suggests that:

* Lower unemployment can increase inflation
* Higher unemployment reduces inflationary pressure

This relationship is important when building predictive economic models.

---

## Federal Funds Rate

The Federal Funds Rate reflects the Federal Reserve’s monetary policy.

Major trends include:

* Near-zero rates after the **2008 financial crisis**
* Another major rate cut during the **COVID-19 pandemic**
* Rapid increases after **2021 to control inflation**

Interest rates directly influence borrowing costs, investment, and inflation.

---

## Housing Market Trends

Housing prices provide insight into consumer demand and economic growth.

Key observations:

* Housing prices dropped significantly during the **2008 financial crisis**
* Prices steadily recovered through the 2010s
* Post-COVID housing prices surged before stabilizing

Housing markets often reflect broader economic conditions and consumer confidence.

---

## Oil Price Trends

Oil prices are highly volatile and respond to global economic conditions.

Key observations:

* Rapid price increases during periods of strong economic growth
* Sharp declines during economic crises
* Major disruptions during **2008 financial crisis** and **COVID-19 pandemic**

Oil prices influence inflation because energy costs affect:

* transportation
* manufacturing
* production costs

For this reason, oil prices are included as an important predictor of inflation.

---

# S&P 500 Market Structure Analysis

Financial markets exhibit complex structural behavior driven by several factors.

The project analyzes five key market dimensions:

1. **Trend / Drift** – direction and persistence of price movements
2. **Volatility** – magnitude of price fluctuations
3. **Volume** – trading activity levels
4. **Liquidity** – ease of trading without price impact
5. **Correlation** – relationships between assets

Understanding these structural properties helps detect:

* market regime changes
* instability periods
* shifts in market behavior

---

# Market Stability Index

A **Market Stability Index** was developed to summarize overall market conditions.

The index combines several market indicators:

| Indicator   | Weight |
| ----------- | ------ |
| Drift       | 0.25   |
| Volatility  | 0.25   |
| Liquidity   | 0.20   |
| Volume      | 0.15   |
| Correlation | 0.15   |

The index is analyzed using a **Markov Switching Model** to detect regime changes and structural market shifts.

Interpretation:

* **High index values** → stable markets
* **Low index values** → high volatility and instability

---

# Predictive Modeling

Two datasets were constructed to evaluate inflation prediction.

## Base Dataset (Macro Only)

Includes:

* Inflation
* Unemployment
* Federal Funds Rate
* Housing indicators

This dataset provides **longer historical coverage**.

---

## Full Dataset (Macro + Market)

Includes:

* All macroeconomic indicators
* Oil prices
* S&P 500 data
* Dollar index

This dataset contains more variables but a shorter time range.

---

# Machine Learning Models

Two models were used to predict inflation.

## Linear Regression

Linear regression was used as a **baseline econometric model** because:

* it is widely used in economic analysis
* results are easily interpretable
* it provides a benchmark for comparison

---

## Random Forest

Random Forest was selected because it:

* captures **nonlinear relationships**
* models complex interactions between indicators
* handles noisy macroeconomic data well
* provides **feature importance analysis**

---

# Model Performance

| Dataset      | Model             | MAE      | RMSE      | R²      |
| ------------ | ----------------- | -------- | --------- | ------- |
| Base Dataset | Random Forest     | **8.48** | **10.54** | -0.44   |
| Full Dataset | Random Forest     | 9.27     | 11.20     | -3.91   |
| Base Dataset | Linear Regression | 24.30    | 39.30     | -18.97  |
| Full Dataset | Linear Regression | 51.23    | 62.82     | -153.24 |

### Key Findings

* **Random Forest significantly outperformed Linear Regression**
* The **Base Dataset produced the best results**
* Adding additional financial variables did not improve prediction accuracy in this model

This suggests that **core macroeconomic indicators contain most of the predictive signal for inflation**.

---

# Feature Importance

The most important predictors in the Random Forest model were:

* unemployment rate
* rolling unemployment averages
* S&P 500 returns
* oil prices
* dollar index indicators

Unemployment-related variables were the strongest predictors, supporting the **Phillips Curve theory**, which links unemployment and inflation.

---

# Key Insights

From this analysis we observe:

* Economic indicators are strongly interconnected
* Market volatility tends to cluster during periods of instability
* Liquidity deteriorates during high volatility periods
* Oil prices and unemployment strongly influence inflation dynamics
* Random Forest models better capture complex economic relationships

---

# Limitations

Several limitations affect the predictive performance:

* relatively small macroeconomic dataset
* structural economic shocks (e.g., pandemics)
* simplified modeling assumptions
* limited historical availability for some financial indicators

Future improvements could include:

* larger datasets
* additional macroeconomic indicators
* more advanced time-series models

---

# Conclusion

This project demonstrates how macroeconomic and financial indicators can be integrated to analyze economic stability and forecast inflation trends.

Key conclusions include:

* Machine learning models can improve macroeconomic forecasting
* Unemployment remains one of the strongest predictors of inflation
* Market indicators such as oil prices and stock market returns provide additional economic signals
* Economic stability can be quantified using structural market indicators



