# 12 — Custom TradingView Indicator Build Plan

This document tracks the build of an original TradingView indicator inspired by the QuantVue workflow documented in this repo.

## Important boundary

This project will **not** copy, decompile, reverse-engineer, or imitate QuantVue proprietary source code.

The goal is to build an original decision-support indicator that follows our documented trading process:

```text
Location + Structure + Trend + Momentum + Risk = Trade quality
```

## Working name

```text
Layer 8 NQ Confluence Engine
```

Alternative names:

- NQ Prop-Firm Confluence Dashboard
- War Machine NQ Signal Framework
- Layer 8 Market Structure Engine

## Goal

Create a TradingView Pine Script indicator that helps identify NQ/MNQ trade candidates using:

- Prior day high/low
- Overnight high/low
- 8am candle zone
- 3-minute opening range
- 15-minute opening range
- Trend cloud
- Momentum confirmation
- ATR / volatility bands
- Swing structure
- Liquidity sweep detection
- Confluence score
- Long Watch / Short Watch alerts

This should support manual Tradovate execution. It should not auto-trade.

## Version roadmap

## MVP v0.1 — Foundation

Status: in progress

Features:

- Prior day high/low
- Overnight high/low
- 8am candle high/low/body
- 3-minute opening range
- 15-minute opening range
- EMA trend cloud
- RSI-style momentum confirmation
- ATR volatility bands
- Basic confluence score table
- Long Watch / Short Watch alerts

File:

```text
pine/layer8_nq_confluence_engine.pine
```

## v0.2 — Structure layer

Features:

- Swing high/low detection
- Basic BOS approximation
- Basic CHoCH approximation
- Liquidity sweep / reclaim detection
- Structure contribution to confluence score

## v0.3 — Strategy-specific signals

Features:

- 15-minute OR retest signal
- 3-minute OR breakout/retest signal
- 8am candle retest signal
- Zone reaction placeholder
- Qgrid-style add-to-winner logic

## v0.4 — Alerts and dashboard polish

Features:

- Long Watch alert
- Short Watch alert
- OR Retest alert
- 8am Retest alert
- Add-to-Winner alert
- No-Trade warning
- Cleaner dashboard labels

## v0.5 — Backtest strategy version

Separate file:

```text
pine/layer8_nq_confluence_strategy.pine
```

Purpose:

- Test rules historically
- Validate false signals
- Estimate expectancy
- Compare NQ vs MNQ behavior

## What we need from QuantVue

We do **not** need more QuantVue information for the MVP.

We would only need more QuantVue screenshots/transcripts if we were trying to reproduce exact behavior of:

- Qpilot
- Qbank Pro
- Iceberg
- Broad Alerts

For this project, those are optional. The custom indicator should stand on its own.

## Required validation before live use

Before any live or prop-firm use:

1. Load the Pine script on TradingView.
2. Confirm it compiles.
3. Test on NQ1! and MNQ1!.
4. Compare signals against the manual playbook.
5. Log at least 20 examples per signal type.
6. Treat all alerts as watch signals only.

## Signal philosophy

The indicator should say:

```text
This setup is worth looking at.
```

It should not say:

```text
Enter automatically.
```

## MVP scoring model

| Layer | Points | Logic |
|---|---:|---|
| Location | 2 | Price is near OR, 8am zone, overnight level, prior day level, or ATR band |
| Trend | 2 | EMA cloud supports direction |
| Momentum | 2 | RSI/momentum supports direction |
| Structure | 2 | BOS/sweep/reclaim supports direction |
| Risk context | 2 | Price has room to next level and is not in chop |

Initial Pine MVP will implement simplified scoring. Later versions can refine the scoring.

## Repo tracking

Related issue:

```text
Issue #4 — Feasibility: Build custom TradingView confluence indicator inspired by QuantVue workflow
```
