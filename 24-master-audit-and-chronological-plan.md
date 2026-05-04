# 24 — Master Audit and Chronological Plan

This is the master decision document for the QuantVue Pro / NQ/MNQ prop-firm trading workflow.

## Current objective

Build a professional NQ/MNQ futures trading workflow using QuantVue Pro, TradingView Premium, CME futures data, and Tradovate manual execution.

## Final platform decision

```text
Primary path: QuantVue-first
Charting platform: TradingView Premium
Market data: CME Group futures data only for now
Execution: Tradovate manual execution
Secondary path: NinjaTrader only if QuantVue confirms equivalent workspaces/tools later
Custom Layer 8 Pine indicator: paused / research sandbox only
Live prop-firm trading: not allowed until validation milestones are complete
```

## Why Premium is now justified

TradingView Plus was tested. It passed basic NQ/MNQ realtime charting and Renko box-size tests, but the actual QuantVue shared layouts required Premium-only features:

```text
Banksy Manual Setup: needed Premium for seconds
Banksy Manual Layout: needed Premium for seconds
Alfredo Qpilot Manual Layout: needed Premium for volume candles
Qgrid Renko Layout: needed Premium for seconds
Broad Alerts Setup: needed Premium for seconds
Tight Band Setup: needed Premium for seconds
```

Decision:

```text
Upgrade to TradingView Premium and proceed with the official/community QuantVue layouts.
```

## CME data decision

The only additional TradingView data needed right now is:

```text
CME Group futures data
```

Do not add NASDAQ, NYSE, OPRA, CBOE, crypto, forex, or international data unless a specific future workflow requires those instruments.

## Trading philosophy

The system is not:

```text
Indicator flashes → enter trade
```

The system is:

```text
Location → Level Test / Level Sweep → Structure → QuantVue Confirmation → Risk → Manual Entry
```

## Repainting / alert rule

TradingView realtime bars and non-standard charts can behave differently from historical bars. Renko projection bars and intrabar alerts may change before confirmation.

Rules:

```text
Alerts are watch signals only.
No alert equals automatic entry.
Prefer confirmed-bar logic where available.
Do not trust an alert until replay and paper/sim validation prove it is useful.
```

---

# Chronological Plan

## Phase 0 — Repo cleanup and scope freeze

Status: complete enough to proceed.

Rules:

```text
Do not resume custom Pine development unless a specific missing feature is identified.
Do not add every freebie indicator just because it exists.
Do not trade prop-firm live until replay/paper validation is complete.
Do not create more decision-history files unless they become permanent operating docs.
```

Active operating files:

```text
README.md
00-daily-runbook.md
01-tradingview-setup.md
02-confluence-system.md
03-strategy-playbook.md
04-alerts-and-tradovate-execution.md
06-video-index.md
08-one-page-trading-plan.md
09-trade-no-trade-decision-tree.md
10-prop-firm-risk-template.md
11-replay-validation-plan.md
24-master-audit-and-chronological-plan.md
29-tradingview-plus-test-results-premium-decision.md
30-premium-setup-and-layout-validation.md
templates/pre-market-checklist.md
templates/trade-journal.csv
```

---

## Phase 1 — Premium platform validation

Use:

```text
30-premium-setup-and-layout-validation.md
```

Checklist:

```text
[ ] Confirm TradingView Premium is active
[ ] Confirm CME Group data says Subscribed
[ ] Open NQ1! and confirm no delayed-data message
[ ] Open MNQ1! and confirm no delayed-data message
[ ] Confirm QuantVue invite-only indicators are visible
[ ] Favorite required public/freebie scripts from Members Freebies
[ ] Open and save Banksy Manual Setup
[ ] Open and save Banksy Manual Layout
[ ] Open and save Alfredo Qpilot Manual Layout
[ ] Open and save Qgrid Renko Layout
[ ] Open Broad/Tight layouts only after Banksy/Alfredo are understood
```

Pass condition:

```text
NQ/MNQ are realtime, official/community layouts load, and the workflow is usable for replay testing.
```

Fail condition:

```text
Missing permissions, missing scripts, delayed data, or layout elements that still do not load after Premium.
```

---

## Phase 2 — Layout audit

Goal:

Find the cleanest layout before building the personal master layout.

Test in this order:

```text
1. Banksy Manual Setup / Banksy Manual Layout
2. Alfredo Qpilot Manual Layout
3. Qgrid Renko setup
4. Broad Band NQ setup
5. Tight Band NQ setup
6. Qbank Pro layout if needed
7. Other community layouts only after the core layouts are understood
```

For each layout, record:

```text
Layout name:
TradingView URL:
Charts in layout:
Indicators per chart:
Missing indicators:
Timeframes:
Renko settings:
Uses seconds? Y/N
Uses volume candles? Y/N
Primary setup style:
Is it readable? Y/N
Best use:
Problems:
Decision: Keep / simplify / ignore
```

Ranking criteria:

```text
Readability
Matches QuantVue training
Works for NQ/MNQ
Clear entry logic
Clear exit logic
Clear risk logic
Low analysis paralysis
Replay-friendly
Prop-firm friendly
```

---

## Phase 3 — Personal master layout build

Goal:

Build one simple layout for actual use.

Starting structure:

```text
Chart 1: 4H or 15m key levels / pivots
Chart 2: 5m SMC / structure / location
Chart 3: 1-second Traditional Renko execution with Qpro / Qwave / Qline / Moneyball
Chart 4: Qpilot or Qgrid / MNQ practice / 3m OR
```

Clean-chart rule:

```text
If an indicator does not directly help location, structure, trigger, exit, or risk, remove it.
```

---

## Phase 4 — Strategy selection

Updated replay priority:

```text
1. Level Test at key higher-timeframe / 15m level
2. Level Sweep reversal
3. 15m Opening Range retest
4. 3m Opening Range breakout/retest
5. Trend continuation pullback to mid-band
6. Qwave/Qline/Oracle Squeezer confluence
7. Qgrid add-to-winner
```

First setup to validate:

```text
Level Test / Level Sweep at key 4H or 15m level
```

Reason:

```text
This is the foundation QuantVue emphasizes before signals.
```

---

## Phase 5 — Replay validation

Goal:

Prove one setup before live trading.

For each setup:

```text
20 replay examples
20 paper/sim examples
Positive or clearly improvable expectancy
Clear failure conditions
Stop size compatible with prop-firm risk
```

Replay classifications:

```text
Valid winner
Valid loser
Invalid / should skip
Missed winner
False alert
Too early
Too late
Chop / no trade
News invalidated
```

Replay workflow:

```text
1. Pick one setup only.
2. Pick one day/session.
3. Mark 4H / 15m levels before replaying.
4. Replay forward without hindsight.
5. Wait for location.
6. Wait for QuantVue confirmation.
7. Define entry, stop, target before entry.
8. Record result in journal.
9. Screenshot setup.
10. Review after 20 examples.
```

---

## Phase 6 — Prop-firm risk model

Default starting risk rules:

```text
Instrument for practice: MNQ
Max trades per day: 3
Max consecutive losses: 2
Max full-risk losses per day: 2
Default risk per trade: small enough to survive a 10-loss sample
No NQ until MNQ execution is consistent
No adding to losers
Qgrid add only after existing trade is profitable
Stop trading after a rule break
```

Risk decision tree:

```text
If stop is too wide for NQ → use MNQ or skip.
If setup score is below A-grade → skip or sim only.
If two losses occur → stop for the day.
If emotional or rushing → stop for the day.
If news is inside lockout window → no trade.
```

---

## Phase 7 — Alert validation

First alert set:

```text
Level touch / level sweep watch
15m OR retest watch
Qline / Qtrend flip at level
Moneyball confirmation at level
Qgrid add-to-winner only
```

Avoid:

```text
Every broad alert
Every color change
Every Qgrid dot
Every signal without location
```

---

## Phase 8 — Live-readiness gate

Live trading is allowed only when all are true:

```text
[ ] TradingView Premium active
[ ] CME futures data realtime
[ ] Final layout works
[ ] Entry/exit rules are written
[ ] Risk rules are written
[ ] First setup has 20 replay examples
[ ] First setup has 20 sim/paper examples
[ ] Journal shows rules followed at least 80% of the time
[ ] Stop sizes fit account rules
[ ] User can explain when NOT to take the setup
[ ] No unresolved platform/data issue
```

If any item fails:

```text
No live prop-firm trade.
```

---

# Immediate next actions

## Today

```text
1. Pull repo updates.
2. Upgrade TradingView to Premium.
3. Open 30-premium-setup-and-layout-validation.md.
4. Confirm NQ1!/MNQ1! are realtime.
5. Load and save Banksy Manual Setup.
6. Load and save Alfredo Qpilot Manual Layout.
7. Send screenshots for review.
```

## This week

```text
1. Complete Premium layout audit.
2. Build/simplify one master layout.
3. Start 20-example replay set for Level Test / Level Sweep.
4. Do not trade live.
```

## Next week

```text
1. Review first 20 replay examples.
2. Decide whether Level Test / Sweep is valid enough for sim.
3. Start sim/paper validation.
4. Add only the minimum alerts needed.
```

---

# One-line operating rule

```text
Do not add more tools, indicators, or live risk until the current validation step proves it is necessary.
```
