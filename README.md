
<img width="1144" height="719" alt="ct1" src="https://github.com/user-attachments/assets/12b5d997-424c-4f8e-a508-4c3e5f060855" />
<img width="1197" height="720" alt="ct2" src="https://github.com/user-attachments/assets/f0b7b5c8-2e54-4506-89d2-f428e06ecc0c" />
<img width="1106" height="718" alt="ct3" src="https://github.com/user-attachments/assets/16c6d1d8-7a35-4bbe-a3ab-eec195ab9a38" />
<img width="1268" height="734" alt="ct4" src="https://github.com/user-attachments/assets/76a539ae-fa14-4acd-b140-1144b6aee795" />


#  Trader Behavior vs Market Sentiment Analysis

## Objective
This project looks into how trader performance changes with overall market sentiment. By combining the Bitcoin Fear & Greed Index with Hyperliquid trading data, the aim is to understand how traders behave under different market conditions.

The focus is on identifying patterns in decision-making and using those insights to improve trading strategies.

---

## atasets

### 1. Bitcoin Market Sentiment Dataset
- Columns: `date`, `classification`
- Sentiment categories: Extreme Fear, Fear, Neutral, Greed, Extreme Greed

### 2. Hyperliquid Historical Trader Data
- Includes fields such as:
  - `account`, `coin`, `execution_price`, `size_usd`
  - `side`, `timestamp_ist`, `closed_pnl`
  - along with other trade-related metrics

---

## Data Processing

- Standardized column names (lowercase, removed spaces)
- Fixed timestamp issues:
  - Ignored the incorrect `timestamp` column (defaulting to 1970 values)
  - Used `timestamp_ist` as the correct time reference
- Converted timestamps into datetime format
- Extracted `date` from timestamps
- Merged trading data with sentiment data based on `date`

---

## Feature Engineering

- **Profit** → derived from `closed_pnl`
- **Win Rate** → trades where profit > 0
- **Position Size** → `size_usd`
- **Trade Direction Encoding** → BUY = 1, SELL = -1

---

## Analysis

### 🔹 Profit by Sentiment
- Highest average profit observed during **Extreme Greed**
- Lower profitability during **Extreme Fear** and **Neutral** phases

### 🔹 Win Rate by Sentiment
- Peak win rate in **Extreme Greed (~46.5%)**
- Lowest win rate in **Extreme Fear (~37%)**

### 🔹 Position Size Behavior
- Largest capital allocation during **Fear (~$7816)**
- Smallest position sizes during **Extreme Greed (~$3112)**

---

## Key Insights

- Trading performance is strongest during **Extreme Greed**, with both higher profits and win rates.
- Traders tend to allocate more capital during **Fear**, even though performance is weaker.
- **Extreme Fear** appears to be the least favorable condition for trading.
- There is a clear behavioral mismatch:
  - Traders take on more risk in uncertain conditions
  - Traders become more cautious when conditions are actually favorable

---

## Strategy Recommendations

- Increase exposure during **Extreme Greed**, where probability of success is higher
- Reduce position size during **Fear** and **Extreme Fear**
- Avoid aggressive trading during highly volatile conditions
- Apply stricter risk management during panic-driven markets

---

## Conclusion

The analysis highlights clear inefficiencies in how traders allocate risk. Aligning capital deployment with favorable sentiment conditions can improve overall performance and reduce unnecessary losses.

---

## Author
**Anumita Kundu**
