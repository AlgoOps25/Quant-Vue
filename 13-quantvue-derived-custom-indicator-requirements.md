# 13 — QuantVue-Derived Custom Indicator Requirements

This document converts everything learned from the QuantVue transcripts, screenshots, and strategy notes into requirements for our own original TradingView indicator.

## Important boundary

This project will use the **workflow, trading concepts, settings observations, and confluence rules** learned from the QuantVue material.

It will **not** copy, decompile, reverse-engineer, or claim to reproduce QuantVue proprietary source code.

The goal is to build an original Layer 8 indicator that supports the same trading process:

```text
Context → Location → Structure → Momentum → Trigger → Risk → Manual execution
```

## Strategic decision

QuantVue remains the primary trading stack for live/paper workflow until the Layer 8 indicator is validated.

The Layer 8 indicator will be developed as:

1. A research sandbox.
2. A custom dashboard.
3. A potential future replacement/helper only after replay validation.

## QuantVue-derived feature map

| QuantVue concept | What we learned | Layer 8 equivalent |
|---|---|---|
| SMC V2 | Manual structure period 20, BOS/CHoCH, order blocks, FVGs, prior highs/lows, session boxes | Structure engine, liquidity engine, prior levels, session levels |
| Qpro/Qcloud | Multi-period trend-state cloud; screenshot periods 19/29/49/59/69/99 | EMA/HMA/ribbon trend-state cloud with configurable periods |
| Qbands | Volatility bands, outer-band reactions, midline targets | ATR/std-dev bands with upper/lower/midline logic |
| Qwave | Weighted price, APB 33, ATR 256, deviation examples 5.5 and 1.5 | Volatility interaction layer and dynamic target bands |
| Qline | Fast trigger/exit line; length 6 or 9, multiplier 0.1, reactivity 0.4 | Fast trend/trigger line and exit confirmation |
| Moneyball | Momentum confirmation; Mode M, All Zero ON, period 4 or 2, thresholds 0.4/-0.4 or 0.35/-0.35 | Normalized momentum oscillator and confirmation score |
| Qgrid | Add-to-winner logic; HA1 33, HA2 5, pullback 3, lift 1, DMA 19, sensitivity 2.9 | Pullback-continuation/add-to-winner module |
| Opening range strategies | 3-minute OR and 15-minute OR breakout/retest workflows | OR high/low capture, breakout/retest detection, alerts |
| 8am candle retest | Mark 8am candle zone, wait for reaction/retest | 8am candle zone module |
| Zone strategy | Draw support/demand and resistance/supply areas, wait for reaction | Manual/algorithmic zone support and zone-reaction alerts |
| Broad alerts | Alerts should be watchlist pings, not automatic entries | Alert system uses watch signals only |

## MVP indicator requirements

The custom indicator must eventually include the following modules.

### 1. Level engine

Required:

- Prior day high/low
- Overnight high/low
- 8am candle high/low/body
- 3-minute opening range high/low
- 15-minute opening range high/low
- Optional weekly/monthly/yearly high/low later

Purpose:

- Define trade location.
- Prevent entries in the middle of nowhere.
- Provide targets and invalidation levels.

### 2. Trend-state engine

Required:

- Cloud/ribbon style trend state.
- Bull, bear, and neutral classification.
- Configurable fast/slow or multi-period smoothing.

QuantVue-inspired reference points:

- Qcloud screenshot periods: 19/29/49/59/69/99.
- Qline examples: length 6 or 9, multiplier 0.1, reactivity 0.4.

Layer 8 implementation direction:

- Start with EMA cloud.
- Add multi-line ribbon later.
- Add Qline-style trigger line later.

### 3. Momentum engine

Required:

- Bull, bear, neutral momentum state.
- Configurable thresholds.
- Momentum must filter labels/alerts.

QuantVue-inspired reference points:

- Moneyball fast scalping period 4, thresholds 0.4/-0.4.
- 3-minute OR example uses period 2, thresholds 0.35/-0.35.

Layer 8 implementation direction:

- Start with RSI/normalized momentum.
- Later create custom normalized oscillator using price velocity, EMA spread, or ROC.

### 4. Volatility / band engine

Required:

