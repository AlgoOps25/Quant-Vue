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

Suggested SMC settings from transcript:

| Component | Suggested starting point |
|---|---|
| EMA/cloud moving average length | 21 |
| Manual structure period | 20 |
| New York session | 09:30 to 16:00 or 16:05 |
| Session box transparency | 99 |
| Prior highs/lows colors | Highs white, lows gray |
| Fair Value Gaps | Prefer separate 15-minute chart |
| FVG extension/count | 500 when using FVG-only chart |

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

Practical use:

- Use outer band interaction for reversal/fade setup.
- Use midline as first target or decision level.
- Use top/bottom band as extended target.

### Qwave

Purpose: dynamic bands, breakout/reversal context, and interaction levels.

Transcript-derived NQ Renko 4 settings:

| Setting | Starting value from transcript |
|---|---|
| Lookback | 33 |
| Method / weighting | Weighted |
| Secondary value shown | 256 |
| Band deviation | 5.5 |

Practical use:

- Top-band rejection + Qline flip can trigger shorts.
- Lower-band rejection + Qline flip can trigger longs.
- Midline is a common first target.
- Qwave can also be used on daily/weekly charts for broader bias, but settings need separate tuning.

### Qline

Purpose: fast scalping confirmation, exit guide, and optional bounce tool.

Transcript-derived notes:

- Qline can be used as an exit signal: stay in until Qline flips.
- Qline length can be lowered, for example to 5, for more sensitive exits.
- Qline multiplier default referenced: 0.1.
- Raising multiplier, for example toward 3, creates a different “Qline bounce” style.

Recommended use:

- Use Qline flip after Qwave band interaction for entry confirmation.
- Use Qline flip against your trade as a reason to exit.
- Do not use Qline alone without location/context.

## 4. Moneyball V2 setup

Purpose: oscillator/momentum confirmation and chop recognition.

Transcript-derived settings:

| Setting | Recommended starting point |
|---|---|
| Mode | M |
| All Zero | Checked / ON |
| Period | 5 on NQ example |
| Scalping period range | 4 to 8 |
| Trend-bias period range | 8 to 20 |
| Upper/lower thresholds | Usually around 3 to 4.5 range |
| Reactivity | Fine-tune only; 0.1 baseline, 0.5 can print earlier |

Optional enhancement:

- Add TradingView Hull Moving Average.
- Move it to the Moneyball pane.
- Set HMA source to Moneyball V2.
- Use it to smooth Moneyball and identify cleaner momentum transitions.

## 5. Qgrid setup

Purpose: pullback/add-on system, not blind first entries.

Key rule:

> Qgrid is best used to add to a winner after the trade is already working.

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
