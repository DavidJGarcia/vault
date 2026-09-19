# nutrition_check

A question asking what he has eaten so far, answered by summing his `meal` rows.
Born September 19, 2026 from "How many total calories and how much protein so far
today?" Three earlier asks of the same sort sat untyped since September 17, so the
kind was born here and those rows were re-filed under it.

props:  asked (what he wanted) - window (the span summed, with timezone) -
        kcal_total (number) - protein_g_total (number) - items (list of
        {item, kcal, protein_g}) - source_records (list of record ids) -
        basis (how the totals were arrived at) - assumed (list)

enrich: answer from `records --kind meal --from ... --to ... --agg
        sum:kcal,sum:protein_g,count --by day`, the window running from local
        midnight to the moment he asked. Name the items on the wrist, biggest
        first, so the total has a shape he can check. Say which numbers came from
        a label and which are estimates. The totals are a snapshot, not a closed
        day: if he asks again later, that is a new row, not an update to this one.

ask:    "what did I ask and what was the answer"; how often he checks; what the
        day stood at when he checked.

notes:  he asks in the early afternoon and again late afternoon. He asks for
        protein alone as often as for both. Transcripts of these get clipped
        mid-sentence ("How much protein have I had to") - read the clipped tail
        as "today" unless something else was said.
