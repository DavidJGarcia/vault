# nutrition_check

A question about his own eating, answered from his `meal` rows: what he has had so
far, or what to eat next. Born September 19, 2026 from "How many total calories and
how much protein so far today?" Three earlier asks of the same sort sat untyped since
September 17, so the kind was born here and those rows were re-filed under it.

**Two shapes.** *The sum* - what the day stands at. *The judgment* - what to eat, how
much of a named food fits, what a restaurant order does to the day. The judgment shape
began October 4, 2026 ("should I have a second pork chop?") and is now most of the
kind: 11 of the 21 rows, 10 of them since October 12. A judgment answers against the
targets below.

props:  asked - window (the span summed, with timezone) - kcal_total -
        protein_g_total - items (list of {item, kcal, protein_g}) - source_records -
        basis (how the totals were arrived at) - assumed (list)

        a judgment also carries: kcal_target - protein_target_g - gap_kcal -
        gap_protein_g - pick - pick_kcal - pick_protein_g - day_if_eaten_kcal -
        day_if_eaten_protein_g - options (list of {item, kcal, protein_g, day_kcal,
        day_protein_g}) - sources - and, when a later note changes it, revises,
        clarifies, corrected_by or superseded_by.

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

enrich: sum with `records --kind meal --from ... --to ... --agg
        sum:kcal,sum:protein_g,count`, the window running from local midnight to the
        moment he asked. Name the items on the wrist, biggest first, so the total has
        a shape he can check. For a judgment: the gap to the targets, one pick with
        what the day lands at, and the alternatives behind it - priced from food his
        own rows show is in the house. Say which numbers came from a label and which
        are estimates. The totals are a snapshot, not a closed day: if he asks again
        later, that is a new row, not an update to this one.

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
        said.
