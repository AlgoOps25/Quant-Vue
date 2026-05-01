# 06 — Transcript-Derived Video Index

This index tracks the videos represented in the uploaded QuantVue transcript file and the role each video plays in the trading system.

> Note: The user clarified that there were 28 videos total because 2 were duplicated across playlists. The uploaded transcript text contains distinct sections for many videos, but not every section has equal detail. This file should be updated as screenshots are added.

## Core indicator tutorials

| Video | Main role in system | Key takeaways |
|---|---|---|
| `All-In-One Trading System! - QuantVue Qpro V2.0 (Full Tutorial)` | Main Qpro setup | Qpro combines Qcloud, Qbands, Qwave, and Qline; use Qcloud for trend state, Qwave/Qbands for location, Qline for trigger/exit. |
| `Ultimate Price Action Indicator! - QuantVue SMC V2.0 Indicator (Full Tutorial)` | 5m bias chart | Use SMC every day on NQ 5m; liquidity, BOS/CHoCH, order blocks, manual structures, prior highs/lows, and session boxes define context. |
| `The MOST Powerful Oscillator On TradingView - QuantVue Moneyball V2.0 (Full Tutorial)` | Momentum confirmation | Moneyball is not just RSI; use period 4–8 for scalping, 8–20 for trend bias, Mode M, All Zero checked. |
| `NEW "Qgrid" TradingView Indicator Is HERE!` | Add-to-winner logic | Qgrid is mainly for pullback/add signals, not blind entries. Use dots/ADD signals after a trend is already valid. |
| `NEW "Qpilot" Trading Indicator - Full Guide!` | Needs more screenshot detail | Qpilot needs full settings screenshots before exact setup is locked. |
| `NEW "Qbank_Pro" TradingView Indicator - Full Guide!` | Trade management / trailing concept | Center-box and two-box trailing logic should be documented with screenshots. |

## Strategy series / playbook videos

| Video | Strategy contribution |
|---|---|
| `Fast Scalping Futures Using QuantVue "Qcloud" - Strategy #2` | Qcloud flip and trend continuation scalping. |
| `Using The Moneyball + Qcloud + Qpro QuantVue Indicators - Strategy #3` | Multi-indicator confluence example. |
| `Find EASY Reversal Trades With QuantVue "Qbands" - Strategy #4` | Qbands reversal / mean-reversion setup. |
| `Simple 3-Minute Opening Range Futures Strategy - Strategy #5` | Opening range breakout and retest framework. |
| `Best 5-Minute Futures Strategy Using QuantVue Qpro - Strategy #6` | 5-minute Qpro strategy using slower chart context. |
| `How To Use QuantVue & The 15-Minute Opening Range - Strategy #7` | Higher-timeframe opening range logic. |
| `How We Find PROFITABLE Trading Setups DAILY! - Strategy #8` | Daily preparation and repeatable setup planning. |
| `8am Candle Retest - Strategy #9` | 8am candle high/low/body retest zones. |
| `Simple "ZONE" Strategy - Strategy #10` | Zone-based trade location and confirmation. |
| `NEW QuantVue Layout To Fast Scalp Futures! - Strategy #11` | Fast scalp chart layout. |
| `How To Use QuantVue On Candlestick Charts - Strategy #12` | How to adapt QuantVue to candles instead of Renko. |
| `Using "Qgrid" To Pass Prop Challenges! - Strategy Series #13` | Qgrid add-to-winner discipline and prop-firm risk. |

## Other referenced videos / topics

| Video/topic | Contribution |
|---|---|
| `The QuantVue "Iceberg" Strategy Explained!` | Needs screenshot/settings capture before detailed integration. |
| `Using "Broad" QuantVue Alerts!` | Broad alerts should be treated as watch signals, not direct entries. |
| `Using QuantVue On 1m Timeframe!` | Workaround for 1-minute / limited plan use; Renko 2 mentioned in transcript-derived notes. |
| Q_Range / trading guides | Day classification and regular-session context if available under plan. |

## Indicator-to-strategy mapping

| Indicator | Primary use | Best strategy family |
|---|---|---|
| Qpro | All-in-one execution dashboard | General execution and confluence |
| Qcloud | Trend state / regime | Trend continuation, fast scalping |
| Qline | Trigger and exit | Qline flip entry/exit, pullback continuation |
| Qwave | Dynamic band location and alerts | Band reversal, breakout context |
| Qbands | Stretch / mean reversion / midline target | Reversal and range-day plays |
| Moneyball | Momentum confirmation | All strategies as confirmation layer |
| Qgrid | Pullback/add-on logic | Add-to-winner only |
| SMC V2 | Structure, liquidity, order blocks | Bias chart and level selection |
| Qpilot | Needs more documentation | Potential signal assistant |
| Qbank Pro | Needs more documentation | Potential trade management / trailing system |

## Known settings extracted from transcripts

| Tool | Setting | Transcript-derived value / guidance |
|---|---|---|
| SMC V2 | EMA/cloud MA length | 21 suggested by speaker |
| SMC V2 | Manual structure period | 20 |
| SMC V2 | FVG chart | Prefer 15-minute FVG-only chart |
| SMC V2 | FVG extension/count | 500 shown in transcript |
| SMC V2 | New York session | 09:30–16:00 or 16:05 for display |
| SMC V2 | Session transparency | 99 |
| Qpro/Qcloud | Default settings | Speaker says default is strong most of the time |
| Qpro/Qbands | Band length | 77 default referenced; 65/60 sometimes used on Renko 4 |
| Qpro/Qbands | Trend period | 15 example for earlier flips |
| Qpro/Qwave | NQ Renko 4 band deviation | 5.5 |
| Qpro/Qwave | Lookback | 33 |
| Qpro/Qwave | Weight/method | Weighted; 256 referenced |
| Qline | Default multiplier | 0.1 referenced |
| Qline | Faster exit length | 5 example |
| Moneyball | Mode | M |
| Moneyball | All Zero | Checked / ON |
| Moneyball | NQ period example | 5 |
| Moneyball | Scalping period range | 4–8 |
| Moneyball | Trend-bias period range | 8–20 |
| Moneyball | Threshold range | Around 3–4.5 |
| Qgrid | Heiken Ashi sensitivity | Around 33 discussed as baseline |

## Update process

When a screenshot is added:

1. Save the image under `/screenshots/`.
2. Link it from the relevant setup guide.
3. Add the video timestamp to this index.
4. Add any exact setting values visible in the screenshot.
5. Update `01-tradingview-setup.md` if the setting changes the morning workflow.
