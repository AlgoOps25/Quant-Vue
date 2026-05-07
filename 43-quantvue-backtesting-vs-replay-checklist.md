# 43 — QuantVue Backtesting vs Replay Checklist

The user noticed QuantVue may be backtestable. This document clarifies how to verify that inside TradingView.

## Key distinction

TradingView has three separate concepts:

```text
1. Bar Replay
2. Strategy Tester
3. Indicator signals / alerts
```

They are not the same.

## Bar Replay

Bar Replay replays chart candles/bars visually.

Limitations:

```text
Does not work on Renko, Range, Kagi, Point & Figure, Line Break, Volume Footprint, TPO, or tick-based charts
Does not automatically generate a trade list from indicators
Useful for practicing candle-based levels, structure, and decision-making
```

## Strategy Tester

Strategy Tester only works if the script is a Pine `strategy`, not a Pine `indicator`.

A strategy can generate:

```text
List of trades
Net profit
Profit factor
Drawdown
Win rate
Entry/exit markers
Performance summary
```

## Indicator-only tools

Most TradingView indicators can show signals and create alerts, but they do not automatically create a Strategy Tester trade list.

Indicators can still be useful for forward testing and manual journaling.

## How to check if a QuantVue script is backtestable

For each QuantVue script, do this:

```text
1. Add the script to a normal candle chart first, not Renko.
2. Open the bottom panel in TradingView.
3. Click Strategy Tester.
4. Look for performance data.
5. If Strategy Tester shows trades/performance, the script is a strategy or has strategy-like backtest support.
6. If Strategy Tester says no data, no strategy, or stays blank, it is likely indicator-only.
```

## Scripts to check

Check these one by one:

```text
QuantVue Q_Pro V2.0
QuantVue Q_Pilot Pro V1.0
QuantVue SMC V2.0
QuantVue Moneyball V2.0
QuantVue Momentum V2.0
QuantVue Qgrid
QuantVue Qbank_Pro V1.0
```

## Test chart to use first

Use a normal candle chart:

```text
Symbol: NQ1! or MNQ1!
Chart type: Candles
Timeframe: 1m, 3m, 5m, or 15m
```

Do not start this test on Renko because Replay has Renko restrictions and some strategy/backtest behavior may be harder to interpret on non-standard charts.

## What to record for each indicator

```text
Indicator name:
Chart type:
Timeframe:
Does it appear in Strategy Tester? Y/N
Does it generate trades? Y/N
Does it show entry/exit markers? Y/N
Can settings be changed? Y/N
Does changing settings change results? Y/N
Does it repaint or warn about repainting? Y/N
Notes:
```

## If QuantVue provides an official backtesting mode

Some vendors include an internal backtesting module or a separate strategy version of an indicator.

Look for:

```text
A separate script with Strategy, Backtest, or Tester in the name
Inputs such as Show Backtest, Enable Strategy, TP, SL, Risk/Reward, Backtest Window
Performance table on the chart
Long/Short entry and exit labels with P&L
```

If found, treat that as the official QuantVue backtesting path.

## If Strategy Tester works

If a QuantVue strategy produces trades, use this workflow:

```text
1. Save the default settings as baseline.
2. Export or screenshot performance summary.
3. Change only one setting.
4. Re-run Strategy Tester.
5. Compare net profit, max drawdown, number of trades, profit factor, and average trade.
6. Avoid choosing the highest net profit if drawdown or trade count is unrealistic.
```

## If Strategy Tester does not work

Continue with:

```text
Forward observation
Manual journaling
Selective alerts
Paper/sim execution
```

## First action

Test `QuantVue Q_Pro V2.0` on a normal NQ1! 5-minute candle chart:

```text
1. New chart
2. Symbol NQ1!
3. Chart type Candles
4. Timeframe 5m
5. Add QuantVue Q_Pro V2.0 only
6. Open Strategy Tester
7. Check whether trades/performance appear
```

Then repeat for Q_Pilot, Qbank, Qgrid, Moneyball, Momentum, and SMC.
