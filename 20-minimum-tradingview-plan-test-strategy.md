# 20 — Minimum TradingView Plan Test Strategy

## Decision

Do **not** buy TradingView Premium immediately unless we confirm it is required.

Because QuantVue provides copy/paste Pro chart layouts in Discord, the better approach is to start with the lowest TradingView paid plan that can run the actual QuantVue layouts you intend to use.

## Current practical recommendation

Start with:

```text
TradingView Plus
+ CME real-time futures data
+ QuantVue Pro
+ Tradovate connected for execution
```

Then upgrade only if you hit a real limitation.

## Why not start with Premium automatically?

Premium is the safest plan, but it may be unnecessary if:

- QuantVue's provided layouts fit inside a lower plan.
- You use a 2-chart or 4-chart workflow.
- You do not need many simultaneous alerts yet.
- You are not using a large number of indicators on each chart.
- You can run replay/testing without second-based features beyond your plan limits.

## What must be tested before upgrading

Test QuantVue's actual Discord layouts first.

The user has saved onboarding/layout notes locally at:

```text
C:\Dev\QuantVue\Quant-Vue\Alfredo_Banksys_Pro_Setups.txt
```

This file should be committed to the repo or pasted into ChatGPT so it can be reviewed.

## Minimum-plan decision tree

### Essential may work if:

- You only use a simple 2-chart layout.
- Indicator count stays under the plan limit.
- Alert count stays low.
- You do not need 4 charts at once.

### Plus is the best starting point if:

- You want a 4-chart layout.
- You need more indicators per chart than Essential.
- You need a reasonable number of alerts.
- You want to run QuantVue's Pro layouts without jumping straight to Premium.

### Premium is justified if:

- QuantVue's layouts exceed Plus indicator limits.
- You need more charts per layout than Plus allows.
- You need many active alerts.
- You need second-based/tick features that are unavailable in Plus.
- You run into replay/data/layout limitations during validation.

## Data streams

For NQ1! and MNQ1!, subscribe to the CME real-time futures data package inside TradingView.

Verify after purchase:

```text
NQ1! does not say delayed
MNQ1! does not say delayed
The chart updates in real time
Tradovate routes orders to the correct account
```

## Recommended purchase sequence

1. Keep QuantVue Pro active.
2. Start with TradingView Plus if budget-conscious.
3. Add CME real-time futures data.
4. Connect Tradovate.
5. Load QuantVue's official Discord chart layouts.
6. Test whether the layout loads without indicator/chart/alert limitations.
7. Upgrade to Premium only if TradingView blocks the workflow.

## Rule

Do not pay for Premium because it is theoretically safer. Pay for Premium only if the real QuantVue layout needs it.

## Immediate next step

Review or import:

```text
Alfredo_Banksys_Pro_Setups.txt
```

Then decide whether the official layouts fit inside Essential, Plus, or require Premium.