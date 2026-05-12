# 50 — Unusual Whales Component Usage Map

## Purpose

If paying for Unusual Whales API Advanced, every useful data category should have a defined role in the trading decision engine.

The system should not blindly trade one data point.

It should use each component in one of these roles:

```text
Regime
Direction
Confirmation
Contract selection
Risk filter
Timing
Invalidation
Post-alert scoring
```

## Core principle

No single component creates a trade.

A trade opportunity is valid only when multiple independent components align:

```text
Market regime + Flow direction + Greek/GEX context + Contract quality + Price confirmation + Risk filter
```

---

# Component usage table

| UW component | Primary role | Used for decision? | How it affects alert |
|---|---|---|---|
| Full Tape / Option Trades | Raw live options transactions | Yes | Detect real-time aggressive 0DTE buying/selling |
| Flow Alerts | Curated unusual flow events | Yes | Fast watchlist triggers, never standalone entries |
| Option Contract Flow Data | Contract-level accumulation | Yes | Confirm repeat activity in same strike/expiry |
| Option Chain / Contracts | Contract universe and liquidity | Yes | Select only liquid contracts with acceptable spreads |
| Greeks | Delta/gamma/theta/vega risk | Yes | Avoid contracts with poor risk/reward or theta danger |
| GEX / Greek Exposure | Dealer positioning/regime | Yes | Decide range vs trend, wall proximity, squeeze risk |
| Greek Flow | Directional Greek pressure | Yes | Confirm whether flow creates meaningful delta/gamma pressure |
| Spot GEX Exposures | Intraday strike-level exposure | Yes | Find walls, magnets, squeeze/rejection zones |
| Market Tide | Broad market options pressure | Yes | Confirm SPX/SPY/QQQ directional environment |
| ETF Tide | ETF-specific options pressure | Yes | Confirm QQQ/SPY/IWM directional pressure |
| Net Flow | Aggregate bullish/bearish premium | Yes | Confirm direction across windows |
| Stock Recent Flows | Ticker-specific recent flow | Yes | Confirm TSLA/NVDA/etc. flow direction |
| Flow per Expiry | Expiration concentration | Yes | Isolate 0DTE vs weekly/monthly activity |
| Flow per Strike | Strike clustering | Yes | Identify target strikes and walls |
| Flow per Strike Intraday | Intraday strike acceleration | Yes | Detect same-strike momentum bursts |
| OI per Expiry / Strike | Positioning context | Yes | Distinguish volume vs existing positioning |
| OI Change | Next-day validation | Secondary | Confirm whether flow likely opened or closed |
| Volume & OI per Expiry | Liquidity and crowding | Yes | Avoid dead contracts; find active expirations |
| Options Volume | Ticker activity filter | Yes | Confirm unusual activity vs normal |
| Max Pain | Pinning/reference level | Secondary | Useful on positive gamma/range days |
| Option Price Levels | Underlying reaction levels | Yes | Mark levels for entries/exits |
| IV Rank / IV / Term Structure | Volatility regime | Yes | Avoid IV crush; confirm expansion setups |
| Realized Volatility | Actual movement regime | Yes | Detect if option premium is justified by movement |
| Volatility Statistics | Context | Secondary | Benchmark current vol vs historical state |
| Stock State / OHLC / Price WS | Underlying confirmation | Yes | Confirm price is moving with flow |
| Technical Indicator endpoint | Simple price filters | Optional | VWAP/EMA/RSI-style confirmation if needed |
| Darkpool / Off-lit Trades | Institutional stock context | Secondary | Confirm accumulation/distribution in underlying |
| Lit Flow | Equity tape confirmation | Secondary | Confirm stock buying/selling behind options |
| News Headlines | Risk filter | Yes | Block/flag news-driven or headline-risk trades |
| Trading Halts WS | Risk kill switch | Yes | Block alerts around halts |
| Economic Calendar | Macro risk filter | Yes | Block FOMC/CPI/NFP windows |
| Earnings Calendar / Earnings History | Single-stock risk filter | Yes | Block or special-handle earnings names |
| Company Profile / Sector | Grouping/context | Optional | Group watchlists and sector confirmation |
| Sector Tide / Sector ETFs | Sector confirmation | Yes for stocks | Confirm NVDA/TSLA sector/theme pressure |
| Top Net Impact | Discovery | Yes | Find tickers driving market options pressure |
| Correlations | Hedge/context | Optional | Determine if stock flow aligns with index |
| Insider/Congress/Institution | Not intraday signal | Mostly no | Long-term context only; not 0DTE trigger |
| Short interest / FTD | Optional catalyst context | Mostly no | Use for squeeze watchlists, not intraday trigger |
| Seasonality | Context only | No for live trigger | Research/statistical backdrop only |

