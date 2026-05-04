# 28 — TradingView Test Links and Renko Box Size Guide

This document gives the direct links and step-by-step instructions for validating TradingView Plus with QuantVue Pro.

## Test 1 — Confirm NQ1! realtime data

Open:

```text
https://www.tradingview.com/chart/?symbol=CME_MINI%3ANQ1%21
```

Pass condition:

```text
NQ1! opens and does not show delayed data.
```

## Test 2 — Confirm MNQ1! realtime data

Open:

```text
https://www.tradingview.com/chart/?symbol=CME_MINI%3AMNQ1%21
```

Pass condition:

```text
MNQ1! opens and does not show delayed data.
```

## Test 3 — 1-second candle test

Open NQ1!:

```text
https://www.tradingview.com/chart/?symbol=CME_MINI%3ANQ1%21
```

Then set interval to:

```text
1S
```

Pass condition:

```text
1-second candles are selectable and update live.
```

## Test 4 — Traditional Renko box-size test

Open NQ1!:

```text
https://www.tradingview.com/chart/?symbol=CME_MINI%3ANQ1%21
```

Then test:

```text
Traditional Renko box size 2
Traditional Renko box size 3
Traditional Renko box size 4
Traditional Renko box size 5
```

Pass condition:

```text
All box sizes render and update correctly.
```

## How to change Renko box size in TradingView

1. Open a chart.
2. Click the candle/chart-type icon near the top toolbar.
3. Select `Renko`.
4. Open chart settings:

```text
Right-click chart → Settings
```

or click the gear icon.

5. Go to:

```text
Symbol tab
```

6. Find the Renko settings.
7. Set style/type to:

```text
Traditional
```

8. Set box size to:

```text
2, 3, 4, or 5
```

9. Click OK / Apply.

## Test 5 — Banksy Manual Setup

Open:

```text
https://www.tradingview.com/chart/dkdjQAG2/
```

Also test alternate Banksy Manual Layout:

```text
https://www.tradingview.com/chart/1pa0fuKD/
```

Save a copy as:

```text
NQ QuantVue Banksy Manual
```

Pass condition:

```text
Layout loads, no missing required indicators, 4 or fewer charts, 10 or fewer indicators per chart.
```

## Test 6 — Banksy videos

General Overview:

```text
https://youtu.be/KUw-k4mwb4Q
```

A+ Setup Overview:

```text
https://youtu.be/ETIrD4ZyfAI
```

## Test 7 — Alfredo Qpilot Manual Layout

Open:

```text
https://www.tradingview.com/chart/mRs5MUmS/
```

Save a copy as:

```text
MNQ Alfredo Qpilot Manual
```

Pass condition:

```text
Layout loads, Q_Pilot works, no missing required indicators, 4 or fewer charts, 10 or fewer indicators per chart.
```

## Test 8 — Alfredo Qpilot user guide and videos

Q_Pilot User Guide:

```text
https://docs.quantvue.io/our-tools/tradingview-indicators/q_pilot-indicator
```

Guide Video:

```text
https://youtu.be/59qyGW_2oug
```

Live Trading Video:

```text
https://youtu.be/5Gc3aiMGyiI
```

## Test 9 — Qgrid Renko Layout

Open:

```text
https://www.tradingview.com/chart/BMOg7VKi/
```

Pass condition:

```text
Layout loads and Qgrid is usable without exceeding Plus limits.
```

## Test 10 — Broad Alerts Setup

Open:

```text
https://www.tradingview.com/chart/5cH27iNG/
```

Pass condition:

```text
Layout loads, but do not enable all alerts yet.
```

## Test 11 — Broad Band NQ setup

Open:

```text
https://www.tradingview.com/chart/ckaU8m5y/
```

This is preferred before tight-band alerts because it should produce fewer signals.

## Test 12 — Tight Band NQ setup

Open:

```text
https://www.tradingview.com/chart/ayo7hEU5/
```

Use this later only if broad-band alerts are too slow or too sparse.

## Test 13 — Indicator-only setup links

Qbands:

```text
https://www.tradingview.com/chart/0cj0nElp/
```

Qline:

```text
https://www.tradingview.com/chart/KcNC1Hrr/
```

Qwave:

```text
https://www.tradingview.com/chart/HiKYMGzt/
```

Qcloud:

```text
https://www.tradingview.com/chart/01f4p1QZ/
```

## Recording the result

For each test, record:

```text
Test name:
Pass/fail:
Screenshot saved? Y/N
Charts in layout:
Indicators per chart:
Missing indicators:
Renko setting:
Does Plus handle it? Y/N
Notes:
```

## Upgrade rule

Stay on TradingView Plus unless one of these fails:

```text
1-second charting is blocked.
Traditional Renko is blocked.
Banksy layout exceeds Plus limits and cannot be simplified.
Alfredo layout exceeds Plus limits and cannot be simplified.
Replay depth is not enough for validation.
```