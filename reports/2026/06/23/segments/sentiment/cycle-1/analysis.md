# Sentiment Segment Analysis - Cycle 1 (2026-06-23)

## Claims Used
- C-2026-06-23-SENTIMENT-C1-SESSION-BASIS
- C-2026-06-23-SENTIMENT-C1-US-CLOSE
- C-2026-06-23-SENTIMENT-C1-FEAR-GREED
- C-2026-06-23-SENTIMENT-C1-VOLATILITY
- C-2026-06-23-SENTIMENT-C1-PUTCALL
- C-2026-06-23-SENTIMENT-C1-AAII
- C-2026-06-23-SENTIMENT-C1-FLOWS
- C-2026-06-23-SENTIMENT-C1-SYNTHESIS

## Overview
June 23 was a live U.S. cash-equity session and the sentiment tape deteriorated sharply from the prior day's "fear headline, rotation bid" setup. AP reported the S&P 500 fell 1.4% to 7,365.46 and the Nasdaq Composite dropped 2.2% to 25,587.04 as Big Tech and AI-related names sold off, with Micron Technology losing 13.2%. The Dow held up better, slipping just 0.1% to 51,666.84, and the Russell 2000 declined 1.0% to 2,975.48. Unlike June 22's rotation, this was a broader pullback: all four major indexes closed lower. [C-2026-06-23-SENTIMENT-C1-US-CLOSE]

The direct sentiment gauges moved decisively into deeper fear. The Fear & Greed Index dropped to 28 (fear) on the Finhacker.cz CNN-tracker, down from approximately 33–35 at the June 22 close, after CNN also applied a methodology update to its Stock Price Breadth indicator. The Cboe VIX product page, as of 8:15 PM ET on June 23, showed a VIX spot of $19.49, up 12.79% or 2.21 points from the prior close of 17.28. Yahoo Finance historical data confirmed the OHLC: open 19.67, high 20.54, low 18.61, close 19.49. [C-2026-06-23-SENTIMENT-C1-FEAR-GREED, C-2026-06-23-SENTIMENT-C1-VOLATILITY]

Flows had not refreshed since the June 22 weekly cycle. ICI's latest combined long-term flow release, published June 17 for the week ended June 10, showed $31.52 billion of inflows with equity at +$16.64 billion and bond at +$18.21 billion. ETF.com's June 22 weekly-flow article reported $119.83 billion of total ETF inflows led by $83.62 billion into U.S. equity ETFs. These remain the latest available flow readings for the June 23 report date. [C-2026-06-23-SENTIMENT-C1-FLOWS]

## Sentiment Snapshot
| Signal | As of / basis | Reading | Source |
| --- | --- | --- | --- |
| Report-date market basis | 2026-06-23, Tuesday | Regular U.S. cash-equity session, day after Juneteenth-weekend return session | S-2026-06-23-801 |
| U.S. close context | 2026-06-23 close | S&P 500 -1.4% to 7,365.46; Nasdaq -2.2% to 25,587.04; Dow -0.1% to 51,666.84; Russell 2000 -1.0% to 2,975.48 | S-2026-06-23-802 |
| Fear & Greed Index | 2026-06-23 post-close | 28, "fear"; prior close approximately 33–35 | S-2026-06-23-803; S-2026-06-23-804 |
| VIX | 2026-06-23 close | 19.49, up 2.21 points or 12.79% from 17.28 on June 22 | S-2026-06-23-805; S-2026-06-23-806 |
| Volatility curve | 2026-06-23 Cboe rows | VIX9D 19.47, VIX 19.49, VIX3M 21.06, VIX6M 22.97 | S-2026-06-23-807; S-2026-06-23-805; S-2026-06-23-808; S-2026-06-23-809 |
| Cboe put/call | Page accessed 2026-06-23 after close; latest published session | Total 0.92; index 1.08; ETP 1.15; equity 0.60; VIX 0.23; SPX + SPXW 1.22 | S-2026-06-23-810 |
| AAII retail survey | Latest survey published 2026-06-18 (week ending 6/17) | Bullish 36.6%, neutral 24.1%, bearish 39.4%; bull-bear spread -2.8 pp | S-2026-06-23-811 |
| ICI fund flows | Week ended 2026-06-10, released 2026-06-17 | Long-term fund/ETF inflows $31.52B; ETF net issuance $48.33B; equity +$16.64B; bond +$18.21B; commodity -$2.27B | S-2026-06-23-812 |
| ETF.com weekly flows | Published 2026-06-22, data as of 6 a.m. ET | Total ETF inflows $119.83B; U.S. equity +$83.62B; international equity +$21.66B; U.S. fixed income +$8.15B; leveraged -$0.51B | S-2026-06-23-813 |

