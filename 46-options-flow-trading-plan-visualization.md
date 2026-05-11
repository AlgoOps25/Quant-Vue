# 46 — Options Flow Trading Plan Visualization Framework

This document converts the options-flow and Greeks framework into a practical planning layer for the QuantVue workflow.

It is not financial advice and it does not guarantee results. It is a structured way to classify market conditions before considering any trade.

## Core idea

QuantVue indicators help with execution signals, trend, momentum, bands, and levels.

Options-flow context helps answer the bigger question:

```text
What type of market am I trading today?
```

Use this split:

```text
Options Flow = market regime and directional pressure
QuantVue = timing, confirmation, execution, and management
Risk Rules = whether the setup is allowed, reduced, or skipped
```

## Greeks translated into trading context

| Force | Practical meaning | NQ/MNQ interpretation |
|---|---|---|
| Delta / DEX | Directional hedge pressure | Dealers may need to buy or sell futures to stay hedged |
| Gamma / GEX | Pinning vs acceleration | Positive gamma tends to fade moves; negative gamma tends to amplify moves |
| Vanna | VIX-driven hedge pressure | Falling VIX can support upside drift; rising VIX can pressure downside |
| Charm | Time-decay drift | Later in the day price can drift toward important option levels |

## Regime map

| Regime | Expected behavior | Preferred playbook | Avoid |
|---|---|---|---|
| Positive gamma | Mean reversion, failed breakouts, pinning | Fade extremes, quicker targets | Chasing breakouts |
| Negative gamma | Expansion, trend continuation, fast movement | Pullback continuation, runners | Countertrend fading without strong confirmation |
| VIX falling | Long-side tailwind / grind risk | Long pullbacks, less aggressive shorts | Shorting without resistance confirmation |
| VIX rising | Downside pressure / volatility expansion | Short pullbacks or reduced long risk | Buying every dip blindly |
| Near call wall | Potential resistance/magnet | Take profits or wait for acceptance above | Longing directly into resistance |
| Near put wall | Potential support/magnet | Take profits on shorts or wait for acceptance below | Shorting directly into support |
| Near gamma flip | Regime decision zone | Wait for acceptance/rejection | Trading the middle with no confirmation |

## Daily planning checklist

Fill this out before RTH:

```text
Date:
Primary market: NQ / MNQ
VIX direction: Rising / Falling / Flat
VIX vs prior close: Above / Below / Flat
Net gamma: Positive / Negative / Neutral / Unknown
Gamma flip:
Call wall:
Put wall:
HVL / main gamma magnet:
0DTE call resistance:
0DTE put support:
Prior day high:
Prior day low:
Prior day close:
Overnight high:
Overnight low:
Opening range high:
Opening range low:
Primary bias:
Primary playbook:
No-trade condition:
Invalidation level:
```

## Visual dashboard design

Add a right-side table to the chart or use an external dashboard:

```text
Layer 8 NQ Data Plan
Regime: POS GEX / NEG GEX / NEUTRAL
Vanna: TAILWIND / HEADWIND / NEUTRAL
VIX: RISING / FALLING / FLAT
Location: CALL WALL / PUT WALL / GAMMA FLIP / MID-RANGE
Playbook: FADE / CONTINUATION / WAIT
Risk Mode: NORMAL / HALF / STAND DOWN
Target Magnet: [level]
Invalidation: [level]
```

## Chart visualization layers

Plot these on the chart:

```text
Call Wall = red resistance line or zone
Put Wall = green support line or zone
Gamma Flip = yellow decision line
HVL = purple or white magnet line
0DTE Call Resistance = red shaded zone
0DTE Put Support = green shaded zone
Opening Range = box
Prior Day High/Low = thin lines
Overnight High/Low = dashed lines
```

## Applying it to QuantVue setups

### Long continuation

Prefer when:

```text
GEX is negative or neutral-to-negative
VIX is falling or stable
Price is above gamma flip or holding support
QuantVue trend is bullish
Moneyball/Qmomentum support upside momentum
Q_Pilot/Q_Pro gives long or re-entry long confirmation
```

Reduce or skip when:

```text
Positive gamma day
Price is directly under call wall
VIX is rising
QuantVue momentum disagrees
```

### Short continuation

Prefer when:

```text
GEX is negative or neutral-to-negative
VIX is rising
Price is below gamma flip or rejecting call wall
QuantVue trend is bearish
Moneyball/Qmomentum support downside momentum
Q_Pilot/Q_Pro gives short or re-entry short confirmation
```

Reduce or skip when:

```text
Price is directly on put wall
VIX is falling hard
Positive gamma environment is pinning price
```

### Mean-reversion fade

Prefer when:

```text
GEX is positive
Price extends into call wall, put wall, or high-gamma level
VIX is flat or calming
QuantVue shows exhaustion, sweep, Qwave reaction, or Moneyball turn
```

Reduce or skip when:

```text
GEX is negative
VIX is expanding
Price is accepting beyond the level
```

## Pre-trade score

Use a 10-point decision score:

```text
Trend alignment: 0-2
Momentum alignment: 0-2
Location quality: 0-2
Options-flow regime alignment: 0-2
Risk/reward quality: 0-1
Session/news safety: 0-1
```

Decision:

```text
8-10 = A setup
6-7 = B setup / reduced size or sim
0-5 = skip
```

## Implementation path

1. Keep QuantVue layouts as execution systems.
2. Add an options-flow context checklist to the morning routine.
3. Manually enter key levels first.
4. Build a Pine overlay with manual inputs for call wall, put wall, gamma flip, HVL, and 0DTE levels.
5. Add a dashboard table showing regime, bias, playbook, and risk mode.
6. Log every trade by regime.
7. Compare which QuantVue setup works best in each regime.

## First build target

Create a Pine overlay named:

```text
Layer 8 NQ Data Plan Overlay
```

Minimum features:

```text
Manual level inputs
Horizontal lines and zones
Regime table
Bias label
Playbook label
No-trade warning
```

## Main rule

No QuantVue signal should be considered alone.

Every signal must answer:

```text
Does this match today’s options-flow regime?
```

If yes, evaluate it.
If no, skip it or mark it observation-only.
