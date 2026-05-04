# 17 — TradingView Layout Build Checklist

Use this checklist while building the final QuantVue-first TradingView layout.

## Goal

Create and save the core layout:

```text
NQ QuantVue Master Layout
```

## Step 1 — Create the chart grid

Preferred 4-chart layout:

```text
Top Left: 5m SMC Bias
Top Right: Renko 4 Execution
Bottom Left: 15m OR / FVG Context
Bottom Right: Optional 3m OR or MNQ Execution
```

If only using 2 charts:

```text
Left: 5m SMC Bias
Right: Renko 4 Execution
```

## Step 2 — Chart A: 5m SMC Bias

Settings:

```text
Symbol: NQ1!
Timeframe: 5-minute candles
Indicator: QuantVue SMC V2
```

Enable / verify:

```text
Manual structure period: 20
Liquidity grabs: ON
BOS / CHoCH: ON
Prior highs/lows: ON
Daily/Weekly/Monthly/Yearly: ON if clean
High color: White
Low color: Gray
FVG: OFF on main bias chart unless needed
Session box: optional
```

Purpose:

```text
Bias
Structure
Liquidity
Major zones
Do-not-trade areas
```

## Step 3 — Chart B: Renko 4 Execution

Settings:

```text
Symbol: NQ1! or MNQ1!
Source chart: 1-second if available
Chart type: Traditional Renko
Box size: 4
Indicators:
- QuantVue Qpro V2
- QuantVue Moneyball V2
- QuantVue Qgrid only when practicing add-to-winner
```

Qpro captured baseline:

```text
Qcloud periods: 19 / 29 / 49 / 59 / 69 / 99
Qbands source: Weighted
Qbands length: 40
Qbands lookback: 256
Qbands deviation: 5
Qbands trend period: 10
Qwave source: Weighted
Qwave APB bars back: 33
Qwave ATR bars back: 256
Qwave band deviation: 5.5
Qline source: close
Qline length: 6
Qline multiplier: 0.1
Qline reactivity: 0.4
```

Moneyball captured baseline:

```text
Bars between signals: 15
Mode: M
Period: 4
All Zero: ON
Upper threshold: 0.4
Lower threshold: -0.4
Reactivity: 0.1
```

Purpose:

```text
Entry timing
Exit timing
Momentum confirmation
Qline/Qwave/Qcloud interaction
```

## Step 4 — Chart C: 15m OR / FVG Context

Settings:

```text
Symbol: NQ1!
Timeframe: 15-minute candles
Indicators:
- Minimal SMC V2 or FVG/order-block context
- Manual 15m opening range high/low
```

Purpose:

```text
Opening range high/low
Retest levels
Higher-timeframe obstacles
Targets
FVG / order block context
```

## Step 5 — Chart D: Optional 3m OR or MNQ

Option A:

```text
Symbol: NQ1!
Timeframe: 3-minute candles
Purpose: 3m opening range breakout/retest
```

Option B:

```text
Symbol: MNQ1!
Same execution layout as NQ
Purpose: lower-risk practice / MNQ execution
```

## Step 6 — Save the layout

Save as:

```text
NQ QuantVue Master Layout
```

Then duplicate if desired:

```text
NQ QuantVue Replay Testing
NQ QuantVue Live Prep
MNQ QuantVue Practice
```

## Step 7 — Clean-chart rule

If the chart looks confusing, remove indicators.

Minimum viable setup:

```text
5m SMC Bias
Renko 4 Qpro
Moneyball
15m OR Context
```

Do not add Qpilot/Qbank/Iceberg until the core workflow is validated.

## Step 8 — Ready for replay

The layout is complete when:

```text
You can identify the 15m OR high/low.
You can see 5m SMC bias clearly.
You can see Renko Qpro/Qline/Qcloud clearly.
You can see Moneyball clearly.
You know where stop and target would go.
The layout does not require you to guess what matters.
```

Next file:

```text
16-first-replay-session-checklist.md
```