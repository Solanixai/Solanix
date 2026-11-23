# SOLNX Tokenomics

Status: supply split below matches the public Solanix site. The vesting curve, emission schedule, and liquidity assumptions are the working model for this repo. They are not yet the live on-chain schedule.

This document is a design model. It is not a price forecast, not an offer of securities, and not a promise of yield.

## Token

| Item | Value |
|---|---|
| Token | SOLNX |
| Chain | BNB Smart Chain |
| Total supply | 1,000,000,000 (fixed) |
| Presale reference | 1 USDT = 10 SOLNX ($0.10) |
| Reference FDV at $0.10 | $100,000,000 |
| Presale contract | `0x26d06521C89Af9499A924b1d46FF322aEfD3d932` |
| Staking contract | `0xd663b0D6ba1d7Ad3e35a37f67e0Cd42a8BFC0e88` |

Reference FDV is supply × the presale price. It is not a market price and it is not a target.

## What the token is

SOLNX is the protocol token: fees, access, and governance.

A solar project’s energy output is a separate claim (a project receipt or kWh record). Do not describe SOLNX as ownership of a farm, of generation revenue, or of a fixed yield. If a product later shares revenue, that product needs its own legal structure. This file does not define that product.

## Supply

| Bucket | % | Tokens | Role |
|---|---:|---:|---|
| Community rewards & staking | 30% | 300,000,000 | Emissions, paid only on the curve below |
| Project development | 20% | 200,000,000 | Treasury for build and operations |
| Strategic partnerships | 15% | 150,000,000 | Partners, released on milestones |
| Public sale | 15% | 150,000,000 | Presale / public buyers |
| Founding team | 10% | 100,000,000 | Locked, then linear |
| Advisers & lawyers | 5% | 50,000,000 | Locked, then linear |
| Liquidity pool | 5% | 50,000,000 | DEX inventory, pool-locked |
| **Total** | **100%** | **1,000,000,000** | |

If the full public-sale bucket sold at the presale reference price, gross proceeds would be 150,000,000 × $0.10 = **$15,000,000**. That figure assumes the whole bucket clears at $0.10. It is not cash already raised.

## Vesting

Time starts at TGE. “Linear” means equal monthly unlocks after the cliff. No bucket may unlock early to fund marketing.

| Bucket | Tokens | At TGE | Cliff | After cliff |
|---|---:|---:|---|---|
| Liquidity pool | 50,000,000 | 100% into the pool | 24 months in the pool | Do not remove LP before month 24 |
| Public sale | 150,000,000 | 20% (30,000,000) | none | 80% (120,000,000) linear over 8 months (15,000,000 / month) |
| Founding team | 100,000,000 | 0 | 24 months | linear over the next 24 months (~4,166,667 / month) |
| Advisers & lawyers | 50,000,000 | 0 | 12 months | linear over 18 months (~2,777,778 / month) |
| Strategic partnerships | 150,000,000 | 0 | milestone, not a date | release only against a signed deliverable |
| Project development | 200,000,000 | 0 | none on a drip | 36 months, quarterly (~16,666,667 / quarter) |
| Staking emissions | 300,000,000 | 0 | none | 48-month declining curve below |

Team “2 year lock” on the site is implemented here as a 24-month cliff and then 24 months of linear release. A single unlock of 100,000,000 on day 730 is not allowed.

### Unlock by year (excluding partnerships)

Partnerships stay at 0 until a milestone is recorded. Do not put them on a calendar by default.

| Year | Public | Team | Advisers | Development | Staking emission | Year total (ex-partners) |
|---|---:|---:|---:|---:|---:|---:|
| 1 | 150,000,000 | 0 | ~33,333,333 | ~66,666,667 | 120,000,000 | ~370,000,000 |
| 2 | 0 | ~50,000,000 | ~16,666,667 | ~66,666,667 | 90,000,000 | ~223,333,334 |
| 3 | 0 | ~50,000,000 | 0 | ~66,666,666 | 60,000,000 | ~176,666,666 |
| 4 | 0 | 0 | 0 | 0 | 30,000,000 | 30,000,000 |

Year-1 public includes the 30,000,000 TGE unlock plus 8 monthly tranches. Advisers start unlocking in month 13, so year 1 is 12 months of the 18-month vest (~33.3M) and year 2 is the remaining ~16.7M. Team starts in month 25.

## Staking emission

The 300,000,000 community bucket is an emission cap, not a pool that can be paid out on demand.

| Year | Share of 300M | Tokens | Approx / month |
|---|---:|---:|---:|
| 1 | 40% | 120,000,000 | 10,000,000 |
| 2 | 30% | 90,000,000 | 7,500,000 |
| 3 | 20% | 60,000,000 | 5,000,000 |
| 4 | 10% | 30,000,000 | 2,500,000 |

Rules:

- No fixed APY. A package may not advertise a token yield until the monthly emission for that month is set and published.
- Token rewards come only from that month’s emission. They are not minted on top of the 1,000,000,000 cap.
- Preferred reward for energy participation is stablecoin from verified generation, not newly unlocked SOLNX.
- Any SOLNX paid as a reward should be matched, over time, by SOLNX taken out of circulation (burn or buyback funded by protocol fees). If fees do not cover it, cut the emission. Do not raise it.

## Liquidity

5% of supply is 50,000,000 SOLNX. A 50/50 pool at the $0.10 reference price needs the other side to be:

`50,000,000 × $0.10 = $5,000,000 USDT`

If the USDT side is smaller, the pool still “contains 5%” of tokens but it cannot absorb sales. Publish the actual USDT deposited, not only the token percentage. LP tokens stay in a lock for 24 months.

## Demand, not a price model

Price is not an output of this sheet. The sheet tracks float.

Each month:

```
net new float = unlocks + staking emission − SOLNX burned − new SOLNX locked in stake
```

Columns to keep:

| Month | Public | Team | Advisers | Partners | Dev | Emission | Burned | Newly staked | Circ. supply | Net new float | Protocol fees (USDT) |
|---|---|---|---|---|---|---|---|---|---|---|---|

Circulating supply starts at the TGE float only:

- Liquidity: 50,000,000 (inside the pool, not a free wallet)
- Public: 30,000,000
- Everything else: 0

So free-wallet float at TGE is **30,000,000 SOLNX**, plus whatever the pool sells. Do not call the other 970,000,000 “circulating”.

Sinks that actually reduce float:

- protocol fee paid in SOLNX and burned
- buyback funded by oracle, listing, or settlement fees
- stake lock with a real unbonding period

A pie-chart allocation is not a sink.

## Scenarios

Use three fee cases. Do not attach a SOLNX price to them.

| Case | Protocol fees | Action on emission |
|---|---|---|
| Low | fees < SOLNX rewards paid that month | cut the next month’s emission |
| Base | fees cover buyback of the SOLNX emitted | hold the curve |
| High | fees exceed emissions | burn the surplus, do not raise the curve |

## Explicit non-goals

- No second mint. Supply stays 1,000,000,000.
- No team or adviser unlock before its cliff, including “for market making”.
- No guaranteed APY, no fixed-day staking package, until the month’s emission is published.
- No claim that holding SOLNX pays the holder a share of solar revenue.
