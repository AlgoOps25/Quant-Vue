# 30 — Premium Setup and Layout Validation

This is the immediate checklist after upgrading to TradingView Premium.

## Current decision

```text
TradingView Premium is justified because TradingView Plus blocked the official QuantVue shared layouts that depend on seconds-based charts and volume candles.
```

## Platform stack

```text
TradingView Premium
CME Group real-time futures data
QuantVue Pro
Tradovate manual execution
```

## Step 1 — Confirm Premium and data

In TradingView:

```text
[ ] Account shows TradingView Premium
[ ] CME Group data shows Subscribed
[ ] NQ1! opens without delayed-data warning
[ ] MNQ1! opens without delayed-data warning
[ ] Symbol source is CME_MINI, not CFD/synthetic NAS100
```

NQ link:

```text
https://www.tradingview.com/chart/?symbol=CME_MINI%3ANQ1%21
```

MNQ link:

```text
https://www.tradingview.com/chart/?symbol=CME_MINI%3AMNQ1%21
```

## Step 2 — Favorite required public/freebie indicators

From `Members Freebies.txt`, favorite/save these first:

```text
[ ] Oracle's Ultimate Reversals
[ ] Oracle's Squeeze Relaxer
[ ] Oracle's Total Recall
[ ] Oracle's 15m Opening Range
[ ] QuantVue Gamma Display
[ ] tiTRADINGwiz Extra Order Blocks
[ ] tiTRADINGwiz Gap Fills
[ ] tiTRADINGwiz Highlight Zones
[ ] Renko Box Time Tester
[ ] Master MACD
[ ] GEX Export
```

Do not add all of them manually to every chart. Only make sure TradingView can load them when a shared layout uses them.

## Step 3 — Confirm invite-only QuantVue indicators

In TradingView Indicators search, confirm these exist:

```text
[ ] QuantVue Q_Pro V2.0
[ ] QuantVue Q_Pilot Pro V1.0
[ ] QuantVue SMC V2.0
[ ] QuantVue Moneyball V2.0
[ ] QuantVue Momentum V2.0
[ ] QuantVue Qgrid
[ ] QuantVue Qbank_Pro V1.0
```

## Step 4 — Validate official/community layouts

Open each layout and save a clean copy.

### Banksy Manual Setup

```text
https://www.tradingview.com/chart/dkdjQAG2/
```

Save as:

```text
NQ QuantVue Banksy Manual Setup
```

### Banksy Manual Layout

```text
https://www.tradingview.com/chart/1pa0fuKD/
```

Save as:

```text
NQ QuantVue Banksy Manual Layout
```

### Alfredo Qpilot Manual Layout

```text
https://www.tradingview.com/chart/mRs5MUmS/
```

Save as:

```text
MNQ Alfredo Qpilot Manual
```

### Qgrid Renko Layout

```text
https://www.tradingview.com/chart/BMOg7VKi/
```

Save as:

```text
NQ Qgrid Renko Layout
```

### Broad Alerts Setup

```text
https://www.tradingview.com/chart/5cH27iNG/
```

Save as:

```text
NQ Broad Alerts Setup
```

### Broad Band NQ Setup

```text
https://www.tradingview.com/chart/ckaU8m5y/
```

Save as:

```text
NQ Broad Band Setup
```

### Tight Band NQ Setup

```text
https://www.tradingview.com/chart/ayo7hEU5/
```

Save as:

```text
NQ Tight Band Setup
```

## Step 5 — Audit each layout

For each saved layout, record:

```text
Layout name:
Loads successfully? Y/N
Missing indicators? Y/N
Charts in layout:
Indicators per chart:
Uses seconds? Y/N
Uses volume candles? Y/N
Renko box size:
Main setup style:
Readable? Y/N
Keep / simplify / ignore:
Notes:
```

## Step 6 — Choose the first two layouts to study

Priority order:

```text
1. Banksy Manual Setup / Layout
2. Alfredo Qpilot Manual Layout
```

Why:

```text
Banksy = more rule-based Renko execution
Alfredo = discretionary confluence and Qpilot workflow
```

## Step 7 — Build the clean master layout

After reviewing Banksy and Alfredo, build one personal layout:

```text
NQ QuantVue Master Layout
```

Starting structure:

```text
Chart 1: 4H or 15m key levels / pivots
Chart 2: 5m SMC / structure / location
Chart 3: 1-second Traditional Renko execution with Qpro / Qwave / Qline / Moneyball
Chart 4: Qpilot or Qgrid / MNQ practice / 3m OR
```

Clean-chart rule:

```text
If it does not directly help location, structure, trigger, exit, or risk, remove it.
```

## Step 8 — First validation setup

Because the Core Prop Training emphasizes location first, validate:

```text
Level Test / Level Sweep at a key 4H or 15m level
```

Before validating opening range or Qgrid.

## Step 9 — Replay/paper requirement

Do not trade live until:

```text
[ ] 20 replay examples of first setup are logged
[ ] 20 paper/sim examples of first setup are logged
[ ] Rules are followed at least 80% of the time
[ ] Average R is positive or clearly improvable
[ ] Stop size fits prop-firm risk
[ ] You can explain when not to take the setup
```

## Step 10 — Screenshots to send back for review

Send screenshots of:

```text
[ ] Banksy layout loaded
[ ] Alfredo layout loaded
[ ] Your first attempt at NQ QuantVue Master Layout
[ ] One marked Level Test example
[ ] One marked Level Sweep example
```

## Current next action

```text
Upgrade to Premium, then load Banksy Manual Setup first.
```
