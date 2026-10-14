# proposal
Something the agent would buy, waiting for his yes. Born 2026-10-13 from "Find me a
gerbil water bottle on Amazon that's not too tall."

props:  retailer (amazon | walmart | heb | homedepot) · item · url · price · qty · total
        · seller (Amazon: who sells it, and its rating) · why (the reason for this pick)
        · weighed (the alternatives and why not) · revised_by (the note that last changed
        its price or item, which cannot approve it)
enrich: nothing. Open until he answers; done when bought, deleted when declined.
ask:    "what's waiting for me to approve".
notes:  filed whenever a buy is not an automatic one — a first purchase, a choice between
        versions, research, a price that jumped, anything past his limits. The reply ends
        with how to say yes.
