# 48 — Unusual Whales Live Alert System Blueprint

## Purpose

Use the Unusual Whales API Advanced plan to build a live-data-driven alert system for NQ/MNQ trading context and optional SPY/QQQ/SPX options plays.

## Important rule

No system can detect 100% guaranteed buy/sell opportunities.

The goal is not certainty.

The goal is:

```text
Live data → objective regime → high-quality opportunity score → alert only when multiple independent data sources agree
```

## Why API Advanced matters

API Advanced is the correct plan because it includes:

```text
Live data streaming via WebSockets
REST API access
Higher daily REST request limits
Longer historical lookback
Premium endpoints
```

Basic can poll data, but Advanced is required for the real-time alert engine.

---

# System architecture

## Data inputs

Primary live inputs:

```text
Unusual Whales WebSocket streams
- Options flow / full tape
- Flow alerts
- Market Tide
- ETF Tide
- Net flow
- Price streams if available
- GEX / Greek-related streams if available
```

REST inputs:

```text
- GEX / Greeks endpoints
- Greek flow
- Spot GEX exposures
- Option chain snapshots
- Contract-level flow
- Dark pool if useful
- Historical lookback for baselines
```

Trading inputs:

```text
QQQ = primary NQ proxy
SPY/SPX = broad index confirmation
VIX = risk / Vanna proxy
NQ1!/MNQ1! = execution market in TradingView/Tradovate
```

---

# Processing pipeline

```text
Unusual Whales API/WebSocket
→ Python ingestion service
→ Normalization layer
→ SQLite/Postgres database
→ Feature calculator
→ Scoring engine
→ Alert engine
→ Discord/Telegram/SMS/email
→ Daily dashboard
→ TradingView manual level overlay / Layer 8 Pine indicator
```

## Python services

Recommended modules:

```text
uw_client.py          # REST and WebSocket client
models.py             # typed data models
storage.py            # database writes/reads
features.py           # flow/GEX/VIX/session calculations
scoring.py            # long/short/range/caution scoring
alerts.py             # Discord/Telegram/SMS/email alert sender
dashboard.py          # Streamlit/FastAPI dashboard
backfill.py           # REST historical baseline pulls
config.yaml           # tickers, thresholds, alert rules
```

---

# MVP tickers

Start only with:

```text
QQQ
SPY
SPX
VIX
```

Reason:

```text
QQQ drives NQ context.
SPY/SPX confirm broad-market alignment.
VIX confirms or fights the directional thesis.
```

Do not start with every stock.

---

# Core alert types

## 1 — NQ Long Context Alert

Fire only when several conditions align:

```text
QQQ bullish premium > bearish premium by threshold
SPY or SPX confirms bullish flow
Market Tide / ETF Tide is positive
VIX is falling or not rising aggressively
Price is not directly into call resistance / major GEX wall
GEX/regime does not warn against continuation
```

Output:

```text
NQ LONG CONTEXT
Preferred setup: pullback long / OR retest / breakout retest
Risk: normal or reduced depending on VIX/GEX
```

## 2 — NQ Short Context Alert

Fire when:

```text
QQQ bearish premium > bullish premium by threshold
SPY or SPX confirms bearish flow
Market Tide / ETF Tide is negative
VIX is rising
Price is below or rejecting a key level
GEX/regime supports continuation or downside pressure
```

Output:

```text
NQ SHORT CONTEXT
Preferred setup: failed bounce / breakdown retest / pullback short
Risk: normal or reduced depending on volatility
```

## 3 — Range / Fade Context Alert

Fire when:

```text
Positive gamma / range regime
Flow is balanced or fading at extremes
Price approaches call resistance or put support
VIX is flat or controlled
No strong directional tide confirmation
```

Output:

```text
RANGE / FADE CONTEXT
Preferred setup: level sweep back into range
Avoid: chasing breakouts
```

## 4 — Caution / No Trade Alert

Fire when:

```text
Flow conflicts between QQQ and SPY/SPX
VIX is rising against long idea
Price is trapped between major levels
GEX/regime is unknown
News window or volatility spike
Signals are too mixed
```

Output:

```text
CAUTION / NO TRADE
Action: wait for cleaner alignment
```

---

# Scoring model

Use a 0–100 score instead of binary signals.

## Long score components

```text
QQQ bullish flow strength: 0–20
SPY/SPX confirmation: 0–15
Market/ETF Tide: 0–15
VIX/Vanna support: 0–15
GEX/regime support: 0–15
Distance to upside wall/resistance: 0–10
Time/session quality: 0–10
```

## Short score components

