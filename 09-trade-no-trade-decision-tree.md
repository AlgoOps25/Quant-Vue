# 09 — Trade / No-Trade Decision Tree

Use this before every NQ/MNQ entry. If any major step fails, do not trade.

## Step 1 — Is the market tradable right now?

### Trade allowed

- No major news within your lockout window.
- Spread and movement are normal.
- You are calm and not trying to recover a loss.
- Tradovate account, symbol, and order size are confirmed.

### No trade

- Major news is about to release.
- Price is whipping both directions.
- You already hit daily loss/trade limit.
- You are emotional or rushing.

Decision:

```text
If market condition is unsafe → NO TRADE.
If market condition is stable → continue.
```

## Step 2 — What type of day is forming?

Choose one primary environment.

| Day type | Clues | Preferred setups |
|---|---|---|
| Trend day | Higher highs/higher lows or lower highs/lower lows, Qcloud one direction | Qcloud continuation, OR retest, Qgrid add-to-winner |
| Range day | Price rotates between levels, Qcloud chops | Qwave/Qbands reversal, zone strategy |
| Reversal day | Liquidity sweep then CHoCH/BOS | SMC liquidity sweep reversal, zone reclaim |
| Opening drive | Strong break after cash open | 3m OR breakout/retest, 15m OR retest |
| Chop/no-trade | Mixed signals, weak levels, no clean structure | Stand down |

Decision:

```text
If you cannot name the day type → NO TRADE.
If you can name the day type → continue.
```

## Step 3 — Is price at a valid location?

Valid locations:

- 15-minute opening range high/low retest
- 3-minute opening range high/low retest
- 8am candle zone retest
- Prior day high/low
- Overnight high/low
- SMC order block
- SMC liquidity sweep zone
- Qwave/Qbands outer band
- Drawn supply/demand zone
- FVG edge or midpoint

Invalid locations:

- Middle of range
- Late after a vertical move
- Directly into opposing zone
- No obvious stop location

Decision:

```text
If price is not at a valid location → NO TRADE.
If price is at a valid location → continue.
```

## Step 4 — Does structure support the trade?

For longs:

- Bullish CHoCH/BOS
- Sell-side liquidity sweep and reclaim
- Higher low forming
- Bullish order block holding
- OR high retest holding as support

For shorts:

- Bearish CHoCH/BOS
- Buy-side liquidity sweep and rejection
- Lower high forming
- Bearish order block holding
- OR low retest rejecting as resistance

Decision:

```text
If structure disagrees → NO TRADE.
If structure agrees → continue.
```

## Step 5 — Does QuantVue confirm?

At least two should agree:

- Qcloud trend state agrees.
- Qline flips in trade direction.
- Moneyball supports momentum.
- Qwave/Qbands location supports the setup.
- Qgrid signal appears only for add-to-winner.

Decision:

```text
If only one raw alert agrees → WAIT.
If two or more tools confirm with structure/location → continue.
```

## Step 6 — Does risk fit the prop-firm account?

Before entry, define:

- Entry
- Stop
- Target 1
- Target 2
- Contract size
- Dollar risk
- Remaining daily loss allowance

Minimum rule:

```text
If you cannot define the stop and target before entry → NO TRADE.
If stop is too wide for NQ → use MNQ or skip.
If reward is not worth risk → NO TRADE.
```

## Step 7 — Grade the trade

Use the confluence score from `02-confluence-system.md`.

| Score | Action |
|---:|---|
| 9–10 | A+ setup; normal planned risk if prop rules allow |
| 7–8 | Valid setup; normal or reduced risk |
| 5–6 | Watch only |
| 0–4 | No trade |

Decision:

```text
Only trade if score >= 7.
```

## Step 8 — Execute manually

1. Alert or setup appears in TradingView.
2. Confirm score >= 7.
3. Open Tradovate.
4. Confirm account and symbol.
5. Place bracket/OCO order.
6. Stop goes in immediately.
7. Target goes in immediately.
8. Journal trade after exit.

## One-line rule

```text
No level + no structure + no trigger + no risk plan = no trade.
```
