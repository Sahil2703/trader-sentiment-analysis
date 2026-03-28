### Project: Market Sentiment & Trader Behavior on Hyperliquid

---

#### Dataset Overview

Two datasets were analyzed jointly. The Fear & Greed Index provided 2,644 daily sentiment readings from February 2018 to May 2025, classified across five labels — Extreme Fear, Fear, Neutral, Greed, and Extreme Greed. The Hyperliquid historical trader dataset contained 211,224 trade-level records across 32 unique accounts, spanning May 2023 to May 2025. After filtering for closed trades only, 104,408 rows with realized PnL were retained. The overlapping analysis window covers exactly 2 years — 480 trading days, during which 2,341 unique trader-day combinations were observed.

---

#### Part A — Does Performance Differ Between Fear and Greed Days?

**Yes, clearly and consistently across all three performance dimensions.**

Greed days produced a median daily PnL of $909 per trader, compared to $663 on Fear days, a 37% advantage. The win rate followed the same pattern: 89.5% of trader-days were profitable during Greed versus 83.4% during Fear, a 6.1 percentage point gap. Most strikingly, the drawdown proxy revealed that when traders lost money on Fear days, the median loss was -$1,622, 2.5 times deeper than the -$648 median loss on Greed days.

Across the full 2-year window, Fear days generated $4.1M in total trader PnL and Greed days generated $4.9M, despite Greed days being nearly 50% more numerous (844 vs 572 trader-days), which confirms that per-day performance is genuinely higher under Greed. Neutral days were consistently the weakest across all three metrics — $568 median PnL, 84.8% win rate, -$857 median loss.

One important methodological caveat: the dataset grew significantly over time, and Fear days are concentrated in the more recent high-activity period (late 2024 to 2025). Per-trader-day medians were used throughout to mitigate this time confound.

---

#### Part B — Do Traders Change Behavior Based on Sentiment?

**Yes, but the behavioral shifts are more nuanced than expected — and they differ dramatically by trader type.**

At the aggregate level, behavioral differences across sentiment groups are modest. Median trade frequency is nearly identical: 31 trades per day on Fear days versus 28 on Greed days. Median trade size is slightly larger on Greed days ($2,005 vs $1,854). The long/short ratio is below 1.0 under all sentiment conditions, meaning traders in this cohort maintain a net short bias regardless of market mood — but Fear days show the least short bias (0.70) while Neutral days show the most (0.60). This is counterintuitive and suggests some traders adopt contrarian long positions during Fear periods expecting a bounce.

The most important behavioral finding emerges at the segment level. Three distinct trader segments were identified:

**Segment 1 — Aggression:** Traders were split at the median trade size ($2,475). High Aggression traders (16 accounts) earn 2.1x more on Fear days than Greed days ($2,679 vs $1,303). Low Aggression traders (16 accounts) earn 2.6x more on Greed days than Fear days ($768 vs $298). The same market conditions produce opposite outcomes depending on position sizing style.

**Segment 2 — Frequency:** Traders were split at the median daily trade count (27.5 trades). Frequent traders (16 accounts) are momentum followers. Their median PnL jumps from $536 (Fear) to $981 (Greed) and their win rate reaches 96% during Greed as they ramp from 53 to 81 trades per day. Infrequent traders (16 accounts) are contrarians, they earn 38% more on Fear days ($1,215 vs $883) and become more active during Fear (26 trades) than Greed (19 trades).

**Segment 3 — Consistency:** Traders were split into thirds by their proportion of profitable days. Consistent Winners (11 accounts, consistency ≥ 0.92) maintain exceptional win rates of 93–96% regardless of sentiment — their edge is structural, not sentiment-dependent. The Middle segment is most vulnerable to sentiment shifts, with PnL ranging from $216 (Fear) to $513 (Greed). Inconsistent traders (11 accounts) paradoxically earn more on Fear days ($907) than Greed days ($716), likely due to large asymmetric bets that occasionally pay off during volatile periods.

---

#### Part C — Actionable Strategy Recommendations

**Strategy 1 — Calibrate Aggression to Sentiment**

High Aggression traders should increase position sizes during Fear periods and apply strict stop losses — their median PnL is 2.1x higher on Fear days but their median loss is also 2.2x deeper, making risk management non-negotiable. Low Aggression traders should scale up during Greed periods where their win rate reaches 92% and losses are shallowest, their edge compounds best in calm trending conditions.

**Strategy 2 — Trade With Your Natural Rhythm**

Frequent traders should maximize trade activity during Greed conditions where momentum strategies thrive and win rates approach 96%. Reducing activity during Fear is advisable — their performance drops measurably and their strategy simply does not fit high-volatility environments. Infrequent traders should lean into Fear periods as contrarian opportunity windows; their $1,215 median PnL on Fear days represents their highest earning environment, driven by selective entries into panic-driven dislocations and mean-reversion setups.

---

#### Key Numbers to Remember

```
• Greed days → +37% higher median PnL than Fear days
• Greed days → 2.5x shallower losses when things go wrong
• High Aggression traders earn 2.1x MORE on Fear vs Greed
• Low Aggression traders earn 2.6x MORE on Greed vs Fear
• Frequent traders: win rate 83% (Fear) → 96% (Greed)
• Infrequent traders earn 38% MORE on Fear vs Greed
• Consistent Winners maintain 93–96% win rate regardless of sentiment
• 32 unique traders, 480 trading days, $10.3M total realized PnL
```

---

#### Files Produced

| File | Contents |
|:--|:--|
| `1_sentiment_distribution.png` | Sentiment score over time + day count per label |
| `2_pnl_distribution.png` | PnL histogram, outcome split, cumulative curve |
| `3_trade_activity_over_time.png` | Volume, trades, traders over time by sentiment |
| `4_performance_vs_sentiment.png` | Part A — PnL, win rate, drawdown by sentiment |
| `5_behavior_vs_sentiment.png` | Part B — frequency, size, ls ratio, fees by sentiment |
| `6_segments_vs_sentiment.png` | Part B — all 3 segments × sentiment |
| `strategy_evidence.png` | Part C — strategy evidence charts |
| `insights_summary.png` | 3 headline insights summary |
