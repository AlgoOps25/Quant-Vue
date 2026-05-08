# 11 — Replay Validation Plan

This plan validates the QuantVue NQ system before live prop-firm use.

## 1. Purpose

Do not trade the system live until each setup has enough replay/paper examples to prove that you can execute it consistently.

The goal is to answer:

- Which setups fit NQ best?
- Which setups fit MNQ while learning?
- What is the average stop size?
- What is the realistic win rate?
- What is the average R multiple?
- Which time of day works best?
- Which alerts are useful versus distracting?

## 2. Required sample size and priority

> **Rule**: Only Strategy 0 — Level Test / Level Sweep may be validated until it has 20 replay + 20 sim/paper examples logged and meets the pass criteria below. No other setup may be promoted to live consideration until Strategy 0 clears the bar.

Priority order:

1. **Strategy 0 — Level Test / Level Sweep at 4H/15m level — 20 replay + 20 sim (CURRENT)**
2. Strategy 7 — 15-minute opening range retest — 20 examples *(after Strategy 0 clears)*
3. Strategy 6 — 3-minute opening range breakout/retest — 20 examples
4. Strategy 8 — 8am candle retest — 20 examples
5. Strategy 9 — Zone strategy — 20 examples
6. Strategy 1 — Qwave/Qbands reversal to midline — 20 examples
7. Strategy 2 — Qcloud trend continuation — 20 examples
8. Strategy 4 — Qgrid add-to-winner — 20 examples

Minimum total before live confidence: 100+ logged examples.

## 3. Replay workflow

For each replay session:

1. Pick **Strategy 0 only** until it clears.
2. Pre-mark 4H and 15m levels BEFORE starting replay.
3. Pick one date and replay forward as if live.
4. Do not fast-forward through the decision point.
5. Score the trade using `02-confluence-system.md` before entry.
6. Record whether the trade would have been taken and why.
7. Record entry, stop, target, and result.
8. Screenshot the chart if useful.
9. Record any mistake or hesitation.

## 4. What to log

Use `templates/trade-journal.csv`.

Required fields:

- Date
- Time
- Setup name
- Direction
- Entry price
- Stop price
- Target
- Contracts
- Stop points
- Dollar risk
- Confluence score
- Result in R
- Rules followed
- Mistake
- Notes

## 5. Pass/fail criteria for a setup

A setup passes initial validation if:

- At least 20 replay examples logged.
- At least 20 sim/paper examples logged.
- At least 80% of entries followed rules.
- Average R is positive.
- Stop size is compatible with prop-firm risk per `10-prop-firm-risk-template.md`.
- You can identify the setup without hesitation.
- You know when NOT to take the setup.

A setup fails or needs more work if:

- You cannot identify it consistently.
- It requires stops too wide for MNQ/NQ risk.
- Most wins require perfect exits.
- It only works in hindsight.
- It triggers too often during chop.

## 6. Metrics to calculate

After every 20 examples, calculate:

```text
Total trades:
Wins:
Losses:
Break-even:
Win rate:
Average win R:
Average loss R:
Average R per trade:
Max losing streak:
Best time of day:
Worst time of day:
Best setup condition:
Worst setup condition:
```

Log these summary blocks at the bottom of your trade-journal.csv notes column or in a separate `11b-replay-results.md` file.

## 7. Time-of-day buckets

Classify each trade:

- Pre-market
- 8am setup window
- NY open first 15 minutes
- NY open first hour (9:30–10:30 ET)
- Power hour (14:00–15:15 ET)
- Midday/lunch (12:00–13:30 ET) — note if this is outside preferred session
- Overnight

## 8. Live progression

### Phase 1 — Replay only

- No real trades.
- Collect screenshots and journal rows.
- Build recognition of Strategy 0 ONLY.

### Phase 2 — Paper trading

- Use real-time data.
- Execute in paper or sim in Tradovate.
- Keep same journal process.
- Strategy 0 ONLY until pass criteria are met.

### Phase 3 — MNQ small size

- Use MNQ only.
- Trade only Strategy 0 (Level Test / Level Sweep).
- Max 1–2 trades per day.
- Stop after any rule break.

### Phase 4 — NQ evaluation mode

- Use NQ only for A/A+ Strategy 0 setups.
- MNQ remains default for uncertain conditions.
- Begin introducing Strategy 7 (15m OR retest) in sim simultaneously.
- Stop after any rule break.

## 9. Final rule

```text
A setup is not real until it is logged, reviewed, and repeatable.
Only one setup family is being validated at a time.
```
