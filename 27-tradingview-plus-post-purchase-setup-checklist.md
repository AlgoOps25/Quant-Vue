# 27 — TradingView Plus Post-Purchase Setup Checklist

The user has purchased TradingView Plus.

This checklist validates that TradingView Plus is sufficient before upgrading to Premium.

## Current decision

```text
Use TradingView Plus as the active platform.
Do not upgrade to Premium unless Plus fails a specific workflow requirement.
```

## Step 1 — Confirm plan and data

In TradingView:

```text
[ ] Confirm account shows TradingView Plus
[ ] Confirm CME Group data shows Subscribed
[ ] Open NQ1!
[ ] Confirm NQ1! does not say delayed
[ ] Open MNQ1!
[ ] Confirm MNQ1! does not say delayed
[ ] Confirm symbol source is CME / Globex futures, not CFD/synthetic NAS100
```

## Step 2 — Confirm QuantVue indicators

In TradingView Indicators search:

```text
[ ] QuantVue Q_Pro V2.0
[ ] QuantVue Q_Pilot Pro V1.0
[ ] QuantVue SMC V2.0
[ ] QuantVue Moneyball V2.0
[ ] QuantVue Momentum V2.0
[ ] QuantVue Qgrid
[ ] QuantVue Qbank_Pro V1.0
```

## Step 3 — Favorite Members Freebies scripts

From Members Freebies:

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

Only add freebies to the chart when required by a layout.

## Step 4 — Test Renko / second-based capability

Use NQ1!:

```text
[ ] 1-second candles selectable
[ ] Traditional Renko chart selectable
[ ] Traditional Renko box size 2 works
[ ] Traditional Renko box size 3 works
[ ] Traditional Renko box size 4 works
[ ] Traditional Renko box size 5 works
[ ] Chart updates in realtime
```

Fail condition:

```text
1-second Renko is blocked or unusable because of plan limits.
```

If this fails, investigate Premium.

## Step 5 — Open official/community layouts

Open and save copies:

```text
[ ] Banksy Manual Setup
[ ] Banksy Manual Layout
[ ] Alfredo Qpilot Manual Layout
```

Suggested saved names:

```text
NQ QuantVue Banksy Manual
MNQ Alfredo Qpilot Manual
NQ QuantVue Layout Testing
```

## Step 6 — Count layout limits

For each layout:

```text
[ ] Count number of charts
[ ] Count indicators per chart
[ ] Confirm no chart exceeds 10 indicators
[ ] Confirm total charts do not exceed 4
[ ] Confirm no missing invite-only indicators
[ ] Confirm no missing freebie indicators
[ ] Save layout successfully
```

Fail condition:

```text
A required chart needs more than 10 indicators and cannot be simplified.
A required layout needs more than 4 charts and cannot be simplified.
```

If this fails, investigate Premium.

## Step 7 — Confirm Bar Replay usefulness

Test one recent NQ session:

```text
[ ] Bar Replay opens
[ ] Replay works on 5m candles
[ ] Replay works on 15m candles
[ ] Replay is acceptable on Renko / execution chart
[ ] Replay depth is enough for recent validation
```

Premium only becomes relevant if replay depth is too shallow for the validation plan.

## Step 8 — Build temporary master layout

Keep it simple:

```text
Chart 1: 15m or 4H key levels / pivots
Chart 2: 5m SMC / structure / location
Chart 3: Renko execution with Qpro / Qwave / Qline / Moneyball
Chart 4: Optional Qpilot / Qgrid / MNQ execution / 3m OR
```

If cluttered, reduce to two charts:

```text
Chart 1: Context / levels
Chart 2: Renko execution
```

## Step 9 — Screenshot and report back

Capture screenshots of:

```text
[ ] NQ1! realtime confirmation
[ ] 1-second Renko working
[ ] Banksy layout loaded
[ ] Alfredo layout loaded
[ ] Indicator count if any chart is close to 10
```

## Decision checkpoint

Stay on TradingView Plus if:

```text
[ ] 1-second Renko works
[ ] Banksy layout loads
[ ] Alfredo layout loads
[ ] No required chart exceeds 10 indicators
[ ] 4 charts are enough
[ ] Replay depth is acceptable
```

Upgrade only if:

```text
[ ] 1-second Renko is blocked
[ ] Required layouts exceed Plus limits
[ ] Replay limitations block validation
[ ] Alert limits become a real issue later
```

## Current next action

The immediate next action is:

```text
Test NQ1! 1-second Traditional Renko box sizes 2, 3, 4, and 5.
```
