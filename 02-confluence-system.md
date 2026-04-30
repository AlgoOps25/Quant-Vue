# 02 — QuantVue Confluence System

The goal is not to take every alert. The goal is to score each idea and only trade the cleanest setups.

## 1. Trade score

Score every trade out of 10 before entry.

| Category | Points | What to check |
|---|---:|---|
| Higher-timeframe context | 2 | 5m/15m/4h structure supports the idea |
| SMC structure | 2 | BOS/CHoCH, liquidity grab, or order block supports direction |
| Location | 2 | Trade begins at level, band, OB, FVG, prior high/low, or opening range |
| QuantVue trigger | 2 | Qcloud/Qline/Qwave/Moneyball/Qgrid trigger is clear |
| Risk/reward | 2 | Stop and target are clean, with at least 2R expected |

Minimum requirements:

- **9–10:** A+ setup. Trade only if risk is controlled.
- **7–8:** Valid setup. Normal risk or reduced risk.
- **5–6:** Watch only. Needs more confirmation.
- **0–4:** No trade.

## 2. Required confluence layers

### Layer 1 — Market context

Ask:

- Are we near prior day high/low?
- Are we near overnight high/low?
- Are we near a major order block?
- Are we inside or outside a fair value gap?
- Are we in New York open, lunch chop, power hour, or overnight?
- Is there scheduled news?

### Layer 2 — SMC structure

Bullish structure:

- Liquidity sweep below lows followed by push higher
- CHoCH to upside
- BOS to upside
- Bullish order block respected
- Higher low forms into market open

Bearish structure:

- Liquidity sweep above highs followed by push lower
- CHoCH to downside
- BOS to downside
- Bearish order block respected
- Lower high forms into market open

### Layer 3 — Location

Good long locations:

- Lower Qwave/Qbands area
- Bullish order block
- Prior resistance turning support
- Opening range retest
- 8am candle retest zone
- 50% FVG fill or FVG edge
- Golden pocket pullback with bullish confirmation

Good short locations:

- Upper Qwave/Qbands area
- Bearish order block
- Prior support turning resistance
- Opening range rejection
- 8am candle retest failure
- 50% FVG fill or FVG edge
- Golden pocket pullback with bearish confirmation

Bad locations:

- Middle of range
- Directly into opposing level
- After extended move with no pullback
- During chop where Qcloud flips repeatedly

### Layer 4 — QuantVue trigger

Valid triggers include:

- Qline flip after Qwave/Qbands band interaction
- Qcloud full flip in direction of structure
- Moneyball diamond aligned with structure and location
- Qgrid ADD/dot after trade is already profitable
- Qwave breakout that aligns with Qcloud/Qline and higher-timeframe context

Invalid triggers:

- Raw alert with no location
- Qcloud flip during chop
- Moneyball diamond against 5m SMC structure
- Qgrid add signal while original trade is losing
- Qwave signal directly into prior high/low without room to target

### Layer 5 — Risk/reward

Before entry, define:

- Entry price
- Stop price
- Stop size in points
- Dollar risk per contract
- Target 1
- Target 2
- Break-even rule
- Invalidation reason

General rule:

- Prefer **2R minimum**.
- Faster scalp systems may use less than 2R only after replay testing proves win rate.

## 3. Example confluence templates

### A+ Long

- 5m SMC bullish CHoCH/BOS
- Price sweeps liquidity below overnight low and reclaims
- Price is at lower Qwave/Qbands area
- Qline flips green
- Moneyball confirms bullish momentum
- Target to midline gives at least 2R

### A+ Short

- 5m SMC bearish CHoCH/BOS
- Price sweeps prior day high and rejects
- Price is at upper Qwave/Qbands area
- Qline flips red
- Moneyball confirms bearish momentum
- Target to midline gives at least 2R

### Trend continuation long

- 5m trend is bullish
- Qcloud is bullish
- Pullback holds Qline/Qcloud or bullish order block
- Moneyball stays supportive
- Entry is near support, not late into extension
- Target is next high, Qwave band, or measured level

### Trend continuation short

- 5m trend is bearish
- Qcloud is bearish
- Pullback rejects Qline/Qcloud or bearish order block
- Moneyball stays supportive
- Entry is near resistance, not late into extension
- Target is next low, Qwave band, or measured level

## 4. When to ignore alerts

Ignore alerts when:

- They fire during scheduled news volatility.
- Price is stuck between major levels.
- The trade has less than 1.5R available to the next opposing level.
- SMC structure disagrees.
- You have already hit your daily trade limit.
- You are emotionally trying to recover a loss.

## 5. Confluence hierarchy

When indicators disagree, prioritize in this order:

1. Prop-firm risk limit
2. Scheduled news / volatility conditions
3. 5m/15m/4h structure
4. Key levels and liquidity
5. Qcloud/Qline trend state
6. Moneyball/Qmomentum confirmation
7. Qgrid add-on signal
8. Raw alerts

Raw alerts are last because alerts are not the edge by themselves.
