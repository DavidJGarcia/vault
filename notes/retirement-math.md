# Retirement math

Numbers David has asked for, with the assumptions each one rests on. Started
October 13, 2026, the day he asked two retirement questions a couple of hours
apart.

## Drawing $180,000 a year from $1,000,000

Asked October 13, 2026. A $1M portfolio, 100% US total stock market, withdrawing
$180,000 at the start of each year in today's dollars (the withdrawal rises with
inflation).

That is an **18% withdrawal rate**. It is not a question of whether the money
runs out — it does, in every path. The only question is the year.

| Confidence | Years the money lasts |
| --- | --- |
| Worst 1-in-20 | 4.7 |
| Worst 1-in-10 | 5.0 |
| Median | 6.4 |
| Best 1-in-10 | 9.0 |
| Best 1-in-20 | 10.0 |

Reaching 15 years takes about 1 path in 500. Reaching 20 years is effectively
impossible — it would need roughly 24% real returns every year for two decades.

**Assumptions.** Real (inflation-adjusted) returns, annual, independent and
lognormal: arithmetic mean 7.0%, standard deviation 17%. That is the long-run US
market — the S&P 500's real mean runs 6.6–8.5% depending on the window, with a
15–16% SD, and total market carries a little more volatility for its small caps.
After the 1.4% variance drag the median path compounds at 5.6%. No taxes, no
fees, no other income offsetting the draw.

**Where the risk sits.** Almost all of it is in the first three years. The
sensitivity of the year-7 balance to each year's return runs $1,150k, $914k,
$694k, $488k, $295k, $115k per unit of return — year one matters ten times as
much as year six, because that is when the dollars are still there. A 2000–2002
or 2008 opening sequence puts it at 5 years. A 1995–1999 opening puts it past 12.

**What $1M does support.** About $40,000 a year at the conventional 4% rate, for
a 30-year retirement. Running the other way: $180,000 a year for 30 years needs
roughly **$4.5M**.

Method note: these are closed-form lognormal percentiles, each run through the
withdrawal ladder year by year, not a drawn-path simulation — good to about half
a year either side.

## Maximum Social Security for a couple

Asked October 13, 2026, 9:02 am. One spouse with a full 35-year record at the
taxable maximum, the other with no earnings record of her own.

- Worker claiming at 70: **$5,181/mo**
- Worker claiming at full retirement age: $4,152/mo
- Spousal benefit at her own FRA: **$2,076/mo**
- **Combined: $7,257/mo, about $87,100/yr**

The spousal benefit is 50% of the worker's FRA amount and earns no delayed
credits, so his delay to 70 does not raise hers. She must be at her own FRA
(66y10m–67) for the full 50%, and he must have filed. 2026 rates, after the
COLA; taxable maximum $184,500. Assumes no WEP or GPO.

## The two together

$87,100 of Social Security plus a $1M portfolio does not fund $180,000 a year
indefinitely, but it changes the shape of the problem: the portfolio only has to
cover the $92,900 gap, which is a 9.3% draw and lasts roughly 12–13 years at the
median rather than 6.4. Thirty years of that gap would need about $2.3M.
