# cart

A change the agent made to a store cart. Born 2026-10-04 from "Add bananas to my Walmart cart".

props:  retailer · item · url · qty_before · qty_after · status (adding | added)
enrich: nothing. Written before the change and completed after it.
ask:    "what did you put in my Walmart cart".
notes:  a record still adding means a run died mid-change: the cart is checked against qty_after
        before anything is added again.
