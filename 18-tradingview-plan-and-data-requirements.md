# 18 — TradingView Plan and Data Requirements

This document tracks the practical TradingView requirements for running the QuantVue-first workflow.

## Important note

TradingView plan limits and exchange-data pricing can change. Verify the current plan limits and data packages inside TradingView before subscribing.

## Recommended setup

For the QuantVue Pro workflow, the practical recommendation is:

```text
TradingView Premium or higher
CME real-time futures market data
QuantVue Pro subscription
Tradovate connected for manual execution
```

## Why Premium is recommended

The planned workflow uses:

- Multiple QuantVue invite-only indicators
- Multiple charts in one layout
- Renko execution chart
- 1-second source / second-based charting if available
- Multiple alerts
- Replay testing
- Saved layouts

A lower TradingView plan may work for a stripped-down two-chart layout, but Premium is safer for the intended workflow.

## Minimum practical layout

A 2-chart layout can work:

```text
Left: 5m SMC Bias
Right: Renko 4 Execution with Qpro + Moneyball
```

This may fit a lower paid plan if it supports the required number of indicators, alerts, and chart types.

## Preferred layout

A 4-chart layout is preferred:

```text
Top Left: 5m SMC Bias
Top Right: Renko 4 Execution
Bottom Left: 15m OR / FVG Context
Bottom Right: 3m OR or MNQ Practice
```

This likely requires a higher TradingView plan because of multi-chart layout limits.

## Data required for NQ/MNQ

NQ and MNQ are CME futures products.

For real-time charting in TradingView, subscribe to the appropriate CME real-time futures data package inside TradingView.

Practical requirement:

```text
CME real-time futures data for NQ/MNQ
```

Without this, TradingView may show delayed data even if Tradovate is connected.

## Tradovate note

Tradovate is for execution.

TradingView charting still needs real-time data entitlements inside TradingView unless the broker integration/data entitlement satisfies the specific TradingView chart requirements.

Verify inside TradingView:

```text
Chart should not say delayed
NQ1! and MNQ1! should update in real time
Orders should route through the correct Tradovate account
```

## What to verify before paying

In TradingView, confirm:

- Number of charts per layout
- Number of indicators per chart
- Number of active alerts
- Whether second-based intervals are included
- Whether Renko settings support the desired source resolution
- Whether Bar Replay works for the timeframes you need
- CME real-time data package availability
- Non-professional market data status if applicable

## Recommended buying order

1. Subscribe to QuantVue Pro.
2. Use at least a TradingView paid plan.
3. Prefer Premium or higher if building the 4-chart layout and 1-second Renko workflow.
4. Add CME real-time futures data.
5. Connect Tradovate.
6. Confirm NQ1!/MNQ1! are real-time, not delayed.
7. Build the layout.
8. Begin replay/paper validation.

## Decision

For this repo's intended workflow, use:

```text
Best recommendation: TradingView Premium or higher + CME real-time futures data
Budget/minimum test: lower paid TradingView plan + CME real-time data + 2-chart layout
Avoid: Free plan for the full QuantVue Pro workflow
```