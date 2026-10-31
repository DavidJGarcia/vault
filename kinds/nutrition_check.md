# nutrition_check

A question about his own eating, answered from his `meal` rows: what he has had so
far, or what to eat next. Born September 19, 2026 from "How many total calories and
how much protein so far today?" Three earlier asks of the same sort sat untyped since
September 17, so the kind was born here and those rows were re-filed under it.

**Three shapes.** *The sum* - what the day stands at. *The judgment* - what to eat, how
much of a named food fits, what a restaurant order does to the day. The judgment shape
began October 4, 2026 ("should I have a second pork chop?") and is now most of the
kind: 11 of the 21 rows, 10 of them since October 12. A judgment answers against the
targets below. *The micronutrient read* - "am I getting the other nutrients that I
need?", October 19, 2026 (rec_20261019T2337209765840bc474): everything past kcal and
protein, answered for the day and for the last 7 days together, because one day of
micronutrients is noise.

props:  asked - window (the span summed, with timezone) - kcal_total -
        protein_g_total - items (list of {item, kcal, protein_g}) - source_records -
        basis (how the totals were arrived at) - assumed (list)

        a judgment also carries: kcal_target - protein_target_g - gap_kcal -
        gap_protein_g - pick - pick_kcal - pick_protein_g - day_if_eaten_kcal -
        day_if_eaten_protein_g - options (list of {item, kcal, protein_g, day_kcal,
        day_protein_g}) - sources - and, when a later note changes it, revises,
        clarifies, corrected_by or superseded_by.

        a micronutrient read also carries: micros_today_estimated (every figure with
        its target beside it) - short_today - adequate_today - week_pattern - fix.

targets: **140 g of protein a day, and 1600-1700 kcal.** Derived October 12, 2026 from
        "Which should I be targeting to build or maintain muscle while losing fat?"
        (rec_20261012T221523302195a18e10): 140 g is 2.2 g/kg at 141.8 lb, the top of
        the range for holding muscle in a deficit, and the calorie window is where his
        logged intake already sat. **He has never set a target of his own**, so every
        answer that leans on these says they are derived. Use these numbers rather
        than deriving new ones, so two answers in one afternoon agree.

        The calorie half is now known to be wrong as a *deficit*: three weeks at a
        logged 1,715 kcal a day left the morning average flat (see `people/david.md`),
        so 1600-1700 is maintenance as logged, not a deficit. It is still a reasonable
        intake to aim at; it is not a window that loses weight. Say so when he asks
        what to eat to lose.

        For the micronutrients, the ordinary adult male RDAs and AIs, settled October
        19, 2026 so the next read agrees with the first: fibre 30 g - potassium
        3,400 mg - magnesium 400 mg - calcium 1,000 mg - vitamin A 900 mcg RAE -
        folate 400 mcg - vitamin K1 120 mcg - vitamin D 15 mcg - vitamin C 90 mg -
        iron 8 mg - zinc 11 mg - B12 2.4 mcg - selenium 55 mcg - sodium under
        2,300 mg - saturated fat under 10 percent of calories. He has set none of
        these either, so say they are the ordinary ones.

enrich: sum with `records --kind meal --from ... --to ... --agg
        sum:kcal,sum:protein_g,count`, the window running from local midnight to the
        moment he asked. Name the items on the wrist, biggest first, so the total has
        a shape he can check. For a judgment: the gap to the targets, one pick with
        what the day lands at, and the alternatives behind it - priced from food his
        own rows show is in the house. Say which numbers came from a label and which
        are estimates. The totals are a snapshot, not a closed day: if he asks again
        later, that is a new row, not an update to this one.

        For a micronutrient read, the aggregate is no help - fat, carbs, fibre and
        sodium are stored on only a few meal rows - so build each figure up food by
        food from the labels already on his rows and USDA composition for the rest,
        and say they are estimates good to about 20 percent. Then read the week with
        `records --kind meal --from <7 days back> --search '<food OR food>' --agg
        count`: row counts by food group find the structural gap that one day cannot.
        Nothing in his records says he takes a multivitamin or any supplement, which
        would change such an answer, so say that assumption on the wrist.

ask:    "what did I ask and what was the answer"; how often he checks; what the day
        stood at when he checked; what he was told to eat.

notes:  he asks in the early afternoon and again late afternoon, and the late ones run
        in chains - seven rows on October 13, 2026 between 4:39 and 5:21 pm, each a
        follow-up on the one before. He asks for protein alone as often as for both.
        A bare product name mid-chain ("Great value, thin and crispy crust, Philly
        cheese steak pizza") is him naming what he actually has, not a note of having
        eaten it: nothing is filed as eaten unless he says he ate it. A fragment that
        reads as pushback may be a question - "Even though I already had 200 g of
        chicken" was read as an objection on October 13 and twelve seconds later he
        said it was a serious question, so answer the question and leave the pick
        standing. Transcripts of these get clipped mid-sentence ("How much protein
        have I had to") - read the clipped tail as "today" unless something else was
        said. A chain can end by widening: the October 19 chain closed with "am I
        getting the other nutrients that I need?" after three protein answers, so
        "other" means what the chain has not covered.
        A second micronutrient read, October 22, 2026: "What about the rest of my
        nutrition?", one minute after a sum answer that gave only kcal and protein.
        "The rest" is the same question as "the other nutrients" of October 19, so it
        takes the micronutrient shape - for the day and then against the last 7 days.
        Count the week with `items:` searches (`--search 'items:spinach OR
        items:broccoli'`), never a bare word search: a bare one gave 10 greens rows
        and 9 fish rows where the items held 0 and 4, because those words appear in
        the `basis` and `assumed` text of neighbouring rows. Settled that day from the
        label: the 5.3 oz Oikos Triple Zero cup carries 0 g fibre and IS fortified
        with vitamin D (about 2 mcg, "good source"), correcting the October 19 read,
        which assumed it unfortified.

        October 31, 2026, a standing instruction (`instructions.md`, *Food,
        continued*): every answer of this kind now expresses each nutrient as a
        percentage of its target — had against should-have — and then names two or
        three foods that would close the gaps without pushing the day much past
        1,700 kcal, saying which gap each food closes. It covers all three shapes,
        the sum included, so a plain "how much protein so far" is answered with the
        percentage, the other nutrients that can be estimated, and what to eat.
        Sodium and saturated fat read as a percentage of their ceiling. The targets
        above are what the percentages are taken against; nothing here sets new
        ones. The props that carry it: `pct_of_target` (a map, nutrient to percent)
        and, on the gap-closing picks, `options` as it is already shaped, each
        option naming the items it closes. Older rows were left as they were — the
        rule changes what an answer says, not what a row holds.
