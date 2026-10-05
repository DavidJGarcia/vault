# cart
A change the agent made to a store cart. Born 2026-10-05 from "Add Cinnamon Toast Crunch to my
Walmart cart".

props:  retailer (amazon | walmart | heb | homedepot) · item · url · qty_before · qty_after ·
        status (adding | added | abandoned)
enrich: nothing. Written before the change and completed after it.
ask:    "what did you put in my Walmart cart".
notes:  a record still adding means a run died mid-change: the cart is checked against qty_after
        before anything is added again. The Walmart cart is free to fill — no approval needed —
        so these records exist to keep a repeated run from adding twice, not to track spending.
