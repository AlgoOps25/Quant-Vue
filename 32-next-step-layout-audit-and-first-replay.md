# 32 — Next Step: Layout Audit and First Replay Workflow

The user saved the primary QuantVue TradingView Premium layouts.

## Confirmed state

```text
TradingView Premium purchased
NQ1! realtime works
MNQ1! realtime works
Core QuantVue invite-only indicators are available
Primary shared layouts were opened and saved
```

Saved layouts:

```text
NQ QuantVue Banksy Manual Setup
NQ QuantVue Banksy Manual Layout
MNQ Alfredo Qpilot Manual
NQ Qgrid Renko Layout
NQ Broad Alerts Setup
```

## Missing freebies status

The user could not locate several public/freebie indicators by searching TradingView manually.

Decision:

```text
This is not a blocker.
If shared layouts load, continue.
Only chase exact freebie links later if a specific layout has a missing-script warning.
```

## Next objective

Choose the first working layout and begin replay validation.

Do not build a master layout yet.

First, compare:

```text
1. Banksy Manual Setup / Layout
2. Alfredo Qpilot Manual Layout
```

## Step 1 — Audit Banksy first

Open:

```text
NQ QuantVue Banksy Manual Setup
```

Then inspect:

```text
[ ] Are all charts using NQ1! or MNQ1!?
[ ] Are any charts using old contract symbols like MNQZ2025/NQZ2025?
[ ] Are the seconds/Renko charts updating?
[ ] Does Qbank_Pro show on the correct chart?
[ ] Does Q_Pro / SMC load where expected?
[ ] Are there any missing indicator warnings?
[ ] Is the layout readable enough to use in replay?
```

If an old contract symbol appears:

```text
Change it to NQ1! for E-mini practice or MNQ1! for micro practice.
```

Preferred symbols:

```text
NQ1!
MNQ1!
```

## Step 2 — Audit Alfredo second

Open:

```text
MNQ Alfredo Qpilot Manual
```

Then inspect:

```text
[ ] Are all charts using MNQ1! or NQ1!?
[ ] Does Q_Pilot load?
[ ] Do volume candles load correctly?
[ ] Does the 1-second Renko chart load?
[ ] Are there missing indicators?
[ ] Is the layout readable or too busy?
```

## Step 3 — Do not use Qgrid or Broad Alerts yet

Qgrid and Broad Alerts loaded, but they are not first-priority.

Use them later as:

```text
Qgrid = add-to-winner training
Broad Alerts = watchlist/alert infrastructure
```

Do not enable broad alerts yet.

## Step 4 — First replay setup

The first setup to validate is:

```text
Level Test / Level Sweep at a key 4H or 15m level
```

Not Qgrid.
Not broad alerts.
Not every signal.

## Step 5 — One replay session process

Use one saved layout, preferably Banksy first.

Replay process:

```text
1. Pick one recent NQ/MNQ session.
2. Before pressing play, mark key 4H or 15m levels.
3. Mark prior session high/low and overnight high/low if visible.
4. Press replay and move forward without hindsight.
5. Wait for price to reach a meaningful level.
6. Watch for Level Test or Level Sweep.
7. Only then look for QuantVue confirmation.
8. Define entry, stop, target before trade entry.
9. Log the trade as valid winner, valid loser, or skip.
10. Screenshot the setup.
```

## Step 6 — Journal fields for the first replay trade

Log:

```text
Date:
Session:
Layout used:
Symbol:
Setup type: Level Test / Level Sweep
Level tested/swept:
Entry reason:
QuantVue confirmations:
Entry price:
Stop price:
Target/exit plan:
Result:
R multiple:
Valid trade? Y/N
Mistake:
Screenshot filename:
Notes:
```

## Step 7 — Pass/fail criteria for this phase

Banksy/Alfredo layout passes if:

```text
It loads cleanly.
Symbols can be updated to NQ1!/MNQ1!.
It gives clear level, trigger, and exit context.
It can be used in replay without confusion.
```

Layout fails if:

```text
It is unreadable.
Too many indicators create analysis paralysis.
Critical indicators are missing.
It does not help identify location, trigger, exit, or risk.
```

## Immediate action

```text
Open NQ QuantVue Banksy Manual Setup.
Convert any old futures symbols to NQ1! or MNQ1!.
Send one screenshot after symbols are updated.
```