---

# Alert decision stack

## Stage 1 — Universe filter

Allowed symbols:

```text
SPX
SPY
QQQ
IWM
TSLA
NVDA
AAPL
AMD
META
MSFT
AMZN
```

Allowed expirations:

```text
0DTE for SPX/SPY/QQQ/IWM
0DTE and current weekly for single stocks
```

Reject if:

```text
Spread too wide
Volume too low
No live price confirmation
Contract too far OTM without catalyst
News/earnings risk unmanaged
```

## Stage 2 — Regime engine

Uses:

```text
GEX / Greek Exposure
Spot GEX exposures
Market Tide
ETF Tide
Net Flow
VIX / volatility endpoints
Realized volatility
```

Outputs:

```text
TREND UP
TREND DOWN
RANGE / PIN
VOL EXPANSION
CAUTION
```

## Stage 3 — Flow engine

Uses:

```text
Full Tape
Flow Alerts
Contract Flow Data
Recent Flows
Flow per Expiry
Flow per Strike
Flow per Strike Intraday
Greek Flow
```

Detects:

```text
Call sweep burst
Put sweep burst
Same-strike accumulation
Repeated aggressive ask-side buying
Large premium cluster
Flow divergence against price
Flow alignment with market tide
```

## Stage 4 — Contract-quality engine

Uses:

```text
Option Chain
Greeks
OI / volume
IV
bid/ask spread
contract intraday data
```

Scores:

```text
Liquidity
Spread quality
Delta suitability
Theta risk
Gamma explosiveness
IV expansion/crush risk
Exit feasibility
```

## Stage 5 — Price confirmation engine

Uses:

```text
Stock price stream / OHLC
VWAP/EMA/technical endpoint if used
Prior high/low
Option price levels
Off-lit/lit flow
```

Requires:

```text
Underlying confirms direction
Not directly into wall unless breakout regime
Room to target
No failed breakout against the signal
```

## Stage 6 — Risk engine

Uses:

```text
Spread
IV
theta
time of day
macro/news calendar
earnings calendar
recent failed signals
position sizing rules
```

Blocks:

```text
Wide spreads
Late-day theta traps
IV crush risk
News windows
Mixed flow
Overtrading
Two failed same-direction alerts
```

---

# 0DTE strategy models

## Model A — 0DTE Trend Continuation

Use when:

```text
Market Tide agrees
ETF Tide agrees
Net Flow agrees
GEX/regime supports continuation
Underlying breaks/retests level
Aggressive 0DTE flow clusters in same direction
```

Best for:

```text
SPX calls/puts
QQQ calls/puts
SPY calls/puts
```

## Model B — 0DTE Gamma Squeeze / Acceleration

Use when:

```text
Negative gamma or squeeze-prone regime
Spot GEX shows weak resistance above / weak support below
Same-side aggressive flow accelerates
Greek flow shows delta/gamma pressure
Underlying confirms breakout
```

Avoid if:

```text
Price is directly into major call wall/put wall
Flow is one-off with no follow-through
VIX/volatility is fighting the move
```

## Model C — 0DTE Range Fade / Pin

Use when:

```text
Positive gamma / pinned regime
Price reaches major wall
Flow stalls or reverses at wall
Market Tide is not strongly directional
IV is not expanding
```

Best for:

```text
SPY/SPX/QQQ fades around walls or max-pain/pin areas
```

## Model D — Single-Stock Flow Momentum

