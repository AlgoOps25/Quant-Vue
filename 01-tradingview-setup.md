# 01 — TradingView Setup Guide

This file converts the transcript settings into a practical TradingView layout for NQ1!.

## 1. Account and symbol setup

- Charting platform: **TradingView**
- Execution platform: **Tradovate**
- Primary symbol: **NQ1!** or active NQ futures contract
- Optional lower-risk practice symbol: **MNQ1!** or active MNQ contract

## 2. Recommended layout

Use a two-chart or three-chart layout.

### Chart A — 5-minute SMC bias chart

Purpose: decide direction, structure, liquidity, and levels.

Settings:

- Symbol: NQ1!
- Timeframe: 5-minute candlesticks
- Indicator: QuantVue Smart Money Concepts V2
- Keep this chart clean. It is for bias and levels, not every execution signal.

Recommended visible SMC features:

- Momentum candle color: ON
- Liquidity: ON
- BOS / CHoCH: ON
- Order blocks: ON
- Manual structures: ON
- Manual structure period: 20
- Previous highs/lows: ON if they are not cluttering the chart
- Time-zone/session box: ON for New York cash session

SMC display fix:

- Open TradingView Object Tree.
- Drag Smart Money Concepts above candles.
- This keeps momentum colors and trend visuals visible in front of candles.

## 2A. Screenshot-confirmed SMC V2 settings — Screenshot Set #3

The following values were confirmed from the SMC V2 screenshots supplied by Michael.

### Structure display settings

| Setting | Confirmed value |
|---|---|
| Labels | ON |
| Label size | Tiny on one screen / Small on manual structure screen |
| Lines style | Dotted for main structure screen |
| Lines width | 1 for main dotted structure |

### Manual structure settings

| Setting | Confirmed value |
|---|---|
| Period | 20 |
| Bullish | ON, Both |
| Bearish | ON, Both |
| Bullish color | Bright green |
| Bearish color | Bright red |
| Order Blocks | Seen OFF in manual structure panel, but chart examples show order-block zones visible from another setting/profile |
| Manual labels | ON, Small |
| Manual lines | Solid |
| Manual line width | 2 |

Interpretation:

- Manual structure period 20 is the core SMC bias setting.
- Use the solid manual structure levels as higher-confidence BOS/CHoCH context.
- The chart examples show order-block zones being used as trade location, so keep order blocks available even if you toggle them off for a cleaner view.

### Fair Value Gap settings

| Setting | Confirmed value |
|---|---|
| FVG | OFF in the shown 5m SMC settings |
| FVG value shown | 10 |

Interpretation:

- Keep FVGs off on the main 5m SMC bias chart unless needed.
- Use a separate 15-minute FVG/context chart when you want fair-value-gap levels without cluttering the execution/bias chart.

### Previous high/low settings

Two states were captured:

| Setting | Confirmed value |
|---|---|
| Daily | ON in final screenshot |
| Weekly | ON in final screenshot |
| Monthly | ON in final screenshot |
| Yearly | ON in final screenshot |
| High color | White in final screenshot |
| Low color | Gray in final screenshot |
| Line style | Dotted |

Interpretation:

- Use prior day/week/month/year levels as major liquidity and reaction zones.
- White highs and gray lows keep the chart cleaner than bright red/green levels.

### Market session settings

| Setting | Confirmed value |
|---|---|
| Timezone | Etc/UTC |
| Session labels | OFF in screenshots |
| Borders | ON |
| Transparency | 95 |
| New York | 13:30–20:00 UTC, blue, checkbox OFF in captured panel |
| London | 07:00–15:30 UTC, cyan, checkbox OFF in captured panel |
| Tokyo | 00:00–06:00 UTC, magenta, checkbox OFF in captured panel |
| Hong Kong | 13:30–20:00 UTC, olive/yellow, checkbox OFF in captured panel |

Interpretation:

- 13:30–20:00 UTC maps to the New York cash session window shown in the video context.
- Borders ON with high transparency keeps sessions visible without overpowering price.
- You can toggle the New York checkbox ON when you want the session box displayed, but the captured settings panel shows it OFF at the moment of screenshot.

Suggested SMC settings from transcript and screenshots:

| Component | Suggested starting point |
|---|---|
| EMA/cloud moving average length | 21 from transcript if using SMC cloud |
| Manual structure period | 20 confirmed |
| New York session | 13:30–20:00 UTC or 09:30–16:00 New York time |
| Session transparency | 95 confirmed; 99 mentioned in transcript |
| Prior highs/lows colors | Highs white, lows gray confirmed |
| Fair Value Gaps | Prefer separate 15-minute chart |
| FVG value shown | 10 confirmed in SMC panel; 500 extension discussed in transcript for FVG-only workflow |

### Chart B — Renko execution chart

Purpose: entries, exits, add-ons, scalps, and alerts.

Settings:

- Symbol: NQ1!
- Base interval: 1 second
- Chart type: Traditional Renko
- Box size: 4 for discretionary Qpro/Qwave/Qline setups
- Box size: 5 only when a strategy video specifically says to use 5-box Renko

