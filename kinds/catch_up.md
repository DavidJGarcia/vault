# catch_up

A name David wants on his standing list of people to reconnect with. Born Sunday,
September 20, 2026 from "Send Stacy Shablin to my people to catch up with.", the second
such note after "People to catch up with include Julie Cahoon and Dave Jenkins."

props:  people (list of {name, relation, last_contact}) · action (string: add, remove,
        done) · vault (path of the list the note changed) · open_list (string: whether he
        signalled more names were coming)
enrich: transcribe each name as heard and say the spelling is unverified; look through the
        vault and earlier records for a relation or a last contact before writing
        "not stated"; these are private individuals, so do not search the web for them.
ask:    "who am I meaning to catch up with"; whether a name is already on the list; when a
        name was added and when he said he had caught up.
notes:  the list itself lives at people/catch-up.md, oldest first, and a name comes off it
        when he says he has caught up. "Send X to my people to catch up with" means add X.
        He gives names alone, with no relation and no deadline, so the record is an
        observation and its age does not change it.
