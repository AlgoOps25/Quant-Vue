# 44 — TradingView Strategy Tester vs Replay Trading Guide

The user opened TradingView Bar Replay and saw the bottom panel labeled:

```text
Replay Trading
Historical data trading
Metrics
List of trades
No data here, yet
Start trading in Bar Replay mode.
```

This is not the Pine Strategy Tester. It is TradingView's Replay Trading panel.

## Key correction

There are two different trade-list systems in TradingView:

```text
1. Strategy Tester
2. Replay Trading / Paper Trading trade list
```

## Strategy Tester

Strategy Tester is used for Pine `strategy` scripts.

It creates trades automatically if the script contains strategy logic such as:

```text
strategy.entry()
strategy.exit()
strategy.close()
```

Most invite-only indicators do not appear as strategy results unless the vendor published a separate strategy/backtest version.

## Replay Trading

Replay Trading lets the user manually place simulated trades while Bar Replay is running.

It can create:

```text
Metrics
List of trades
Manual replay order history
```

But only after the user actually places Buy/Sell orders during replay.

If no trades were placed, it will show:

```text
No data here, yet
Start trading in Bar Replay mode.
```

## What the screenshot means

The screenshot shows:

```text
Bar Replay is active
Replay Trading panel is open
Historical data trading is selected
No trades have been placed yet
QuantVue Q_Pro and Qmomentum are on the chart
```

This does not prove Q_Pro is backtestable as a Pine strategy.

It means the user can manually practice trades in Bar Replay and TradingView will track those manual replay trades.

## How to find Strategy Tester

Try these options:

```text
Bottom panel tabs: Pine Editor / Strategy Tester / Trading Panel
If the tabs are hidden, expand the bottom panel
Look for a three-dot or menu icon on the bottom panel
Close or minimize Replay Trading to reveal the normal bottom tabs
Use TradingView layout reset if the panel is hidden
```

If Strategy Tester still does not appear, the active panel may be locked into Replay Trading while Bar Replay is running.

Stop Bar Replay and check the normal bottom panel again.

## How to test whether QuantVue is a strategy

Use a normal candle chart, not Renko.

```text
1. Stop Bar Replay.
2. Open a clean NQ1! 5-minute candle chart.
3. Add only one QuantVue script, such as Q_Pro V2.0.
4. Open Strategy Tester from the bottom panel.
5. Check whether performance data appears automatically.
```

If nothing appears in Strategy Tester:

```text
That script is likely indicator-only.
```

If performance appears:

```text
That script has strategy/backtest support.
```

## How to use Replay Trading manually

If using the panel shown in the screenshot:

```text
1. Start Bar Replay on a supported chart type, such as candles.
2. Let price play forward.
3. When a valid setup appears, click Trade.
4. Place Buy or Sell manually.
5. Add stop/target if available.
6. Continue replay.
7. Close the trade manually or let stop/target close it.
8. Review Metrics and List of trades.
```

## Recommended use for QuantVue project

Use both tools for different purposes:

```text
Replay Trading = manual practice and trade list during candle replay
Strategy Tester = only if QuantVue provides a strategy/backtest version
Forward Observation = required for Renko layouts because Bar Replay does not support Renko
```

## Immediate next step

Since the screenshot shows Replay Trading is working, the user should test manual replay trading first:

```text
1. Start Bar Replay on NQ1! 5m candles.
2. Wait for a Level Test / Level Sweep.
3. Click Trade.
4. Place a small simulated Buy/Sell trade.
5. Close it after target/stop.
6. Open List of trades.
7. Confirm the trade appears.
```

This gives an automated trade list for manual replay trades, even if QuantVue itself is not running a Pine strategy backtest.
