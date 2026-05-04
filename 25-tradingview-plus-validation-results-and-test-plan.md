# 25 — TradingView Plus Validation Results and Test Plan

This document answers whether TradingView Plus appears sufficient for the QuantVue Pro NQ/MNQ workflow and defines the exact empirical tests to run before buying Premium.

## Bottom line

Current research indicates:

```text
TradingView Plus should be enough to test and begin the QuantVue workflow.
Do not upgrade to Premium unless Plus fails one of the validation tests below.
```

## What TradingView Plus appears to include

TradingView's current pricing/features indicate Plus includes:

```text
4 charts per tab
10 indicators per chart
10K historical bars
100 price alerts
100 technical alerts
Second-based intervals
Intraday Renko
Bar Replay
10 saved chart layouts
```

This is enough on paper for:

```text
4-chart QuantVue layout
Banksy Manual Layout if each chart stays under 10 indicators
Alfredo Qpilot Manual Layout if each chart stays under 10 indicators
NQ/MNQ Renko execution chart
Basic alert testing
Replay validation on recent data
```

## Known documentation conflict

There is a mismatch between current TradingView features and QuantVue's FAQ-style guidance.

```text
TradingView current feature table: Plus includes second-based intervals and intraday Renko.
QuantVue FAQ/guidance: Premium may be recommended/required for 1-second data and Renko bricks.
```

Interpretation:

```text
QuantVue may be using older TradingView plan guidance, or they may recommend Premium conservatively because of replay/history depth and fewer limits.
```

Decision:

```text
Validate Plus empirically. Upgrade only if an actual layout or feature fails.
```

## Requirement-by-requirement answer

## 1. Does 1-second Renko work on Plus?

Research answer:

```text
Likely yes for live charting, because Plus shows second-based intervals and intraday Renko.
```

But this must be tested inside the account because QuantVue's docs may still recommend Premium.

Test:

```text
Open NQ1!
Switch interval to 1S
Change chart type to Renko
Set Renko type to Traditional
Test box sizes 2, 3, 4, and 5
```

Pass:

```text
1S is selectable and Traditional Renko renders normally.
```

Fail:

```text
1S is blocked, Renko is blocked, or 1S + Renko cannot be used together.
```

## 2. Does Banksy layout load on Plus?

Research answer:

```text
Unknown until opened in the user's account.
```

Reason:

```text
Shared TradingView chart links are private/account-specific runtime tests. Public docs cannot show exactly how many indicators are active on each chart after permissions are applied.
```

Test:

```text
Open Banksy Manual Setup / Banksy Manual Layout from Pro Chart Layouts.
Save a copy.
Count charts.
Count indicators per chart.
Check for missing indicators.
```

Pass:

```text
4 or fewer charts total.
10 or fewer indicators per chart.
No missing invite-only or freebie indicators.
Layout saves correctly.
```

Fail:

```text
More than 4 charts, more than 10 indicators on any chart, or missing/unavailable indicators.
```

## 3. Does Alfredo Qpilot layout load on Plus?

Research answer:

```text
Unknown until opened in the user's account.
```

Reason:

```text
The layout depends on Q_Pilot and any public/free scripts included in that shared layout.
```

Test:

```text
Open Alfredo's Qpilot Manual Layout.
Save a copy.
Confirm Q_Pilot loads.
Count charts.
Count indicators per chart.
Check for missing indicators.
```

Pass:

```text
4 or fewer charts.
10 or fewer indicators per chart.
Q_Pilot loads successfully.
No critical missing scripts.
```

Fail:

```text
Q_Pilot missing, layout exceeds Plus limits, or critical indicator permissions are missing.
```

## 4. Does any chart exceed 10 indicators?

Research answer:

```text
Unknown until the shared layouts are opened.
```

TradingView Plus limit:

```text
10 indicators per chart.
```

Test:

```text
Open Object Tree or Indicators list on each chart.
Count each active indicator.
```

Pass:

```text
Each chart is 10 or fewer indicators.
```

Fail:

```text
Any chart has 11 or more indicators and cannot be simplified without breaking the layout.
```

## 5. Are 4 charts enough?

Research answer:

```text
Yes for the planned workflow.
```

Recommended 4-chart workflow:

```text
Chart 1: 4H or 15m key levels / pivots
Chart 2: 5m SMC / structure / location
Chart 3: Renko execution with Qpro / Qwave / Qline / Moneyball
Chart 4: Optional Qpilot / Qgrid / MNQ execution / 3m OR
```

If a shared layout uses more than 4 charts:

```text
Simplify before upgrading.
```

Upgrade only if:

```text
The extra charts are essential and cannot be consolidated.
```

## 6. Is replay depth acceptable?

Research answer:

```text
Probably acceptable for recent workflow training, but Premium is better for deep historical second-based replay.
```

Plus appears suitable for:

```text
Recent replay
1-minute replay
Basic layout validation
Pattern recognition drills
```

Premium may be justified if:

```text
You need older 1-second sessions.
You need deep historical Renko/second-based replay.
You need many months/years of granular second-based replay.
```

## Decision matrix

| Requirement | Plus likely enough? | Certainty | How to verify |
|---|---:|---:|---|
| 1-second interval | Likely yes | Medium-high | Open NQ1! and select 1S |
| Traditional Renko | Likely yes | Medium-high | Change chart type to Renko |
| 1-second Traditional Renko | Likely yes, but must test | Medium | Combine 1S + Traditional Renko |
| Banksy layout loads | Unknown | Low until tested | Open shared layout and count charts/indicators |
| Alfredo layout loads | Unknown | Low until tested | Open shared layout and confirm Q_Pilot/scripts |
| 10 indicators per chart enough | Likely yes if layout is clean | Medium | Count indicators on each chart |
| 4 charts enough | Yes for planned workflow | High | Use 4-chart master layout |
| Replay depth acceptable | Yes for recent validation, not deep historical 1S | Medium | Test three replay sessions |

## Upgrade triggers

Upgrade to Premium only if one of these happens:

```text
1S is blocked on Plus.
1S + Traditional Renko is blocked on Plus.
Banksy layout needs more than 4 charts.
Alfredo layout needs more than 4 charts.
Any required chart needs more than 10 indicators and cannot be simplified.
Replay depth is insufficient for the validation plan.
You need more than 100 technical alerts.
```

## Do not upgrade for these reasons alone

Do not upgrade just because:

```text
Premium is safer.
QuantVue mentioned Premium without testing current Plus.
A layout looks busy but can be simplified.
You might need more alerts later.
You are still in replay/paper validation.
```

## Exact testing order

```text
1. Favorite/freebie all required public scripts from Members Freebies.
2. Confirm QuantVue invite-only indicators are visible.
3. Open NQ1! and MNQ1! and confirm realtime data.
4. Test NQ1! 1S normal candles.
5. Test NQ1! Traditional Renko box size 2.
6. Test NQ1! Traditional Renko box size 3.
7. Test NQ1! Traditional Renko box size 4.
8. Test NQ1! Traditional Renko box size 5.
9. Open Banksy Manual Layout.
10. Open Alfredo Qpilot Manual Layout.
11. Count charts and indicators.
12. Run one recent replay session.
13. Decide whether Plus passes or Premium is necessary.
```

## Final recommendation

```text
Stay on TradingView Plus for now.
Run the tests.
Upgrade only if Plus fails a specific requirement.
```
