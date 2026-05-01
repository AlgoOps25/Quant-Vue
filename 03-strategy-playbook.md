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

### Source screenshots

Screenshot Set #7 was captured from `Simple 3-Minute Opening Range Futures Strategy - Strategy #5`.

Captured examples:

- Opening range breakout chart on **S&P 500 E-mini Futures 3-minute chart**.
- Aqua opening range high/low box.
- Large bullish breakout candle through the opening range.
- Qpro settings panels from the strategy video.
- Moneyball_Q settings panel from the strategy video.

Important adaptation note:

- The video example is on **ES**, not NQ.
- For this repo, use the same logic on NQ/MNQ, but validate stop size and volatility separately because NQ moves faster and farther than ES.

### Confirmed settings shown in the Strategy #5 screenshots

#### Moneyball_Q settings

| Setting | Confirmed value |
|---|---|
| Number of bars between signals | 15 |
| Mode | M |
| Period | 2 |
| All Zero | ON |
| Upper Threshold | 0.35 |
| Lower Threshold | -0.35 |
| Reactivity | 0.1 |

#### Qpro/Qcloud settings shown

| Setting | Confirmed value |
|---|---|
| Qcloud Period 1 | 19 |
| Qcloud Period 2 | 29 |
| Qcloud Period 3 | 49 |
| Qcloud Period 4 | 59 |
| Qcloud Period 5 | 69 |
| Qcloud Period 6 | 99 |

#### Qbands settings shown

Two panels were captured. Treat these as strategy-video examples, not the main NQ Renko baseline.

| Setting | Confirmed value |
|---|---|
| Use Qbands | ON |
| Qbands Source | Weighted |
| Qbands Length | 155 in one panel; 77 in another panel |
| ATR Lookback / Lookback Distance | 256 |
| Band Deviation | 6.8 in one panel; 5 in another panel |
| Trend Period | 20 |
| Center Line Up | Green |
| Center Line Down | Red |

#### Qwave settings shown

| Setting | Confirmed value |
|---|---|
| Use Qwave | ON |
| Trading Session | 08:30–16:00 shown in one panel |
| Timezone | UTC-5 shown in one panel |
| Price To Use | Weighted |
| APB Bars Back | 33 |
| ATR Bars Back | 256 |
| Qwave Band Deviation | 1.5 |
| Show Qwave ADD Alerts? | ON in one panel |

#### Qline settings shown

| Setting | Confirmed value |
|---|---|
| Use Qline | ON |
| Qline Source | close |
| Qline Length | 9 |
| Qline Multiplier | 0.1 |
| Qline Common Period | 39 |
| Qline Reactivity | 0.4 |
| Qline Ribbon | ON in one panel |

### Best market condition

- Strong volume at market open.
- Opening range is clean and obvious.
- Price breaks the opening range decisively.
- Qpro/Qcloud direction agrees with the breakout.
- Moneyball supports the breakout direction.
- The breakout has room before the next major level.

### Setup

1. On a 3-minute chart, mark the opening range high and low.
2. Wait for a decisive break above or below the range.
3. Do not chase if the breakout candle is already too extended.
4. Prefer a retest of the opening range boundary.
5. Confirm with Qpro/Qcloud direction.
6. Confirm with Moneyball momentum.
7. Enter only if the stop can sit on the other side of the retest/range and target gives acceptable R.

### Long opening-range breakout

A valid long requires:

- Price breaks above the opening range high.
- Breakout candle closes strong or price retests the OR high as support.
- Qcloud/Qpro is bullish.
- Moneyball_Q is above zero or printing bullish confirmation.
- Target is not directly into a major resistance/order block.

### Short opening-range breakout

A valid short requires:

- Price breaks below the opening range low.
- Breakout candle closes strong or price retests the OR low as resistance.
- Qcloud/Qpro is bearish.
- Moneyball_Q is below zero or printing bearish confirmation.
- Target is not directly into a major support/order block.

### Stop

- Long: below the opening range high retest, below the breakout candle low, or below the range depending on volatility.
- Short: above the opening range low retest, above the breakout candle high, or above the range depending on volatility.

