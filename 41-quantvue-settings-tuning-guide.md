# 41 — QuantVue Settings Tuning Guide

This guide consolidates the QuantVue transcripts, screenshots, onboarding notes, saved layouts, and repo playbooks into one practical tuning plan.

## Purpose

Since the protected QuantVue indicators cannot be formally backtested as Pine strategies, the goal is to tune each TradingView setup in a controlled way:

```text
Use official/shared QuantVue layouts as baseline
Tune one variable at a time
Forward-observe live market behavior
Journal every candidate
Rank setups by repeatability, profitability, ease, and prop-firm safety
```

## Core rule

Do not tune indicators randomly.

Every setting must support one of these jobs:

```text
Location
Direction
Trigger
Stop placement
Exit timing
Add-to-winner logic
Alert/watchlist filtering
```

---

# 1 — Layout priority

Use the saved TradingView Premium layouts in this order:

```text
1. NQ QuantVue Banksy Manual Setup
2. NQ QuantVue Banksy Manual Layout
3. MNQ Alfredo Qpilot Manual
4. NQ Qgrid Renko Layout
5. NQ Broad Band Setup
6. NQ Tight Band Setup
7. NQ Broad Alerts Setup
```

## Layout roles

| Layout | Role | When to use |
|---|---|---|
| Banksy Manual Setup | Cleanest rule-based layout | First validation layout |
| Banksy Manual Layout | Qbank/box/trailing execution | After Banksy setup is understood |
| Alfredo Qpilot Manual | Discretionary Qpilot/volume confluence | Second study layout |
| Qgrid Renko | Add-to-winner | Only after profitable initial trade logic exists |
| Broad Band | Fewer broader watch signals | Later alert testing |
| Tight Band | More sensitive watch signals | Later, only if broad is too slow |
| Broad Alerts | Alert infrastructure | Do not enable everything at once |

---

# 2 — Baseline symbol and chart settings

## Main symbols

```text
NQ1! = primary visual analysis
MNQ1! = lower-risk practice / execution sizing
```

## Renko execution baselines

From the repo and screenshots, there are several valid Renko settings depending on layout:

| Use case | Chart | Starting box size |
|---|---|---:|
| Banksy shared setup observed | 1-second Traditional Renko | 10 |
| Alfredo Qpilot observed | 1-second Traditional Renko | 5 |
| Qpro/Qwave/Qline discretionary setup | 1-second Traditional Renko | 4 |
| Faster NQ/MNQ experiments | Traditional Renko | 2–3 |
| Banksy-style quantitative testing | Traditional Renko | 5 |

## Tuning rule for Renko

Do not change the original shared layout immediately.

Instead create copies:

```text
NQ Banksy Renko 10 - Original
NQ Banksy Renko 5 - Test
NQ Banksy Renko 4 - Test
MNQ Alfredo Renko 5 - Original
MNQ Alfredo Renko 4 - Test
```

Then compare:

```text
Signal speed
False signals
Stop size
Ease of execution
Chop behavior
Missed trades
```

---

# 3 — SMC V2 tuning

## Purpose

SMC V2 is the bias/location tool.

It should answer:

```text
Where are the meaningful highs/lows?
Was liquidity swept?
Did structure break or shift?
Where are order blocks / FVGs / prior levels?
```

## Baseline settings

| Component | Starting setting |
|---|---|
| Main chart | 5-minute candles |
| Momentum candle color | ON |
| Liquidity | ON |
| BOS / CHoCH | ON |
| Order blocks | ON if useful, OFF if cluttered |
| Manual structures | ON |
| Manual structure period | 20 |
| Previous highs/lows | ON if clean |
| High color | White |
| Low color | Gray |
| FVGs | OFF on main 5m chart; use separate 15m chart |
| Session box | New York session optional |

## Tuning choices

### Cleaner bias chart

Use when chart is cluttered:

```text
Manual structure period: 20
BOS/CHoCH: ON
Liquidity: ON
Prior highs/lows: ON
FVG: OFF
Order blocks: only if they are not cluttering
```

### More complete context chart

Use on 15m or 4H context chart:

```text
FVG: ON
Order blocks: ON
Prior highs/lows: ON
Manual structure period: 20
```

## What to test

For each setup candidate, log whether SMC helped with:

