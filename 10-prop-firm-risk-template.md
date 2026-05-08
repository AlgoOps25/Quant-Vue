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

Your personal limits should be **stricter** than the prop firm rules.

```text
Personal daily max loss:
Personal max trades per day: 3
Personal max consecutive losses: 2
Max loss per trade:
Max risk after first loss: reduce to 50% of default
Max risk after second loss: stop trading for the day
Stop trading after rule break? Yes — no exceptions
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

- Collecting first 20 replay + 20 sim examples of any setup (always MNQ at this stage).
- Stop is wider than your default max dollar risk.
- You already had one loss today.
- Market is fast or news-driven.
- Confluence score is below 9.
- You are not fully confident.

Use NQ only when:

- Strategy 0 has 40+ logged examples and passes criteria in `11-replay-validation-plan.md`.
- Setup scores A or A+ (9–10 per `02-confluence-system.md`).
- Stop is small enough to fit within personal daily loss limit with room for at least 2 more trades.
- Target is clean and at least 2R.
- You are under daily risk.
- No emotional compromise.

## 5. Evaluation mode defaults

Use these until the full validation pipeline in `11-replay-validation-plan.md` is complete:

```text
Instrument: MNQ (NQ only for A/A+ after Strategy 0 is validated)
Max trades per day: 3
Max full-risk losses: 2
Max consecutive losses: 2
Max NQ contracts: 1
Default testing size: MNQ
Stop after rule break: Yes
Trade during major news: No
Add to losers: Never
Qgrid add: only after first target or break-even move, and only in open profit
```

## 6. Session and news lockout windows

```text
No new entries within 2 minutes before or after a scheduled red/orange news event.
No new entries in the first 1 minute of RTH (9:30:00–9:30:59 ET) — let the opening candle form.
Prefer entries in 9:30–11:00 ET and 14:00–15:15 ET windows.
Avoid 12:00–13:30 ET unless confluence score is 9–10 and setup is exceptionally clean.
```

Check ForexFactory or CME calendar for daily news times before market open. Log the news times in the Daily Risk Worksheet below.

## 7. Daily shutdown triggers

Stop trading immediately if:

- Personal daily max loss is hit.
- Two full-risk losses occur.
- Three total losses occur.
- You widen a stop after entry.
- You add to a losing trade.
- You trade during a news lockout window.
- You take a setup with a confluence score below 7.
- You revenge trade.
- You feel emotional, rushed, or frustrated.

## 8. Setup-based sizing

| Setup score | Trade action | Size idea |
|---:|---|---|
| 9–10 | A+ setup | Planned normal size |
| 7–8 | Valid setup | Reduced size (MNQ preferred unless fully validated) |
| 5–6 | Watch only | No trade or sim only |
| 0–4 | Invalid | No trade |

## 9. Daily risk worksheet

Complete before market open.

```text
Date:
Account:
Starting balance:
Prop firm daily loss limit:
Personal daily loss limit:
Max risk per trade:
Max trades:
Scheduled news times:
No-trade windows:
Primary setup to watch: Strategy 0 — Level Test / Level Sweep
Key 4H levels for today:
Key 15m levels (mark after open):
Backup: no trade
No-trade condition:
```

## 10. Post-day review

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
One good trade is worth more than three impulsive ones.
```
