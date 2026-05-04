# Quant-Vue NQ/MNQ Prop-Firm Trading System

This repository is the operating manual for building and validating a **QuantVue Pro + TradingView Premium + Tradovate** workflow for NQ/MNQ futures.

> Educational trading documentation only. This is not financial advice. Every setup must be validated in replay and paper/sim mode before use in a live or prop-firm account.

## Current platform decision

The final decision is:

```text
TradingView Premium
+ CME Group real-time futures data
+ QuantVue Pro
+ Tradovate manual execution
```

Reason: TradingView Plus worked for basic NQ/MNQ charting and Renko box-size tests, but the actual QuantVue shared layouts required Premium-only features such as seconds-based charts and volume candles.

## Current operating rule

```text
Location → Level Test / Level Sweep → Structure → QuantVue Confirmation → Risk → Manual Entry
```

Do not trade raw indicator flashes. QuantVue alerts are watch signals only.

## Lean repo map

| File | Purpose |
|---|---|
| [`00-daily-runbook.md`](00-daily-runbook.md) | Daily prep and operating checklist |
| [`01-tradingview-setup.md`](01-tradingview-setup.md) | QuantVue indicator settings captured from videos/screenshots |
| [`02-confluence-system.md`](02-confluence-system.md) | Trade-quality scoring model |
| [`03-strategy-playbook.md`](03-strategy-playbook.md) | Strategy families converted into rules |
| [`04-alerts-and-tradovate-execution.md`](04-alerts-and-tradovate-execution.md) | Alerts, manual execution, and Tradovate handling |
| [`06-video-index.md`](06-video-index.md) | Source index for the original QuantVue transcripts/videos |
| [`08-one-page-trading-plan.md`](08-one-page-trading-plan.md) | One-page operating plan |
| [`09-trade-no-trade-decision-tree.md`](09-trade-no-trade-decision-tree.md) | Entry filter and no-trade logic |
| [`10-prop-firm-risk-template.md`](10-prop-firm-risk-template.md) | Prop-firm risk template |
| [`11-replay-validation-plan.md`](11-replay-validation-plan.md) | Replay/paper validation process |
| [`24-master-audit-and-chronological-plan.md`](24-master-audit-and-chronological-plan.md) | Final chronological plan and decision log |
| [`30-premium-setup-and-layout-validation.md`](30-premium-setup-and-layout-validation.md) | Immediate post-upgrade setup checklist |
| [`templates/pre-market-checklist.md`](templates/pre-market-checklist.md) | Copy/paste pre-market checklist |
| [`templates/trade-journal.csv`](templates/trade-journal.csv) | Trade journal template |

## Files removed during cleanup

The repo previously contained many step-by-step decision files created while comparing TradingView Plus, TradingView Premium, NinjaTrader, custom Pine development, and screenshot collection. Those interim files were consolidated into:

```text
24-master-audit-and-chronological-plan.md
30-premium-setup-and-layout-validation.md
```

## Minimum live-trading gate

Before using this workflow in a prop-firm account:

```text
[ ] TradingView Premium active
[ ] CME Group futures data active
[ ] NQ1! / MNQ1! not delayed
[ ] Banksy layout loads
[ ] Alfredo Qpilot layout loads
[ ] Replay workflow works
[ ] First setup has 20 replay examples
[ ] First setup has 20 paper/sim examples
[ ] Rules followed at least 80% of the time
[ ] Stop size fits MNQ/NQ risk plan
[ ] Daily shutdown rule is written and followed
```

## Immediate next step

After upgrading to TradingView Premium:

```text
1. Open 30-premium-setup-and-layout-validation.md
2. Load Banksy Manual Setup
3. Load Alfredo Qpilot Manual Layout
4. Save clean copies of both layouts
5. Begin replay validation with Level Test / Level Sweep setups
```