Indicators:

- QuantVue Qpro V2
- Moneyball V2
- Qgrid when using add-on strategy
- Optional Qmomentum only if using divergence confirmation

### Chart C — 15-minute / 4-hour context chart

Purpose: higher-timeframe FVGs, order blocks, and major trend structure.

Use this chart only for context. Do not clutter your execution chart with every higher-timeframe zone.

## 3. Qpro V2 setup

Qpro is the all-in-one dashboard that includes Qcloud, Qbands, Qwave, and Qline logic.

Transcript-derived notes:

- Load from TradingView **Invite-only scripts**.
- Qpro initially looks busy. Turn modules on one at a time while learning.
- Use session background to identify your active trading window.
- Many users keep raw bull/bear signals off to reduce clutter.

## 3A. Screenshot-confirmed Qpro settings — Screenshot Set #1

The following values were confirmed from the first screenshots supplied by Michael.

### Time settings

| Setting | Confirmed value |
|---|---|
| Use Session? | ON |
| Trading Session | 09:30–16:00 |
| Timezone | America |

### Qcloud settings

| Setting | Confirmed value |
|---|---|
| Use Qcloud | ON |
| Qcloud Source | close |
| Qcloud Period 1 | 19 |
| Qcloud Period 2 | 29 |
| Qcloud Period 3 | 49 |
| Qcloud Period 4 | 59 |
| Qcloud Period 5 | 69 |
| Qcloud Period 6 | 99 |
| Show Qcloud Bull/Bear Signals | OFF |

Interpretation:

- Use Qcloud as the broad trend-state layer.
- Keep bull/bear labels off to reduce noise.
- Do not trade every Qcloud color change during chop.

### Qbands settings

| Setting | Confirmed value |
|---|---|
| Use Qbands | ON |
| Qbands Source | Weighted |
| Qbands Length | 40 |
| Qbands Lookback Distance | 256 |
| Qbands Band Deviation | 5 |
| Qbands Trend Period | 10 |
| Show Qbands Bull/Bear Signals | OFF |

Interpretation:

- These are more responsive than the broader transcript examples that referenced 77 length.
- Treat these as the current captured setup, not a universal default.
- Validate on NQ Renko before using real prop-firm size.

### Qwave settings

| Setting | Confirmed value |
|---|---|
| Use Qwave | ON |
| Price To Use | Weighted |
| APB Number Of Bars Back | 33 |
| ATR Number Of Bars Back | 256 |
| Qwave Band Deviation | 5.5 |
| Show Qwave ADD Alerts? | OFF |

Interpretation:

- Qwave 33 / 256 / 5.5 is the main NQ Renko 4 band interaction setup from the tutorial.
- Use upper/lower band interaction as location, then require Qline/Moneyball/SMC confirmation.

### Qline settings

| Setting | Confirmed value |
|---|---|
| Use Qline | ON |
| Qline Source | close |
| Qline Length | 6 |
| Qline Multiplier | 0.1 |
| Qline Change Calculation — no volume data | OFF |
| Qline Reactivity | 0.4 |

Interpretation:

- Qline is being used as a responsive trigger/exit line.
- Qline length 6 and reactivity 0.4 are faster than a slow trend filter.
- Use Qline flip as confirmation after price reaches a level/band, not as a standalone trade.

### Qcloud

Purpose: trend-state filter.

How to use:

- Use Qcloud ribbon flips for trend state.
- Do not blindly take every bull/bear flip, especially around chop or news.
- Use Qcloud as a directional filter with SMC and Moneyball.

Transcript tuning note:

- The speaker says the default settings are strong most of the time.
- Responsiveness can be adjusted by modifying the final Qcloud periods in small increments.

### Qbands

Purpose: stretched price, mean-reversion zones, continuation interaction, and midline targets.

Transcript-derived NQ Renko 4 notes:

- Band Length default referenced: 77
- On Renko 4, the speaker sometimes reduces band length to about 65 or 60.
- Trend period example: 15 for earlier flips.
- Upper/lower Qbands are often turned off because Qwave has better band logic.
- Screenshot Set #1 confirms a separate captured setup using Length 40, Lookback 256, Band Deviation 5, Trend Period 10.

Practical use:

- Use outer band interaction for reversal/fade setup.
- Use midline as first target or decision level.
- Use top/bottom band as extended target.

### Qwave

Purpose: dynamic bands, breakout/reversal context, and interaction levels.

Transcript-derived NQ Renko 4 settings:

| Setting | Starting value from transcript / screenshot |
|---|---|
| Lookback / APB Bars Back | 33 |
| Method / Price To Use | Weighted |
| ATR Bars Back / Secondary value | 256 |
| Band deviation | 5.5 |
| ADD Alerts | OFF in Screenshot Set #1 |

Practical use:

