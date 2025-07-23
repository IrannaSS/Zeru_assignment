
# Wallet Credit Score Analysis

This document analyzes how wallet credit scores are distributed and interprets behavioral patterns of wallets across different score ranges.

---

## Distribution Graph

The histogram below shows how wallet scores are distributed from 0 to 1000.

![Wallet Score Distribution](wallet_score_distribution.png)

---

## Score Buckets

Wallet scores were grouped into bins:

| Score Range | Description |
|-------------|-------------|
| 0–100       | Highly risky, mostly liquidated or only borrowing |
| 101–200     | Some repay history, but still risky |
| 201–400     | Mixed behavior, occasional liquidations |
| 401–600     | Balanced usage, average activity |
| 601–800     | Good behavior, mostly repaying and depositing |
| 801–1000    | Strong, responsible users with diversified actions |

---

## Observations

### Low Scores (0–200)
- High frequency of borrows
- Little or no repayment
- Many liquidation events
- Bot-like behavior or exploit patterns

### Mid Scores (400–600)
- Some repayment and deposits
- Occasional liquidations
- Moderate protocol usage

### High Scores (800–1000)
- High deposit and repay values
- No or rare liquidations
- Active over long periods
- Trusted wallet profiles

---

## Summary

The scoring model successfully differentiates between exploitative and responsible wallets based on Aave V2 interaction behavior. These scores can be useful in DeFi risk management, user tiering, or reward programs.