# meal

Something eaten or drunk, one row per eating. Born September 19, 2026 from
"Track 1, Kirtland Signatures, Carmel S'mores Cluster." The week already held two
dozen untyped food notes, so the kind was born here and those rows were re-filed
under it.

props:  items (list) - portion (string, as he said it) - kcal (number) -
        protein_g (number) - place - meal (breakfast, lunch, dinner, snack) -
        basis (how the numbers were arrived at) - assumed (list) - sources (list of URLs)

enrich: when he does not weigh or say, estimate kcal and protein from typical
        portions and put the basis next to the number on the wrist. A brand and
        product name means label numbers, not an estimate. Day totals are never
        stored on a row - they come from
        `records --kind meal --from ... --agg sum:kcal,count --by day`.

ask:    "how many calories today"; "how much protein this week";
        "when did I last eat X"; calories and protein per day.

notes:  he opens with "Track" or "Log". A second helping of the same thing a few
        minutes later updates the same row rather than filing a new one. He names
        brands often, and the label beats an estimate. Transcription mangles brand
        names ("Kirtland Signatures" for Kirkland Signature) - resolve them and say
        what was resolved.
        A bare number in a Track note is the count of that helping, not a running
        total for the day. On September 19, 2026 "Track 11: Jesus." was read as a
        running count and the cluster row was raised to eleven; he corrected it to
        three nine minutes later. When a number looks like a jump, keep the helpings
        already counted and say what was assumed.
        "a white X" is a transcription slip for "a bite of X": on September 21,
        2026 "a white frozen pepperoni pizza" was filed as a whole white (alfredo)
        pizza, 420 kcal, and he corrected it to a bite of an ordinary pepperoni
        one, about 60 kcal, thirteen minutes later. A puzzling adjective in front
        of a food is worth reading as a portion word first.
        Every meal receipt carries the day so far: total kcal and total protein
        for his local day, including the meal just filed (his standing
        instruction of September 21, 2026, in instructions.md). One query,
        `--agg sum:kcal,sum:protein_g,count`; never a running total on a row.
        "the usual" for breakfast, redefined October 14, 2026 at 11:46 am by "The
        usual should be 1 serving or 2 scoops, or 46 g of Orgain organic protein
        powder, which has 150 calories and 21 g of protein": 46 g Orgain Organic
        Protein plant-based powder, 2 scoops (150 kcal, 21 g protein), 1/3 cup
        dry rolled oats, 27 g (100 kcal, 3.3 g), 1 cup fresh blueberries, 148 g
        (84 kcal, 1.1 g) and 3/8 cup unsweetened vanilla almond milk, 90 ml
        (11 kcal, 0.4 g) - 345 kcal, 25.8 g protein; about 54 g carbs, 7 g fat,
        10 g fiber. The powder was 27 g Sprouts chocolate whey (100 kcal, 18 g
        protein) until that note - the Orgain replaces it, it is not a second
        scoop beside it. The oats were 1/2 cup dry (40 g, 150 kcal) until 9:41
        that same morning, and before September 30, 2026 the blueberries were
        1 1/2 cups with no milk. Expand "the usual" from this line, and change it
        here when he changes the recipe again. A redefinition is forward-looking -
        the mornings already filed stay as they were eaten - unless it lands within
        minutes of that morning's own row, as on September 30, 2026, when it
        revises that row too.
        "a third cup" is 1/3 cup, not the third cup of three. On October 7, 2026
        "I'm having a third cup of pumpkin spice popcorn" was filed as three cups of
        drizzled kettle corn, 335 kcal, and he corrected it six minutes later to
        1/3 cup of LesserEvil Pumpkin Spice Popcorn, 18 kcal. Read a fraction word
        before an ordinal: "a half cup", "a third cup", "a quarter cup" are
        measures.
        A note comparing two ingredients revises the row just filed rather than
        filing a new one. On October 7, 2026 a homemade beef taco was filed at
        5:43 pm, and five minutes later "I'm having more beans than beef" - beans
        were never mentioned in the first note. Read as the fill ratio of that
        taco: beans added as the larger share (1/2 cup refried pinto), the beef
        halved from 4 oz to 2 oz, the fill the same size overall - 405 kcal to
        415, protein 32 g to 24 g. He describes one plate across two captures, so
        a short follow-up with no verb of eating is usually a correction.
        A restated ingredient is a confirmation, not a second helping. On October 7,
        2026 the taco of 5:43 pm already listed guacamole, and at 5:49 pm he said
        "Oh and guacamole." - the row stayed at 2 Tbsp and the receipt said it was
        already counted. When he names an ingredient the row already holds, say so
        rather than adding it again; he gives a quantity when he means more.
        "N more" can mean a food no row holds, and the total he names can cover
        helpings that were never spoken. On October 9, 2026 "I'm having 8 more."
        was filed as eight 0.78 oz Rice Krispies Treats bars, 720 kcal, that bar
        being the only thing counted so far that day; two minutes later he
        corrected it to "8 more whole almonds for a total of 18". The 10 earlier
        almonds had never been captured, so the row was made to carry all 18,
        127 kcal. When "more" has no antecedent in the day's rows, say plainly
        what it was read against.
        "skills" is a transcription slip for "Skittles". On October 15, 2026 at 8:56pm
        "I have four individual skills." was filed as a fragment, unactionable because it
        named no domain; twelve minutes later "I was saying I did 4 Skittles." showed the
        sentence had been "I had four individual Skittles" — four pieces, 16 kcal
        (rec_20261016T02104124016620e97b, filed at the 8:56pm moment, not at the
        clarification). A short complete sentence with a count in it and nothing to act on
        is worth testing as food first: the odd noun is usually a mangled brand or candy,
        and "individual" in front of a plural is him counting pieces.
        "cheese and crackers" can be Cheez-Its, one food and not two. On October 16,
        2026 at 1:52 pm "I'm having cheese and crackers." was filed as an ounce of
        cheddar with six Ritz-style crackers, 215 kcal; 68 seconds later "Not cheese
        and crackers, Cheese-It brand snack crackers." corrected it to one 30 g
        serving of Cheez-It Original, 150 kcal, 3 g protein. "Cheese-It" is the
        transcription of Cheez-It. When a note names a cheese-flavored cracker, ask
        whether the cheese is a separate item before adding it.
        "Bucky's" is Buc-ee's, the Texas chain, and he eats its branded candy: on
        October 17, 2026 "three Bucky's Blast Pop mints" was filed from the tin's
        label (sugar-free, 6 kcal per 2-piece serving, so 3 kcal a mint; cherry,
        lemon-lime and blue raspberry share one label, so the flavor does not change
        the number). A Buc-ee's product name has label numbers and is worth looking
        up rather than estimating.
        "a protein shake" can be a bottled one. On October 18, 2026 at 11:28 am "I'm
        having a protein shake." was filed as 46 g Orgain powder in almond milk,
        180 kcal and 22 g protein; 91 seconds later "The protein shake that I just
        had was a Premier Protein 11.5 oz, 30 g of protein, cookies and cream
        flavored shake." corrected it to one bottle, 160 kcal and 30 g protein by
        label (5 g carbs, 3 g fat, 1 g sugar; the flavors share the number). He
        drinks both, so a bare "protein shake" is worth saying was read as the
        powder, and he will name the bottle when it was one.
        "paste sauce" and "paste picante" are Pace Picante, the salsa. On October
        18, 2026 at 5:26 pm, three seconds after an Alexa shopping-list command the
        ring overheard, he said: When I said "paste sauce" I meant "paste picante
        sauce." The September 15, 2026 row "Check 1/4 cup of paste picante, medium"
        is the same word, filed from the Pace Picante label (20 kcal, 500 mg sodium
        per 1/4 cup); medium is the one he buys. Read "paste" in front of "picante"
        or "sauce" as the brand - never tomato paste, never pasta sauce.
        A reduced usual scales the whole recipe and does not redefine it. On October
        19, 2026 "I had the usual breakfast but for today only reduced the quantities
        by about a third because I shared it with my kids" was filed as two thirds of
        each ingredient - 230 kcal, 17.2 g protein - with the recipe above left as it
        is. "For today only" is him guarding against exactly that, so a fraction word
        in a usual note is a portion for that morning, never a new usual.
        A weight he gives for a jarred sauce can be the weight of a blend he made,
        not of the sauce alone. On October 20, 2026 "140 g of tiki masala sauce with
        black beans" was filed as 140 g of sauce with about 120 g of beans beside it,
        268 kcal; three minutes later "The Tiki Matolos sauce (140 g) was inclusive of
        the black beans, which have been blended into it" cut it to 140 kcal and 4.5 g
        protein. His batch: one 15 oz can of black beans, drained, blended into one to
        one and a half 15 oz jars of Patak's Tikka Masala simmer sauce - so the blend is
        about two thirds sauce, 100 kcal per 100 g, and 140 g of it is 140 kcal. The
        ratio he is unsure of hardly matters: one jar and a jar and a half differ by
        3 kcal in a 140 g serving. The October 15, 2026 row, 190 g of sauce over rice
        and chicken, was sauce alone and stands. When he names a sauce by weight and a
        second food with it, the weight may cover both; a blended sauce is his, not the
        jar's.
        "protein oats" is the bowl, not a fortified oat product. On October 22, 2026
        "1/3 cup of protein oats, 2 scoops of Orgain protein powder, 3/8 cup of
        unsweetened vanilla almond milk, and 124 g of banana" was filed as the usual
        breakfast with 124 g banana in place of the cup of blueberries - 371 kcal,
        26.1 g protein. The oats were counted as plain dry rolled oats, 27 g, because
        he names the powder separately in the same breath; reading "protein oats" as a
        high-protein oat product would count its protein twice. The usual recipe above
        is unchanged by a fruit swap he does not call a redefinition.
        Correction to the paragraph just above, same morning: "protein oats" IS a
        protein-fortified oat product, bought in place of the usual rolled oats, and not
        a name for the bowl. Eight minutes after that first filing he said "For breakfast
        I specifically meant that I'm having protein oats instead of the usual rolled
        oats." The oats are the protein kind and the 2 scoops of Orgain still go in on
        top, so both count. Priced from the Quaker Protein Old Fashioned Rolled Oats
        label (160 kcal, 10 g protein, 24 g carb, 2.5 g fat, 3 g fiber per 1/2 cup,
        41 g), so 1/3 cup, 27 g, is about 107 kcal and 6.7 g protein against 100 kcal and
        3.3 g plain: the row went from 371 kcal and 26.1 g protein to 378 and 29.5. No
        purchase or cart record names a protein oats brand - every oats row of his is
        plain Great Value or Quaker old-fashioned - so that label stands in until he
        names the bag; Kodiak Protein-Packed Classic would be about 20 kcal and 1 g more
        at this portion. The usual recipe above still holds plain rolled oats: "protein
        oats" in a note is a swap for that morning, and so is a fruit he names in place
        of the blueberries.
        "prepared craft macaroni and cheese" is Kraft, and he says it in exactly those
        words: 127 g on October 14, 2026, 80 g on October 22. One basis holds both, the
        Kraft Original label prepared as directed - 350 kcal and 10 g protein per 70 g dry
        serving, about 200-210 g on the plate, so 1.7 kcal/g and 0.055 g protein/g. Use it
        unless he names a change to the preparation, as he did on September 28, 2026
        ("prepared with half the butter", which takes about 0.4 kcal/g off).
        Pico de gallo comes from two Walmart labels and they differ by half. The
        refrigerated Freshness Guaranteed Mild tub is 36 kcal per 100 g (the October
        21, 2026 row); Great Value Mild Pico de Gallo is 5 kcal, 0 g protein, 2 g
        carbs and 90 mg sodium per 2 Tbsp (28 g), so 18 kcal per 100 g - 62 g on
        October 22, 2026 was 11 kcal, where the tub would have given 22. Take the
        label he names; neither moves a day much, but say which was used. Mild is
        the one he buys either way.
