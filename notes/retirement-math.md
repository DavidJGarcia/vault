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

## The same draw with a growing supplement

Asked October 13, 2026, minutes after the Monte Carlo above. Same $1M, same
$180,000 a year, but outside income supplements it: $2,000/mo in year 1,
$4,000/mo in year 2, $6,000/mo in year 3, climbing $2,000/mo every year.

**The money stops running out.** The portfolio only covers the gap, and the gap
closes:

| Year | Supplement | Portfolio draw |
| --- | --- | --- |
| 1 | $24,000 | $156,000 |
| 2 | $48,000 | $132,000 |
| 3 | $72,000 | $108,000 |
| 4 | $96,000 | $84,000 |
| 5 | $120,000 | $60,000 |
| 6 | $144,000 | $36,000 |
| 7 | $168,000 | $12,000 |
| 8 | $192,000 | none — income exceeds the spend |

Seven years of draws totalling **$588,000**, with a present value of about
**$533,000** at the 5.6% median rate. Half the million is enough; the other half
compounds. From year 8 the portfolio is never touched again.

| Confidence | Balance at year 8 |
| --- | --- |
| Worst 1-in-20 | $280,000 |
| Worst 1-in-10 | $340,000 |
| Median | $680,000 |

The median path reaches roughly **$2.4M** in today's dollars by year 30, left
alone, on top of a supplement that by then is $62,000 a month.

**What would break it.** Running dry takes something like −21% real every year
for six consecutive years, a cumulative −78%. Run the ladder through the three
worst openings on record and all three survive: a 2000 start leaves about $250k
at year 8, a 1973 start about $150k, and a 1929 start comes through with roughly
$50k at its thinnest before the 1933 recovery — intact, but only just. Call it
under 1 path in 1,000.

Same assumptions as above: real returns, 7.0% arithmetic mean, 17% SD, no taxes
or fees. Both the spend and the supplement are in today's dollars. If instead
the supplement were fixed nominal dollars while the spend tracked inflation, the
bridge stretches about two more years of small draws and nothing else changes.

## The same supplement, starting from $400,000

Asked October 13, 2026, straight after the $1M version. Everything identical —
$180,000 a year, the supplement climbing $2,000/mo each year — except the
portfolio starts at **$400,000**.

The bridge is the same seven years of draws, $588,000 nominal and about
**$533,000** in present value. $400,000 is roughly **$133,000 short of it**, so
the money runs out before the supplement takes over.

The median path, year by year:

| Year | Draw | Left after the draw | Grown at 5.6% |
| --- | --- | --- | --- |
| 1 | $156,000 | $244,000 | $258,000 |
| 2 | $132,000 | $126,000 | $133,000 |
| 3 | $108,000 | $25,000 | $26,000 |
| 4 | $84,000 | empty about four months in | — |

| Confidence | Years the money lasts |
| --- | --- |
| Worst 1-in-20 | 2.7 |
| Worst 1-in-10 | 2.8 |
| Median | 3.3 |
| Best 1-in-10 | 4.0 |
| Best 1-in-20 | 4.4 |

The band is narrower than the $1M case because the draws are front-loaded
against a small balance — returns barely get a chance to matter. The three worst
openings on record all land in year 3: a 1973 start 2.4 years, 1929 2.6, 2000
2.7.

**The hole.** Years 4 through 7 are unfunded: gaps of $84,000, $60,000, $36,000
and $12,000, about **$166,000** after the $26,000 the portfolio leaves behind.
From year 8 the supplement exceeds the spend and the problem ends on its own, so
this is a four-year hole, not a permanent one.

**Two ways to close it.**

- More capital: about **$533,000** to bridge it at median returns, **$660,000**
  to survive a sustained −6%/yr decade.
- Less spending: **$156,000/yr ($13,000/mo)** is what $400,000 bridges exactly
  at the median, and **$144,000/yr ($12,000/mo)** holds even through a bad run.

Same assumptions and same method as the sections above: real returns, 7.0%
arithmetic mean, 17% SD, draws at the start of each year, no taxes or fees,
closed-form percentiles rather than a drawn-path simulation.

## What the supplement would have to be for $400,000 to work

Asked October 13, 2026, straight after the $400,000 run. Same $180,000 a year,
same $400,000 start, the supplement still growing in a straight line — but how
steep does the line have to be?

Write the step as $m a month: the supplement is $m/mo in year 1, $2m in year 2,
$3m in year 3, and the portfolio covers only what the supplement does not. A
steeper line shortens the bridge from both ends — fewer years, and smaller draws
in the years that remain.

| Step | What it survives |
| --- | --- |
| $2,000/mo | nothing — this is the case above, dry in year 4 |
| **$2,600/mo** | the median path, and nothing worse |
| **$2,900/mo** | a sustained −6%/yr decade |
| $3,150/mo | a 2000–2002 opening |
| $3,200/mo | a 1929–1932 opening |
| **$3,400/mo** | a 1973–1974 opening, the worst on record here |

So **call it $3,500/mo** — $3,500 in year 1, $7,000 in year 2, $10,500 in year 3,
$14,000 in year 4, and from year 5 the supplement is $17,500/mo, $210,000 a year,
more than the spend. That is a four-year bridge instead of seven:

| Year | Supplement | Portfolio draw |
| --- | --- | --- |
| 1 | $42,000 | $138,000 |
| 2 | $84,000 | $96,000 |
| 3 | $126,000 | $54,000 |
| 4 | $168,000 | $12,000 |
| 5 | $210,000 | none — income exceeds the spend |

$300,000 of draws, present value about **$288,000** against the $400,000 on hand.
The median path leaves roughly **$140,000** untouched from year 5 on. A 1973
opening leaves about $11,000 at its thinnest and recovers. At $3,400/mo that
1973 path finishes year 4 with about $1,000 — it survives on paper and nothing
else, which is why the number to say out loud is $3,500.

Why the jump from $2,600 to $3,500 buys so much: the first-year draw is 35% of
the balance at $2,600/mo and 29% at $3,500/mo, and one fewer year of drawing
removes the draw that a bad opening makes unaffordable. The whole question is
decided in years 1–3, as in every section above.

Same assumptions and method throughout: real returns, 7.0% arithmetic mean, 17%
SD, 5.6% median compounding, draws at the start of each year, no taxes or fees,
spend and supplement both in today's dollars. Thresholds solved backwards
through the ladder; the historical ones run the actual opening sequences by hand.

## The years these numbers sit in

Added October 21, 2026, when he said his birthday: born December 10, 1983, so he
is 42. Everything above was asked and answered in the abstract; this is where it
lands on a calendar.

- **Social Security full retirement age 67** — anyone born 1960 or later — reached
  **December 2050**. The age-70 claim that the $5,181/mo above assumes is
  **December 2053**, 27 years out.
- Earliest claim, age 62, is December 2045.
- So the 2026 dollar figures in the Social Security section are 24–27 years away
  and stated in today's dollars; the taxable maximum, the COLA and the benefit
  formula will all have moved many times by then. The ratios hold — spousal at 50%
  of his FRA amount, no delayed credits on hers — the dollars do not.
- The portfolio sections are horizon-free, but worth reading against the same
  clock: a seven-year bridge begun at 60 ends at 67, exactly where the Social
  Security income starts, which is the one combination the sections above never
  put together.
