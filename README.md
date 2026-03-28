
<img width="1144" height="719" alt="ct1" src="https://github.com/user-attachments/assets/12b5d997-424c-4f8e-a508-4c3e5f060855" />
<img width="1197" height="720" alt="ct2" src="https://github.com/user-attachments/assets/f0b7b5c8-2e54-4506-89d2-f428e06ecc0c" />
<img width="1106" height="718" alt="ct3" src="https://github.com/user-attachments/assets/16c6d1d8-7a35-4bbe-a3ab-eec195ab9a38" />
<img width="1268" height="734" alt="ct4" src="https://github.com/user-attachments/assets/76a539ae-fa14-4acd-b140-1144b6aee795" />



# 📊 Trader Behavior vs Market Sentiment Analysis

## 📌 Objective
This project explores the relationship between trader performance and market sentiment using the Bitcoin Fear & Greed Index and Hyperliquid trading data.

The goal is to identify behavioral patterns and derive actionable insights that can improve trading strategies.

---

## 📂 Datasets

### 1. Bitcoin Market Sentiment Dataset
- Columns: `date`, `classification`
- Categories: Extreme Fear, Fear, Neutral, Greed, Extreme Greed

### 2. Hyperliquid Historical Trader Data
- Columns include:
  - `account`, `coin`, `execution_price`, `size_usd`
  - `side`, `timestamp_ist`, `closed_pnl`
  - and other trading-related features

---

## 🛠 Data Processing

- Cleaned column names (lowercase, removed spaces)
- Fixed timestamp issue:
  - Ignored incorrect `timestamp` column (1970 values)
  - Used `timestamp_ist` as the correct time reference
- Converted timestamps to datetime format
- Extracted `date` from timestamps
- Merged sentiment data with trading data on `date`

---

## ⚙️ Feature Engineering

- **Profit** → `closed_pnl`
- **Win Rate** → `profit > 0`
- **Position Size** → `size_usd`
- **Trade Direction Encoding** → BUY = 1, SELL = -1

---

## 📈 Analysis

### 🔹 Profit by Sentiment
- Highest average profit during **Extreme Greed**
- Lowest during **Extreme Fear / Neutral**

### 🔹 Win Rate by Sentiment
- Peak win rate in **Extreme Greed (~46.5%)**
- Lowest in **Extreme Fear (~37%)**

### 🔹 Position Size Behavior
- Highest capital deployed during **Fear (~$7816)**
- Lowest during **Extreme Greed (~$3112)**

---

## 🧠 Key Insights

- Traders perform best during **Extreme Greed**, where both profitability and win rate are highest.
- Despite this, they allocate the **largest capital during Fear**, indicating inefficient risk allocation.
- **Extreme Fear** represents the most unfavorable trading condition.
- There is a clear behavioral mismatch:
  - Traders are **risk-seeking in uncertain conditions**
  - Traders are **risk-averse in optimal conditions**

---

## 📌 Strategy Recommendations

- Increase exposure during **Extreme Greed** (higher success probability)
- Reduce position size during **Fear and Extreme Fear**
- Avoid aggressive trading in volatile market conditions
- Implement stricter risk management during panic phases

---

## 🚀 Conclusion

The analysis reveals strong behavioral inefficiencies in trading decisions. Aligning capital allocation with favorable sentiment conditions can significantly improve performance and reduce risk.

---

## 📎 Author
**Rajdip Dey**
