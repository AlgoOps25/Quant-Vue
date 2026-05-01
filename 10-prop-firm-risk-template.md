# 10 — Prop-Firm Risk Template

This file defines the risk rules to protect an evaluation or funded prop-firm account.

## 1. Account details

Fill these in for each prop firm account.

```text
Prop firm:
Account size:
Platform: Tradovate
Instrument: NQ / MNQ
Daily loss limit:
Trailing drawdown rule:
End-of-day drawdown rule:
Consistency rule:
Profit target:
Max contracts allowed:
Personal max contracts:
```

## 2. Personal safety limits

Your personal limits should be stricter than the prop firm rules.

```text
Personal daily max loss:
Personal max trades per day:
Personal max consecutive losses:
Max loss per trade:
Max risk after first loss:
Max risk after second loss:
Stop trading after rule break? Yes
```

## 3. Contract sizing guide

General formula:

```text
Dollar risk = stop points × dollars per point × contracts
```

Approximate point values:

| Instrument | Approx. value per point |
|---|---:|
| NQ | $20 per point |
| MNQ | $2 per point |

Examples:

| Stop size | 1 MNQ | 1 NQ |
|---:|---:|---:|
| 5 points | $10 | $100 |
| 10 points | $20 | $200 |
| 20 points | $40 | $400 |
| 30 points | $60 | $600 |

## 4. When to use MNQ instead of NQ

Use MNQ when:

- Testing a new setup.
- Stop is wider than expected.
- You already had one loss.
- Market is fast or news-driven.
- You are not fully confident in the confluence score.
- You are collecting first 20 examples of a setup.

Use NQ only when:

- Setup is A or A+.
- Stop is small enough.
- Target is clean.
- You are under daily risk.
- You are not emotionally compromised.

## 5. Suggested evaluation mode defaults

Use these until the system is proven:

```text
Max trades per day: 3
Max full-risk losses: 2
Max consecutive losses: 2 or 3
Max NQ contracts: 1
Default testing size: MNQ
Stop after rule break: Yes
Trade during major news: No
Add to losers: Never
Qgrid add: only after open profit
```

## 6. Daily shutdown triggers

Stop trading immediately if:

- Personal daily max loss is hit.
- Two full-risk losses occur.
- Three total losses occur.
- You widen a stop.
- You add to a losing trade.
- You trade during a news lockout.
- You take a setup below 7/10 confluence.
- You revenge trade.

## 7. Setup-based sizing

| Setup score | Trade action | Size idea |
|---:|---|---|
| 9–10 | A+ setup | Planned normal size |
| 7–8 | Valid setup | Normal or reduced size |
| 5–6 | Watch only | No trade or sim only |
| 0–4 | Invalid | No trade |

## 8. Daily risk worksheet

Complete before market open.

```text
Date:
Account:
Starting balance:
Prop firm daily loss limit:
Personal daily loss limit:
Max risk per trade:
Max trades:
News times:
No-trade windows:
Primary setup to watch:
Backup setup:
No-trade condition:
```

## 9. Post-day review

```text
Trades taken:
Wins:
Losses:
Net R:
Net dollars:
Rules followed? Y/N
Best trade:
Worst trade:
Did I stop when I should have?
Tomorrow's correction:
```

## Hard rule

```text
The goal is to pass and keep the account, not to maximize one trade.
```
