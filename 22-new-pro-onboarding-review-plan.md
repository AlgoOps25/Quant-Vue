# 22 — New QuantVue Pro Onboarding Review Plan

The user added new QuantVue Pro onboarding materials:

```text
QuantVue Core Prop-Training Course
Repainting
Pro Chart Layouts
Settings Tips
Members Freebies
```

## Purpose

Use these materials to refine the QuantVue-first workflow before live prop-firm use.

The current objective is not to add more random indicators. The objective is to create the cleanest, most repeatable QuantVue workflow for NQ/MNQ trading.

## Key updates from the new documents

## 1. Trade location is the foundation

The QuantVue Core Prop-Training Course emphasizes that the best trade setups happen at meaningful price locations.

Core location concepts:

```text
Higher-timeframe structural pivots
Support / resistance edges
Level tests
Level sweeps
Reactionary price areas
```

Workflow impact:

```text
Do not treat QuantVue signals as standalone entries.
First mark location, then wait for signal confirmation.
```

## 2. Use higher-timeframe levels

The course recommends marking key pivots from higher timeframes, especially the 4-hour chart, then carrying those levels down to the intraday execution chart.

Workflow impact:

```text
Add 4H structural level review to the daily runbook.
Use 15m / 5m / Renko only after key levels are known.
```

## 3. Level tests and level sweeps become core setups

The new course material reinforces two primary setup families:

```text
Level Test: price retests a prior pivot/level and rejects.
Level Sweep: price breaks through a level, sweeps liquidity, then reverses back into prior range.
```

Workflow impact:

```text
Level Test and Level Sweep should become primary replay-tested setups.
```

## 4. Repainting must be understood before alerting

The TradingView repainting document explains that many indicators behave differently on realtime bars than historical bars.

Workflow impact:

```text
Alerts should be treated as watch signals.
Prefer confirmed-bar alerts when possible.
Do not trust intrabar signals without understanding whether they can disappear/change.
For custom Pine development, avoid misleading repainting behavior.
```

## 5. Pro Chart Layouts should be tested before custom layouts

The Pro Chart Layouts document includes several official/community layouts:

```text
Tucci NQ setup
TI Trading Wiz NQ triple setup
Iceberg NQ setup
Qgrid Renko layout
Broad Alerts setup
Tight Band setup
Broad Band setup
Banksy Manual Setup
Alfredo Qpilot Manual Layout
Qbank Pro layout
Indicator-only layouts for Qbands, Qline, Qwave, Qcloud
```

Workflow impact:

```text
Test official/community layouts first before manually recreating everything.
Use the layouts as the baseline, then remove clutter.
```

## 6. Settings Tips change the Renko plan

Settings Tips notes for NQ/MNQ:

```text
Renko core setup: Traditional, 2, 3, or 4 box size
Normal candles: supported
Range bars: supported
Heikin Ashi: supported
```

This differs slightly from the Banksys file, which discussed Traditional 5 Renko.

Workflow impact:

```text
Test both:
- Traditional 4 Renko for faster execution
- Traditional 5 Renko for Banksys-style rule testing
```

## Updated QuantVue-first layout priority

## Layout 1 — Core Prop Training Layout

Purpose:

```text
Trade location, level tests, level sweeps, Q Zone / Q Trend concepts
```

Charts:

```text
4H key levels
15m pivots/context
5m SMC/structure
Renko execution
```

## Layout 2 — Banksy Manual / Quantitative Layout

Purpose:

```text
Rule-based Renko execution
```

Test:

```text
Traditional Renko 5
1-second source if TradingView Plus supports it
Buy/sell stop entries one tick past trigger
Trailing stop logic
```

## Layout 3 — Alfredo Qpilot Manual Layout

Purpose:

```text
Discretionary confluence workflow
```

Focus:

```text
Qwave bounce
Qline interaction
Oracle Squeezer
Qpilot volume exhaustion
15m context
3–5 confluences for entry and exit
```

## Layout 4 — Broad/Tight Band Alert Layouts

Purpose:

```text
Alert testing only
```

Start with Broad Band first for fewer alerts.

## Immediate action order

1. Confirm TradingView Plus supports the required Renko setup.
2. Load the official Pro Chart Layouts one at a time.
3. Start with Banksy Manual Layout and Alfredo Qpilot Manual Layout.
4. Do not add all freebie indicators at once.
5. Build a clean master layout from the best parts.
6. Begin replay validation with Level Test and Level Sweep setups.

## New replay priority

Original first replay setup was 15m opening range retest.

After reviewing the new onboarding material, the replay priority should become:

```text
1. Level Test at higher-timeframe / 15m level
2. Level Sweep reversal
3. 15m Opening Range retest
4. 3m Opening Range breakout/retest
5. Trend continuation pullback to mid-band
6. Qwave/Qline/Oracle Squeezer confluence
7. Qgrid add-to-winner
```

## Rule

No indicator or layout is considered useful until it produces logged replay examples with clear entry, stop, exit, and invalidation rules.
