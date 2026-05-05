# 42 — Step-by-Step QuantVue Setup Buildout Instructions

This document gives fully detailed instructions for creating clean, distinguishable TradingView layouts for each QuantVue setup.

## Goal

Build a controlled set of TradingView layouts so every setup can be tested without confusion.

The rule is:

```text
Original layouts stay untouched.
Test layouts are clearly named.
Only one major setting changes at a time.
```

## Master naming convention

Use this layout name format:

```text
QV-[Market]-[Setup]-[ChartType]-[KeySetting]-[Status]
```

Examples:

```text
QV-NQ-Banksy-Original-R10-LOCKED
QV-NQ-Banksy-Test-R5
QV-NQ-Banksy-Test-R4
QV-MNQ-Alfredo-Original-R5-LOCKED
QV-MNQ-Alfredo-Test-R4
QV-NQ-Qgrid-AddWinner-R4
QV-NQ-OR3-QPro-MB2
QV-NQ-OR15-QPro-MB4
QV-NQ-BroadBand-WatchOnly
QV-NQ-TightBand-WatchOnly
```

## Layout status labels

Use these suffixes:

```text
LOCKED = original reference layout; do not edit
TEST = actively testing one variable
KEEP = validated enough to continue
DROP = too noisy or not useful
WATCH = alert/watchlist only
```

---

# Phase 0 — Preserve original layouts

Before tuning anything, create locked copies of the current shared layouts.

## Original locked layouts

Save or rename the shared layouts as:

```text
QV-NQ-Banksy-Original-R10-LOCKED
QV-NQ-BanksyManual-Original-LOCKED
QV-MNQ-Alfredo-Original-R5-LOCKED
QV-NQ-Qgrid-Original-LOCKED
QV-NQ-BroadAlerts-Original-LOCKED
QV-NQ-BroadBand-Original-LOCKED
QV-NQ-TightBand-Original-LOCKED
```

## Rule

```text
Never tune a LOCKED layout.
Only duplicate it, rename the duplicate, and tune the duplicate.
```

---

# Setup 1 — Banksy Level Test / Level Sweep

## Purpose

Banksy is the first setup to test because it is cleaner and more rule-based than Alfredo.

Use it for:

```text
Level Test
Level Sweep
Structure-driven reversals
Qbank/Q_Pro confirmation
Renko execution behavior
```

## Original reference layout

Use:

```text
QV-NQ-Banksy-Original-R10-LOCKED
```

Observed structure:

```text
Main chart: NQ1! / 1-second / Traditional Renko 10
Context chart: NQ1! / 15-minute
Lower chart: NQ1! / 2-minute
```

## Build Test Layout 1A — Banksy Renko 10 baseline

### Layout name

```text
QV-NQ-Banksy-LevelTestSweep-R10-TEST
```

### Steps

1. Open:

```text
QV-NQ-Banksy-Original-R10-LOCKED
```

2. Save a duplicate as:

```text
QV-NQ-Banksy-LevelTestSweep-R10-TEST
```

3. Confirm all charts use:

```text
NQ1!
```

or, if practicing micro behavior:

```text
MNQ1!
```

4. Do not change indicators.
5. Do not change Qbank/Q_Pro settings.
6. Do not enable alerts.
7. Use this layout to collect the first 20 observations.

### What to observe

For every candidate, log:

```text
Level Test or Level Sweep?
Was the level obvious before price reached it?
Did SMC/BOS/CHoCH support the setup?
Did Q_Pro/Qbank confirm after the reaction?
Was entry early, late, or clean?
Was the stop too wide?
Did Renko 10 reduce noise or make entry too late?
```

## Build Test Layout 1B — Banksy Renko 5

Only create this after 20 Renko 10 observations.

### Layout name

```text
QV-NQ-Banksy-LevelTestSweep-R5-TEST
```

### Steps

1. Open:

```text
QV-NQ-Banksy-LevelTestSweep-R10-TEST
```

