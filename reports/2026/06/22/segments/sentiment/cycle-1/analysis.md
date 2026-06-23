# Sentiment Segment Analysis - Cycle 1 (2026-06-22)

## Claims Used
- C-2026-06-22-SENTIMENT-C1-SESSION-BASIS
- C-2026-06-22-SENTIMENT-C1-US-CLOSE
- C-2026-06-22-SENTIMENT-C1-FEAR-GREED
- C-2026-06-22-SENTIMENT-C1-VOLATILITY
- C-2026-06-22-SENTIMENT-C1-PUTCALL
- C-2026-06-22-SENTIMENT-C1-AAII
- C-2026-06-22-SENTIMENT-C1-FLOWS
- C-2026-06-22-SENTIMENT-C1-SYNTHESIS

## Overview
June 22 was a live U.S. cash-equity session after the Juneteenth/weekend break, and the sentiment tape reopened with a split message. Broad price action was rotation rather than liquidation: AP reported the S&P 500 down 0.4% to 7,472.79 and the Nasdaq Composite down 1.3% to 26,166.60 as Big Tech weakened, while the Dow rose 0.3% to 51,712.71 and the Russell 2000 gained 0.8% to 3,004.40. [C-2026-06-22-SENTIMENT-C1-US-CLOSE]

The direct sentiment gauges stayed defensive. The public CNN Fear & Greed mirror printed 34.74 for June 22, still in "fear", after 31.60 on June 19 and 41.57 on June 15. VIX rose to 17.28 from 16.78, and Cboe's daily market-statistics page showed total put/call at 0.92 and equity put/call at 0.60. Those are caution readings, but not panic readings. [C-2026-06-22-SENTIMENT-C1-FEAR-GREED, C-2026-06-22-SENTIMENT-C1-VOLATILITY, C-2026-06-22-SENTIMENT-C1-PUTCALL]

Flows were the offset. ETF.com's June 22 weekly-flow article reported $119.83 billion of total ETF inflows, led by $83.62 billion into U.S. equity ETFs and $21.66 billion into international equity ETFs, with IVV, SPYM, XLK, and SMH among the largest creations. Retail survey sentiment remained net bearish, but AAII's latest survey showed pessimism receding and the bull-bear spread improving to -2.8 percentage points. [C-2026-06-22-SENTIMENT-C1-AAII, C-2026-06-22-SENTIMENT-C1-FLOWS]

## Sentiment Snapshot
| Signal | As of / basis | Reading | Source |
| --- | --- | --- | --- |
| Report-date market basis | 2026-06-22, Monday | Regular U.S. cash-equity session after Juneteenth/weekend closure | S-2026-06-22-801; S-2026-06-22-802 |
| U.S. close context | 2026-06-22 close | S&P 500 -0.4% to 7,472.79; Nasdaq -1.3% to 26,166.60; Dow +0.3% to 51,712.71; Russell 2000 +0.8% to 3,004.40 | S-2026-06-22-802 |
| CNN Fear & Greed mirror | 2026-06-22 | 34.74, "fear"; prior market day 31.60, prior week 41.57 | S-2026-06-22-803; S-2026-06-22-804 |
| VIX | 2026-06-22 Cboe CSV row | 17.28 close, up 0.50 points or 2.98% from June 19 | S-2026-06-22-805 |
| Volatility curve | 2026-06-22 common Cboe row | VIX9D 16.29, VIX 17.28, VIX3M 19.76, VIX6M 22.15 | S-2026-06-22-805; S-2026-06-22-806; S-2026-06-22-807; S-2026-06-22-808 |
| Cboe put/call | Page accessed 2026-06-23; current daily table | Total 0.92; index 1.08; ETP 1.15; equity 0.60; VIX 0.23; SPX + SPXW 1.22 | S-2026-06-22-809 |
| AAII retail survey | Latest survey published 2026-06-20 | Bullish 36.6%, neutral 24.1%, bearish 39.4%; bull-bear spread -2.8 pp | S-2026-06-22-810 |
| ICI fund flows | Week ended 2026-06-10, released 2026-06-17 | Long-term fund/ETF inflows $31.52B; ETF net issuance $48.33B; equity +$16.64B; bond +$18.21B; commodity -$2.27B | S-2026-06-22-811 |
| ETF.com weekly flows | Published 2026-06-22, data as of 6 a.m. ET | Total ETF inflows $119.83B; U.S. equity +$83.62B; international equity +$21.66B; U.S. fixed income +$8.15B; leveraged -$0.51B | S-2026-06-22-812 |

