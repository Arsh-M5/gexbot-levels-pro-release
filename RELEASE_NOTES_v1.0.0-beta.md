# Gexbot Levels Pro — v1.0.0-beta

**First public beta.** Compiled, obfuscated ATAS X indicator (`net10.0`).

Gexbot Levels Pro renders GEXBOT gamma-structure levels — Major Positive /
Negative gamma, Zero-Gamma, top-N per-strike GEX (volume and open interest) and
state Major Call / Major Put — directly on the futures chart, projected onto the
instrument's exact price scale.

## Highlights
- **Validated on NQ and ES.** Conversion engine numerically verified against live
  GEXBOT data: NDX→NQ and SPX→ES within basis-freshness tolerance; iso-% fallback
  preserves the exact percentage offset for single names.
- **Liquidity / confluence zones.** Levels that stack within a configurable tick
  tolerance are grouped into highlighted intervention zones, with distinct-source
  and minimum-count rules.
- **Two modes.** Epoch-guarded *Frozen EOD* snapshot and periodic *Live* refresh
  (fast `state` loop / slower `classic` loop).
- **Correctness guards.** Contract-roll protection, maximum-basis-age gate, and
  explicit banners for intraday / forced-target / stale-basis conditions.

## Contents of this release
- `Gexbot_Levels_Pro_Hermes.dll` — the obfuscated indicator assembly.

## Installation
Copy the DLL into `%APPDATA%\ATAS X\Indicators`, restart ATAS X, add
**Gexbot Levels Pro** to a chart, and enter your GEXBOT API key. See `README.md`
for parameters.

## Requirements
- ATAS X (`net10.0`)
- A valid GEXBOT API key

## Known limitations (beta)
- Conversion accuracy depends on GEXBOT basis freshness; keep native
  (`NQ_NDX` / `ES_SPX`) tickers available when using iso-% conversions.
- Half-sessions and unusual expiry calendars may affect EOD tagging.

## Disclaimer
For informational purposes only; not investment advice. Trading leveraged
instruments carries substantial risk of loss. Software provided "as is" without
warranty. See the full disclaimer in `README.md`.