2. Save a duplicate as:

```text
QV-NQ-Banksy-LevelTestSweep-R5-TEST
```

3. On the main execution chart, open chart settings.
4. Go to Renko settings.
5. Change:

```text
Traditional Renko box size: 5
```

6. Leave every QuantVue indicator setting unchanged.
7. Collect 20 observations.

### Compare against R10

```text
Did R5 enter earlier?
Did R5 create more false signals?
Was stop size smaller?
Was it harder to execute manually?
Was there more chop?
```

## Build Test Layout 1C — Banksy Renko 4

Only create after R10 and R5 have initial samples.

### Layout name

```text
QV-NQ-Banksy-LevelTestSweep-R4-TEST
```

### Steps

1. Duplicate:

```text
QV-NQ-Banksy-LevelTestSweep-R5-TEST
```

2. Rename duplicate:

```text
QV-NQ-Banksy-LevelTestSweep-R4-TEST
```

3. Change only the execution chart:

```text
Traditional Renko box size: 4
```

4. Leave everything else unchanged.

### R4 warning

Renko 4 may feel better because it is faster, but it can also create more false turns. Do not prefer it unless the journal proves it improves clarity and R.

---

# Setup 2 — Alfredo Qpilot Level Reaction / Re-entry

## Purpose

Alfredo is the second setup to test. It is more discretionary and signal-heavy.

Use it for:

```text
Qpilot Buy/Sell labels
Re-entry Long / Re-entry Short
TP labels
Volume Peak / Volume Bottom
Volume-candle confluence
Discretionary confirmation after a level reaction
```

## Original reference layout

Use:

```text
QV-MNQ-Alfredo-Original-R5-LOCKED
```

Observed structure:

```text
Top-left: MNQ1! / 1-minute
Top-middle: NQ1! / 5-minute
Top-right: NQ1! / 15-minute
Bottom: NQ1! / 1-second / Traditional Renko 5
```

## Build Test Layout 2A — Alfredo Original R5

### Layout name

```text
QV-MNQ-Alfredo-Qpilot-Reentry-R5-TEST
```

### Steps

1. Open:

```text
QV-MNQ-Alfredo-Original-R5-LOCKED
```

2. Save duplicate as:

```text
QV-MNQ-Alfredo-Qpilot-Reentry-R5-TEST
```

3. Keep original chart structure.
4. Do not tune Qpilot settings yet.
5. Do not enable alerts.
6. Observe only signals that occur at or after a real level reaction.

### What to log

For each Qpilot signal:

```text
Was signal at a marked level?
Was it after a sweep/test?
Was Buy/Sell early, late, or useful?
Was Re-entry Long/Short useful or too late?
Did TP help exit?
Did Volume Peak/Bottom warn of exhaustion?
Did the layout reduce or increase hesitation?
```

## Build Test Layout 2B — Alfredo R4 Test

Only create this after R5 is understood.

### Layout name

```text
QV-MNQ-Alfredo-Qpilot-Reentry-R4-TEST
```

### Steps

1. Duplicate:

```text
QV-MNQ-Alfredo-Qpilot-Reentry-R5-TEST
```

2. Rename:

```text
QV-MNQ-Alfredo-Qpilot-Reentry-R4-TEST
```

3. Change only the bottom execution chart:

```text
Traditional Renko box size: 4
```

4. Leave Qpilot settings unchanged.

### Compare R5 vs R4

```text
Did R4 create better early entries?
Did R4 increase noise?
Did Qpilot labels become too frequent?
Did TP labels still make sense?
```

---

# Setup 3 — Q_Pro / Qwave / Qline Reversal to Midline

## Purpose

This setup tests Q_Pro as an execution confluence package after price reaches an outer band or meaningful level.

Use it for:

```text
Qwave lower/upper band reactions
Qline flip confirmation
Moneyball momentum confirmation
Midline targets
SMC sweep/reclaim context
```

## Layout to create

### Layout name

