# 26 — Market Data Stream Decision

## Question

Do we need any additional TradingView data streams beyond the CME Group futures package?

## Decision

For the current QuantVue Pro NQ/MNQ futures workflow, the required data stream is:

```text
CME Group futures data
```

The user already reports this is subscribed:

```text
CME Group (E-mini included)
CME, CBOT, COMEX, NYMEX
Subscribed
```

## Current answer

No additional TradingView data streams are needed right now if the user is only trading:

```text
NQ1!
MNQ1!
ES/MES
YM/MYM
RTY/M2K
CL
GC
```

These are covered by the CME Group exchange family when the correct real-time futures data package is active.

## Do not buy additional data streams yet

Do not buy:

```text
NASDAQ stocks data
NYSE stocks data
NYSE Arca stocks data
OPRA options data
CBOE data
Crypto data
Forex data
International exchange data
```

unless the strategy specifically requires one of those instruments.

## When additional data might be needed

Additional streams may be needed only if the user starts using:

```text
QQQ / SPY / stock market internals requiring equity exchange data
Options flow or OPRA options chains
VIX / CBOE index data
NASDAQ TotalView or stock depth data
NYSE stocks
International futures or CFDs
Broker-specific synthetic NAS100 / US100 symbols
```

## Verification checklist

Before paying for anything extra, verify:

```text
[ ] NQ1! does not say delayed
[ ] MNQ1! does not say delayed
[ ] ES1! / MES1! do not say delayed if used
[ ] Tradovate connection routes orders correctly
[ ] QuantVue indicators update in real time on NQ/MNQ
[ ] The selected TradingView symbol is CME/Globex futures, not a CFD/synthetic NAS100 symbol
```

## Rule

```text
Only pay for data for the instruments actually traded or required by the layout.
```

## Current recommendation

```text
Keep CME Group only.
Do not add more data streams yet.
Spend the money only if a specific chart/layout says delayed or unavailable.
```
