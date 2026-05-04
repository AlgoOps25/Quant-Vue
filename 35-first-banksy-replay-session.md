# 35 — First Banksy Replay Session

This is the first structured replay session using the Banksy layout.

## Purpose

Validate one setup only:

```text
Level Test / Level Sweep at a key 15m or 4H level
```

Do not test every signal. Do not enable alerts. Do not trade live.

## Layout

Use:

```text
NQ QuantVue Banksy Manual Setup - Working Copy
```

Current observed chart structure:

```text
Main left chart: NQ1! / 1-second / Renko Traditional 10
Top-right chart: NQ1! / 15-minute
Bottom-right chart: NQ1! / 2-minute
```

## Instrument choice

Start with:

```text
MNQ1! for practice / risk simulation
```

If the saved Banksy layout is built on NQ1!, keep NQ1! for visual analysis, but when simulating risk, size as if using MNQ.

## Replay date selection

Pick one recent regular trading session.

Preferred session:

```text
New York RTH: 9:30 AM — 4:00 PM Eastern
```

Avoid at first:

```text
FOMC days
CPI/PPI/NFP days
Major news release windows
Low-volume holiday sessions
```

## Pre-replay setup

Before pressing play:

```text
[ ] Open Banksy working copy
[ ] Confirm charts use NQ1! or MNQ1!
[ ] Confirm no missing indicators
[ ] Confirm 15m chart is visible
[ ] Confirm Renko execution chart is visible
[ ] Set Bar Replay start before 9:30 AM ET
[ ] Mark overnight high
[ ] Mark overnight low
[ ] Mark prior day high
[ ] Mark prior day low
[ ] Mark obvious 15m swing high/low levels
[ ] Mark the opening range only after it forms
```

## What counts as a valid Level Test

A Level Test occurs when:

```text
Price approaches a marked level
Price reacts at or near the level
The level holds without a clean sweep/reclaim
Structure or QuantVue confirmation appears after the reaction
Entry can be defined with a clear stop beyond the level
```

## What counts as a valid Level Sweep

A Level Sweep occurs when:

```text
Price pushes through a marked high/low or level
Liquidity is taken
Price rejects and returns back through the level
Structure shifts or QuantVue confirmation appears after the reclaim/rejection
Entry can be defined with a clear stop beyond the sweep extreme
```

## Entry checklist

A simulated trade is allowed only if all are true:

```text
[ ] Price is at a marked level
[ ] Setup is Level Test or Level Sweep
[ ] Direction is clear before entry
[ ] Stop location is clear before entry
[ ] Target/exit logic is clear before entry
[ ] QuantVue confirmation appears after location reaction
[ ] Risk is acceptable for MNQ practice
```

## QuantVue confirmation examples

Possible confirmations:

```text
BOS / CHoCH in the trade direction
Bull/Bear state shift
Q_Pro / Qbank directional color support
Swing high/low reaction
Re-entry style confirmation
Price reclaiming or rejecting a level
```

Do not require every confirmation. The point is to log what appeared and whether it helped.

## Stop placement logic

For a long after a sweep/test:

```text
Stop below the sweep low or tested support level
```

For a short after a sweep/test:

```text
Stop above the sweep high or tested resistance level
```

If the stop is too wide:

```text
Skip the trade or use MNQ risk only
```

## Exit logic

Use one of:

```text
Next marked level
Opposite band/structure area
Qbank/Q_Pro opposite shift
Renko reversal / two-box adverse move if using that rule
Minimum 1R then manage
```

Do not freestyle exits. Pick the exit reason before entry.

## Replay logging template

For each setup candidate:

```text
Date:
Session:
Layout:
Symbol:
Setup: Level Test / Level Sweep
Level involved:
Long or short:
Why this level mattered:
Confirmation seen:
Entry price:
Stop price:
Initial target:
Risk in points:
Reward in points:
Result in R:
Winner / Loser / Skip:
Was it valid? Y/N
Mistake:
Screenshot filename:
Notes:
```

## Classification

Classify every candidate as:

```text
Valid winner
Valid loser
Invalid / should skip
Missed winner
False alert / false signal
Too early
Too late
Chop / no trade
News invalidated
```

## First session goal

Do not try to make money in replay.

Goal:

```text
Find and document 3–5 Level Test / Level Sweep candidates.
```

Stop after:

```text
3 valid trade examples
or
5 total candidates
or
one full RTH session reviewed
```

## Screenshot requirements

Capture:

```text
[ ] Before entry, with level visible
[ ] After entry, showing reaction/confirmation
[ ] After exit, showing result
```

## Pass/fail for first replay

Pass if:

```text
You can identify levels before price reaches them
You can wait for price to reach the level
You can define entry/stop/target before entry
You can classify the result honestly
```

Fail if:

```text
You chase every signal
You enter away from marked levels
You cannot define stop before entry
The layout is too confusing to use
```

## Next step after replay

Send screenshots of the first 1–3 candidates and the completed log fields.
