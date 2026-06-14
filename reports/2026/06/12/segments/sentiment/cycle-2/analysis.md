# Sentiment Analysis - 2026-06-12 - Cycle 2

Report date: 2026-06-12 (Friday, regular U.S. session). Segment: sentiment and positioning.
This cycle replaces the blocked cycle 1 (PR #11), whose source ledger cited a non-verifiable
stand-in URL and whose owner summary described its numbers as not real. All claims below are
backed by real, public, retrievable sources recorded in `sources.yaml`; every cited source
resolves to a genuine publisher domain, and no invented or non-reproducible values appear.

## Claims Used

- C-2026-06-12-SEN-C2-001 - CBOE Volatility Index (VIX) close
- C-2026-06-12-SEN-C2-002 - AAII Investor Sentiment Survey, bullish
- C-2026-06-12-SEN-C2-003 - AAII Investor Sentiment Survey, bearish
- C-2026-06-12-SEN-C2-004 - University of Michigan preliminary Consumer Sentiment (June 2026)
- C-2026-06-12-SEN-C2-005 - CNN Fear & Greed Index

## Analysis

Market sentiment on Friday, 2026-06-12 was characterised by a sharp easing of equity-volatility
fear set against still-cautious-to-pessimistic survey-based positioning - a "calmer tape, wary
participants" split.

The implied-volatility read turned decisively calmer. The VIX closed at 17.68, down 1.76 points
(-9.05%) from the prior session's 19.44 (C-2026-06-12-SEN-C2-001). That close completed a
spike-and-fade week: the gauge had jumped to an intraweek closing high of 22.22 on 2026-06-10
before retreating to 17.68 by Friday (C-2026-06-12-SEN-C2-001). The fall in the fear gauge is
consistent with the day's risk-on price action - the three major U.S. indexes closed higher and
finished up for the week, the 10th positive week in 11 for the S&P 500, with oil down about 3.8%
on U.S.-Iran de-escalation hopes and a record-setting SpaceX IPO drawing attention (market
backdrop, source S-2026-06-12-008; *contextual, macro/US segment owns the index claims*).

Survey-based sentiment, however, remained defensive. The AAII Investor Sentiment Survey for the
week ending 2026-06-11 showed bullish sentiment at just 30.37% - down from 36.26% a week earlier
and well below the 37.61% long-term average (C-2026-06-12-SEN-C2-002) - while bearish sentiment
jumped to 47.66%, a print AAII headlined as "Pessimism Surges" (C-2026-06-12-SEN-C2-003). The
resulting bull-bear spread of roughly -17.3 percentage points (*derived from claims C2-002 and
C2-003: 30.37% - 47.66%*) marks a net-pessimistic individual-investor stance even as prices rose.

Consumer sentiment told a "less-bad" story. The University of Michigan preliminary Index of
Consumer Sentiment for June 2026 rose to 48.9 from May's record low of 44.8, released 2026-06-12
(C-2026-06-12-SEN-C2-004) - the first monthly improvement after consecutive declines, but still a
historically depressed level, with survey commentary flagging persistent labor-market pessimism.

The composite gauge corroborated the cautious tone: CNN's Fear & Greed Index stood at 34 on
2026-06-12 - up modestly from a prior reading near 31.6 but still firmly in "Fear" territory
(C-2026-06-12-SEN-C2-005).

**Net read (editorial synthesis):** volatility-based fear receded into the weekly close
(VIX -9.05%), but positioning and survey gauges - AAII bullishness below average with bearishness
near 48%, consumer sentiment improving only off a record low, and a Fear & Greed reading of 34 -
show that the underlying sentiment regime stayed defensive. The divergence between a calming VIX
and persistently bearish survey readings is the key sentiment signal for the session.

## As-Of and Session Basis

| Claim | Indicator | Value | As-Of | Session / Period Basis |
| --- | --- | --- | --- | --- |
| C2-001 | VIX close | 17.68 | 2026-06-12T16:00:00-04:00 | Regular U.S. close (vs 2026-06-11 close 19.44) |
| C2-002 | AAII bullish | 30.37% | 2026-06-11 | AAII weekly survey, week ending 2026-06-11 |
| C2-003 | AAII bearish | 47.66% | 2026-06-11 | AAII weekly survey, week ending 2026-06-11 |
| C2-004 | UMich consumer sentiment (prelim) | 48.9 | 2026-06-12T10:00:00-04:00 | Monthly preliminary release for June 2026 (vs May 44.8) |
| C2-005 | CNN Fear & Greed Index | 34 | 2026-06-12T16:00:00-04:00 | Daily close-of-session composite reading |

## Source Discipline

- All sources resolve to real, public domains (Yahoo Finance, FRED/St. Louis Fed, AAII,
  University of Michigan, Trading Economics, Investopedia, YCharts, MacroMicro, Seeking Alpha).
  No stand-in domains, fabricated publishers, or invented metadata are present.
- VIX is double-sourced: the 2026-06-12 close (17.68) is from Yahoo Finance (S-001); the adjacent
  closes (2026-06-08 18.92, 06-09 19.87, 06-10 22.22, 06-11 19.44) are independently confirmed by
  FRED VIXCLS (S-002), which matched Yahoo exactly for those dates.
- AAII is triangulated across YCharts (bullish 30.37%, S-003), MacroMicro (bearish 47.66% /
  neutral 21.96%, S-004), and the AAII primary writeup (S-005); shares sum to ~100%.
- UMich June preliminary (48.9) is corroborated across the official UM Surveys of Consumers page
  (S-006) and Trading Economics (S-007). A stray 49.8 figure seen on a UM political-party-subgroup
  addenda table was **excluded** in favour of the headline 48.9 carried by the primary release and
  multiple independent reports.
- The CNN Fear & Greed reading (S-009) is a mutable, daily composite gauge; it is recorded with
  `mutable: true` and assigned `medium` confidence. It is distinct from MacroMicro's own
  proprietary "MM Fear and Greed Index" (a different series), which is **not** used here.

## Derivations and Inference (non-claim statements)

- Bull-bear spread (-17.3 pp): arithmetic from C2-002 and C2-003.
- VIX daily change (-1.76 pts / -9.05%): arithmetic from C2-001 closes (17.68 vs 19.44).
- The index/oil/IPO market backdrop is contextual (source S-2026-06-12-008) and is owned by the
  macro/US segments; it is cited here only to frame the sentiment read, not as a sentiment claim.
- The "net read" paragraph is editorial synthesis of the five claims above.
