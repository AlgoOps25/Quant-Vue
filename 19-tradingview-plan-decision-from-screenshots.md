# 19 — TradingView Plan Decision From Screenshots

The user provided screenshots of TradingView subscription tiers and market-data streams.

## Decision

For the QuantVue-first workflow, the practical recommendation remains:

```text
TradingView Premium or higher
+ CME real-time futures data
+ QuantVue Pro
+ Tradovate manual execution
```

## Why Premium is the best fit

The intended workflow uses:

- Multi-chart layouts
- Multiple QuantVue invite-only indicators
- Renko execution chart
- Potential second-based charting / 1-second source behavior
- Multiple alerts
- Bar Replay
- Saved layouts
- Futures market data

A lower plan may work for a stripped-down two-chart version, but Premium is the safer baseline for the full workflow.

## Market data requirement

For NQ1! / MNQ1!, the user should subscribe to the CME real-time futures market data package inside TradingView.

After subscribing, verify:

```text
NQ1! chart does not say delayed
MNQ1! chart does not say delayed
Bid/ask updates in real time
TradingView + Tradovate account routing is correct
```

## Practical setup options

### Best setup

```text
TradingView Premium
CME real-time futures data
QuantVue Pro
Tradovate connected
```

### Budget setup

```text
Lower paid TradingView plan
CME real-time futures data
2-chart layout only
QuantVue Pro
Tradovate connected
```

Risk: may run into chart, indicator, alert, or second-based charting limitations.

## Action item

Before purchasing, confirm in TradingView checkout:

- The selected plan supports enough charts per layout.
- The selected plan supports enough indicators per chart.
- The selected plan supports enough alerts.
- Second-based timeframes are available if needed.
- CME real-time data is included as a separate data subscription.

## Final recommendation

Use Premium unless there is a strong budget reason not to.

Do not rely on the free plan for this workflow.