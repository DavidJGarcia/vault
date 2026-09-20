# gift_idea

Something he wants to give, or that someone on his list wants to be given. Born Sunday
September 20, 2026 from "Land of Story: Treasury of Classic Fairy Tales is on Abby's
Christmas list." The two before it, both from Monday September 14, 2026 — "I'm thinking
Emily could get me, for a present, a second eraser so I have one in the shower and one at
the counter" (corrected to razor the same minute) and "Another idea could be short small
dry-fit garment bottoms" — were re-derived into this shape when it was born.

props:  item (string: the thing, short) · recipient (person it is for) · giver (person who
        would give it, when he names or implies one) · occasion (christmas | birthday |
        none) · occasion_date (ISO date, when the occasion has one) · source (their_list |
        his_idea) · price_usd (number) · price_basis (where the price came from) · where
        (retailer or edition) · status (idea | bought | given) · notes

enrich: identify the product properly when he names one loosely — full title, author,
        edition, format — and say what you matched it to. Give a current price with where
        it came from and keep the URLs in sources. Name the occasion from how he said it:
        "on X's Christmas list" is christmas, source their_list, occasion_date the coming
        December 25. A present he says someone could get him is his_idea with himself as
        recipient. status stays idea until a later note says it was bought or given.

ask:    "what is on Abby's Christmas list"; ideas by recipient; what is still unbought
        before a date; roughly what the list costs.

notes:  he says "is on X's list" for what someone else wants, and "I'm thinking X could
        get me" for what he wants. Ideas arrive in runs — one note, then "another idea
        could be", which carries the same giver and occasion as the note before it. One
        item per record so each can be bought on its own. His six kids are David, Derek,
        Abigail (Abby), Jeffrey, Andrew and Cody.
