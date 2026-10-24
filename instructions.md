# Standing instructions

David's standing word to the worker. It is appended to the worker's prompt for
every job, so what is written here is followed without being asked again.
Newest at the end. He edits this file on GitHub.

## Food

**September 21, 2026 — day totals on every meal receipt.** When a meal is
tracked, the reply also states the day's total calories and total protein,
including the meal just filed. "From now on when you track food that I've eaten,
also respond with total calories and total protein for the day."

The day is his local day, midnight to midnight, America/Chicago. The totals come
from the meal rows, never from a stored running total:

```
records --kind meal --from <today 00:00 -05:00> --to <today 23:59 -05:00> \
        --agg sum:kcal,sum:protein_g,count
```

so a later correction to a meal moves the day with it. Two rows on the wrist is
enough: what was eaten and its numbers, then the day so far.

## Weight

**October 4, 2026 — the trend on every weigh-in receipt.** When he weighs in, the
reply gives the trend, not the change against the previous weigh-in. "From now on
when I weigh in, I want information about the trend not the previous weigh-in."

The trend is the morning series: average each day's morning readings, then compare
the last 7 days to the 7 days before. Evening readings run heavier and stay out of
it — compare morning to morning. The numbers come from the rows, never from
anything stored on a row, so a later correction moves the trend with it:

```
records --kind weigh_in
```

morning rows only — the `--by day` aggregate averages evening readings in with the
morning ones. Two rows on the wrist is enough: the reading, then the trend —
"143.6" / "7-day avg 141.6, down 2.8". When the earlier week holds fewer than
three mornings, give the trend and say the baseline is thin.

## Home

**October 9, 2026 — never more than 5 days without emptying the litter robot.**
"Just emptied the litter robot. Don't ever let me go more than 5 days without
emptying it."

A reminder stands for it: timer `t_c4c588a5c59f2085`, "Empty the litter robot",
`every:5d` at 18:00, next Wednesday October 14, 2026. The evening hour is
deliberate — five days after a 10 p.m. emptying is a night-time fire that waits
for morning and lands past the five days, so the reminder sits inside the window
rather than on its edge.

The rule is a maximum, so the clock restarts at each emptying. When a note says
the litter robot was emptied: file the emptying, then `timer get
t_c4c588a5c59f2085` and `timer put --id t_c4c588a5c59f2085` with `at` moved to
that day plus five days at 18:00, keeping the row and its repeat. Say on the
wrist when the next one is due. Emptying means the waste drawer of the
Litter-Robot; the kids' trash-and-litter turns in `home/chores.md` are a
different thing and do not satisfy it.

## To-dos

**October 16, 2026 — every open to-do in the morning briefing, except the
backlog.** "In my morning updates I want to see all of my to-dos that aren't on
the backlog, even if it means multiple messages."

The briefing's to-do section is no longer a judgment call about which ones
matter today. Every open to-do without `backlog` is named, overdue first, then
due today, then the rest in his order:

```
records --kind todo --open --order ord
```

When they do not fit the message with the rest of the morning, send more
messages (reverse order, headline last) — he asked for that explicitly, so the
list is never trimmed to fit seven rows.