- Top-band rejection + Qline flip can trigger shorts.
- Lower-band rejection + Qline flip can trigger longs.
- Midline is a common first target.
- Qwave can also be used on daily/weekly charts for broader bias, but settings need separate tuning.

### Qline

Purpose: fast scalping confirmation, exit guide, and optional bounce tool.

Screenshot-confirmed settings:

| Setting | Confirmed value |
|---|---|
| Source | close |
| Length | 6 |
| Multiplier | 0.1 |
| Reactivity | 0.4 |

Recommended use:

- Use Qline flip after Qwave band interaction for entry confirmation.
- Use Qline flip against your trade as a reason to exit.
- Do not use Qline alone without location/context.

## 4. Moneyball V2 setup

Purpose: oscillator/momentum confirmation and chop recognition.

## 4A. Screenshot-confirmed Moneyball settings — Screenshot Set #2

| Setting | Confirmed value |
|---|---|
| Number of bars between signals | 15 |
| Mode | M |
| Period | 4 |
| All Zero | ON / checked |
| Upper Threshold | 0.4 |
| Lower Threshold | -0.4 |
| Reactivity | 0.1 |

Interpretation:

- This is a faster scalping configuration because Period is set to 4.
- The transcript said most intraday scalping configurations stay in the 4–8 period range; this screenshot confirms the aggressive end of that range.
- Thresholds at 0.4 / -0.4 are much tighter than the broader transcript discussion, so validate this on your exact NQ Renko layout before trusting it live.
- Number of bars between signals at 15 should reduce repeated diamonds/signals during noisy chop.

Transcript-derived guidance:

| Setting | Recommended starting point |
|---|---|
| Mode | M |
| All Zero | Checked / ON |
| Period | 4 to 8 for scalping; screenshot uses 4 |
| Trend-bias period range | 8 to 20 |
| Upper/lower thresholds | Screenshot uses 0.4 / -0.4 |
| Reactivity | Screenshot uses 0.1; higher values can print earlier |

Optional enhancement:

- Add TradingView Hull Moving Average.
- Move it to the Moneyball pane.
- Set HMA source to Moneyball V2.
- Use it to smooth Moneyball and identify cleaner momentum transitions.

## 5. Qgrid setup

Purpose: pullback/add-on system, not blind first entries.

Key rule:

> Qgrid is best used to add to a winner after the trade is already working.

## 5A. Screenshot-confirmed Qgrid settings — Screenshot Set #4

The following values were confirmed from the `NEW "Qgrid" TradingView Indicator Is HERE!` screenshot supplied by Michael.

### Heiken Ashi 1

| Setting | Confirmed value |
|---|---|
| HA1 Smooth Mode | Atrens |
| HA1 Smooth Period | 33 |
| Bull Color | Cyan/teal |
| Bear Color | Blue |

### Heiken Ashi 2

| Setting | Confirmed value |
|---|---|
| HA2 Smooth Mode | Atrens |
| HA2 Smooth Period | 5 |
| Bull Color | Cyan/teal |
| Bear Color | Blue |

### Add Heiken Ashi 2

| Setting | Confirmed value |
|---|---|
| Number of bars for the pullback | 3 |
| Number of bars for the lift after the pullback | 1 |

### DMA

| Setting | Confirmed value |
|---|---|
| DMA Length | 19 |

### Step Moving Average

| Setting | Confirmed value |
|---|---|
| Sensitivity Factor | 2.9 |
| Bull Color | Cyan/teal |
| Bear Color | Blue |

Interpretation:

- HA1 period 33 is the slower trend/pullback context.
- HA2 period 5 is the faster reaction layer.
- Pullback 3 and lift 1 make Qgrid look for a short pullback followed by immediate continuation.
- DMA 19 and Step MA sensitivity 2.9 are the current captured baseline.
- Use Qgrid for add-to-winner and continuation confirmation, not for averaging down.

Transcript-derived notes:

- Qgrid uses dots/add signals around a step moving average.
- NQ examples use Renko 3 or 4.
- Heiken Ashi 1/2 sensitivity defaults are discussed around 33.
- Lower sensitivity values make it tighter/faster.
- Higher sensitivity values make it smoother/slower.

Practical prop-firm rule:

- Do not use Qgrid to add to a losing position.
- Add only after entry is in profit and the pullback holds structure.
- Keep total risk inside the daily loss plan.

## 6. Indicator overload rule

It is technically possible to run many indicators at the same time, but the chart becomes hard to trade.

Recommended approach:

- Bias chart: SMC only plus key levels.
- Execution chart: Qpro + Moneyball.
- Add Qgrid only when actively using add-on logic.
- Add Qmomentum only when actively using divergence logic.
- Use alerts as attention signals, not automatic trade entries.

## 7. Save TradingView layouts

Create saved layouts:

1. `NQ QuantVue Bias - 5m SMC`
2. `NQ QuantVue Execution - Renko 4`
3. `NQ QuantVue System - Renko 5`
4. `NQ QuantVue FVG Context - 15m`
5. `NQ QuantVue HTF Context - 4h`
