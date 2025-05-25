# 📈 Bitcoin Sentiment vs. Trader Performance

**An exploratory data science project to understand how Bitcoin market sentiment influences trader behavior and profitability on Hyperliquid.**

---

## 📘 Project Notebook

📂 `Trader_Behavior_Insights.ipynb`  
The complete analysis is available in the Jupyter Notebook included in this repository.  
It contains all preprocessing, visualizations, insights, and statistical testing.

---

## 🧠 Overview

This project explores the correlation between **Bitcoin market sentiment** (Fear & Greed Index) and **trader performance** using historical trading data from Hyperliquid.

By connecting sentiment indicators to trading metrics (PnL, volume, trade count), we aim to answer:
> _"Does trader profitability change with the market's emotional state?"_

---

## 📁 Datasets

> ⚠️ Due to large file sizes, datasets are hosted externally. Please download and place them in a `data/` folder.

### 🧾 1. Fear & Greed Index  
- Columns: `timestamp`, `value`, `classification` (Extreme Fear → Extreme Greed)
- 📥 [Download CSV](https://drive.google.com/file/d/1PgQC0tO8XN-wqkNyghWc_-mnrYv_nhSf/view?usp=sharing)

### 📊 2. Hyperliquid Trader History  
- Columns: `account`, `symbol`, `execution price`, `size USD`, `side`, `Closed PnL`, etc.
- 📥 [Download CSV](https://drive.google.com/file/d/1IAfLZwu6rJzyWKgBToqwSmmVYU6VbjVs/view?usp=sharing)

---

## 🔍 Methodology

### 1. Data Preprocessing  
- Converted UNIX timestamps to readable dates  
- Normalized timezones to UTC  
- Filtered BTC trades (`Coin` column)  
- Mapped sentiment labels to numeric scores

### 2. Daily Aggregation  
- Aggregated metrics per day:
  - `total_volume_usd`
  - `avg_execution_price`
  - `net_pnl`
  - `trade_count`
- Averaged sentiment scores and values per day

### 3. Data Merging  
- Merged datasets on `date` column  
- Filtered out days with zero trades

### 4. Exploratory Analysis & Visualization  
- Scatter plot: Sentiment value vs Net PnL  
- Bar plot: Avg PnL by Sentiment Classification

### 5. Statistical Testing  
- ANOVA test to check if average PnL differs significantly across sentiment levels

---

## 📌 Insights

- 📉 Traders lose more on **Extreme Fear** days  
- 📈 **Neutral** and **Greed** days show higher profitability  
- ✅ ANOVA p-value < 0.05 → sentiment has **statistically significant** impact on performance

---

## ▶️ How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/Tamannasinghk/bitcoin-sentiment-vs-trader-performance.git
   cd bitcoin-sentiment-vs-trader-performance
   ```
2. Download the datasets from the links above Place them in a folder named data/ like this:
   ```bash
   /data
   ├── fear_greed_index.csv
   └── historical_data.csv
   ```
3. Install dependencies :
   ```python
   pip install pandas matplotlib seaborn scipy jupyter
   ```
4. Run the notebook in google colab :
   ```bash
   Trader_Behavior_Insights.ipynb
   ```
---
## Connect with me:
LinkedIn : [Tamanna Singh](https://www.linkedin.com/in/tamanna-singh-6a7b51249/)