### Targets

- Target 1: measured move equal to range height or nearest structure.
- Target 2: prior day high/low, overnight high/low, Qwave/Qbands level, or opposing liquidity.

### Avoid

- Entering before the range is defined.
- Entering on a fakeout without close/retest confirmation.
- Chasing a huge candle after the move already expanded.
- Trading the breakout directly into red/green opposing zones.
- Using ES settings blindly on NQ without testing.

## Strategy 7 — 15-Minute Opening Range Retest

### Source screenshots

Screenshot Set #8 was captured from `How To Use QuantVue & The 15-Minute Opening Range - Strategy #7`.

Captured examples show:

- Multi-chart NQ layout.
- NQ 1-second / Renko execution view.
- NQ 3-minute Renko execution view.
- NQ 5-minute and 15-minute context views.
- Yellow 15-minute opening range high/low levels drawn across the layout.
- Purple higher-timeframe zones / fair value gap style areas.
- Qcloud/Qpro trend context on Renko charts.
- Moneyball momentum pane showing bearish momentum expansion.
- Marked/circled areas showing rejection, retest, continuation, and target zones.

### Best market condition

- The first 15-minute opening range is clear.
- Price breaks the 15-minute range and then retests one side.
- Multiple charts agree: 15m context, 5m structure, and Renko execution all point the same way.
- Moneyball confirms direction.
- Qpro/Qcloud on execution chart supports the direction.
- There is enough room to the next higher-timeframe level or FVG/zone.

### Setup

1. Mark the first 15-minute opening range high and low.
2. Extend those levels across the active charts.
3. Wait for price to break out of the range.
4. Do not chase the first impulse if it is already extended.
5. Wait for retest or rejection around the 15-minute OR level.
6. Confirm direction on execution Renko chart with Qpro/Qcloud/Qline.
7. Confirm momentum with Moneyball.
8. Check the 5m/15m chart for opposing FVGs, order blocks, or major levels.
9. Enter only when stop and target are obvious.

### Long 15-minute OR setup

A valid long requires:

- Price breaks above the 15-minute OR high.
- Retest holds the OR high as support.
- Qpro/Qcloud turns or stays bullish on execution chart.
- Moneyball supports upward momentum.
- 5m/15m context does not show immediate major resistance directly overhead.
- Target is next liquidity, prior high, Qwave/Qbands level, or higher-timeframe zone.

### Short 15-minute OR setup

A valid short requires:

- Price breaks below the 15-minute OR low.
- Retest rejects the OR low as resistance.
- Qpro/Qcloud turns or stays bearish on execution chart.
- Moneyball supports downward momentum.
- 5m/15m context does not show immediate major support directly underneath.
- Target is next liquidity, prior low, Qwave/Qbands level, or higher-timeframe zone.

### Stop

- Long: below the retest low or back inside the 15-minute range.
- Short: above the retest high or back inside the 15-minute range.

### Targets

- Target 1: next intraday swing or 1R/2R depending on stop size.
- Target 2: higher-timeframe zone, FVG edge, prior high/low, or opposing liquidity.
- Runner: trail with Qline, Qcloud, or structure if trend day develops.

### Avoid

- Chasing the first candle after the range break.
- Trading into a purple FVG/zone directly in front of price.
- Taking the trade when Renko execution and 15m context disagree.
- Taking the trade after Moneyball has already exhausted and reversed.
- Entering when the stop must be too wide for prop-firm risk.

## Strategy 8 — 8am Candle Retest

### Source screenshot

Screenshot Set #6 includes an `8am Candle Retest - Strategy #9` example around **1:13**.

The captured example shows:

- A major bullish trend leg beginning near the 8am candle/zone area.
- A yellow trendline following the impulse move.
- Qcloud/Qpro support underneath price.
- Green SMC/structure levels below price.
- Red resistance/supply area above price.
- A clean idea: mark the 8am zone, wait for reaction/retest, then trade continuation if structure confirms.

### Best market condition

