# Sentiment Segment Analysis - Cycle 1 (2026-06-20)

## Claims Used
- C-2026-06-20-SENTIMENT-C1-SESSION-BASIS
- C-2026-06-20-SENTIMENT-C1-FEAR-GREED
- C-2026-06-20-SENTIMENT-C1-VOLATILITY
- C-2026-06-20-SENTIMENT-C1-PUTCALL
- C-2026-06-20-SENTIMENT-C1-AAII
- C-2026-06-20-SENTIMENT-C1-FLOWS
- C-2026-06-20-SENTIMENT-C1-SYNTHESIS

## Overview
The June 20 report date is a weekend no-session day for US cash equities, immediately after the Juneteenth closure on Friday, June 19. The sentiment ledger is therefore a latest-available pre-weekend read, not a Saturday trading print. The clean signal is mixed rather than one-directional: CNN Fear & Greed remained in "fear" at 37.26 as of June 19 and retail investors were still net bearish in the June 18 AAII survey, but volatility was not in panic territory and ETF flow data showed large equity and semiconductor inflows into the weekend.

The result is a defensive sentiment label with risk-appetite pockets. Investors were not euphoric on broad composite or survey gauges, yet actual fund-flow behavior still chased US equities, semiconductors, and large passive exposure. That tension matters for the full Pulse: it argues against calling the tape outright bearish, but it also leaves the market vulnerable to weekend gap risk if geopolitics or rates challenge the flow momentum.

## Sentiment Snapshot
| Signal | As of / basis | Reading | Source |
| --- | --- | --- | --- |
| Report-date market basis | 2026-06-20, Saturday | No regular US cash-equity session; Juneteenth closed NYSE markets on June 19 | S-2026-06-20-713 |
| CNN Fear & Greed mirror | 2026-06-19 00:59:47 UTC | 37.26, "fear"; previous week 35.51, previous month 59.37 | S-2026-06-20-701; S-2026-06-20-702 |
| VIX | 2026-06-19 Cboe CSV row | 16.78, up from 16.40 on June 18 | S-2026-06-20-703 |
| Volatility term structure | Latest common Cboe row, 2026-06-18 | VIX9D 13.93, VIX 16.40, VIX3M 19.57, VIX6M 21.99 | S-2026-06-20-703; S-2026-06-20-704; S-2026-06-20-705; S-2026-06-20-706 |
| Cboe put/call | Latest dated YCharts/Cboe period, 2026-06-18 | Total 0.91; equity 0.58; current Cboe page shows the same ratios | S-2026-06-20-707; S-2026-06-20-708; S-2026-06-20-709 |
| AAII retail survey | Week of 2026-06-18 | Bullish 36.6%, neutral 24.1%, bearish 39.4%; bull-bear spread about -2.8 pp | S-2026-06-20-710 |
| ICI fund flows | Week ended 2026-06-10, released 2026-06-17 | Long-term fund/ETF inflows $31.52B; ETF net issuance $48.33B; commodity outflows $2.27B | S-2026-06-20-711 |
| ETF.com weekly flows | Week ended 2026-06-12, published 2026-06-15 | US-listed ETF inflows $41.80B; US equity +$22.83B; US fixed income +$11.07B; commodities -$1.70B | S-2026-06-20-712 |
| ETF.com daily flows | Data as of 2026-06-18 06:00 ET | Daily ETF inflows $64.55B; US equity +$53.80B; SMH +$6.93B; QQQ +$3.43B | S-2026-06-20-714 |

## Composite Sentiment
The headline composite was still defensive. The public GitHub mirror of CNN's Fear & Greed endpoint showed a June 19 score of 37.2571, labeled "fear", with the same value in its generated CNN JSON at timestamp 2026-06-19T00:59:47Z. That was only slightly above the prior-week reading of 35.5143, but well below the prior-month reading of 59.3714. MacroMicro's live chart snippet corroborated the June 19 level at 37.26. CNN's own endpoint returned a bot block during this collection, so the ledger uses the mirror and MacroMicro rather than claiming a direct CNN fetch.

