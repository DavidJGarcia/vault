# build_request

He asks for something to be made and kept — a document, a tool, a graph — rather than
asked or done. Born Tuesday October 20, 2026 from "Build me an interactive 3D graph of our
travel time splits…", the second of its sort after "Create a document detailing how I could
get you access to a database of real nutrition data for tracking my food." of September 18,
2026, which was re-filed under it.

Not a question (that is answered from the world and the answer is the whole of it), not a
to-do (that is work *he* will do). This is work handed over, built in the job that heard it,
and the thing built is the point — so the record's job is to say where it landed and what it
still needs.

props:  request (string: what to make, short) · artifact (what sort: document | graph |
        tool | plan) · target (the vault path it lands at) · topic · status (open | done) ·
        wrote (list of paths written) · needs (what he must do before it is usable; null
        when nothing) · built_from (where the content came from: a kind, a search, a file) ·
        then one named key per particular the build turned on, flat, no nesting ·
        sources (list of URLs) · searches (int) · assumed (list)

enrich: build it in the job that heard the note — he is handing over work, not adding to a
        list, so `status` is `done` before the receipt goes out unless something outside
        this machine blocks it. Name the target from the vault's own layout (`notes/` for
        reference he will come back to) and keep the name short enough to read on the
        wrist. The vault is Markdown only, so anything that is not prose ships as a fenced
        block inside a document that says how to use it, and `needs` says so. When the
        thing is built from his own records, name the kind in `built_from` and say in the
        document how many rows it drew on, so a later rebuild knows what has changed.

ask:    "what have you built for me"; "where is the thing about X"; what is still open and
        what each one is waiting on me for.

notes:  he opens one with a bare imperative — "Build me…", "Create a document…", "Draft a
        plan…" — and gives the shape he wants in the same breath, often more precisely than
        he needs to ("y is the length of travel time, x is clustering by the time that we
        started"). Take that shape literally: it is the specification, and a better idea
        goes in the document beside it, not instead of it. A later note that changes the
        thing updates this record and rewrites the file rather than filing a second.