- Clear 8am candle range or zone.
- Price leaves the 8am zone with strength.
- Price later retests or respects that zone.
- The retest aligns with Qpro/Qcloud, SMC structure, or a trendline.
- There is open room to the next liquidity target.

### Setup

1. At 8am, mark the candle high, low, and body zone.
2. Note whether price immediately expands away from that candle.
3. Wait for price to return to the zone or to use that zone as support/resistance.
4. Check SMC structure: BOS/CHoCH should support the direction.
5. Check Qpro/Qcloud: trend-state should agree with the trade.
6. Check Qline/Moneyball for trigger confirmation.
7. Trade away from the 8am zone toward the next liquidity/level.

### Long 8am retest

A valid long requires:

- Price leaves the 8am zone upward or reclaims it after a sweep.
- Retest holds the zone as support.
- Qcloud/Qline turns or remains bullish.
- SMC supports bullish structure.
- Target is not directly into a major red resistance zone.

### Short 8am retest

A valid short requires:

- Price leaves the 8am zone downward or loses it after a sweep.
- Retest rejects the zone as resistance.
- Qcloud/Qline turns or remains bearish.
- SMC supports bearish structure.
- Target is not directly into a major green support zone.

### Stop

- Long: below the retest low or below the 8am zone.
- Short: above the retest high or above the 8am zone.

### Targets

- First target: nearest structure level, Qwave/Qbands midline, or prior intraday swing.
- Second target: prior day high/low, overnight high/low, or next SMC liquidity level.

### Avoid

- Chasing after price has already gone vertical.
- Entering directly under a large red resistance block.
- Trading the 8am zone when the day is chopping and Qcloud is flipping repeatedly.

## Strategy 9 — Zone Strategy

### Source screenshot

Screenshot Set #6 includes a `Simple "ZONE" Strategy - Strategy #10` example around **0:44**.

The captured example shows a multi-chart layout with:

- 5-minute NQ chart for larger structure.
- Smaller execution views for trigger timing.
- Yellow horizontal zone/level drawn across charts.
- QuantVue Elite directional labels on lower panels.
- The main idea: define the zone first, then wait for price reaction and confirmation.

### Best market condition

- Clean 2m/5m structure.
- Price repeatedly respects a supply/demand zone.
- The zone aligns with prior high/low, SMC level, order block, FVG edge, or high-volume reaction area.
- The level is visible across multiple timeframes.

### Setup

1. Identify a high-probability zone before entry.
2. Draw the zone as a horizontal area, not a single perfect line.
3. Wait for price to revisit the zone.
4. Confirm reaction: wick, rejection, reclaim, BOS/CHoCH, Qline flip, or Moneyball confirmation.
5. Enter only after reaction, not while price is blindly falling/rising into the zone.
6. Stop goes outside the zone.
7. Target goes to the next opposing zone or liquidity pool.

### Long zone trade

A valid long requires:

- Price enters demand/support zone.
- Price rejects lower prices or reclaims the zone.
- SMC or Qpro confirms bullish reaction.
- Stop can be placed below the zone.
- Target gives at least 2R or a clearly tested scalp expectancy.

### Short zone trade

A valid short requires:

- Price enters supply/resistance zone.
- Price rejects higher prices or loses the zone.
- SMC or Qpro confirms bearish reaction.
- Stop can be placed above the zone.
- Target gives at least 2R or a clearly tested scalp expectancy.

### Avoid

- Drawing too many zones.
- Trading the middle of a wide zone.
- Taking a zone trade with no confirmation.
- Taking a zone trade directly into the next opposing zone.

## Strategy 10 — Candlestick Chart Strategy

Use when you cannot or do not want to trade Renko.

### Recommended use

- NQ/MNQ 5-minute candlesticks.
- SMC for structure.
- Qpro/Qcloud for trend.
- Moneyball for momentum.
- Use fewer signals and wider stops than Renko.

## Strategy 11 — Broad Alert Workflow

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
| Clean breakout | 3-minute OR breakout/retest or 15-minute OR retest |
| Already in profit | Qgrid add-to-winner |
| Unclear | No trade |