```text
Valid level identification
Sweep/reclaim identification
BOS/CHoCH confirmation
Avoiding bad trades in the middle of nowhere
```

---

# 4 — Q_Pro / Qcloud / Qbands / Qwave / Qline tuning

Q_Pro is the main execution/confluence package.

## Qcloud baseline

| Setting | Starting value |
|---|---:|
| Use Qcloud | ON |
| Source | close |
| Period 1 | 19 |
| Period 2 | 29 |
| Period 3 | 49 |
| Period 4 | 59 |
| Period 5 | 69 |
| Period 6 | 99 |
| Bull/Bear labels | OFF initially |

Use Qcloud as:

```text
Trend-state filter
Not an entry by itself
```

## Qcloud tuning

| Need | Adjustment |
|---|---|
| Too late | Lower the later periods slightly |
| Too noisy | Raise the later periods slightly |
| Too many flips in chop | Keep labels OFF and require SMC/level context |

Do not tune Qcloud until at least 10 examples are logged with baseline settings.

## Qbands baseline profiles

### Captured responsive profile

| Setting | Value |
|---|---:|
| Use Qbands | ON |
| Source | Weighted |
| Length | 40 |
| Lookback | 256 |
| Band Deviation | 5 |
| Trend Period | 10 |
| Bull/Bear signals | OFF |

### Broader transcript / OR profile

| Setting | Value |
|---|---:|
| Length | 77 / 155 |
| Lookback | 256 |
| Band Deviation | 5 / 6.8 |
| Trend Period | 20 |

## Qbands tuning

| Use case | Suggested profile |
|---|---|
| Fast Renko reversal | Length 40, deviation 5, trend 10 |
| Broader range / OR context | Length 77, deviation 5, trend 15–20 |
| Fewer signals | Length 155, deviation 6.8, trend 20 |

Qbands should be used for:

```text
Outer-band stretch
Mean reversion context
Midline target
Not standalone entries
```

## Qwave baseline

| Setting | Starting value |
|---|---:|
| Use Qwave | ON |
| Price to Use | Weighted |
| APB Bars Back | 33 |
| ATR Bars Back | 256 |
| Band Deviation | 5.5 for NQ Renko 4-style execution |
| ADD Alerts | OFF initially |

## Qwave alternate OR profile

| Setting | Value |
|---|---:|
| APB Bars Back | 33 |
| ATR Bars Back | 256 |
| Band Deviation | 1.5 |
| ADD Alerts | ON in one OR strategy panel |

## Qwave tuning

| Need | Adjustment |
|---|---|
| Bands too far away | Lower deviation |
| Too many touches/noise | Raise deviation |
| Want broader reversal zones | Use 5.5 profile |
| Want tighter opening-range context | Test 1.5 profile only on OR layouts |

## Qline baseline

| Setting | Starting value |
|---|---:|
| Use Qline | ON |
| Source | close |
| Length | 6 |
| Multiplier | 0.1 |
| Reactivity | 0.4 |
| No-volume change calculation | OFF |

## Qline alternate OR profile

| Setting | Value |
|---|---:|
| Length | 9 |
| Multiplier | 0.1 |
| Common Period | 39 |
| Reactivity | 0.4 |
| Ribbon | ON in one OR panel |

## Qline tuning

| Need | Adjustment |
|---|---|
| Faster exits | Length 5–6 |
| Fewer flips | Length 9 |
| More visual trend ribbon | Enable ribbon only on OR/context tests |

Use Qline as:

```text
Entry confirmation after location reaction
Exit warning if it flips against trade
Not a standalone entry system
```

---

# 5 — Moneyball V2 tuning

## Purpose

Moneyball confirms momentum and helps avoid weak/choppy entries.

## Baseline scalping profile

| Setting | Value |
|---|---:|
| Bars between signals | 15 |
| Mode | M |
| Period | 4 |
| All Zero | ON |
| Upper Threshold | 0.4 |
| Lower Threshold | -0.4 |
| Reactivity | 0.1 |

## Opening-range profile

| Setting | Value |
|---|---:|
| Bars between signals | 15 |
| Mode | M |
| Period | 2 |
| All Zero | ON |
| Upper Threshold | 0.35 |
| Lower Threshold | -0.35 |
| Reactivity | 0.1 |

## Tuning options

