# meal
Something he ate, logged. Born 2026-09-16 from "Log homemade spaghetti and meatballs dinner
with a side Caesar salad." — the second food note, after "Log 80 g of banana."

props:  meal (breakfast | lunch | dinner | snack) · items (list: name, grams or count, state) ·
        kcal · protein_g · carbs_g · fat_g · homemade (bool) · basis (string: what the numbers
        are counted from) · assumed (list) · sources (list of URLs)
enrich: name the meal from the clock time he spoke it (before 10:30 breakfast, 11-14 lunch,
        17-21 dinner, otherwise snack). When he gives no weight, take one ordinary serving of
        the dish and say so; when he gives grams, use them. Look nutrition up on the web when
        it is not obvious, keep the URLs in `sources`, and put the basis on the wrist next to
        the number.
ask:    "how much did I eat today"; kcal and protein by day or week, one `--agg` query.
notes:  he says "log" and then the food. Homemade dishes come with no weights, so the number
        is an estimate of a serving and the receipt says which serving. A single fruit or
        snack is still a meal row, with `meal: snack`.
