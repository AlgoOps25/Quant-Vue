# Quant-Vue NQ1! Prop-Firm Trading System

This repository documents a manual trading workflow for **NQ1! / MNQ / NQ futures** using:

- **TradingView** for charting and alerts
- **QuantVue Pro indicators** for confluence
- **Tradovate** for manual execution
- **Prop-firm risk rules** as the hard constraint

> Educational trading documentation only. This is not financial advice. Validate every rule in replay/paper mode before using it in a prop-firm account.

## Important privacy note

GitHub currently reports this repo as **public**. Do not commit:

- Tradovate credentials
- Prop-firm account numbers
- API keys
- Screenshots showing balances, account IDs, or login details
- Proprietary QuantVue source code

Screenshots should only show chart layouts, indicator settings, and marked-up examples.

## Main idea

The QuantVue videos point to a **confluence system**, not a single alert-following system.

A valid trade should answer five questions:

1. **Context:** Is NQ trending, ranging, reversing, or chopping?
2. **Location:** Am I trading from a meaningful level instead of chasing?
3. **Direction:** Do higher-timeframe structure and execution signals agree?
4. **Trigger:** Did Qpro / Qcloud / Qline / Moneyball / Qgrid give a clear trigger?
5. **Risk:** Does the trade fit the prop-firm daily loss, trailing drawdown, and minimum reward:risk rules?

## Repo map

| File | Purpose |
|---|---|
| [`00-daily-runbook.md`](00-daily-runbook.md) | Morning checklist and daily workflow |
| [`01-tradingview-setup.md`](01-tradingview-setup.md) | TradingView layout, indicators, and settings |
| [`02-confluence-system.md`](02-confluence-system.md) | Scoring model for deciding whether a setup is worth trading |
| [`03-strategy-playbook.md`](03-strategy-playbook.md) | Strategy families from the videos converted into executable rules |
| [`04-alerts-and-tradovate-execution.md`](04-alerts-and-tradovate-execution.md) | Alerts, manual execution, brackets, and risk handling |
| [`05-screenshots-needed.md`](05-screenshots-needed.md) | Screenshots still needed from the videos with timestamps |
| [`06-video-index.md`](06-video-index.md) | Transcript-derived video index and what each video contributes |
| [`templates/pre-market-checklist.md`](templates/pre-market-checklist.md) | Copy/paste morning checklist |
| [`templates/trade-journal.csv`](templates/trade-journal.csv) | Journal template for tracking setup quality |

## Core layout

Use two primary charts:

1. **Bias Chart:** NQ1! 5-minute candlestick chart
   - QuantVue SMC V2
   - Liquidity grabs
   - BOS / CHoCH
   - Manual structure period 20
   - Order blocks
   - Prior day/week highs and lows
   - Optional fair value gaps on a separate 15-minute chart

2. **Execution Chart:** NQ1! Renko chart
   - 1-second source chart
   - Traditional Renko
   - 4-box Renko for discretionary Qpro/Qwave/Qline trading
   - 5-box Renko when using strategy/system examples that specifically require 5-box Renko
   - Qpro V2, Qcloud, Qline, Qbands, Qwave, Moneyball, Qgrid as needed

## Minimum live-trading gate

Before using this with a live prop-firm account:

- Replay test each setup family.
- Log at least 20 examples of each setup.
- Know the average stop size in points.
- Know the dollar risk per NQ and MNQ contract.
- Confirm Tradovate bracket behavior.
- Define a daily shutdown rule.

## Current status

This repository is the working reference system. The next improvement is to add screenshots from the exact video timestamps listed in `05-screenshots-needed.md`.
