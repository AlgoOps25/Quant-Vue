# 15 — QuantVue Alert Plan

This document defines the alert workflow for the QuantVue-first system.

## Alert philosophy

Alerts are not entries.

Alerts mean:

```text
Look at the chart and score the setup.
```

Alerts do not mean:

```text
Click buy or sell immediately.
```

## Alert categories

## Category 1 — High-priority trade watch alerts

Use these during active trading windows.

```text
Qcloud bullish flip near valid long location
Qcloud bearish flip near valid short location
Qline bullish flip at Qwave/Qbands lower area
Qline bearish flip at Qwave/Qbands upper area
Moneyball bullish confirmation at valid long location
Moneyball bearish confirmation at valid short location
15m opening range high retest
15m opening range low retest
3m opening range high retest
3m opening range low retest
8am candle long retest
8am candle short retest
```

## Category 2 — Medium-priority watchlist alerts

Use these to bring attention to the chart, not to enter.

```text
Qwave upper/lower band touch
Qbands upper/lower band touch
Prior day high/low touch
Overnight high/low touch
SMC liquidity grab
SMC BOS/CHoCH
FVG touch
Zone touch
```

## Category 3 — Add-to-winner alerts

Use only when already in a trade.

```text
Qgrid long add signal
Qgrid short add signal
```

Qgrid alerts are invalid if:

```text
The original trade is losing
The trade has not reached partial target or break-even plan
The add would exceed daily risk
The add is directly into a major opposing level
```

## Recommended alert names

Use clear names in TradingView.

```text
NQ Qcloud Bull Flip — Check Long Bias
NQ Qcloud Bear Flip — Check Short Bias
NQ Qline Bull Flip — Check Level
NQ Qline Bear Flip — Check Level
NQ Moneyball Bull — Confirm Structure
NQ Moneyball Bear — Confirm Structure
NQ 15m OR High Retest — Long Watch
NQ 15m OR Low Retest — Short Watch
NQ 3m OR High Retest — Long Watch
NQ 3m OR Low Retest — Short Watch
NQ 8am Zone Long Retest
NQ 8am Zone Short Retest
NQ Qgrid Long Add — Only If Winner
NQ Qgrid Short Add — Only If Winner
```

## Alert-to-trade checklist

When an alert fires:

1. Check 5m SMC bias.
2. Confirm price is at a real level.
3. Confirm whether this is one of the approved setups.
4. Check Qpro/Qcloud/Qline.
5. Check Moneyball.
6. Check next opposing level.
7. Calculate stop and target.
8. Score setup using `02-confluence-system.md`.
9. Enter manually in Tradovate only if score is valid and risk fits.

## Alerts to avoid at first

Do not create every possible alert.

Avoid:

```text
Every raw bull/bear signal
Every tiny Qcloud color change
Every Qgrid dot when not in trade
Every broad alert with no filter
Alerts during major news windows
```

## Initial alert set

Start with only these:

```text
1. 15m opening range high/low retest
2. 3m opening range high/low retest
3. Qline flip at Qwave/Qbands area
4. Moneyball confirmation at marked level
5. Qgrid add-to-winner only
```

## Alert review process

At the end of each day, classify each alert:

```text
Useful
Too early
Too late
Noisy
Ignored correctly
Should have taken
Should not have taken
```

Keep only alerts that improve decision-making.

## Prop-firm rule

If an alert fires after a daily shutdown rule has triggered, ignore it.

The account rules override the chart.