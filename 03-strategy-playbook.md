# 03 — Strategy Playbook

This file converts the QuantVue video concepts into practical NQ1! setups.

## Strategy 1 — Qwave Band Reversal to Midline

### Best market condition

- Range day
- Exhaustion move
- Sweep into prior high/low
- Price reaches outer Qwave/Qbands area

### Long entry

1. Price pushes into or through lower Qwave/Qbands area.
2. SMC shows liquidity grab or bullish CHoCH.
3. Qline flips bullish or starts supporting price.
4. Moneyball confirms bullish momentum.
5. Enter long only if target to midline provides acceptable R.

### Short entry

1. Price pushes into or through upper Qwave/Qbands area.
2. SMC shows liquidity grab or bearish CHoCH.
3. Qline flips bearish or starts rejecting price.
4. Moneyball confirms bearish momentum.
5. Enter short only if target to midline provides acceptable R.

### Stop

- Beyond the sweep high/low or beyond the outer band structure.

### Targets

- Target 1: Qwave/Qbands midline.
- Target 2: opposite band or next major level.

## Strategy 2 — Qcloud Trend Continuation

### Best market condition

- Trend day
- Opening drive
- Breakout from range
- Clear SMC BOS in same direction

### Long entry

1. 5m SMC is bullish.
2. Qcloud is bullish or flips bullish.
3. Pullback holds Qline/Qcloud or bullish order block.
4. Moneyball stays bullish.
5. Enter on continuation trigger.

### Short entry

1. 5m SMC is bearish.
2. Qcloud is bearish or flips bearish.
3. Pullback rejects Qline/Qcloud or bearish order block.
4. Moneyball stays bearish.
5. Enter on continuation trigger.

### Stop

- Beyond pullback structure.
- Beyond Qcloud/Qline invalidation area.

### Targets

- Prior high/low.
- Qwave band.
- Measured move.
- Trail with Qline or Qcloud depending on speed.

## Strategy 3 — Qline Flip Entry / Exit

### Best market condition

- Price reacts from a known level.
- Qwave/Qbands location is clear.
- Need a fast confirmation trigger.

### Entry

- Use Qline flip after price reacts from band, level, order block, or liquidity zone.

### Exit

- Exit when Qline flips against the trade.
- For faster scalping, test lower Qline length such as 5.

### Warning

Qline alone is not enough. Use it after location and structure are already known.

## Strategy 4 — Qgrid Add-to-Winner

### Source screenshots

Screenshot Set #5 was captured from `Using "Qgrid" To Pass Prop Challenges! - Strategy Series #13`.

Captured examples:

- **2:37** — Initial long example on NQ 5-minute candlestick chart with green target and red stop drawn on chart.
- **5:08** — Qgrid Bull / Qgrid Bear visual showing step moving average, pullbacks, and continuation dots.
- **Later close-up** — Long continuation example showing target 25.00 points, stop 12.50 points, and risk/reward ratio 2.

### Best market condition

- Existing trade is already profitable.
- Trend remains intact.
- Pullback is controlled.
- Price is above the relevant step moving average for longs or below it for shorts.
- Qgrid prints a dot/ADD signal in the direction of the existing profitable trade.

### Initial-entry rule

Qgrid can identify directional pullbacks, but for prop-firm use the safer model is:

1. Take the initial position from a separate valid setup.
2. Example initial setups can be SMC structure, Qcloud trend continuation, Qline flip from level, opening range retest, or Qwave/Qbands reaction.
3. Use Qgrid as confirmation that the pullback is continuing in your favor.

### Add-to-winner rule

1. Enter initial position from another valid setup.
2. Wait for the trade to move into open profit.
3. Wait for a controlled pullback.
4. Confirm the pullback does **not** invalidate structure.
5. Add only when Qgrid prints ADD/dot in the original trade direction.
6. Added risk must still fit the prop-firm daily loss plan.
7. If adding makes total risk unclear, do not add.

### Long example logic

A valid long add requires:

- Existing long is green/open profit.
- Price remains above or reclaims the Qgrid step moving average.
- Pullback is shallow and controlled.
- Qgrid Bull / cyan dot appears.
- Stop can be placed below the pullback/structure.
- Target still offers acceptable R, ideally around 2R or better.

### Short example logic

A valid short add requires:

- Existing short is green/open profit.
- Price remains below or rejects the Qgrid step moving average.
- Pullback is shallow and controlled.
- Qgrid Bear / blue dot appears.
- Stop can be placed above the pullback/structure.
- Target still offers acceptable R, ideally around 2R or better.

### Hard rule

Never use Qgrid to average down a losing prop-firm trade.

If the original trade is red, Qgrid is **not** permission to add. It is a warning to reassess risk.

### Prop-firm simplification

For evaluations or funded accounts:

- Use Qgrid adds only after the first target or break-even move.
- Use MNQ while learning the add-on logic.
- Do not add during news candles.
- Do not add into prior high/low, daily level, or major opposing order block.
- Journal every Qgrid add separately.

## Strategy 5 — SMC Liquidity Sweep Reversal

### Best market condition

- Price sweeps obvious highs/lows.
- Sweep occurs near prior day high/low, overnight high/low, order block, FVG, or Qwave/Qbands edge.

### Long entry

1. Price sweeps sell-side liquidity below lows.
2. Price reclaims level.
3. SMC prints bullish CHoCH or BOS.
4. Qline/Moneyball confirms.
5. Target midrange, session open, or opposing liquidity.

### Short entry

1. Price sweeps buy-side liquidity above highs.
2. Price rejects level.
3. SMC prints bearish CHoCH or BOS.
4. Qline/Moneyball confirms.
5. Target midrange, session open, or opposing liquidity.

## Strategy 6 — Opening Range Breakout / Retest

### Best market condition

- Strong volume at New York open.
- Opening range forms cleanly.
- Higher timeframe has room in breakout direction.

### Setup

1. Mark opening range.
2. Wait for break and retest.
3. Confirm with SMC structure.
4. Confirm with Qcloud/Qline/Moneyball.
5. Enter only if not chasing extension.

### Avoid

- First candle impulse without retest.
- Breakout directly into major level.
- News spike without structure.

## Strategy 7 — 8am Candle Retest

### Best market condition

- Clear 8am candle range.
- Price returns to 8am level later.
- Liquidity and structure align.

### Setup

1. Mark 8am candle high/low/body zone.
2. Wait for retest.
3. Use SMC and Qpro to confirm reaction.
4. Trade away from the zone toward next liquidity/level.

## Strategy 8 — Zone Strategy

### Best market condition

- Clean 2m/5m structure.
- Price repeatedly respects a supply/demand zone.

### Setup

1. Mark zone from SMC/order-block context.
2. Wait for price to revisit.
3. Use Qline/Moneyball/Qcloud to confirm direction.
4. Enter only with clear stop beyond zone.

## Strategy 9 — Candlestick Chart Strategy

Use when you cannot or do not want to trade Renko.

### Recommended use

- NQ/MNQ 5-minute candlesticks.
- SMC for structure.
- Qpro/Qcloud for trend.
- Moneyball for momentum.
- Use fewer signals and wider stops than Renko.

## Strategy 10 — Broad Alert Workflow

Broad alerts should be treated as watchlist pings.

### Use them to say:

- “Look at the chart now.”
- “A possible setup is forming.”
- “Check whether confluence exists.”

### Do not use them to say:

- “Enter automatically.”
- “Ignore SMC.”
- “Ignore stop/target math.”

## Strategy selection by day type

| Day type | Preferred strategy |
|---|---|
| Opening drive trend | Qcloud trend continuation, Qline exit |
| Range/chop | Qwave/Qbands mean reversion only, or stand down |
| Liquidity sweep reversal | SMC sweep reversal + Qline/Moneyball confirmation |
| Clean breakout | Opening range breakout/retest |
| Already in profit | Qgrid add-to-winner |
| Unclear | No trade |
