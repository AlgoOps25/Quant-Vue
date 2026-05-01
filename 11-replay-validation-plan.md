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

## 2. Required sample size

Collect at least 20 examples per setup before using it live.

Priority order:

1. 15-minute opening range retest — 20 examples
2. 3-minute opening range breakout/retest — 20 examples
3. 8am candle retest — 20 examples
4. Zone strategy — 20 examples
5. SMC liquidity sweep reversal — 20 examples
6. Qwave/Qbands reversal to midline — 20 examples
7. Qcloud trend continuation — 20 examples
8. Qgrid add-to-winner — 20 examples

Minimum total before live confidence: 100+ logged examples.

## 3. Replay workflow

For each replay session:

1. Pick one setup only.
2. Pick one date.
3. Replay as if live.
4. Do not fast-forward through the decision point.
5. Score the trade before entry.
6. Record whether it would have been taken.
7. Record entry, stop, target, and result.
8. Screenshot the chart if useful.
9. Record mistake or hesitation.

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

- At least 20 examples logged.
- At least 80% of entries followed rules.
- Average R is positive.
- Stop size is compatible with prop-firm risk.
- You can identify the setup without hesitation.
- You know when not to take it.

A setup fails or needs more work if:

- You cannot identify it consistently.
- It requires stops too wide for NQ.
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

## 7. Time-of-day buckets

Classify each trade:

- Pre-market
- 8am setup window
- NY open first 15 minutes
- NY open first hour
- Midday/lunch
- Power hour
- Overnight

## 8. Live progression

### Phase 1 — Replay only

- No real trades.
- Collect screenshots and journal rows.
- Build recognition.

### Phase 2 — Paper trading

- Use real-time data.
- Execute in paper or sim.
- Keep same journal process.

### Phase 3 — MNQ small size

- Use MNQ only.
- Trade only best setup family.
- Max 1–2 trades per day.

### Phase 4 — NQ evaluation mode

- Use NQ only for A/A+ setups.
- MNQ remains default for uncertain conditions.
- Stop after any rule break.

## 9. Final rule

```text
A setup is not real until it is logged, reviewed, and repeatable.
```