| Use case | Period | Threshold |
|---|---:|---:|
| Aggressive scalping | 2–4 | 0.35–0.4 |
| Normal intraday scalping | 4–8 | 0.4 |
| Bias/trend filter | 8–20 | wider thresholds if needed |

## Optional smoothing

Optional enhancement:

```text
Add TradingView Hull Moving Average
Move it to Moneyball pane
Set HMA source to Moneyball V2
Use it to smooth momentum transitions
```

Do not add HMA if it makes the layout harder to read.

---

# 6 — Qgrid tuning

## Purpose

Qgrid is for add-to-winner logic, not blind initial entries.

## Known baseline notes

| Setting / concept | Starting note |
|---|---|
| NQ Renko | 3 or 4 box setting discussed in Qgrid tutorial |
| Heikin Ashi sensitivity | Around 33 discussed as baseline |
| Step moving average | Used as trend/pullback guide |
| ADD alerts | Use only after original trade is profitable |

## Qgrid use rules

A valid Qgrid long add requires:

```text
Original long is already profitable
Price remains above or reclaims step moving average
Pullback is shallow and controlled
Qgrid Bull / cyan dot appears
Stop can sit below pullback/structure
Target still offers acceptable R
```

A valid Qgrid short add requires:

```text
Original short is already profitable
Price remains below or rejects step moving average
Pullback is shallow and controlled
Qgrid Bear / blue dot appears
Stop can sit above pullback/structure
Target still offers acceptable R
```

Hard rule:

```text
Never use Qgrid to add to a losing prop-firm trade.
```

Do not tune Qgrid until a base entry setup is already working.

---

# 7 — Qbank / Banksy tuning

## Role

Qbank/Banksy is treated as:

```text
Rule-based execution and trade-management layout
```

## Observed Banksy layout

From the saved layout screenshot:

```text
Main chart: NQ1! / 1-second / Renko Traditional 10
Context chart: NQ1! / 15-minute
Lower chart: NQ1! / 2-minute
```

## Banksy tuning plan

Do not change the original.

Create copies:

```text
Banksy Original - Renko 10
Banksy Test - Renko 5
Banksy Test - Renko 4
```

Compare:

```text
Does Renko 10 avoid chop better?
Does Renko 5 catch entries earlier without too much noise?
Does Renko 4 become too fast or more useful for MNQ?
```

## Banksy evaluation questions

For each Level Test / Level Sweep candidate:

```text
Did Banksy identify the direction clearly?
Did Qbank help with stop/trailing logic?
Was the entry too late or clean?
Was the stop size realistic?
Did the layout reduce or increase hesitation?
```

---

# 8 — Alfredo Qpilot tuning

## Role

Alfredo is treated as:

```text
Discretionary Qpilot / volume-event confluence layout
```

## Observed Alfredo layout

From screenshot:

```text
Top-left: MNQ1! / 1-minute
Top-middle: NQ1! / 5-minute
Top-right: NQ1! / 15-minute
Bottom: NQ1! / 1-second / Renko Traditional 5
```

Visible label types:

```text
Buy
Sell
Re-entry Long
Re-entry Short
TP
Volume Peak
Volume Bottom
```

## Alfredo tuning plan

Do not tune Qpilot settings first.

First classify signals:

```text
Buy/Sell after level reaction
Re-entry after trend pullback
TP labels near target/exit
Volume Peak / Volume Bottom as exhaustion clues
```

## Alfredo evaluation questions

For each candidate:

```text
Did Qpilot signal before or after the best entry?
Did it help avoid a bad trade?
Did TP/Volume Peak help with exits?
Did labels appear too frequently?
Did it make the decision easier or more confusing?
```

If Alfredo is too noisy:

```text
Use it only as secondary confirmation after Banksy/SMC level setup
```

---

# 9 — Broad Band, Tight Band, and Broad Alerts

## Role

These are not primary entry systems yet.

Use them later as:

```text
Watchlist / alert discovery tools
```

## Test order

```text
1. Broad Band first
2. Tight Band second
3. Broad Alerts last
```

## Broad vs Tight expectation

| Layout | Expected behavior |
|---|---|
| Broad Band | Fewer, broader signals; better first alert layer |
| Tight Band | More frequent/sensitive signals; likely noisier |
| Broad Alerts | Infrastructure; only enable selective alerts |