```text
QQQ bearish flow strength: 0–20
SPY/SPX confirmation: 0–15
Market/ETF Tide: 0–15
VIX/Vanna pressure: 0–15
GEX/regime support: 0–15
Distance to downside wall/support: 0–10
Time/session quality: 0–10
```

## Alert thresholds

```text
80–100 = Strong context alert
65–79  = Watchlist alert
50–64  = Weak / no alert
<50    = Ignore
```

## Prop-firm safety filter

Block or demote alerts if:

```text
The expected stop is too wide
The move is already extended
Price is directly into a major opposing wall
News is imminent
Spread/volatility is abnormal
Two recent alerts failed in same direction
```

---

# Feature calculations

## Flow imbalance

```text
Bullish premium = sum of call ask-side + put bid-side premium
Bearish premium = sum of put ask-side + call bid-side premium
Net premium = bullish premium - bearish premium
Flow ratio = bullish premium / bearish premium
```

## Size filters

Ignore noise:

```text
Minimum premium per print
Minimum total premium per 5-min window
Minimum OI/volume context
Sweep/block/aggressor flags if available
```

## Time windows

Calculate rolling windows:

```text
1 minute
5 minutes
15 minutes
30 minutes
RTH session cumulative
```

## VIX filter

```text
VIX falling = long tailwind
VIX rising = short/caution tailwind
VIX spike = caution / no trade
```

## GEX/regime filter

```text
Positive gamma = range/fade mode
Negative gamma = continuation/trend mode
Near call wall = do not chase longs
Near put wall = do not chase shorts unless breakdown confirms
Zero gamma cross = regime shift warning
```

---

# Alert message format

Example Discord/Telegram alert:

```text
🚨 NQ LONG CONTEXT — 84/100

Reason:
- QQQ bullish premium dominant: +$X over 5m
- SPY/SPX confirming positive tide
- VIX falling
- Price has room to next upside wall
- Regime supports continuation

Preferred Setup:
- Pullback long
- OR high retest
- Breakout retest

Invalidation:
- VIX flips up sharply
- Price rejects call wall
- QQQ flow turns bearish

Execution:
- Use TradingView/Tradovate only after price confirms
```

---

# TradingView visualization

Use the existing Layer 8 Pine indicator for visualization.

Manual levels entered from UW/Python dashboard:

```text
HVL / key gamma level
Call resistance
Put support
Zero gamma
```

Future enhancement:

```text
Have Python generate a daily levels JSON/CSV
Manually paste key levels into Pine settings
or display them in a local dashboard next to TradingView
```

Pine cannot directly call the Unusual Whales API, so API data must be handled by Python.

---

# Dashboard view

Build a Streamlit dashboard with:

```text
Current regime: RANGE / TREND UP / TREND DOWN / CAUTION
Long score
Short score
VIX status
QQQ flow summary
SPY/SPX confirmation
Key levels
Latest high-conviction prints
Active alert log
Post-alert outcome tracking
```

---

# Reliability requirements

To make the system reliable, include:

```text
Heartbeat monitor for WebSocket connection
Reconnect logic
Duplicate alert suppression
Rate-limit handling
Data validation
Timestamp synchronization
Local database persistence
Alert cooldowns
Kill switch during news
Daily reset
Post-alert outcome tracking
```

---

# Build phases

## Phase 1 — API connection test

```text
Authenticate to UW API
Pull QQQ/SPY/SPX/VIX snapshots
Connect to WebSocket
Print live events to terminal
Save events to SQLite
```

## Phase 2 — Basic flow dashboard

```text
Aggregate QQQ flow by 1m/5m/15m
Aggregate SPY/SPX confirmation
Track VIX direction
Show long/short score
```

## Phase 3 — Alert engine

```text
Create 4 alert types:
- NQ LONG CONTEXT
- NQ SHORT CONTEXT
- RANGE / FADE CONTEXT
- CAUTION / NO TRADE
Send to Discord or Telegram
```

## Phase 4 — Outcome tracker

```text
After each alert, track NQ/MNQ price after:
5 minutes
15 minutes
30 minutes
60 minutes

Record:
Max favorable excursion
Max adverse excursion
Hit +25 before -15?
Hit +50 before -25?
```

## Phase 5 — Threshold tuning

```text
Keep alerts that show positive expectancy
Remove noisy conditions
Tune score thresholds
Add time-of-day filters
Add regime-specific rules
```

---

# Final operating rule

The system should never say:

```text
Buy now guaranteed
```

It should say:

```text
Live data strongly favors this market context.
Only execute if price confirms and risk is acceptable.
```
