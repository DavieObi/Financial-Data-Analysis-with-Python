# 📊 Financial Data Analysis — Nifty 50 Portfolio Evaluation

## 📘 Project Overview

This project analyzed the historical closing prices of selected **Nifty 50 stocks** to perform a comprehensive **financial data analysis**, including portfolio performance, risk assessment, correlation analysis, technical indicators, and simulation-based forecasting. The analysis provided valuable insights into market trends, stock behavior, and investment risks.

---

## 🧩 Data Preparation

The dataset (`nifty50_closing_prices.csv`) contained daily closing prices for Nifty 50 stocks, including a `Date` column.

### Key Steps:

* Checked for **missing values**, **date format validity**, and **sufficient rows** for time-series analysis.
* Found that the `HDFC.NS` column contained 100% missing values, which was dropped.
* Converted the `Date` column to a valid datetime format and sorted the dataset chronologically.
* Reset the index for a clean, structured DataFrame.

### Outcome:

* **Missing Values:** Only `HDFC.NS` had missing data and was removed.
* **Date Column:** Valid format confirmed.
* **Rows:** Dataset had enough entries for rolling and moving average calculations.

---

## 📈 Descriptive Statistics

Descriptive statistics were calculated for all stocks, providing insights into their **mean**, **standard deviation**, **minimum**, and **maximum** prices.

### Findings:

* Stocks like **MARUTI.NS** and **BAJAJ-AUTO.NS** showed the highest average prices.
* **ITC.NS** and **HINDALCO.NS** had relatively low price volatility, while **BAJFINANCE.NS** exhibited significant fluctuations.
* The summary helped identify both stable and volatile stocks across the Nifty 50.

---

## 💼 Portfolio Analysis

A portfolio was constructed using **RELIANCE.NS (40%)**, **HDFCBANK.NS (35%)**, and **ICICIBANK.NS (25%)**.

### Steps:

* Calculated daily percentage returns for each stock.
* Computed weighted portfolio returns by multiplying individual returns by their respective weights.

### Insights:

* The portfolio’s daily returns fluctuated between positive and negative values, showing natural market volatility.
* A daily return of `0.004495` represented a **0.4495% increase**, while `-0.002790` represented a **0.279% decrease** in portfolio value.

---

## ⚠️ Risk Assessment

Risk was analyzed using **Volatility (Standard Deviation)** and **Value at Risk (VaR)** at a 95% confidence level.

| Stock        | Volatility (Std Dev) | Value at Risk (VaR) |
| ------------ | -------------------- | ------------------- |
| RELIANCE.NS  | 0.0087               | -0.0136             |
| HDFCBANK.NS  | 0.0069               | -0.0060             |
| ICICIBANK.NS | 0.0116               | -0.0086             |

### Interpretation:

* **ICICIBANK.NS** had the highest volatility, implying higher price fluctuations.
* **HDFCBANK.NS** was the least volatile and carried the lowest potential loss.
* **RELIANCE.NS** showed moderate volatility, balancing risk and return.

---

## 🔗 Correlation Analysis

A correlation matrix was created to examine relationships between the stock returns.

### Results:

* **RELIANCE & HDFCBANK:** 0.42 (moderate positive correlation)
* **ICICIBANK & HDFCBANK:** 0.69 (strong positive correlation)
* **RELIANCE & ICICIBANK:** 0.37 (weaker correlation)

### Insight:

The results indicated that while all three stocks tended to move in the same direction, **HDFCBANK and ICICIBANK** shared stronger co-movement, likely due to both belonging to the banking sector.

---

## 📊 Moving Averages

Moving averages were calculated for **RELIANCE.NS** using 5-day and 20-day windows.

### Findings:

* The **5-day moving average** closely followed short-term price movements.
* The **20-day moving average** provided a smoother trend, indicating medium-term price direction.
* A downward crossover (price falling below the 20-day MA) indicated **bearish momentum**, suggesting potential sell signals.

---

## 📉 Relative Strength Index (RSI)

The RSI was calculated using a 14-day window for **RELIANCE.NS**.

### Observations:

* RSI values fluctuated mostly between **30 and 60**, indicating moderate momentum.
* The stock did not enter the overbought region (>70), suggesting **limited short-term bullish pressure**.
* Occasional dips near **30** signaled **potential buying opportunities** during oversold conditions.

---

## 📈 Sharpe Ratio

The **Sharpe Ratio** was computed to measure risk-adjusted returns, assuming a **risk-free rate** of `0.04/252`.

| Stock        | Sharpe Ratio |
| ------------ | ------------ |
| RELIANCE.NS  | -0.05        |
| HDFCBANK.NS  | 0.37         |
| ICICIBANK.NS | 0.47         |

### Insight:

* **ICICIBANK.NS** offered the best **risk-adjusted returns**, making it the most attractive among the three.
* **RELIANCE.NS** had a negative Sharpe Ratio, indicating returns below the risk-free rate.

---

## 🎲 Monte Carlo Simulation

A **Monte Carlo Simulation** with **1,000 iterations** was performed for **RELIANCE.NS** over **252 trading days** (1 year).

### Findings:

* Simulated price paths projected a wide range of future prices due to volatility.
* The spread of trajectories widened over time, representing **increasing uncertainty** in long-term price prediction.
* The simulation highlighted both upside potential and downside risks under random market fluctuations.

---

## 🧠 Insights & Conclusion

### Key Insights:

* The dataset was clean and well-structured for time-series analysis.
* Among the analyzed stocks, **ICICIBANK.NS** delivered the most favorable balance between return and risk.
* **HDFCBANK.NS** showed consistent stability with lower volatility, suitable for conservative investors.
* **RELIANCE.NS** exhibited moderate volatility and mixed performance, suggesting a neutral outlook.
* Strong correlations within the banking sector indicated that diversification benefits might be limited when combining bank stocks.

### Conclusion:

This financial analysis provided a holistic view of portfolio behavior, stock risks, and potential price dynamics.
The results demonstrated the importance of:

* **Diversification** across uncorrelated sectors,
* **Monitoring technical indicators** like RSI and moving averages for trading signals, and
* **Evaluating risk-adjusted returns** (Sharpe Ratio) before making investment decisions.

Monte Carlo simulations further emphasized that while short-term predictions can be reliable, long-term forecasts carry substantial uncertainty — highlighting the need for disciplined, risk-aware investment strategies.

---

### 🧰 Tools & Libraries

* **Python**: Data analysis and computation
* **Pandas**: Data manipulation
* **NumPy**: Numerical computations
* **Plotly**: Interactive visualizations
