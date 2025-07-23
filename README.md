# Aave V2 Wallet Credit Scoring (0–1000)

This project presents a machine learning approach to assign credit scores to wallets based on their interaction history with the Aave V2 protocol. Credit scores range from 0 to 1000, with higher scores reflecting responsible and consistent DeFi usage.

---

##  Problem Statement

Given raw transaction data from Aave V2 (~100K transactions), score each wallet based on their activity patterns like deposits, borrows, repayments, redemptions, and liquidations.

---

##  Methodology

### Data Source
Input: JSON file containing wallet-level transactions on Aave V2. Each record includes:
- `action`: e.g., deposit, borrow, repay, etc.
- `actionData`: includes amount
- `timestamp`, `userWallet`

### Feature Engineering
For each wallet:
- Total transaction count
- Action-specific counts (deposit, borrow, repay, etc.)
- Total deposit/borrow/repay amounts
- Repay-to-borrow ratio
- Liquidation count
- Number of active days
- Days since last activity

### Score Calculation
Heuristic formula:
```text
raw_score = 
    0.4 * log(deposit amount) +
    0.3 * repay-to-borrow ratio +
    0.2 * active days -
    0.1 * liquidation count