```text
QV-NQ-QPro-QwaveReversal-R4-TEST
```

## Build steps

1. Start from a clean NQ chart or duplicate a simple Q_Pro layout.
2. Set symbol:

```text
NQ1!
```

3. Set chart:

```text
1-second Traditional Renko 4
```

4. Add/confirm:

```text
QuantVue Q_Pro V2.0
QuantVue Moneyball V2.0
Optional SMC V2 on separate 5m chart
```

5. Qcloud settings:

```text
Use Qcloud: ON
Source: close
Periods: 19 / 29 / 49 / 59 / 69 / 99
Bull/Bear labels: OFF
```

6. Qwave settings:

```text
Use Qwave: ON
Price: Weighted
APB Bars Back: 33
ATR Bars Back: 256
Band Deviation: 5.5
ADD Alerts: OFF
```

7. Qline settings:

```text
Use Qline: ON
Source: close
Length: 6
Multiplier: 0.1
Reactivity: 0.4
```

8. Moneyball settings:

```text
Bars Between Signals: 15
Mode: M
Period: 4
All Zero: ON
Upper Threshold: 0.4
Lower Threshold: -0.4
Reactivity: 0.1
```

## Valid long setup

```text
Price reaches lower Qwave/Qbands area or marked support
SMC shows sweep/reclaim or bullish structure shift
Qline flips/supports upward after level reaction
Moneyball confirms bullish momentum
Target to Qwave/Qbands midline gives acceptable R
```

## Valid short setup

```text
Price reaches upper Qwave/Qbands area or marked resistance
SMC shows sweep/reject or bearish structure shift
Qline flips/rejects downward after level reaction
Moneyball confirms bearish momentum
Target to Qwave/Qbands midline gives acceptable R
```

## Do not take

```text
Band touch without level context
Qline flip in the middle of nowhere
Moneyball signal directly into opposing level
Entry where midline target gives poor R
```

---

# Setup 4 — 3-Minute Opening Range Breakout / Retest

## Purpose

This tests the 3-minute opening range strategy from the strategy series.

Use it for:

```text
Opening drive continuation
Breakout/retest of first 3-minute range
Qcloud/Qpro direction confirmation
Moneyball_Q momentum confirmation
```

## Layout to create

### Layout name

```text
QV-NQ-OR3-QPro-MB2-TEST
```

## Build steps

1. Create a new layout or duplicate a clean Q_Pro layout.
2. Use a 3-chart layout:

```text
Chart 1: NQ1! / 3-minute candles — OR range
Chart 2: NQ1! / 5-minute SMC — structure/context
Chart 3: NQ1! / Renko or 1-minute — execution confirmation
```

3. On the 3-minute chart, mark first 3-minute candle/range after market open.

4. Qcloud settings:

```text
Periods: 19 / 29 / 49 / 59 / 69 / 99
```

5. Moneyball_Q settings:

```text
Bars Between Signals: 15
Mode: M
Period: 2
All Zero: ON
Upper Threshold: 0.35
Lower Threshold: -0.35
Reactivity: 0.1
```

6. OR-specific Qline settings:

```text
Qline Length: 9
Multiplier: 0.1
Common Period: 39
Reactivity: 0.4
Ribbon: ON only if helpful
```

7. OR-specific Qwave/Qbands context:

```text
Qwave APB: 33
Qwave ATR: 256
Qwave Deviation: 1.5
Qbands Length: 77 or 155
Qbands Deviation: 5 or 6.8
Qbands Trend Period: 20
```

## Valid long OR setup

```text
First 3-minute opening range is defined
Price breaks above OR high
Breakout is not already overextended
Price retests OR high as support or holds above cleanly
Qcloud/Qpro bullish
Moneyball_Q supports long momentum
Target is not directly into major resistance
```

## Valid short OR setup

```text
First 3-minute opening range is defined
Price breaks below OR low
Breakout is not already overextended
Price retests OR low as resistance or holds below cleanly
Qcloud/Qpro bearish
Moneyball_Q supports short momentum
Target is not directly into major support
```

