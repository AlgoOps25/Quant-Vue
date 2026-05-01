# 16 — First QuantVue Replay Session Checklist

This is the first actionable validation checklist for the QuantVue-first system.

## Goal

Validate the first setup before live or prop-firm use:

```text
15-minute opening range retest
```

Do not test every setup at once. The first objective is to collect clean examples of one setup until the rules are obvious.

## Required TradingView layout

Use the layout from:

```text
14-final-quantvue-tradingview-layout.md
```

Minimum charts:

```text
Chart A: NQ1! 5m candles with SMC V2
Chart B: NQ1! Renko 4 with Qpro + Moneyball
Chart C: NQ1! 15m candles for opening range / FVG / zone context
```

Optional:

```text
Chart D: MNQ1! or 3m OR chart
```

## First setup to validate

### 15-minute Opening Range Retest

A valid long requires:

```text
1. First 15-minute opening range high is marked.
2. Price breaks above the 15m OR high.
3. Price retests the OR high as support.
4. 5m SMC does not strongly oppose the trade.
5. Qpro/Qcloud supports bullish direction.
6. Moneyball supports bullish momentum.
7. Stop can be placed below the retest / back inside the range.
8. Target has room before the next major resistance.
```

A valid short requires:

```text
1. First 15-minute opening range low is marked.
2. Price breaks below the 15m OR low.
3. Price retests the OR low as resistance.
4. 5m SMC does not strongly oppose the trade.
5. Qpro/Qcloud supports bearish direction.
6. Moneyball supports bearish momentum.
7. Stop can be placed above the retest / back inside the range.
8. Target has room before the next major support.
```

## Replay workflow

For each replay day:

```text
1. Choose one trading day.
2. Start replay before 9:30 AM New York time.
3. Mark prior day high/low.
4. Mark overnight high/low.
5. Let the first 15-minute opening range form.
6. Mark OR high and OR low.
7. Watch only for OR break and retest.
8. Ignore all non-OR setups.
9. Score the setup before entry.
10. Record the result in the trade journal.
```

## What to log

Use:

```text
templates/trade-journal.csv
```

Required columns to complete:

```text
date
time
market
setup_name
bias
long_or_short
entry_price
stop_price
target_1
target_2
contracts
stop_points
dollar_risk
confluence_score
smc_context
quantvue_trigger
location_reason
news_checked
result_r
rules_followed
mistake
notes
screenshot_link
```

## First 20-example target

Collect:

```text
20 examples of 15m OR retest
```

Classify each example as:

```text
Valid winner
Valid loser
Invalid / should skip
Missed winner
False alert
Too late
Too early
```

## Pass criteria

The 15m OR retest setup is allowed to move to paper trading only if:

```text
At least 20 examples are logged.
Rules were followed on at least 80% of examples.
Average R is positive or clearly improvable.
Stop size is realistic for MNQ/NQ prop-firm risk.
You can explain when not to take the setup.
```

## Fail criteria

Keep replaying or modify rules if:

```text
You cannot identify the retest consistently.
The stop is usually too wide.
The setup only looks obvious in hindsight.
It fires directly into opposing levels.
Moneyball/Qcloud are often late or contradictory.
You feel tempted to chase the first breakout candle.
```

## Do not trade live yet

This phase is replay/paper validation only.

No prop-firm execution until at least one setup has been validated with logged examples.

## Next setup after completion

After the 15m OR retest has 20 examples, move to:

```text
3-minute opening range breakout/retest
```