## Composite Sentiment
The composite headline deepened from "fear headline, rotation bid underneath" on June 22 to unambiguous risk-off on June 23. Finhacker.cz's CNN-tracker showed the Fear & Greed Index at 28 (fear) as of the June 23 post-close update (6:52 PM ET), while CNN's own page displayed 33 with a "Last updated Jun 23 at 4:11 AM ET" timestamp and a published "Index Update" notice about a methodology change to the Stock Price Breadth indicator. The drop from the prior reading of approximately 33–35 into the high-20s is consistent with a session that saw the S&P 500 fall 1.4% and the Nasdaq drop 2.2%. The signal is therefore "deeper fear, rotation bid tested."

## Volatility And Options
Cboe's VIX product page (data as of 8:15 PM ET, June 23) showed a VIX spot price of $19.49, up 12.79% or 2.21 points from the June 22 close of 17.28. Yahoo Finance historical data provided the full OHLC: open 19.67, high 20.54, low 18.61, close 19.49. The intraday range of roughly 1.93 points (18.61 to 20.54) was wider than June 22's range, reflecting elevated uncertainty during the session.

The volatility curve from Cboe's daily CSV files was upward sloping but with a flat front: VIX9D closed at 19.47, VIX at 19.49, VIX3M at 21.06, and VIX6M at 22.97. The near-flat VIX9D-to-VIX relationship (0.02 points apart) shows that very near-term stress almost matched the 30-day measure, but the curve did not invert at the front. The VIX9D itself had an explosive intraday range — open 21.44, high 21.54, low 18.06, close 19.47 — suggesting early session panic that partially eased into the close.

Cboe's daily market-statistics page was accessed after the June 23 close. It displayed total put/call at 0.92, index put/call at 1.08, ETP put/call at 1.15, equity put/call at 0.60, VIX put/call at 0.23, and SPX + SPXW put/call at 1.22. [C-2026-06-23-SENTIMENT-C1-PUTCALL]

## Survey Sentiment
The latest AAII survey remained the June 18 publication covering the week ending June 17, the same reading used for the June 22 report. Bullish sentiment was 36.6%, neutral 24.1%, and bearish 39.4%, leaving a bull-bear spread of -2.8 percentage points. This survey does not yet reflect the June 23 selloff; the next AAII release is expected Thursday June 25. [C-2026-06-23-SENTIMENT-C1-AAII]

## Flow Sentiment
No new weekly fund-flow data was released between the June 22 and June 23 report dates. The latest ICI release, published June 17 for the week ended June 10, showed $31.52 billion of total estimated long-term inflows, with $48.33 billion of ETF net issuance, $16.64 billion into equity funds, $18.21 billion into bond funds, and $2.27 billion out of commodity funds.

ETF.com's June 22 weekly-flow article, the most recent weekly flow source available, reported $119.83 billion of total ETF inflows led by $83.62 billion into U.S. equity ETFs and $21.66 billion into international equity ETFs. Top creations included IVV at $30.40 billion, SPYM at $12.87 billion, XLK at $8.33 billion, and SMH at $7.44 billion. These flow readings are lagging indicators: they predate the June 23 risk-off session and therefore provide context for positioning heading into the selloff, not a real-time gauge of Tuesday's flow response. [C-2026-06-23-SENTIMENT-C1-FLOWS]

## Read-Through
The June 23 sentiment regime is "deeper fear, rotation bid tested." The June 22 setup was fragile but not capitulation — Fear & Greed in fear, VIX contained at 17.28, Dow and Russell positive. June 23 broke that bid: all four major indexes fell, VIX spiked nearly 13% to 19.49, and Fear & Greed dropped to 28. The Dow's narrow 0.1% decline and the modest Russell 2000 drop (1.0%) suggest some rotation persistence, but the breadth of the technology and AI selloff was severe enough to drag the entire tape lower.

For the full Pulse, that makes sentiment a clear risk-off signal. The key question is whether June 23 is a one-day washout or the start of a deeper correction. The AAII survey (next release June 25) and the next round of weekly ETF flows will be critical for confirming whether positioning shifts corroborate the price action. The flat-but-not-inverted VIX9D/VIX front end and the absence of fresh flow data leave the door open to either interpretation. [C-2026-06-23-SENTIMENT-C1-SYNTHESIS]

## Source Basis
The report-date session basis uses NYSE trading-hours policy and AP's June 23 U.S. close. Fear & Greed uses Finhacker.cz's CNN-tracker (updated post-close June 23) corroborated by CNN's Fear & Greed page, which noted a methodology change to its Stock Price Breadth indicator. Volatility data use the Cboe VIX product page for the VIX spot/close, Yahoo Finance for VIX OHLC, and Cboe public historical CSV files for VIX9D, VIX3M, and VIX6M. The Cboe VIX_History.csv had not published a June 23 row at collection time. Options sentiment uses Cboe's public daily market-statistics page. Retail survey readings use AAII's June 18 sentiment publication. Fund-flow readings use ICI's June 17 release and ETF.com's June 22 weekly-flow article, both the latest available. Every material number in this segment is represented in `claims.jsonl` and tied to a source ID in `sources.yaml`.
