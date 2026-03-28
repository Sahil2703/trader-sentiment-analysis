# Hyperliquid × Fear & Greed — Trader Sentiment Analysis

Analysis of how Bitcoin market sentiment (Fear/Greed) relates to 
trader behavior and performance on the Hyperliquid derivatives platform.

---

## Project Structure
```
trader-sentiment-analysis/
├── notebook/        # Jupyter notebook with full analysis
├── charts/          # All output visualizations
├── data/            # Data source information
├── README.md        # This file
└── WRITEUP.md       # 1-page summary of findings
```

---

## Setup & How to Run

### Requirements
- Python 3.8+
- Jupyter Notebook or JupyterLab

### Install Dependencies
```bash
pip install pandas numpy matplotlib seaborn
```

### Steps

1. Clone this repository
```bash
git clone https://github.com/YOUR_USERNAME/trader-sentiment-analysis.git
cd trader-sentiment-analysis
```

2. Add the data files (see `data/README.md` for details)

3. Launch Jupyter
```bash
jupyter notebook
```

4. Open `notebook/Trader_Performance_vs_Market_Sentiment_Analysis.ipynb`

5. Run all cells in order — Kernel → Restart & Run All

---

## Key Findings

- **Greed days** produce 37% higher median PnL and 2.5x shallower losses
- **High Aggression traders** earn 2.1x more on Fear days than Greed days
- **Low Aggression traders** earn 2.6x more on Greed days than Fear days
- **Frequent traders** are momentum followers — win rate reaches 96% on Greed days
- **Infrequent traders** are contrarians — earn 38% more on Fear days
- **Consistent Winners** maintain 93–96% win rate regardless of sentiment

See `WRITEUP.md` for full methodology and strategy recommendations.

---

## Output Charts

| Chart | Description |
|---|---|
| 1_sentiment_distribution | Sentiment score over time + day count per label |
| 2_pnl_distribution | PnL histogram, outcome split, cumulative curve |
| 3_trade_activity_over_time | Volume, trades, traders over time by sentiment |
| 4_performance_vs_sentiment | Part A — PnL, win rate, drawdown by sentiment |
| 5_behavior_vs_sentiment | Part B — frequency, size, ls ratio, fees |
| 6_segments_vs_sentiment | Part B — all 3 segments × sentiment |
| strategy_evidence | Part C — strategy evidence charts |
| insights_summary | 3 headline insights summary |
