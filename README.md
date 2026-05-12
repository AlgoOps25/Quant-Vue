# Layer 8 Options Flow Trading System

This repository is now the planning and build workspace for a **data-first options-flow trading system** using **Unusual Whales API Advanced + Python + dashboard/alerts**.

> Educational trading documentation only. This is not financial advice. No system guarantees profitable trades. Every model, alert, and setup must be validated through live observation, paper trading, and outcome tracking before risking real capital.

## Official roadmap

The single source of truth is:

```text
00-HOLY-GRAIL-UW-OPTIONS-SYSTEM.md
```

Start there for every question about the system.

## Current strategic direction

The active direction is no longer QuantVue-first futures execution.

The active direction is:

```text
Unusual Whales API Advanced
+ Python live data engine
+ SQLite/Postgres database
+ Streamlit/FastAPI dashboard
+ Discord/Telegram alerting
+ TradingView visualization only
+ manual broker execution first
```

Primary markets:

```text
SPX 0DTE
SPY 0DTE
QQQ 0DTE
IWM 0DTE
TSLA / NVDA / AAPL / AMD / META / MSFT / AMZN options
```

## Core decision framework

Every alert must pass through this stack:

```text
Regime
→ Flow
→ Dealer/GEX context
→ Contract quality
→ Price confirmation
→ Risk filter
→ Alert
→ Outcome tracking
```

No single data point creates a trade.

## Active repo map

| File / Folder | Purpose |
|---|---|
| [`00-HOLY-GRAIL-UW-OPTIONS-SYSTEM.md`](00-HOLY-GRAIL-UW-OPTIONS-SYSTEM.md) | Official master roadmap and system reference |
| [`archive/reference/README.md`](archive/reference/README.md) | Archive index for superseded decision documents |
| [`archive/reference/uw-decision-archive.md`](archive/reference/uw-decision-archive.md) | Preserved summary of prior UW vendor/system decisions |
| [`pine/Layer8_NQ_DataPlan_Context_v0_1.pine`](pine/Layer8_NQ_DataPlan_Context_v0_1.pine) | Earlier TradingView context indicator; retained as reference |
| [`templates/`](templates/) | Templates retained for future journal/checklist reuse |

## Archived / superseded direction

Older QuantVue, Skylit, TradingView Premium, and futures-focused files remain historical reference unless the Holy Grail roadmap explicitly points to them.

The following UW transition documents have been consolidated and archived:

```text
47-options-data-vendor-decision.md
48-unusual-whales-live-alert-system-blueprint.md
49-options-data-stack-decision-uw-vs-alternatives.md
50-unusual-whales-component-usage-map.md
```

Their active decisions now live in:

```text
00-HOLY-GRAIL-UW-OPTIONS-SYSTEM.md
archive/reference/uw-decision-archive.md
```

## Pre-purchase gate

Before buying Unusual Whales API Advanced:

```text
[ ] Review 00-HOLY-GRAIL-UW-OPTIONS-SYSTEM.md
[ ] Send UW support the pre-purchase endpoint/access question from Section 12
[ ] Confirm API Advanced includes required WebSocket/REST access
[ ] Confirm no $250 historical option-trades add-on is required for the MVP
[ ] Confirm private personal-use alerting/local storage is allowed
[ ] Confirm SPX/SPY/QQQ/IWM/TSLA/NVDA/AAPL/AMD/META/MSFT/AMZN endpoint coverage
```

## First implementation phase after purchase

```text
1. Authenticate with bearer token.
2. Pull stock state for SPY/QQQ/NVDA.
3. Pull option chains for SPY/QQQ/NVDA.
4. Pull recent flows.
5. Pull Market Tide / ETF Tide / Net Flow.
6. Pull GEX / Greek exposure.
7. Connect to live WebSocket streams.
8. Write raw events to SQLite.
9. Build SPX/SPY/QQQ 0DTE APEX alerts.
10. Track every alert outcome before real-money execution.
```

## Final operating principle

The system should never say:

```text
Buy now, guaranteed.
```

It should say:

```text
Live options data strongly favors this context. Trade only if execution, spread, risk, and price confirmation are acceptable.
```
