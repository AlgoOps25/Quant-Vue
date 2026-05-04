# 36 — TradingView Bar Replay Beginner Guide

This guide walks through the first replay session for a new TradingView Bar Replay user.

## Goal

Use Bar Replay to practice the Banksy layout without risking money.

First setup to practice:

```text
Level Test / Level Sweep at a marked 15m or 4H level
```

## Important rule

```text
Do not trade live from replay practice.
Do not enable alerts yet.
Do not take every signal.
```

## Step 1 — Open the correct layout

Open your saved layout:

```text
NQ QuantVue Banksy Manual Setup - Working Copy
```

Confirm the layout has:

```text
Main chart: NQ1! 1-second Renko execution chart
Top-right chart: NQ1! 15-minute context chart
Bottom-right chart: NQ1! 2-minute context chart
```

## Step 2 — Pick a replay day

Pick one normal recent trading day.

Avoid:

```text
FOMC
CPI
PPI
NFP
major Fed speeches
half-days / holidays
```

Start with the New York regular session:

```text
9:30 AM — 4:00 PM Eastern
```

## Step 3 — Mark levels before pressing play

On the 15-minute chart, mark:

```text
Prior day high
Prior day low
Overnight high
Overnight low
Obvious 15-minute swing high
Obvious 15-minute swing low
```

Use horizontal lines.

Suggested colors:

```text
Prior day high/low: white or gray
Overnight high/low: yellow or orange
15m swing levels: blue or green
```

## Step 4 — Open Bar Replay

In TradingView top toolbar:

```text
Click Replay
```

or:

```text
Click the Bar Replay icon near the top toolbar
```

It looks like a rewind/playback icon.

## Step 5 — Choose the replay start point

After clicking Replay, TradingView will show a vertical line/cursor.

Move the cursor to a time before the New York open.

Recommended start:

```text
9:15 AM Eastern
```

Then click the chart at that point.

## Step 6 — Start replay slowly

Use the replay controls at the bottom/top of the chart.

Start with:

```text
Speed: slow
```

Recommended:

```text
Use step-forward one candle/bar at a time at first.
```

Do not use fast replay yet.

## Step 7 — Wait for location

Do not enter just because a signal appears.

Wait for price to reach one of your marked levels.

Valid location examples:

```text
Prior day high/low
Overnight high/low
15m swing high/low
Major pivot/level from the layout
```

## Step 8 — Identify Level Test or Level Sweep

### Level Test

A Level Test means:

```text
Price reaches a level
Price reacts at the level
The level holds
Price confirms away from the level
```

### Level Sweep

A Level Sweep means:

```text
Price pushes through the level
Liquidity is taken
Price rejects back through the level
Confirmation appears after the reclaim/rejection
```

## Step 9 — Only then look for QuantVue confirmation

Examples of confirmation:

```text
BOS / CHoCH in trade direction
Bull/Bear label after reaction
Q_Pro / Qbank color shift
Swing high/low reaction
Renko reversal after level reaction
```

Do not require everything. Log what appears.

## Step 10 — Define trade before entry

Before simulating an entry, write down:

```text
Direction:
Entry price:
Stop price:
Target:
Why this level matters:
Confirmation seen:
```

If you cannot define a stop, skip the trade.

## Step 11 — Manage the replay trade

For long:

```text
Stop below the tested/swept low
```

For short:

```text
Stop above the tested/swept high
```

Target options:

```text
Next marked level
Opposite structure/band
1R minimum
Opposite QuantVue shift
```

## Step 12 — Take screenshots

Capture three screenshots if possible:

```text
Before entry
After confirmation/entry
After exit/result
```

## Step 13 — Log the replay trade

Use this template:

```text
Date:
Session:
Layout: Banksy
Symbol: NQ1! / MNQ1!
Setup: Level Test / Level Sweep
Level involved:
Long or short:
Entry:
Stop:
Target:
Result in R:
Valid trade? Y/N
Mistake:
Screenshot filename:
Notes:
```

## First replay session target

Stop after:

```text
3 valid examples
or
5 total candidates
or
one full RTH session
```

The goal is not profit. The goal is learning whether you can identify location, confirmation, risk, and result without hindsight.

## What to send ChatGPT

Send:

```text
1. Screenshot before entry
2. Entry/stop/target notes
3. Result screenshot if available
```

Ask:

```text
Was this a valid Level Test or Level Sweep?
```
