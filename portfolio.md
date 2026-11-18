# My investment policy, holdings and theses

The bot reads this file before every answer, alert and summary.
Edit it on GitHub (pencil icon) whenever something changes; the bot redeploys by itself.

## Objective
- Goal: beat the S&P 500 on compounded return over 10+ years.
- Structure: about 70% high-growth leaders (core) and about 30% potential 10x stocks (sleeve).
- 5-6 stocks maximum. Position size by conviction.
- Drawdowns: no hard cap. Diagnose the cause first. Market-wide drop with the business intact: consider adding. Fundamentals changed: re-test the thesis.
- 10x sleeve entry test (all four): large TAM; paying customers; 2+ years of cash; a disruptive idea that breaks an industry trade-off.

## What I decide myself
The thesis for each stock, the growth rates in my DCF, the discount-rate sign-off, and every buy, sell and position size.

## Holdings (Nov 14, 2026)
| Stock | Weight | Bucket |
|---|---|---|
| AVGO (Broadcom) | 35.94% | Core |
| PLTR (Palantir) | 33.34% | Core |
| NVDA (Nvidia) | 18.97% | Core |
| AMZN (Amazon) | 11.51% | Core |

10x sleeve today: 0% (target about 30%). I plan to add one speculative stock, funded by new cash and trimming.

## My theses (I write these; 1-2 lines each)
- AVGO: I hold AVGO as long as it stays the main design partner for custom AI chips (keeps its big customers through each new generation) and the leading AI networking supplier, its AI revenue keeps growing toward management's targets, and its customers can fund their commitments, at a price that still makes sense. I review after each earnings report and act on 2-quarter trends.
- PLTR: I hold PLTR as long as it keeps its lead as the operating layer for enterprise AI (high net retention), keeps adding new customers at a strong pace, and maintains its margins, at a valuation that still makes sense. I review after each earnings report and act on 2-quarter trends.
- NVDA: not written yet
- AMZN: not written yet

## My entry and exit rules (I set these; the bot reports their status, it never acts on them)
Each rule has a metric, a threshold and the latest value. "2 quarters" means two reported quarters in a row, not one.

### PLTR (set Nov 17, 2026; latest values from Q3 2026, reported Nov 2)
Add (all four must hold):
- A1 Moat intact: net dollar retention at or above 120% and $10M+ deals rising. Latest: 165%; 64 deals of $10M+ (61 in Q4 2025). Met.
- A2 Customer growth: US commercial customers growing 15%+ a year. Latest: 686, +29% (sequential growth slowed to 5%). Met.
- A3 Margins stable: no sustained fall in adjusted operating margin. Latest: 62% (57% in Q4 2025). Met.
- A4 Price: add 10% at or below $124 (base DCF value); add 25% at or below $99; add 50% at or below $83. Latest price: $160.39 (Nov 16). Not met.
Full exit (thesis broken), any one of these for 2 quarters:
- X1 Net dollar retention below 120%.
- X2 US commercial customer growth below 15% a year while competitors (Microsoft, Databricks, Snowflake, OpenAI, Anthropic) announce wins.
- X3 Adjusted operating margin falling while management cites pricing pressure.
Trim (business fine, price stretched):
- T1 Price above $171 (Monte Carlo 90th percentile) with no matching jump in growth. Latest: $160.39, about 6% below. Not triggered.
Position size:
- P1 Investment policy flag: above 30% of the portfolio. Latest: 33.34%. Flagged.
Immediate review (not an exit by itself):
- R1 Loss of a major government contract, a big competitor breakthrough, or management saying "pricing pressure" or "longer sales cycles".
Warnings to watch:
- W1 US commercial new deal value (TCV) falling year on year for 2 quarters. Latest: +11%.
- W2 US commercial remaining deal value falling quarter on quarter. Latest: $6.517B, +4%.
- W3 International commercial growth. Latest: +1% quarter on quarter.