## Composite Sentiment
The composite headline stayed in fear. The public `whit3rabbit/fear-greed-data` mirror showed 34.7429 for June 22, while MacroMicro's page showed the same June 22 CNN Fear & Greed level at 34.74. That was above the June 19 mirror value of 31.60, but below the June 15 value of 41.57. The signal is therefore "fear, modestly repaired from Friday's low", not a durable risk-on reset.

## Volatility And Options
Cboe's VIX historical CSV printed a June 22 close of 17.28, up from 16.78 on June 19. The one-day increase was about 2.98%, but the level remained below the June 17 spike of 18.44. The curve was still upward-sloping on the same June 22 date: VIX9D 16.29, VIX 17.28, VIX3M 19.76, and VIX6M 22.15. That shape shows near-term stress lifted, but not a front-end volatility inversion.

Cboe's daily options market-statistics page was consistent with hedging demand rather than disorder. Total put/call stood at 0.92, index put/call at 1.08, ETP put/call at 1.15, and equity put/call at 0.60. Investors were buying protection or downside exposure in index and ETP products, while equity-only flow remained call-heavy enough to keep the equity ratio well below 1.0.

## Survey Sentiment
The latest AAII survey was still net bearish but less so than the prior week. AAII's June 20 post reported bullish sentiment up 6.2 percentage points to 36.6%, neutral up 2.1 points to 24.1%, and bearish down 8.3 points to 39.4%. The bull-bear spread improved to -2.8 percentage points. That does not remove retail caution, but it does argue against a capitulation-style survey backdrop.

## Flow Sentiment
The strongest risk-appetite evidence came from flows. ICI's latest combined long-term fund and ETF release, for the week ended June 10, showed $31.52 billion of total estimated inflows, with $48.33 billion of ETF net issuance, $16.64 billion into equity funds, $18.21 billion into bond funds, and $2.27 billion out of commodity funds.

ETF.com's June 22 weekly-flow article was more current and more aggressive: total ETF inflows were $119.83 billion, U.S. equity ETFs took in $83.62 billion, international equity ETFs took in $21.66 billion, and U.S. fixed income ETFs added $8.15 billion. The top creations included IVV at $30.40 billion, SPYM at $12.87 billion, XLK at $8.33 billion, and SMH at $7.44 billion. Redemptions from SPY and VOO show vehicle-level rotation, not a simple equity exit, because the asset-class total for U.S. equity remained strongly positive.

## Read-Through
The June 22 sentiment regime is "fear headline, rotation bid underneath." The visible tape was not euphoric: Big Tech dragged the Nasdaq lower, Fear & Greed stayed in fear, VIX rose, and index/ETP put-call ratios reflected hedging. But the Dow and Russell 2000 gained, volatility did not break into panic, AAII pessimism receded, and ETF flows still showed heavy equity allocation.

For the full Pulse, that makes sentiment fragile but not washed out. Risk is concentrated in crowded technology exposure and in any next-day follow-through from the Nasdaq selloff; the offset is that allocation behavior still favors equities, including technology and semiconductors, rather than cash-like retreat.

## Source Basis
The report-date session basis uses NYSE trading-hours policy and AP's June 22 U.S. close. CNN Fear & Greed uses the public GitHub mirror of CNN's endpoint, corroborated by MacroMicro. Volatility data use Cboe public historical CSV files. Options sentiment uses Cboe's public daily market-statistics page. Retail survey readings use AAII's June 20 sentiment post. Fund-flow readings use ICI's June 17 release and ETF.com's June 22 weekly-flow article. Every material number in this segment is represented in `claims.jsonl` and tied to a source ID in `sources.yaml`.