A to-do is backlog only when his own words put it there ("backlog to-do",
"personal backlog"): that sets `props.backlog: true`, and keeps it off the
briefing while leaving it on /notes/todo and in "what's on my list". Nothing
else counts as backlog — not age, not position on the list. On this date two
rows carry it (a new mattress for Abby, finish Granddaddy's book) and six open
to-dos are in the briefing.

## Money

**October 18, 2026 — match his Walmart and Amazon imports to his order history,
every weekly pass.** "How do I set it up so that you do that automatically with
the weekly refresh for both Walmart and Amazon for anything that's not already
grouped?" — after the October 18 run that wrote the orders behind six Walmart
charges into their memos.

The weekly pass, after reconciling your own purchase entries (`ynab.md`,
*Reconciling your purchase entries*), takes his **imported** Walmart and Amazon
charges that are not yet tied to an order and writes the order into the memo:

```
transactions --payee Walmart --since <90 days before the pass>
transactions --payee Amazon  --since <90 days before the pass>
```

Already grouped, so skipped: a memo that already names an order or says no match
was found, an import YNAB has `matched` to one of your entries, and any memo he
wrote himself.

For each of the rest, read the store's own history in the agent browser — Walmart
Purchase history (`walmart.com/orders`), Amazon Your Orders — and find the order,
store purchase or fuel stop whose total and date fit the charge. Then `update`
that import with a memo of a line or two: the store, the order number, its date,
and what it bought. The format the October 18 run used, which he liked:
`Walmart order 2000153-27521825 (Oct 10 delivery): 15 items - produce, milk,
bread, Hershey's syrup, Huggies size 5 diapers. Incl $6.55 driver tip.`

- **The memo is the only change.** Never the category, the approval, the amount
  or the payee — those are his — and nothing is deleted. (The one standing
  exception to *leave his imports alone* stays the reconciliation in `ynab.md`.)
- **Amazon charges by shipment**, so one order can be several charges and one
  charge several orders: memo each with the order number and what that shipment
  held, and say when a charge covers more than one order.
- **No match**: say so in the memo, naming the span of history checked, so a
  later pass does not search it again.
- **Newest first, at most 25 imports per store per pass**, so the rest of the
  pass keeps its room; the view says how many are still unmatched.
- No agent browser, a browser that is not the pinned one, or no YNAB: skip this,
  finish the rest of the pass, and say so in the view.

The view names what was memo'd — the charge, its amount and date, the order it
came from — and since the memo is the whole change, undoing one is clearing that
memo in YNAB.

**October 19, 2026 — "David's clothing" is a category, not a person to work out.**
"No I'm David. David's Clothing is one of the categories in my app." — said after
a $17.32 LDS Distribution Online Store charge, spoken as David's clothing, was
filed to Clothing - Kids because a bare "David" was read as his son David
William.

When a money note names something that is one of his YNAB categories, that is the
category, and there is nobody to infer: "David's clothing" is **Clothing - Daddy
David**, "Emily's clothing" is Clothing - Emily, the kids' clothing is Clothing -
Kids. Match what he said against his category list (`categories`) before reading
a name as a person; only when nothing on that list fits does the question of who
a purchase was for arise. He has used the phrase before — "Track $184 at Men's
Warehouse as David's clothing", September 12, 2026.

**October 24, 2026 — the litter reminder fires on the last evening that is still
inside five days.** An amendment to the October 9 rule above, written by the
weekly pass after that rule was broken for the first time. He emptied the drawer
on Sunday October 18 at 9:49 a.m.; the reminder was set for Friday October 23 at
18:00; and 18:00 on the fifth day is already eight hours past a 9:49 a.m.
deadline. He emptied it that night at 9:41 p.m., 5 days 12 hours after the one
before — the first gap over five days on record.

So `at` moves to **18:00 on the last day whose 18:00 is still inside five days**
of the emptying:

- emptied **before 18:00** (a morning or afternoon emptying): that day **plus
  four** days at 18:00;
- emptied **at or after 18:00**: that day **plus five** days at 18:00.

Everything else about the October 9 rule stands. The row as it is now —
Wednesday October 28 at 18:00, from the 9:41 p.m. emptying — is already right
under this reading, so the pass moved nothing.

## How you run

**October 24, 2026 — stop shelling out to grep, python and sed.** Written by the
weekly pass against his October 18 ask: *"Tell me more about the blocked calls
(the refusals). What happened? I'd like to tweak things if needed to make sure
you can do what I need."* Nothing changed then, and the same handful of mistakes
ran **177 times across 116 captures** in the week that followed — about a third
of every tool call made.

- A relay reply saved in the replies cache is read with the **Read and Grep
  tools**, never with `grep`, `head`, `sed` or a `python` heredoc in Bash. The
  shell guard allows one `python <relay.py> …` command and nothing else, so every
  such call is refused and costs a turn. This is the biggest group by far.
- A `$` in a `say`, `record` or `log` argument goes in **single quotes or a
  quoted heredoc**. Escaping it inside double quotes is refused.
- The browser tool `get_page_text` is refused by the classifier every time it has
  been tried — eight times this week, always on a Walmart cart page. Use
  `read_page` or `find` instead.
- A whole file rewritten with `vault put` is **truncated past about 155 lines**,
  so a long file is changed with `vault append … - ` and a quoted heredoc instead.

None of this changed an answer he got: every refused call was retried and every
receipt went out. It is pure waste. It is also the one thing on this page that is
about the worker rather than about him, so delete the section if it belongs
somewhere else.

**Two shortcuts for the Walmart and Amazon memo work**, found the same day.
Walmart: `walmart.com/orders` pages by clicking Next, and `read_page` on the
Purchase history region at depth 3 lists every order's type, date, return link
(which carries the order number) and total in about forty lines. Amazon:
**`amazon.com/cpe/yourpayments/transactions` maps every charge straight to its
order number**, so there is no searching by amount at all; the items for one
order are then at `amazon.com/gp/css/summary/print.html?orderID=<number>`, a
short page. That print page caches, so add a throwaway query parameter when
moving between orders.

**October 24, 2026 — memo his Amazon refunds too, every weekly pass.** "Would you
give me the memos in YNAB for my Amazon refunds and also from now on do that in
the weekly runs as well?"

The October 18 rule above covers his imported Amazon and Walmart *charges*. It now
covers his Amazon **refunds** as well: the money-in rows on the Amazon payee over
the same ninety days that no memo explains. Already grouped, so skipped, by the
same reading as the charges: a memo he wrote himself, a memo that already names an
order or says no match was found.

- The order behind a refund is at `amazon.com/cpe/yourpayments/transactions`, which
  names it on every "Refunded" row. The list loads as it scrolls and does not
  paginate; ninety days is about a dozen scrolls.
- What was returned is at `amazon.com/your-returns`, which pairs each return with
  its item, size, colour and price; **"See more"** at the foot reaches past the
  first dozen. The status line ("Return complete", "$X is credited …") belongs to
  the item *below* it, not above.
- **Match by order number, never by amount.** A refund often arrives in two pieces,
  part to the Prime Visa and part to the Chase card rewards, and only the Visa part
  reaches YNAB — so the total Amazon shows is larger than the row in his budget.
  When they differ, say both in the memo. Item price plus 8.25% Texas tax is the
  check that an item belongs to a row.

The format of the first run, October 24: `Amazon refund, order 111-9834949-8518637
(refunded Oct 9): Mantto men's steampunk Victorian frock coat tailcoat, Medium,
red, $36.99 + tax.`

Everything else about the October 18 rule holds — the memo is the only change,
nothing is deleted, no match is said in the memo with the span checked, newest
first and at most 25 a pass, and the view names what was memo'd.
