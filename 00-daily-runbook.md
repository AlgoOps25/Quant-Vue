# 00 — Daily NQ1! Runbook

Use this every trading morning before taking any setup.

## 1. Pre-market preparation

Complete this before the New York cash open.

- Open TradingView.
- Load **NQ1!** or the active NQ contract.
- Confirm data is flowing correctly.
- Confirm Tradovate connection separately.
- Check the economic calendar.
- Mark major news times.
- Mark prior day high and low.
- Mark overnight high and low.
- Mark weekly high and low if nearby.
- Mark obvious liquidity pools above equal highs / below equal lows.
- Mark visible order blocks and fair value gaps from higher timeframes.
- Decide whether the day is likely trend, range, reversal, or no-trade/chop.

## 2. Chart checklist

### Bias chart

Use a 5-minute NQ chart with SMC V2.

Required visible elements:

- Momentum-colored candles
- Liquidity grabs
- BOS / CHoCH
- Manual structure period 20
- Order blocks
- Previous highs/lows
- New York session box

Optional higher-timeframe confirmation:

- 15-minute fair value gaps
- 4-hour SMC for major BOS/CHoCH and order-block context

### Execution chart

Use NQ Renko:

- 1-second source chart
- Traditional Renko
- 4-box Renko for discretionary Qpro/Qwave/Qline trading
- 5-box Renko only when the strategy specifically requires 5-box Renko

Required tools:

- Qpro V2
- Qcloud
- Qwave
- Qline
- Qbands
- Moneyball
- Qgrid only for pullback/add logic

## 3. Morning bias decision

Choose only one primary mode at a time.

### Long-biased day

Only consider longs when most of the following are true:

- 5-minute SMC shows bullish BOS/CHoCH.
- Price respects bullish order blocks.
- Liquidity grabs below lows reverse upward.
- Qcloud/Qline on execution chart favors long.
- Moneyball supports bullish momentum.
- Trade is not directly into a major resistance level.

### Short-biased day

Only consider shorts when most of the following are true:

- 5-minute SMC shows bearish BOS/CHoCH.
- Price respects bearish order blocks.
- Liquidity grabs above highs reverse downward.
- Qcloud/Qline on execution chart favors short.
- Moneyball supports bearish momentum.
- Trade is not directly into a major support level.

### Neutral/range day

Reduce trade frequency and size. Prefer:

- Qbands outer-band fades
- Liquidity sweeps into known levels
- Midline/mean-reversion targets
- Fast profit-taking

### No-trade day

Stand down when:

- Signals flip repeatedly.
- Qcloud chops back and forth.
- Moneyball is noisy.
- SMC structure is unclear.
- Price is between levels with no clean reward:risk.
- Major news is imminent.

## 4. Trade-quality gate

Before entry, score the trade in `02-confluence-system.md`.

Do not trade unless:

- The setup has at least 7/10 confluence.
- The target gives at least 2R unless it is a deliberately tested scalp system.
- The stop is clearly defined.
- You know the dollar risk before clicking buy/sell in Tradovate.

## 5. Execution workflow

1. TradingView creates the idea.
2. Confirm confluence manually.
3. Open Tradovate order ticket.
4. Use bracket/OCO order.
5. Place stop immediately.
6. Take partials at planned targets.
7. Move stop only according to the plan.
8. Journal the trade immediately after exit.

## 6. Shutdown rules

Stop trading for the day when any one happens:

- Daily max-loss threshold is hit.
- Three consecutive losses occur.
- Two full-risk losses occur.
- You break a rule.
- You enter revenge-trade mode.
- You no longer know whether the day is trending or ranging.

## 7. End-of-day review

Record:

- Setup name
- Bias direction
- Confluence score
- Entry reason
- Stop reason
- Target reason
- R multiple
- Mistake, if any
- Screenshot link or file name

Then classify the day:

- Trend day
- Range day
- Reversal day
- News-driven day
- Chop/no-trade day
