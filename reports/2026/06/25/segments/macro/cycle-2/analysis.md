# Macro Analysis - 2026-06-25 - Cycle 2

**As of:** 2026-06-25 (Thursday). The session anchor was the BEA May 2026 Personal Income and Outlays release, published before the U.S. cash session, plus the official U.S. Treasury 06/25/2026 par-yield row and mutable public vendor pages for DXY, Brent and gold. All vendor market prices are treated as basis-specific live references, not official settlement records.

**Basis:** BEA data are the official May 2026 release dated June 25. Treasury rates are the official 06/25/2026 par-yield curve row versus the 06/24/2026 row. DXY, Brent and gold are Trading Economics live public pages updated around 2026-06-25 23:15-23:20 UTC; their mutable source and OTC/CFD basis are disclosed in `sources.yaml`. This cycle removes the unsupported consensus/causality language from cycle 1 and uses only source-backed release data plus attributed market context.

## Claims Used
- C-2026-06-25-MACRO-C2-SESSION-STATUS
- C-2026-06-25-MACRO-C2-PCE
- C-2026-06-25-MACRO-C2-TREASURY-CURVE
- C-2026-06-25-MACRO-C2-DXY
- C-2026-06-25-MACRO-C2-BRENT
- C-2026-06-25-MACRO-C2-GOLD

## Market Snapshot
| Signal | As of / basis | Reading | Source |
| --- | --- | --- | --- |
| Session anchor | 2026-06-25, U.S. macro session | BEA May Personal Income and Outlays release; official Treasury 06/25 row available | S-2026-06-25-802; S-2026-06-25-801 |
| May PCE release | May 2026, released 2026-06-25 | Personal income +0.7%; current-dollar PCE +$156.1B / +0.7%; real PCE +$43.8B / +0.3%; PCE prices +0.4% MoM / +4.1% YoY; core +0.3% MoM / +3.4% YoY | S-2026-06-25-802 |
| U.S. Treasury curve | 2026-06-25 official par-yield close | 2Y 4.09%, 5Y 4.15%, 10Y 4.40%, 30Y 4.86%; 2s10s +31 bp; 2Y and 5Y -2 bp vs Jun 24, 10Y -1 bp | S-2026-06-25-801; S-2026-06-25-803 |
| U.S. Dollar Index | 2026-06-25 Trading Economics daily update | 101.4879, -0.12% on the day, +2.34% over one month | S-2026-06-25-804 |
| Brent crude | 2026-06-25 Trading Economics CFD basis | $74.84/bbl, +1.50% on the day, -22.58% over one month | S-2026-06-25-805 |
| Gold | 2026-06-25 Trading Economics OTC/CFD basis | $4,024.91/t oz, +0.63% on the day, -10.76% over one month | S-2026-06-25-806 |

## Analysis

June 25 was a macro-data session, not a clean risk-on or risk-off session. The hard data message from BEA was sticky inflation alongside resilient nominal income and positive real spending: personal income rose $181.6B / 0.7%, current-dollar PCE rose $156.1B / 0.7%, and real PCE rose $43.8B / 0.3% in May. The PCE price index increased 0.4% month over month and 4.1% year over year; core PCE increased 0.3% month over month and 3.4% year over year. The important correction versus the blocked cycle 1 artifact is that May spending was not soft in the BEA release: current-dollar PCE was +0.7% and real PCE was +0.3%. [C-2026-06-25-MACRO-C2-PCE]

Rates did not sell off on that data. The official Treasury par curve closed with the 2-year at 4.09%, the 5-year at 4.15%, the 10-year at 4.40% and the 30-year at 4.86%. Against June 24, that is a small front/intermediate rally: -2 bp on the 2-year, -2 bp on the 5-year, -1 bp on the 10-year and flat 20-year/30-year yields. The 2s10s slope widened only 1 bp, from +30 bp to +31 bp, so the curve move is better described as a modest lower-yield drift than a major steepening signal. Trading Economics separately described the 10-year near 4.40% as the lowest in seven weeks, but that is carried as vendor context, not an official Treasury label. [C-2026-06-25-MACRO-C2-TREASURY-CURVE]