## Do not take

```text
Trade before OR is defined
Huge breakout candle with no retest and poor stop
Fakeout without close/retest confirmation
Breakout directly into prior day/overnight level
News candle
```

---

# Setup 5 — 15-Minute Opening Range Retest

## Purpose

This setup uses the first 15 minutes of RTH as a major directional framework.

## Layout to create

### Layout name

```text
QV-NQ-OR15-QPro-Retest-TEST
```

## Build steps

1. Create a 4-chart layout:

```text
Chart 1: NQ1! / 15-minute candles — OR high/low and context
Chart 2: NQ1! / 5-minute SMC — structure
Chart 3: NQ1! / 1-second Traditional Renko 4 or 5 — execution
Chart 4: NQ1! / 1-minute or 2-minute candles — extra timing
```

2. Mark:

```text
First 15-minute opening range high
First 15-minute opening range low
Prior day high/low
Overnight high/low
Major 15m swing high/low
```

3. Use Q_Pro/Qcloud and Moneyball confirmation.
4. Do not change Q_Pro baseline settings unless the OR-specific test requires it.

## Valid long setup

```text
15m OR high is broken
Price retests OR high as support
5m SMC supports bullish structure
Renko/Q_Pro supports continuation
Moneyball confirms momentum
There is room to next level
```

## Valid short setup

```text
15m OR low is broken
Price retests OR low as resistance
5m SMC supports bearish structure
Renko/Q_Pro supports continuation
Moneyball confirms momentum
There is room to next level
```

## Do not take

```text
No clean OR high/low
Price chops inside range
Retest happens directly into opposing level
Stop is too wide
Move is already exhausted
```

---

# Setup 6 — Qcloud / Qline Trend Continuation

## Purpose

This setup is for trend days and continuation pullbacks.

## Layout to create

### Layout name

```text
QV-NQ-Qcloud-Qline-TrendContinuation-TEST
```

## Build steps

1. Use 3 charts:

```text
Chart 1: NQ1! / 15m — trend and major levels
Chart 2: NQ1! / 5m SMC — BOS/CHoCH/order blocks
Chart 3: NQ1! / 1s Traditional Renko 4 or 5 — execution
```

2. Qcloud baseline:

```text
19 / 29 / 49 / 59 / 69 / 99
```

3. Qline baseline:

```text
Length 6
Multiplier 0.1
Reactivity 0.4
```

4. Moneyball:

```text
Period 4 for scalping confirmation
Period 8–20 if testing broader trend bias
```

## Valid long continuation

```text
15m/5m structure bullish
Qcloud bullish or flips bullish
Pullback holds Qline/Qcloud/order block
Moneyball remains bullish or re-confirms
Stop below pullback structure
Target to prior high/Qwave band/measured move
```

## Valid short continuation

```text
15m/5m structure bearish
Qcloud bearish or flips bearish
Pullback rejects Qline/Qcloud/order block
Moneyball remains bearish or re-confirms
Stop above pullback structure
Target to prior low/Qwave band/measured move
```

---

# Setup 7 — Qgrid Add-to-Winner

## Purpose

Qgrid is not an initial entry system. It is an add-to-winner tool.

## Layout to create

### Layout name

```text
QV-NQ-Qgrid-AddWinner-R4-WATCH
```

## Build steps

1. Open:

```text
QV-NQ-Qgrid-Original-LOCKED
```

2. Duplicate as:

```text
QV-NQ-Qgrid-AddWinner-R4-WATCH
```

3. Use this only after a trade is already profitable.
4. Do not enable automatic adds.
5. Do not use Qgrid to average down.

## Valid long add

```text
Original long is profitable
Price remains above or reclaims Qgrid step moving average
Pullback is shallow and controlled
Qgrid Bull / cyan dot appears
Stop can sit below pullback/structure
Add does not violate daily risk
```

## Valid short add