Use when:

```text
Ticker-specific flow clusters
Premium is large relative to normal
Volume exceeds OI context
Underlying confirms move
Sector/ETF confirms
No earnings/news trap unless intentionally trading catalyst
```

Best for:

```text
TSLA
NVDA
AAPL
AMD
META
MSFT
AMZN
```

## Model E — Volatility Expansion Put/Call

Use when:

```text
VIX/volatility rising
IV expanding
Put or call flow accelerates aggressively
Underlying breaks key level
Market Tide confirms
```

---

# Scoring framework

All opportunities receive a 0–100 score.

## Directional flow score — 25 points

```text
Ask-side calls / ask-side puts
Sweep/block flags if available
Premium size
Repeat prints
Same-strike clustering
```

## Market confirmation score — 20 points

```text
Market Tide
ETF Tide
Net Flow
Sector Tide for single stocks
SPY/SPX/QQQ agreement
```

## Dealer/GEX score — 20 points

```text
GEX regime
Spot GEX walls
Gamma flip proximity
Greek flow
Room to next wall
Pin vs continuation state
```

## Contract quality score — 15 points

```text
Bid/ask spread
Volume
OI context
Delta/gamma/theta
IV behavior
Exit liquidity
```

## Price action score — 10 points

```text
Underlying trend
Break/retest
VWAP/level confirmation
Avoiding obvious opposing level
```

## Risk filter score — 10 points

```text
News/earnings/macro safety
Time of day
Recent failed alerts
No halt risk
No abnormal spread expansion
```

## Alert bands

```text
90–100 = Apex alert
85–89 = Strong alert
78–84 = Watch only
Below 78 = No alert
```

---

# How every component prevents bad trades

```text
Full Tape prevents missing real prints.
Flow Alerts prevent missing curated unusual flow.
Market Tide prevents fighting the broad options market.
ETF Tide prevents fighting QQQ/SPY/IWM pressure.
Net Flow prevents chasing one-off prints against aggregate flow.
GEX prevents chasing into walls or fading in acceleration regimes.
Greek Flow confirms whether flow creates meaningful hedge pressure.
Option Chain prevents trading illiquid contracts.
Greeks prevent theta/IV/delta traps.
OI/Volume prevents mistaking dead contracts for opportunity.
IV/Vol stats prevent buying inflated premium blindly.
News/Economic calendar prevents headline traps.
Darkpool/Lit flow confirms or warns against underlying accumulation/distribution.
Outcome tracking prevents keeping rules that do not work.
```

---

# First MVP build using all useful components

## MVP 1 — Index 0DTE

Symbols:

```text
SPX
SPY
QQQ
IWM
```

Components:

```text
Full Tape
Flow Alerts
Market Tide
ETF Tide
Net Flow
GEX / Greek Exposure
Spot GEX
Greek Flow
Option Chain
Greeks
IV
News/Economic Calendar
Price WebSocket
```

Outputs:

```text
SPX 0DTE CALL APEX
SPX 0DTE PUT APEX
QQQ 0DTE CALL MOMENTUM
QQQ 0DTE PUT MOMENTUM
SPY RANGE FADE
CAUTION / NO TRADE
```

## MVP 2 — Single-stock options

Symbols:

```text
TSLA
NVDA
AAPL
AMD
META
MSFT
AMZN
```

Components:

```text
Full Tape
Stock Recent Flows
Flow per Expiry
Flow per Strike
Flow per Strike Intraday
Greeks
Option Chain
IV Rank
Volume/OI
Stock Price
Sector Tide
News/Earnings
Darkpool/Lit flow
```

Outputs:

```text
NVDA CALL MOMENTUM
TSLA PUT BREAKDOWN
AAPL CALL ACCUMULATION
META CAUTION / EARNINGS RISK
```

---

# Final design rule

Every endpoint is useful, but not every endpoint should be active in every alert.

Use this rule:

```text
Data that identifies opportunity = trigger layer
Data that confirms opportunity = confirmation layer
Data that prevents bad trades = risk layer
Data that evaluates performance = learning layer
```
