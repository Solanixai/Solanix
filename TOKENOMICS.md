# SOLNX Tokenomics Model

Status: design draft for the Solanix repository.
Chain: BNB Smart Chain.
Ticker: SOLNX.
This document is not a legal opinion, not an offer to sell securities, and not a price forecast.

Published reference: [solanix.xyz](https://solanix.xyz/) (supply pie and presale price). The vesting curve, emission curve, and revenue link below are a design on top of that pie. They are not yet what the website states, except the founding-team 2-year lock.

## 1. What this model is

A tokenomics model is three schedules, not a pie chart:

1. Unlock schedule: how many tokens become transferable, and when.
2. Demand schedule: who must buy, lock, or burn SOLNX.
3. Revenue link: how verified solar generation touches the token without pretending SOLNX itself is a deed to a farm.

Keep two claims separate:

| Claim | Instrument | What the holder gets |
|---|---|---|
| Solar project cashflow or kWh | RWA receipt (separate asset) | A defined claim on measured generation or contracted revenue |
| Protocol utility | SOLNX | Fees, access, governance, discounts |

Do not market SOLNX as ownership of a solar farm unless a separate legal instrument says that.

## 2. Supply

Hard cap. No mint beyond this cap.

| Bucket | Share | Tokens |
|---|---:|---:|
| Community rewards and staking | 30% | 300,000,000 |
| Project development | 20% | 200,000,000 |
| Strategic partnerships | 15% | 150,000,000 |
| Public sale | 15% | 150,000,000 |
| Founding team | 10% | 100,000,000 |
| Advisers and lawyers | 5% | 50,000,000 |
| Liquidity pool | 5% | 50,000,000 |
| **Total** | **100%** | **1,000,000,000** |

Presale quote on the site: 1 USDT = 10 SOLNX, so **$0.10 per SOLNX**.

| Metric | Formula | At $0.10 |
|---|---|---:|
| Fully diluted valuation | 1,000,000,000 × price | $100,000,000 |
| Public-sale proceeds if the full 15% sells at this price | 150,000,000 × $0.10 | $15,000,000 |
| USDT needed for a 50/50 pool against the full 5% liquidity allocation | 50,000,000 × $0.10 | $5,000,000 |

If the pool is funded with less than $5,000,000 USDT, do not describe 5% of supply as deep liquidity. Price impact will be larger than the pie chart implies.

Contracts referenced on the site (verify before relying on them):

- Presale: `0x26d06521C89Af9499A924b1d46FF322aEfD3d932`
- Staking: `0xd663b0D6ba1d7Ad3e35a37f67e0Cd42a8BFC0e88`

## 3. Vesting design

TGE means the moment SOLNX becomes transferable on the public market. Cliff means nothing from that bucket moves before the cliff ends. Linear means the remainder releases in equal monthly amounts after the cliff.

| Bucket | Tokens | At TGE | Cliff | After cliff |
|---|---:|---:|---:|---|
| Liquidity pool | 50,000,000 | 100% into the pool | Pool position locked 24 months | Do not pull liquidity for 24 months |
| Public sale | 150,000,000 | 20% (30,000,000) | None | 80% (120,000,000) linear over 8 months = 15,000,000 / month |
| Founding team | 100,000,000 | 0 | 24 months | Then linear over 24 months = 4,166,666.67 / month |
| Advisers and lawyers | 50,000,000 | 0 | 12 months | Then linear over 18 months = 2,777,777.78 / month |
| Strategic partnerships | 150,000,000 | 0 | Milestone, not a date | Release only against a signed deliverable |
| Project development | 200,000,000 | 0 | None, but no lump | Quarterly over 36 months = 16,666,666.67 / quarter |
| Staking emissions | 300,000,000 | 0 | None | Declining 4-year curve in section 4. Not a flat APY |

A bare "2-year lock" on the team bucket is a cliff with a 100,000,000-token market event on day 731. This design replaces that with a 24-month cliff plus 24 months of linear release, so the same 2-year wait happens before the first team token moves, and the rest does not hit the book in one print.

Partnership tokens stay at 0 until a milestone is accepted. Do not pre-commit them to a calendar.

## 4. Staking emissions

The 300,000,000 community bucket is an emission cap, not a promised yield.

| Year | Share of the 300M | Tokens released | Approx. per month |
|---|---:|---:|---:|
| 1 | 40% | 120,000,000 | 10,000,000 |
| 2 | 30% | 90,000,000 | 7,500,000 |
| 3 | 20% | 60,000,000 | 5,000,000 |
| 4 | 10% | 30,000,000 | 2,500,000 |
| **Total** | **100%** | **300,000,000** |  |

Rules:

- No emissions after month 48 from this bucket.
- Do not advertise a fixed APY. Website staking packages that still read "— DAYS" stay unpublished until generation revenue exists.
- Preferred reward for stakers is a defined share of verified energy revenue, paid in USDT (or the settlement currency), not in newly circulating SOLNX.
- SOLNX-denominated rewards are allowed only up to the monthly emission cap, and only if protocol fees buy back or burn at least the same number of SOLNX that month. If fees do not cover it, cut the emission. Do not "make up" yield by printing.

Illustrative month-1 staking inflation if circulating float is about 80,000,000 (see section 5): 10,000,000 / 80,000,000 = 12.5% new supply in a single month before any burn. That is why emissions must be capped by fees, not by a marketing APY.

## 5. Float at TGE

Design assumption, not an on-chain fact:

| Source | Tokens transferable at TGE |
|---|---:|
| Liquidity pool (inside the pool, not a seller wallet) | 50,000,000 |
| Public sale, 20% unlock | 30,000,000 |
| Team, advisers, partnerships, development, staking | 0 |
| **Outside the pool** | **30,000,000** |
| **Touching the market, including pool inventory** | **80,000,000** |

At $0.10, the outside-the-pool float is $3,000,000 fully diluted against that slice, while headline FDV stays $100,000,000. Say both numbers. FDV alone hides how small the initial float is, and how violent later unlocks are.

### Worked unlocks, first year (no partnership milestones)

Public: 30,000,000 at TGE, then 15,000,000 in each of months 1 through 8. Public bucket is fully circulating by month 8.

Staking emissions: 10,000,000 per month in year 1, unless cut because fees did not cover the buyback rule.

Team: 0 in months 0 through 24.
Advisers: 0 in months 0 through 12, then about 2,777,778 per month.
Development: about 5,555,556 per month if the quarterly release is smoothed (16,666,667 per quarter).

Month-0 circulating, excluding tokens sitting inside the locked LP position: **30,000,000**.
Month-8 circulating, same exclusion, before any stake-lock or burn: 30,000,000 + 120,000,000 public remainder + 80,000,000 of year-1 emissions already released across months 1–8 = **230,000,000**, plus smoothed development of about 44,400,000. Partnerships stay 0 until a milestone.

Treat the month-8 figure as sellable supply, not as a price target.

## 6. Demand sinks

A sink only counts if a rational user must spend or lock SOLNX to get something they cannot get cheaper in USDT.

| Sink | Payer | Effect on float |
|---|---|---|
| Farm listing bond | Project owner | Locked, returned only if data obligations are met; slashed to the treasury otherwise |
| Oracle / settlement fee | Buyer of energy data or the offtaker | Bought and burned, or bought into the treasury |
| Carbon-retirement fee | Credit buyer | Burn or treasury, in SOLNX terms via buyback |
| Governance | Token holder | Locked during the vote; not a yield |
| Fee discount | Active user | Optional. A discount is not a sink unless the undiscounted path is expensive enough |

Explicitly not a sink: staking SOLNX to receive more SOLNX. That is a transfer from the emission bucket to a staker, and it increases sellable supply when they unstake.

Revenue waterfall for verified generation, once a farm is live:

1. Operating costs and debt, off-token.
2. Contracted offtaker payment, off-token, to the RWA receipt holder.
3. Protocol fee, small and fixed in the contract, converted to SOLNX and burned or held by the treasury.
4. Only then, and only inside the yearly emission cap, any SOLNX incentive.

If step 3 is zero, step 4 is zero.

## 7. Spreadsheet

One row per month, month 0 through 48.

| Column | Formula |
|---|---|
| Public unlock | Month 0 = 30,000,000. Months 1–8 = 15,000,000. Else 0 |
| Team unlock | 0 through month 24. Months 25–48 = 100,000,000 / 24 |
| Adviser unlock | 0 through month 12. Months 13–30 = 50,000,000 / 18 |
| Partner unlock | Manual, only when a milestone is marked done |
| Dev unlock | 200,000,000 / 36 each month, or the same amount in a quarterly lump |
| Staking emission | Year-1 months 10,000,000; year-2 7,500,000; year-3 5,000,000; year-4 2,500,000. Set to 0 if that month's buyback is below the emission |
| Gross new float | Sum of the six unlock columns |
| SOLNX burned | Protocol fees in USDT ÷ SOLNX price used for the buyback |
| Newly staked | Tokens that entered a lock this month and cannot transfer |
| Unstaked | Tokens whose lock ended this month |
| Net new float | Gross new float − burned − newly staked + unstaked |
| Circulating | Previous circulating + net new float |
| Protocol fees USDT | Scenario input, not a formula |

Do not add a "target price" column. Add three fee scenarios instead: low, base, high. The only output that should change between them is burned tokens and whether the emission cap was cut.

## 8. Liquidity rule

- 50,000,000 SOLNX goes to the pool at TGE and the LP position is locked for 24 months.
- Pair side at the presale price is $5,000,000 USDT. Raise this from the public-sale proceeds before listing. Do not list on $500,000 and call the 5% allocation "the liquidity".
- No team, adviser, or partnership wallet adds sell-side liquidity.
- Publish the lock transaction hash in this file when it exists.

## 9. What is still unpublished

- Staking package length, reward rate, and bonus (site still shows placeholders).
- Per-milestone partnership schedule.
- The legal split between the RWA receipt and SOLNX (needs counsel; a revenue or profit share can be treated as a security, including under UAE VARA, depending on structure).
- Oracle source for the India pilot generation data.
- Buyback executor: who can call it, and the maximum SOLNX bought per day.

## 10. Decision log

| Date | Decision |
|---|---|
| 2026-11-23 | Adopted the published 1,000,000,000 cap and the seven-bucket split from solanix.xyz. |
| 2026-11-23 | Replaced a single team cliff-unlock with 24-month cliff + 24-month linear vest. |
| 2026-11-23 | Capped staking emissions on the 4-year declining curve and tied any SOLNX reward to a matching buyback. |
| 2026-11-23 | Set the 50/50 pool funding target at $5,000,000 USDT against 50,000,000 SOLNX at $0.10. |
