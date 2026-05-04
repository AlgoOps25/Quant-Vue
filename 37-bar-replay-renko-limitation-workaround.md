# 37 — Bar Replay Renko Limitation Workaround

TradingView Bar Replay does not support non-traditional chart types such as:

```text
Renko
Kagi
Point & Figure
Range
Line Break
Volume footprint
Time Price Opportunity
Tick-based charts
```

Therefore, the original replay plan must be adjusted.

## Key correction

The Banksy and Alfredo execution charts use Renko / seconds / volume-style charts.

Those layouts are useful for live chart reading and forward testing, but TradingView Bar Replay cannot be run directly from the Renko chart.

## Updated workflow

Use a two-part validation process:

```text
1. Bar Replay on standard time-based candles for level/location practice.
2. Live market forward testing on Renko layouts for execution practice.
```

## What Bar Replay is still useful for

Use Bar Replay on normal candles to practice:

```text
Marking prior day high/low
Marking overnight high/low
Marking 15m swing highs/lows
Identifying level tests
Identifying level sweeps
Recognizing CHoCH / BOS behavior
Practicing patience before a level is touched
```

## What Bar Replay is not useful for

Do not use TradingView Bar Replay for:

```text
Renko execution timing
Qbank Renko trailing behavior
1-second Renko entry timing
Qgrid add-to-winner timing
Volume candle replay
```

## Replacement plan for Renko validation

For Renko, use live market forward testing instead:

```text
Use market replay/forward observation during live hours.
Do not place real trades.
Log candidates in real time.
Use paper/sim only after several observation sessions.
```

## New validation sequence

## Phase A — Candle replay for location

Use a standard chart:

```text
NQ1! or MNQ1!
Chart type: Candles
Timeframes: 15m, 5m, 2m, or 1m
```

Practice:

```text
Level Test
Level Sweep
Opening range behavior
BOS / CHoCH at levels
```

## Phase B — Live/forward Renko observation

Use the Banksy layout during live market hours:

```text
NQ QuantVue Banksy Manual Setup - Working Copy
```

Observe only:

```text
How Renko prints after level tests/sweeps
How Q_Pro / Qbank react after the level reaction
How late/early Bull/Bear labels appear
Where a realistic stop would be
Whether entries are chasey or clean
```

## Phase C — Paper/sim execution

Only after Phase A and B:

```text
Use Tradovate sim or TradingView paper trading.
Practice MNQ only first.
Do not use NQ until MNQ execution is consistent.
```

## Practical first session now

Because Replay cannot run on Renko:

```text
1. Open a normal NQ1! candle chart.
2. Use 15m chart for levels.
3. Use 5m or 2m chart for replay execution practice.
4. Replay one RTH session.
5. Mark level tests/sweeps.
6. Screenshot candidates.
7. Then compare live/forward Renko behavior on a future session.
```

## Recommended chart layout for replay

Use a simple replay-only layout:

```text
Chart 1: NQ1! 15m candles — levels/context
Chart 2: NQ1! 5m candles — structure
Chart 3: NQ1! 1m or 2m candles — execution practice
```

Avoid Renko in Replay.

## Updated first validation goal

First goal:

```text
20 candle-replay examples of Level Test / Level Sweep
```

Second goal:

```text
10 live/forward Renko observations of the same setup type
```

Only then move to paper/sim execution.

## Decision

TradingView Premium is still useful because the QuantVue layouts require seconds/volume features, but Bar Replay cannot replay Renko itself.

Premium solves the layout-loading problem, not the non-traditional-chart Replay limitation.
