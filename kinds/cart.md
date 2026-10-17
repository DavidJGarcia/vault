# cart
A change the agent made to a store cart. Born 2026-10-05 from "Add Cinnamon Toast Crunch to my
Walmart cart".

props:  retailer (amazon | walmart | heb | homedepot) - item - url - qty_before - qty_after -
        status (adding | added | abandoned) - price - unit_price (what the pick was judged on) -
        chosen_because or why (the bought-before mark, the order history or the unit price that
        decided it) - weighed (the versions passed over, with their unit prices) - cart_before and
        cart_after (count and subtotal either side, read off the cart page) - heard_as (the
        transcription, when it was not the product) - attempts (a click that did not register) -
        and for a removal or a correction: undoes, corrects, reversed_by, wrong_pick
enrich: nothing invented about the item. Written before the change and completed after it.
ask:    "what did you put in my Walmart cart"; what the cart held on a day; what was passed over
        and why.
notes:  a record still adding means a run died mid-change: the cart is checked against qty_after
        before anything is added again. The Walmart cart is free to fill - no approval needed -
        so these records exist to keep a repeated run from adding twice, not to track spending.

        An Add click by element ref often does not register. Read the cart count back afterwards
        and repeat the click by coordinate; October 10, 14 and 15, 2026 all needed it, and the
        attempts prop is where that goes.

        A removal is a `cart` row too, qty_after 0, naming the row it undoes. Four of the week's
        rows are removals and two are a mishearing corrected ("blueberry cereal" was Bluey by Kix).

        **The cart does reach his orders.** It held 14 items and $57.61 on October 15, 2026 and
        was empty by the 17th, with a $356.29 Walmart charge dated the 15th; the Amazon cart went
        the same way. He checks out himself and says so in `notes/claude-walmart-cart.md`, so a
        cart filling up over days is a shopping list working, not a cart ignored.
