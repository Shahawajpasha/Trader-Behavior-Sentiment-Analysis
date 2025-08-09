# Trader Behavior & Market Sentiment Analysis

## 📌 Overview
This project analyzes how trader performance correlates with Bitcoin market sentiment (Fear, Neutral, Greed, and Unknown) using historical trade records from Hyperliquid and the Fear & Greed Index.  
The goal is to uncover patterns in profitability, trade sizes, and win rates to inform smarter trading strategies.

---

## 📂 Dataset
**1. Historical Trader Data**  
- Source: Hyperliquid  
- Key Fields: `account`, `symbol`, `execution price`, `size`, `side`, `Timestamp IST`, `Closed PnL`, `leverage`  
- Granularity: Individual trades  

**2. Fear & Greed Index**  
- Source: Alternative.me  
- Fields: `date`, `classification` (Fear, Neutral, Greed)  
- Granularity: Daily sentiment classification

---

## ⚙️ Steps Performed
1. **Data Loading & Cleaning**  
   - Parsed timestamps (`Timestamp IST`) and sentiment dates  
   - Renamed `classification` → `Sentiment`  
   - Merged datasets on `date`  
   - Filled missing sentiments with `'Unknown'`

2. **Feature Engineering**  
   - Created `PnL_Category` (Loss, Low Profit, Medium Profit, High Profit)  
   - Added `Direction` (Long/Short) based on trade side  
   - Extracted trade execution `Hour`  
   - Created `Win` flag for profitable trades

3. **Exploratory Data Analysis (EDA)**  
   - Sentiment distribution  
   - PnL by sentiment  
   - Trade size by sentiment  
   - Win rate by sentiment  
   - Trading hour patterns

4. **Insight Generation**  
   - Automated summary of key findings  
   - Exported insights to `key_insights.txt`

---

## 📊 Key Insights
From the merged dataset:

1. Most common market sentiment: **Fear**
2. Highest average Closed PnL: **Unknown** sentiment (7078.67)
3. Lowest average Closed PnL: **Neutral** sentiment (34.31)
4. Highest average trade size: **Unknown** sentiment (14,778.14 USD)
5. Highest win rate: **Unknown** sentiment (100%)
6. Peak trading time: **00:00 hours**

---

## 📈 Visual Outputs
All plots are stored in the `outputs/` folder:
- `sentiment_distribution.png`
- `pnl_by_sentiment.png`
- `trade_size_vs_sentiment.png`
- `key_insights.txt` (text summary of insights)

---

## 🗂️ Folder Structure
ds_shahawajpasha/
├── notebook_1.ipynb
├── csv_files/
│ ├── historical_data.csv
│ └── fear_greed_index.csv
├── outputs/
│ ├── sentiment_distribution.png
│ ├── pnl_by_sentiment.png
│ ├── trade_size_vs_sentiment.png
│ └── key_insights.txt
├── ds_report.pdf
└── README.md

---

## 🔗 Links
- **Google Colab Notebook:** https://colab.research.google.com/drive/1Ki8Ju8HdwS85sLDuIrzG23YPFFSx03GV?usp=sharing

- **GitHub Repository:** https://github.com/Shahawajpasha/Trader-Behavior-Sentiment-Analysis

---

## 👨‍💻 Author
**Shahawaj Pasha**  
Final-year BSc Data Science student passionate about data analytics, trading insights, and real-world problem solving.
