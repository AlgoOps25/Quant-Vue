# 14 — Final QuantVue TradingView Layout

This is the QuantVue-first layout for NQ1!/MNQ1! trading with manual execution through Tradovate.

## Purpose

The goal is to use QuantVue as the primary trading stack and use the repo as the operating manual.

The custom Layer 8 Pine indicator is paused as a research sandbox. The active trading workflow is QuantVue-first.

## Core rule

QuantVue indicators create **watch signals**, not automatic entries.

Every trade still needs:

```text
Location + Structure + Momentum + Trigger + Risk Plan
```

## Recommended saved TradingView layouts

Create these saved layouts in TradingView:

```text
NQ QuantVue Master Layout
NQ QuantVue Bias - 5m SMC
NQ QuantVue Execution - Renko 4
NQ QuantVue OR Context - 15m
NQ QuantVue Replay Testing
```

## Layout 1 — NQ QuantVue Master Layout

Use this as the main screen during live prep and replay.

### Suggested chart grid

Use a 3-chart or 4-chart grid if your TradingView plan supports it.

```text
Top left: 5m SMC bias chart
Top right: Renko 4 execution chart
Bottom left: 15m opening range / FVG context chart
Bottom right: Optional 3m OR or MNQ execution chart
```

If limited to two charts:

```text
Left: 5m SMC bias chart
Right: Renko 4 execution chart
```

## Chart A — 5m SMC Bias Chart

Purpose:

- Decide directional bias.
- Mark structure.
- Identify liquidity sweeps.
- Identify BOS/CHoCH.
- Identify order blocks and major zones.
- Prevent trades in bad locations.

Settings:

```text
Symbol: NQ1! or MNQ1!
Timeframe: 5-minute candles
Indicator: QuantVue SMC V2
```

Use this chart for:

- Prior high/low context
- Liquidity grabs
- BOS / CHoCH
- Manual structure period 20
- Order blocks
- Previous daily/weekly/monthly/yearly highs/lows
- Session boxes if helpful

Do not use this chart for:

- Every execution click
- Chasing raw signals
- Overloading with every possible visual

## Chart B — Renko 4 Execution Chart

Purpose:

- Entry timing.
- Exit timing.
- Qline/Qcloud/Qwave interaction.
- Moneyball confirmation.
- Qgrid add-to-winner only.

Settings:

```text
Symbol: NQ1! or MNQ1!
Chart source: 1-second if available
Chart type: Traditional Renko
Box size: 4
Indicators:
- QuantVue Qpro V2
- QuantVue Moneyball V2
- QuantVue Qgrid only when using add-to-winner logic
```

Primary use:

- Wait for price to arrive at a real level.
- Use Qpro/Qcloud for trend state.
- Use Qwave/Qbands for location and target context.
- Use Qline as a trigger/exit confirmation.
- Use Moneyball for momentum confirmation.
- Use Qgrid only after a trade is already working.

## Chart C — 15m Opening Range / FVG Context Chart

Purpose:

- Track 15-minute opening range.
- Track higher-timeframe zones.
- Track fair value gaps if used.
- Avoid trading directly into major opposing areas.

Settings:

```text
Symbol: NQ1!
Timeframe: 15-minute candles
Indicators:
- SMC V2 or minimal FVG/order-block context
- Opening range high/low manually or with available OR tool
```

Use this chart for:

- 15m OR high/low
- 15m OR retests
- Higher-timeframe target areas
- FVG/zone obstacles

## Chart D — Optional 3m Opening Range Chart

Purpose:

- Watch the first 3-minute opening range breakout/retest.
- Compare faster OR behavior against 5m/15m context.

Settings:

```text
Symbol: NQ1! or MNQ1!
Timeframe: 3-minute candles
Indicators:
- Qpro if clean
- Moneyball if helpful
- OR high/low manually marked
```

Use this only if it does not distract from the main 5m/15m/Renko workflow.

## Final QuantVue indicator stack

### Required

```text
QuantVue Qpro V2
QuantVue SMC V2
QuantVue Moneyball V2
```

### Conditional

```text
QuantVue Qgrid — only for add-to-winner logic
Qpilot/Qbank/Iceberg — optional, not required for the first validation cycle
```

## Settings already captured

Refer to:

```text
01-tradingview-setup.md
```

Confirmed captured settings include:

- Qpro/Qcloud
- Qbands
- Qwave
- Qline
- Moneyball
- SMC V2
- Qgrid

## Primary setups to validate first

Test these in this exact order:

```text
1. 15-minute opening range retest
2. 3-minute opening range breakout/retest
3. 8am candle retest
4. Zone strategy
5. SMC liquidity sweep reversal
6. Qwave/Qbands reversal to midline
7. Qcloud trend continuation
8. Qgrid add-to-winner only
```

## Default live-prep workflow

Before taking any trade:

1. Check economic news.
2. Mark prior day high/low.
3. Mark overnight high/low.
4. Mark 8am candle zone if using it.
5. Mark 15m opening range after market open.
6. Check 5m SMC bias.
7. Check Renko 4 execution chart.
8. Confirm Moneyball momentum.
9. Confirm stop and target.
10. Execute manually in Tradovate only if the setup passes the decision tree.

## What not to do

Do not:

- Trade every QuantVue alert.
- Trade every Qcloud flip.
- Add with Qgrid unless the original trade is already profitable.
- Trade directly into a major opposing level.
- Trade below 7/10 confluence.
- Use the custom Layer 8 Pine indicator as the primary decision tool yet.

## Immediate next step

Build the `NQ QuantVue Master Layout` in TradingView and save it.

Then begin replay validation using:

```text
11-replay-validation-plan.md
templates/trade-journal.csv
```