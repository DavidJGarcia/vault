# Hark

Researched October 7, 2026, from "Research Hark.com and figure out if I can have
you use that to get work done."

## What it is

hark.com is Hark Pro, a personal AI assistant from a new lab founded by Brett
Adcock (the Figure AI founder). Raised a Series A of more than $700M at a $6B
valuation in May 2026; AT&T has invested and NVIDIA supplies the training
compute. Its own pitch: "A new kind of system for getting things done. Whatever
you need, let Hark handle it."

Two parts worth knowing about:

- **Hark Pro** — a chat assistant with persistent memory, "Action Buttons" for
  suggested tasks, Projects for longer undertakings (a trip, a job search), and
  Custom Panels that pull from Spotify, Strava, Venmo and the like.
- **Handoff** — a computer-use agent, previewed August 2026. It gets a fresh
  virtual machine per request (browser, file system, terminal) and operates
  websites by clicking and typing rather than through APIs: ordering food,
  booking flights, shopping, reservations, research. Hark claims benchmark
  numbers above OpenAI's and Anthropic's at a lower token cost.

Available now on web, iOS and Android. Free tier, with paid tiers at $20 and
$100 a month for higher limits. First hardware device is slated for 2027.

## Can the Index worker use it?

**No — not programmatically.** Hark publishes no developer portal, no
documentation, no public API, no SDK and no machine-readable contract of any
kind. The platform is consumer-app-only, and Handoff is still behind a
request-access form. There is nothing for this worker to call.

What is possible: David uses Hark Pro himself, in the app, as a second
assistant alongside Index. That is a parallel tool, not an integration — it
would keep its own memory, and nothing it did would land in the records, the
vault or the briefing.

Worth noting the overlap: Handoff's headline trick, driving a real browser to
place an order, is what this worker already does for Amazon, Walmart, H-E-B and
Home Depot under `jobs/shopping.md`.

## If this changes

The thing to watch for is a Hark API or MCP server. If one ships, Handoff
becomes a tool this worker could hand a task to — the same way it hands one to
the browser today. Until then, re-checking costs one search.