```text
Original short is profitable
Price remains below or rejects Qgrid step moving average
Pullback is shallow and controlled
Qgrid Bear / blue dot appears
Stop can sit above pullback/structure
Add does not violate daily risk
```

## Hard rule

```text
If original trade is red, do not add.
```

---

# Setup 8 — Broad Band / Tight Band / Broad Alerts

## Purpose

These are watchlist/alert systems, not primary entry systems yet.

## Layout names

```text
QV-NQ-BroadBand-WatchOnly
QV-NQ-TightBand-WatchOnly
QV-NQ-BroadAlerts-WatchOnly
```

## Build steps

1. Duplicate original layouts.
2. Rename with WatchOnly suffix.
3. Do not enable all alerts.
4. Observe signal frequency first.

## Test Broad Band first

Use Broad Band first because it should produce fewer signals.

Log:

```text
How many signals per session?
How many occurred at meaningful levels?
How many were late?
How many were useful watch pings?
```

## Test Tight Band second

Use only if Broad Band is too slow or too sparse.

Expected issue:

```text
More signals, more noise
```

## Test Broad Alerts last

Only activate selected alert types after you know which setups matter.

First allowed alerts:

```text
Level touch / sweep watch
15m OR retest watch
Qline/Qtrend flip at level
Moneyball confirmation at level
Qgrid add-to-winner only
```

---

# Testing order summary

Do not test all layouts at once.

## Round 1

```text
QV-NQ-Banksy-LevelTestSweep-R10-TEST
20 observations
```

## Round 2

```text
QV-NQ-Banksy-LevelTestSweep-R5-TEST
20 observations
```

## Round 3

```text
QV-MNQ-Alfredo-Qpilot-Reentry-R5-TEST
20 observations
```

## Round 4

```text
QV-NQ-QPro-QwaveReversal-R4-TEST
20 observations
```

## Round 5

```text
QV-NQ-OR15-QPro-Retest-TEST
20 observations
```

## Round 6

```text
QV-NQ-OR3-QPro-MB2-TEST
20 observations
```

## Round 7

```text
QV-NQ-Qgrid-AddWinner-R4-WATCH
Observation only after initial entry is profitable
```

## Round 8

```text
QV-NQ-BroadBand-WatchOnly
QV-NQ-TightBand-WatchOnly
QV-NQ-BroadAlerts-WatchOnly
```

---

# Journal requirements per observation

Every observation must include:

```text
Date:
Time:
Layout name:
Setup name:
Symbol:
Chart type / Renko size:
Level involved:
Long or short:
Entry idea:
Stop idea:
Target idea:
QuantVue confirmations:
Did signal occur before/after level reaction?
Would this be executable manually? Y/N
Result: winner / loser / skip / missed / invalid
Estimated R:
Mistake or issue:
Screenshot filename:
Decision: Keep / Refine / Drop / Watch only
```

---

# Rule for changing settings

Only change one variable at a time.

Allowed first changes:

```text
Renko 10 → 5 → 4
Moneyball period 4 → 2 only for OR strategy
Qline length 6 → 9 only for OR strategy
Qwave deviation 5.5 → 1.5 only for OR strategy
Qbands length 40 → 77/155 only for OR/broad context
```

Forbidden:

```text
Changing Renko, Moneyball, Qline, Qwave, and Qbands all at once
Changing a layout after only one trade
Judging accuracy from one screenshot
Using Qgrid to add to losers
Turning on all Broad Alerts immediately
```

---

# What to build first now

Start here:

```text
1. Duplicate QV-NQ-Banksy-Original-R10-LOCKED
2. Rename duplicate QV-NQ-Banksy-LevelTestSweep-R10-TEST
3. Do not change settings
4. Observe 20 Level Test / Level Sweep candidates
5. Then duplicate to QV-NQ-Banksy-LevelTestSweep-R5-TEST
```

This gives us a clean, distinguishable testing path without wasting the paid QuantVue layouts.
