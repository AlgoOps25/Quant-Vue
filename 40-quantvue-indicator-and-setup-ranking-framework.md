# 40 — QuantVue Indicator and Setup Ranking Framework

This document defines the clear testing direction for ranking QuantVue indicators, layouts, and setups from best to worst.

## Purpose

Use all QuantVue transcripts, onboarding notes, screenshots, and saved layouts to answer:

```text
Which QuantVue setups are most accurate, most profitable, easiest to execute, and safest for prop-firm rules?
```

The goal is not to test everything randomly. The goal is to create a repeatable ranking system that narrows the workflow down to the best 1–3 setups.

## Core principle

QuantVue indicators are not judged in isolation.

They are judged by how well they help with:

```text
Location
Direction
Trigger
Stop placement
Exit timing
Risk control
Repeatability
Prop-firm safety
```

## Testing hierarchy

Rank in this order:

```text
1. Setup family
2. Layout
3. Indicator confirmation
4. Settings variation
5. Alert usefulness
```

Do not start by optimizing every indicator setting. Start by finding which setup family actually works.

---

# Phase 1 — Setups to rank

Test these setup families in this order:

## Tier 1 candidates — primary focus

```text
1. Level Test at 15m / 4H / prior session level
2. Level Sweep reversal at 15m / 4H / prior session level
3. 15-minute Opening Range retest
4. 3-minute Opening Range breakout/retest
```

Reason:

```text
These begin with location and structure, not random signals.
```

## Tier 2 candidates — secondary focus

```text
5. Qwave/Qbands reversal to midline
6. Qcloud/Qline trend continuation pullback
7. Qpilot re-entry after location reaction
8. Qbank / Banksy trailing execution
```

Reason:

```text
These depend more heavily on indicator behavior and need context first.
```

## Tier 3 candidates — later focus

```text
9. Qgrid add-to-winner
10. Broad Alerts watchlist signals
11. Tight Band signals
12. Fast scalp layouts
```

Reason:

```text
These are likely useful, but only after the user understands location, direction, and risk.
```

---

# Phase 2 — Layouts to rank

Test layouts in this order:

```text
1. Banksy Manual Setup
2. Banksy Manual Layout
3. Alfredo Qpilot Manual Layout
4. Qgrid Renko Layout
5. Broad Band Setup
6. Tight Band Setup
7. Broad Alerts Setup
```

## Expected role of each layout

| Layout | Role | Priority |
|---|---|---:|
| Banksy Manual Setup | Rule-based execution / structure | 1 |
| Banksy Manual Layout | Qbank/trailing execution | 2 |
| Alfredo Qpilot Manual | Discretionary Qpilot confluence | 3 |
| Qgrid Renko | Add-to-winner only | 4 |
| Broad Band | Fewer watch signals | 5 |
| Tight Band | More sensitive watch signals | 6 |
| Broad Alerts | Alert infrastructure only | 7 |

---

# Phase 3 — Indicators to rank

## Primary indicators

```text
SMC V2
Q_Pro V2
Qbank_Pro
Q_Pilot Pro
Moneyball V2
Qgrid
Momentum V2
```

## Indicator roles

| Indicator | Primary role | Test question |
|---|---|---|
| SMC V2 | Location, liquidity, BOS/CHoCH, structure | Does it keep trades at real levels? |
| Q_Pro V2 | Trend state, Qcloud/Qline/Qwave/Qbands | Does it improve entries/exits after location? |
| Qbank_Pro | Trade management/trailing/box logic | Does it reduce bad exits or late exits? |
| Q_Pilot Pro | Re-entry, TP, volume events | Does it improve discretionary timing? |
| Moneyball V2 | Momentum confirmation | Does it filter bad trades or confirm winners? |
| Qgrid | Add-to-winner | Does it help scale only into winning trades? |
| Momentum V2 | Momentum/secondary confirmation | Does it add value beyond Moneyball/Q_Pro? |

## Testing rule

Each indicator is scored only when used in a specific setup.

Example:

```text
Q_Pilot is not scored globally.
Q_Pilot is scored on Level Sweep reversals, OR retests, and trend continuation entries.
```

---

# Phase 4 — Scoring system

Every candidate trade gets scored after completion.

## Trade quality score: 0–10

| Category | Points | Question |
|---|---:|---|
| Location | 0–2 | Was price at a meaningful level? |
| Structure | 0–2 | Was there BOS/CHoCH/sweep/retest logic? |
| Direction | 0–2 | Did higher context support the trade? |
| QuantVue confirmation | 0–2 | Did the selected tools confirm after location? |
| Risk/exit | 0–2 | Was stop/target clear before entry? |

## Result classification

```text
A+ = 9–10 score and clean result
A = 8 score and valid result
B = 6–7 score, educational but not preferred
C = 4–5 score, weak/unclear
F = below 4, should not trade
```