- Basis/midline.
- Upper/lower dynamic bands.
- Outer-band reaction context.
- Midline as target.

QuantVue-inspired reference points:

- Qbands examples: length 40/77/155, lookback 256, deviations 5 and 6.8.
- Qwave examples: APB 33, ATR 256, deviation 5.5 or 1.5.

Layer 8 implementation direction:

- Start with ATR bands.
- Later test standard deviation bands and weighted price.

### 5. Structure engine

Required:

- Swing highs/lows.
- Basic BOS approximation.
- Basic CHoCH approximation later.
- Liquidity sweep and reclaim/rejection.

QuantVue-inspired reference points:

- SMC manual structure period 20.
- Bullish and bearish structure both enabled.
- Prior highs/lows used as liquidity context.

Layer 8 implementation direction:

- Start with pivot-based swing detection.
- Improve with separate internal/external structure later.

### 6. Strategy modules

Required strategy detection:

1. 15-minute OR retest.
2. 3-minute OR breakout/retest.
3. 8am candle retest.
4. SMC-style liquidity sweep reversal.
5. Qwave/Qbands-style band reversal to midline.
6. Qcloud-style trend continuation.
7. Qgrid-style add-to-winner.
8. Zone reaction module later.

### 7. Confluence score

Required:

- 0–10 score.
- Long and short score separately.
- Dashboard state: Long Watch, Short Watch, Wait.

Scoring model:

| Layer | Points |
|---|---:|
| Location | 2 |
| Trend | 2 |
| Momentum | 2 |
| Structure/retest | 2 |
| Room/risk context | 2 |

### 8. Alert philosophy

All alerts are watch signals only.

Allowed alerts:

- Long Watch
- Short Watch
- 15m OR Long Retest
- 15m OR Short Retest
- 3m OR Long Retest
- 3m OR Short Retest
- 8am Retest
- Liquidity Sweep/Reclaim
- Add-to-Winner

Not allowed:

- Auto-entry alert language.
- Claims of guaranteed signal accuracy.
- Signals without stop/target/risk validation.

## Current implementation status

Current Pine file:

```text
pine/layer8_nq_confluence_engine.pine
```

Current version:

```text
v0.4
```

Implemented:

- Prior day high/low
- Overnight high/low
- 8am candle zone
- 3-minute OR
- 15-minute OR
- EMA cloud trend
- RSI momentum
- ATR bands
- Basic swing structure
- Sweep/reclaim detection
- Confluence score
- Dashboard
- Display modes: Dashboard Only, Minimal Markers, Full Labels
- Watch alerts

Needs improvement:

- Reduce false positives in chop.
- Improve structure logic.
- Add dedicated strategy modules.
- Add Qgrid-style add-to-winner logic.
- Add optional zone module.
- Add validation journal results before any live usage.

## Development roadmap from here

### v0.5 — QuantVue workflow alignment

- Add module toggles for each strategy.
- Add 15m OR retest signal quality filters.
- Add 3m OR retest/breakout module.
- Add 8am retest module.
- Add separate signal type text in dashboard.

### v0.6 — Better structure

- Improve BOS/CHoCH approximation.
- Add swing-strength settings.
- Add separate internal/external structure.
- Add cleaner sweep/reclaim logic.

### v0.7 — Momentum and band refinement

- Replace or supplement RSI with normalized momentum.
- Add Moneyball-inspired thresholding without copying QuantVue logic.
- Add weighted source option.
- Add ATR/std-dev band selection.

### v0.8 — Add-to-winner module

- Add Qgrid-style pullback continuation logic.
- Only trigger if original trend is already in profit or trend leg is established.
- Never signal add-to-loser.

### v0.9 — Backtest strategy

Create separate strategy file:

```text
pine/layer8_nq_confluence_strategy.pine
```

Purpose:

- Backtest signal logic.
- Estimate expectancy.
- Compare NQ vs MNQ.
- Validate time-of-day behavior.

## Validation requirement

Before this custom indicator becomes primary, each signal type must have at least:

```text
20 replay examples
20 paper/live-sim examples
Positive average R
Clear failure rules
Documented best/worst market conditions
```

Until then, QuantVue remains the primary system.