The composite message is not capitulation. A score near 37 is inside CNN's fear band, not extreme fear. It says the market entered the weekend cautious after the early-June volatility burst, but not washed out.

## Volatility And Options
Cboe's VIX historical CSV showed VIX at 16.78 on its June 19 row, up from 16.40 on June 18 and down from the June 17 spike at 18.44. The latest common date across the Cboe volatility curve was June 18: VIX9D at 13.93, VIX at 16.40, VIX3M at 19.57, and VIX6M at 21.99. That upward slope is consistent with contained spot stress and greater uncertainty priced further out, rather than front-end panic.

Options positioning was not complacent, but equity-only demand still leaned call-heavy. YCharts' Cboe-sourced pages listed the latest dated June 18 readings at 0.91 for total put/call and 0.58 for equity put/call; Cboe's daily market-statistics page, accessed for this cycle, showed the same current ratios and the underlying volume split. Total put/call near 0.9 reflects hedging demand across all products, while equity put/call below 0.6 points to continued single-stock call appetite.

## Survey Sentiment
The AAII retail survey was still net bearish but improved. AAII's June 18 Seeking Alpha post reported bullish sentiment up 6.2 percentage points to 36.6%, neutral sentiment up 2.1 points to 24.1%, and bearish sentiment down 8.3 points to 39.4%. That puts the bull-bear spread at roughly -2.8 percentage points. Retail investors therefore remained more bearish than bullish, but the direction of travel was less pessimistic than the prior survey.

## Flow Sentiment
Fund-flow behavior was more constructive than the surveys. ICI's June 17 release for the week ended June 10 reported $31.52 billion of estimated long-term fund and ETF inflows, including $48.33 billion of ETF net issuance. Equity funds took in $16.64 billion, domestic equity funds $18.28 billion, and bond funds $18.21 billion; commodity funds lost $2.27 billion. The flow split is not a pure risk-on message because bonds also drew money and commodities saw redemptions, but it does show fresh capital still entering market exposure.

ETF.com's more recent weekly and daily flow stories sharpen that point. For the week ended June 12, US-listed ETFs took in $41.80 billion, with US equity ETFs adding $22.83 billion and US fixed income adding $11.07 billion. VOO and SPY were large creation-side winners, while QQQ and GLD were redemption-side names. On the June 18 daily screen, total ETF inflows jumped to $64.55 billion and US equity ETFs alone added $53.80 billion, with SMH adding $6.93 billion and QQQ adding $3.43 billion. That is active chase behavior in semiconductors and broad US equity exposure despite the defensive headline sentiment gauges.

## Read-Through
The sentiment read for the weekend is mixed-defensive. Fear & Greed and AAII say caution; the volatility curve says stress is present but not disorderly; Cboe put/call ratios show hedging in aggregate but still-call-heavy single-stock behavior; ETF flows say buyers were still willing to allocate aggressively to equities and semiconductors. The most useful label is "fear headline, risk-appetite flows."

For the June 20 Pulse, that means the market setup is fragile rather than outright bearish. A negative weekend catalyst could hit a market with headline fear already elevated, but the flow base still contains enough risk appetite to buy dips if the catalyst set stabilizes into the June 22 reopen.

## Source Basis
The report-date session basis comes from the official NYSE 2026 calendar and trading-hours page, which lists Juneteenth National Independence Day on Friday, June 19, and normal core trading hours only for trading sessions. CNN Fear & Greed is sourced to the public `whit3rabbit/fear-greed-data` mirror of CNN's endpoint, with MacroMicro used as corroboration because CNN's live endpoint blocked automated access. VIX and volatility-curve data are sourced to Cboe's public historical CSV files. Put/call readings are sourced to Cboe's daily market-statistics page and YCharts' Cboe-sourced dated pages. Retail survey readings are sourced to AAII's June 18 Seeking Alpha post. Fund-flow readings are sourced to ICI's June 17 combined long-term flows release and ETF.com's June 15 and June 18 flow articles. Every sentiment value is tied to a named source.