## Setup result categories

```text
Valid winner
Valid loser
Invalid / should skip
Missed winner
Too early
Too late
Chop / no trade
News invalidated
False signal
```

---

# Phase 5 — Ranking metrics

For each setup/layout/indicator combination, track:

```text
Number of samples
Win rate
Average R
Profit factor estimate
Average stop size
Largest loss
Worst losing streak
Best time of day
Worst time of day
How often setup was obvious before entry
How often it required chasing
How easy it was to execute
How prop-firm safe it was
```

## Minimum sample size

Do not rank a setup seriously until it has at least:

```text
20 observed examples
```

Preferred:

```text
20 forward observations
20 paper/sim executions
```

## Ranking formula

Use this weighting:

```text
40% Average R / profitability
20% Win rate consistency
15% Stop-size practicality
15% Ease of execution
10% Prop-firm safety
```

## Prop-firm safety adjustment

Demote any setup that:

```text
Requires wide stops too often
Requires chasing fast moves
Triggers too many trades per day
Has frequent back-to-back losses
Works only during high-stress volatility
Is hard to execute manually
```

---

# Phase 6 — Testing method

Because TradingView Bar Replay cannot replay Renko/non-traditional charts, testing is split:

## A — Candle Replay testing

Use standard candle charts to test:

```text
Level Test
Level Sweep
Opening Range Retest
Structure behavior
Location quality
```

Charts:

```text
15m candles for context
5m candles for structure
1m/2m candles for execution approximation
```

## B — Forward observation testing

Use live market observation, no real trades, to test:

```text
Banksy Renko behavior
Qbank behavior
Q_Pilot labels
Qgrid add signals
Broad/Tight alert behavior
```

## C — Paper/sim testing

Only after candle replay and forward observation:

```text
Use MNQ first
Use defined entry/stop/target
No live prop-firm risk
```

---

# Phase 7 — Testing matrix

Use this matrix to track combinations.

| Test ID | Layout | Setup | Primary indicator | Secondary confirmation | Market | Timeframe/chart | Sample target |
|---|---|---|---|---|---|---|---:|
| T1 | Banksy | Level Test | SMC/Q_Pro | Qbank | NQ/MNQ | 15m + 1s Renko | 20 |
| T2 | Banksy | Level Sweep | SMC/Q_Pro | Qbank | NQ/MNQ | 15m + 1s Renko | 20 |
| T3 | Banksy | 15m OR Retest | SMC/Q_Pro | Qbank | NQ/MNQ | 15m + Renko | 20 |
| T4 | Alfredo | Level Sweep | Q_Pilot | Moneyball/Q_Pro | NQ/MNQ | 15m + Renko 5 | 20 |
| T5 | Alfredo | Qpilot Re-entry | Q_Pilot | SMC level | NQ/MNQ | 5m + Renko 5 | 20 |
| T6 | Qgrid | Add-to-winner | Qgrid | Q_Pro trend | NQ/MNQ | Renko | 20 |
| T7 | Broad Band | Watch signal | Qwave/Qbands | Moneyball | NQ/MNQ | seconds/Renko | 20 |
| T8 | Tight Band | Watch signal | Qwave/Qbands | Moneyball | NQ/MNQ | seconds/Renko | 20 |

---

# Phase 8 — First narrowing goal

The first goal is not to find the perfect system.

The first goal is to answer:

```text
Which 2 setups are worth studying further?
Which 2 setups are too noisy or too hard to execute?
Which indicators actually help versus create noise?
```

## First 40-sample target

Collect:

```text
20 Banksy Level Test / Sweep candidates
20 Alfredo Level Test / Sweep candidates
```

Then compare:

```text
Accuracy
Average R
Execution clarity
Stop size
Signal noise
Ease of use
```

---

# Phase 9 — Ranking output

After each 20-sample block, create a ranking table:

| Rank | Setup/Layout | Score | Avg R | Win Rate | Notes | Decision |
|---:|---|---:|---:|---:|---|---|
| 1 | TBD | TBD | TBD | TBD | TBD | Keep |
| 2 | TBD | TBD | TBD | TBD | TBD | Keep |
| 3 | TBD | TBD | TBD | TBD | TBD | Refine |
| 4 | TBD | TBD | TBD | TBD | TBD | Drop |

## Decision labels

```text
Keep = continue testing
Refine = adjust settings/rules and retest
Watch only = useful alert but not entry system
Drop = too noisy / not profitable / too hard
```

---

# Immediate next action

Start with:

```text
T1 — Banksy Level Test
T2 — Banksy Level Sweep
```

Use candle replay for level identification and live/forward observation for Renko behavior.

Do not test Alfredo, Qgrid, or Broad Alerts until the first 20 Banksy examples are logged.