### AVGO (set Nov 18, 2026; latest values from Q3 fiscal 2026, reported Sep 2; Q4 due Dec 9)
Add (all four must hold):
- A1 Design partner position: no top custom-chip (XPU) customer lost; customer count steady or rising. Latest: 6 customers, 4 named (Google, Meta, OpenAI, Anthropic). Met.
- A2 AI growth on track: AI revenue growing 50%+ a year and the fiscal 2027 outlook of about $115B intact. Latest: $16.7B, +221%; Q4 guide about $21.7B. Met.
- A3 Margins: adjusted gross margin 70%+ and free cash flow margin 40%+. Latest: 75% (Q4 guided about 73%) and 46%. Met.
- A4 Price: add 10% at or below $383 (base DCF value); add 25% at or below $306; add 50% at or below $255. Latest price: $341.60 (Nov 17). Met for the 10% level.
Full exit (thesis broken):
- X1 A top-3 XPU customer moves its next chip generation to another partner (Marvell, MediaTek) or in-house. This is an event: no 2-quarter wait.
- X2 AI revenue growth below 20% a year for 2 quarters.
- X3 Adjusted gross margin below 68% for 2 quarters while management cites pricing pressure.
- X4 A customer financing guarantee is called, or Anthropic or OpenAI cannot fund their commitments. This is an event: no 2-quarter wait.
Trim (business fine, price stretched):
- T1 Price above $499 (Monte Carlo 90th percentile) with no matching jump in growth. Latest: $341.60, about 32% below. Not triggered.
Position size:
- P1 Investment policy flag: above 30% of the portfolio. Latest: 35.94%. Flagged (conflicts with A4; the investor decides).
Immediate review (not an exit by itself):
- R1 Hock Tan leaving; a customer naming a second chip partner; export-control action against Broadcom; a large Nvidia Spectrum-X networking win at a Broadcom customer.
Warnings to watch:
- W1 AI networking revenue falling year on year. Latest: about $4.5B in Q3 (27% of AI revenue).
- W2 Fiscal 2027 AI outlook (about $115B) cut or fiscal 2028 (about $230B) withdrawn.
- W3 Free cash flow margin below 40%. Latest: 46%.

### NVDA, AMZN
Not written yet.

## Research snapshot (goes out of date; update after each earnings report)
- AVGO, DCF of Nov 13, 2026: optimistic $732, base $383, pessimistic $163 per share, at a 10.95% discount rate. Base case assumes management's AI revenue outlook of about $115B in fiscal 2027 and $230B in fiscal 2028 is met. Monte Carlo median about $364; at the $341.60 price (Nov 17) about 60% chance the value is above the price. Risk score 2.29 of 5 (lower risk); highest risks are industry and external (AI spending cycle, all chips made by TSMC in Taiwan) and customer concentration (about six customers; about $72B of customer financing guarantees). Next results Dec 9, 2026; Q4 guide: revenue about $34.8B, AI revenue about $21.7B.
- NVDA, DCF of Nov 12, 2026: optimistic $407, base $195, pessimistic $84 per share, at a 14.3% discount rate. Base case assumes 2030 data-center capex of $2.5T and a 40% Nvidia share. Results due Nov 17, 2026.
- AMZN: research report done Nov 2026 (AWS and AI data-center build-out); no current DCF values.
- PLTR, DCF of Nov 17, 2026: optimistic $314, base $124, pessimistic $37 per share, at an 11.73% discount rate (beta 1.62, 2,409M shares). Monte Carlo median about $114; about 14% chance the value is above the $160.39 price. The price implies about 37% free cash flow growth a year for 5 years (about $40B of revenue in 2031). Risk score 2.50 of 5 (medium); highest risk is valuation. Next results early February 2027; Q4 guide: revenue $2.649-2.653B.

## What counts as urgent
Business model or strategy change, CEO or senior management change, large insider selling, a key customer won or lost, guidance changes, regulation or legal action against the company, major deals or dilution, and any news that reports a metric used in my entry and exit rules (for example net retention, customer counts, margins, contract wins or losses). A price move on its own is not urgent; price levels in my rules are checked in the weekly summary.