Do not enable all alerts.

Start with:

```text
Level touch / level sweep watch
15m OR retest watch
Qline/Qtrend flip at level
Moneyball confirmation at level
Qgrid add-to-winner only
```

---

# 10 — Setup-specific tuning presets

## Preset A — Level Test / Level Sweep

Best layout:

```text
Banksy first
Alfredo second
```

Charts:

```text
15m / 4H context
5m SMC structure
1-second Renko execution
```

Core settings:

```text
SMC manual structure period: 20
Qcloud: 19/29/49/59/69/99
Qwave: 33 / 256 / 5.5
Qline: length 6, multiplier 0.1, reactivity 0.4
Moneyball: period 4, thresholds 0.4 / -0.4
```

## Preset B — 3m Opening Range

Best layout:

```text
OR-specific chart + Qpro + Moneyball_Q
```

Core settings:

```text
Moneyball period: 2
Thresholds: 0.35 / -0.35
Qcloud: 19/29/49/59/69/99
Qline length: 9
Qline common period: 39
Qwave deviation: 1.5
Qbands length: 77 or 155, deviation 5 or 6.8, trend period 20
```

## Preset C — 15m Opening Range Retest

Best layout:

```text
15m context + 5m structure + Renko execution
```

Rules:

```text
Mark first 15m OR high/low
Wait for breakout
Avoid chasing impulse
Prefer retest/rejection
Confirm with Qcloud/Qpro and Moneyball
Target nearest higher-timeframe level or Qwave/Qbands area
```

## Preset D — Qwave/Qbands Reversal

Best market:

```text
Range day
Exhaustion move
Sweep into prior high/low
Outer Qwave/Qbands interaction
```

Core settings:

```text
Qwave: 33 / 256 / 5.5
Qline: 6 / 0.1 / 0.4
Moneyball: period 4, thresholds 0.4 / -0.4
SMC: liquidity + CHoCH/BOS confirmation
```

## Preset E — Trend Continuation

Best market:

```text
Trend day
Opening drive
Breakout from range
Clear SMC BOS in same direction
```

Core settings:

```text
Qcloud: 19/29/49/59/69/99
Qline: support/rejection trigger
Moneyball: bullish/bearish continuation
SMC: trend direction and pullback structure
```

## Preset F — Qgrid Add-to-Winner

Use only after:

```text
Initial trade is profitable
Break-even or first target has been reached
Pullback is controlled
No major opposing level is directly ahead
```

---

# 11 — How to tune without overfitting

## One-variable rule

Only change one thing at a time:

```text
Renko size
or Moneyball period
or Qwave deviation
or Qline length
or Qbands length
```

Never change all at once.

## Sample rule

Do not judge a setting from one trade.

Minimum:

```text
10 observations before rejecting obviously bad settings
20 observations before ranking a setup
40 observations before making it a main workflow
```

## Journal every test

Use:

```text
templates/trade-journal.csv
```

Add these columns mentally or in a future version:

```text
Layout
Preset
Renko size
Moneyball setting
Qwave setting
Qline setting
Signal source
Did it help? Y/N
```

---

# 12 — Immediate implementation plan

## Step 1 — Lock original layouts

Keep originals unchanged:

```text
Banksy Original - Renko 10
Alfredo Original - Renko 5
```

## Step 2 — Create two test copies only

```text
Banksy Test - Renko 5
Banksy Test - Renko 4
```

Do not create 10 layouts yet.

## Step 3 — Start first test block

Test:

```text
Setup: Level Test / Level Sweep
Layout: Banksy
Settings: Original Renko 10 first
Sample target: 20 observations
```

## Step 4 — Compare against Banksy Renko 5

After 20 observations on Renko 10:

```text
Duplicate layout
Change execution chart to Renko 5
Observe 20 similar candidates
Compare stop size, clarity, speed, and noise
```

## Step 5 — Only then compare Alfredo

Use Alfredo after Banksy baseline exists:

```text
Does Qpilot improve entries/exits?
Or does it create extra noise?
```

---

# Final tuning direction

The goal is not to find the flashiest signal.

The goal is to find the smallest set of settings that reliably answers:

```text
Where is the trade?
Which direction is favored?
What confirms entry?
Where is the stop?
Where is the target?
Should I skip?
```
