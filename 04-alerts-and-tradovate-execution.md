# 04 — Alerts and Tradovate Manual Execution

This system uses **TradingView for charting/alerts** and **Tradovate for manual execution**.

## 1. Core rule

TradingView alerts are not trade entries. They are attention signals.

When an alert fires:

1. Look at the chart.
2. Check confluence score.
3. Confirm stop and target.
4. Confirm prop-firm risk.
5. Execute manually in Tradovate only if the setup passes.

## 2. Recommended alert categories

### High-priority alerts

Use these when they align with your playbook:

- Qcloud flip in direction of 5m SMC bias
- Qline flip after Qwave/Qbands band reaction
- Moneyball bull/bear signal near key level
- Qgrid ADD/dot after an existing profitable trade
- Price crossing prior day high/low or overnight high/low
- Price entering a marked order block/FVG

### Low-priority alerts

Treat these as visual reminders only:

- Raw Qwave bull/bear alerts with no location
- Signals during lunch chop
- Signals during scheduled news
- Signals directly into opposing support/resistance

## 3. Alert naming convention

Use alert names that force context.

Examples:

- `NQ LONG WATCH — Qline Flip + Lower Band`
- `NQ SHORT WATCH — Prior High Sweep`
- `NQ ADD WATCH — Qgrid Dot In Profit`
- `NQ NO-CHASE — Upper Band Breakout`
- `NQ NEWS LOCKOUT — Do Not Trade`

## 4. Manual Tradovate workflow

Before entering:

- Confirm symbol.
- Confirm account.
- Confirm contract quantity.
- Confirm stop distance.
- Confirm daily loss remaining.
- Confirm no duplicate position is open.

Order process:

1. Use bracket/OCO order.
2. Place protective stop immediately.
3. Place target order immediately.
4. Do not widen stop after entry.
5. Move stop to break-even only when plan allows.
6. If platform behavior is uncertain, trade MNQ or paper until confirmed.

## 5. Position sizing

General formula:

```text
Dollar risk = stop distance in points × dollars per point × contracts
```

NQ is much larger than MNQ. Use MNQ for testing or when stop size is too large for the prop-firm risk plan.

## 6. Break-even rules

Possible break-even triggers:

- After first partial at 1R.
- After price closes beyond Qwave/Qbands midline.
- After price breaks and holds beyond structure.
- After Qgrid add is taken and total position risk must be protected.

Do not move to break-even too early if normal pullback would stop you out.

## 7. Scaling rules

The Qpro video describes scaling out in groups at logical levels.

Practical model:

- Partial 1: midline or 1R
- Partial 2: upper/lower band or 2R
- Partial 3: major level, golden pocket, prior high/low, or opposing liquidity
- Runner: trail with Qline/Qcloud or structure

Prop-firm simplification:

- Start with one contract or MNQ.
- Scale only after you have a documented edge.
- Avoid large contract sets until the playbook is proven.

## 8. Daily risk protection

Set these before the session:

- Max daily loss
- Max trades
- Max consecutive losses
- Max size
- News lockout windows
- Time of day to stop trading

Suggested conservative defaults:

- Stop after 3 losses.
- Stop after 2 full-risk losses.
- Stop after one emotional/rule-breaking trade.
- Reduce size after first loss.

## 9. Common execution mistakes

- Taking alert without confluence.
- Forgetting Tradovate is real execution while TradingView is only charting.
- Entering before stop/target is known.
- Adding with Qgrid while the original trade is losing.
- Trading NQ size when MNQ is more appropriate.
- Trading through news.
- Widening stop after entry.

## 10. Manual execution checklist

Before clicking buy/sell:

```text
[ ] Correct Tradovate account selected
[ ] Correct symbol selected
[ ] Setup name identified
[ ] Bias matches trade direction
[ ] Entry level defined
[ ] Stop level defined
[ ] Target 1 defined
[ ] Reward:risk acceptable
[ ] Daily risk remaining
[ ] News checked
[ ] Confluence score >= 7
```