The dollar softened only slightly. On Trading Economics' mutable DXY page, the Dollar Index was 101.4879 on June 25, down 0.12% from the previous session, while still up 2.34% over the past month and 4.47% over the past year. That mix matters for the macro read: the day did not erase the dollar's broader tightening impulse, but it did interrupt the latest rally as markets digested the inflation, spending and oil-supply signals. [C-2026-06-25-MACRO-C2-DXY]

Oil remained the disinflationary offset even though Brent bounced on the day. Trading Economics showed Brent at $74.84/bbl on its CFD reference basis, up 1.50% on June 25 but down 22.58% over one month. The page commentary pointed to renewed Strait of Hormuz shipping concerns after a cargo ship was struck off Oman, while also keeping the broader supply-normalization story alive after US-Iran peace progress. For the macro tape, that means the daily oil bounce was not enough to undo the month-long energy-price relief channel. [C-2026-06-25-MACRO-C2-BRENT]

Gold picked up the lower-yield and softer-dollar side of the session. Trading Economics reported gold at $4,024.91/t oz, up 0.63% on the day, while still down 10.76% over one month and up 20.92% year over year. Its commentary attributed the rebound to a weaker dollar and lower Treasury yields after the PCE release. This is a vendor-basis market read, but it is internally consistent with the official Treasury move and the DXY page: less rate pressure on the day, not a full reversal of the broader hawkish-dollar backdrop. [C-2026-06-25-MACRO-C2-GOLD]

Net read: cycle 2 should replace cycle 1 because the corrected source trail changes the spending interpretation. May inflation was still too hot for a dovish all-clear, with headline PCE at +0.4% MoM / +4.1% YoY and core at +0.3% MoM / +3.4% YoY. But spending and income were firm, not flat, and the market response was a modest Treasury rally, a slight DXY pullback, an oil complex still far below its prior-month level, and a gold rebound. The clean macro conclusion is mixed: inflation pressure remains elevated, real demand did not crack, and the cross-asset tape leaned toward lower immediate inflation-risk pricing without supporting an unsupported "PCE met consensus, therefore Treasuries rallied" causal claim. [C-2026-06-25-MACRO-C2-SESSION-STATUS]

## Source Basis
- **S-2026-06-25-801** - U.S. Treasury official June 2026 daily par-yield CSV, fetched live: 06/25/2026 row 2Y 4.09, 5Y 4.15, 10Y 4.40, 20Y 4.87, 30Y 4.86; 06/24/2026 row 2Y 4.11, 5Y 4.17, 10Y 4.41, 20Y 4.87, 30Y 4.86.
- **S-2026-06-25-802** - BEA Personal Income and Outlays, May 2026: personal income +$181.6B / +0.7%, DPI +$164.9B / +0.7%, current-dollar PCE +$156.1B / +0.7%, real PCE +$43.8B / +0.3%, PCE prices +0.4% MoM / +4.1% YoY, core +0.3% MoM / +3.4% YoY.
- **S-2026-06-25-803** - Trading Economics US 10-year Treasury note yield page, mutable vendor context: 10Y around 4.40%, lowest in seven weeks, down 0.10 points over the past month.
- **S-2026-06-25-804** - Trading Economics U.S. Dollar page, mutable vendor basis: DXY 101.4879, -0.12% daily, +2.34% one-month, +4.47% 12-month.
- **S-2026-06-25-805** - Trading Economics Brent page, mutable CFD basis: Brent $74.84/bbl, +1.50% daily, -22.58% one-month, +12.22% 12-month, with Strait of Hormuz shipment-monitoring context.
- **S-2026-06-25-806** - Trading Economics gold page, mutable OTC/CFD basis: gold $4,024.91/t oz, +0.63% daily, -10.76% one-month, +20.92% 12-month, with lower-yield/weaker-dollar rebound context.
