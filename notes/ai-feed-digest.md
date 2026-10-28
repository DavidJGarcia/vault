# Getting AI news without opening X

Written Wednesday, October 28, 2026, from: "I hate that I have to keep opening the
X app in order to know what's going on in the world of AI and what new breakthroughs
are happening. How can I set up something to pay attention to my Twitter feed for me
and just tell me the stuff I actually want to know?"

## The question under the question

Two different things are being asked for, and they cost very different amounts:

1. **Knowing what broke in AI this week.** Almost all of that signal exists outside
   X as well, in feeds that are free and stable.
2. **Your feed specifically** — the people you chose to follow, their replies, their
   quote-tweets, the stuff that never leaves X.

Only the second one needs X. So the plan starts with the first, for nothing, and
buys the second only if a week of evidence says the first wasn't enough.

## Phase 0 — an AI section in the morning briefing. Free, works tomorrow.

Nothing new runs. The 05:35 briefing already fires every morning; a standing
instruction gives it one more section. Each morning it does one or two searches
for what moved in AI in the last 24 hours, reads a short list of high-signal
sources, and writes the long version to an `ai` view, with the two or three lines
that actually matter on the wrist.

Sources worth starting with, all free, all real RSS or a public API:

- Hacker News front page via the Algolia API (`hn.algolia.com/api/v1/search?tags=front_page`)
- Techmeme
- Simon Willison's blog — the best single filter on what is genuinely new
- Import AI (Jack Clark), Ahead of AI (Sebastian Raschka)
- arXiv cs.LG and cs.AI new-submissions feeds, for the papers everyone is about to
  quote-tweet
- the model vendors' own release notes: Anthropic, OpenAI, Google DeepMind

**Cost:** nothing. **Work:** one line appended to `instructions.md`.

**Falsification test:** after seven mornings, do you still open the X app? If you
don't, you're done and the rest of this document is academic. If you do, write down
what the digest missed — that single list decides between Phase 1 and Phase 2.

## Phase 1 — a curated X List, read through a bridge

X gives no RSS of its own, so this needs a middleman.

You spend twenty minutes in the app once, building a List of the twenty to forty
accounts that actually produce your AI signal. Then a bridge service turns that
List into an RSS feed, and the briefing fetches the feed like any other source.

- **RSS.app**, the most durable of the bridges: Developer tier, about $17/month
  (100 feeds, 15-minute refresh, 50 posts per feed). The free tier is 2 feeds,
  5 posts, 24-hour refresh — too thin to be useful.
- Free bridges (Nitter instances, keep.md, assorted RSS generators) exist and go
  down. Several shut down or went paid-only during 2026 as X tightened access.

**Cost:** about $17/month. **Work:** build the List, paste one URL.

**Falsification test:** does the feed still deliver thirty days later, without you
noticing it had stopped? A bridge that silently goes stale is worse than no bridge,
so the briefing has to say out loud when the feed returns nothing.

## Phase 2 — your actual home timeline, through the official API

The one route that genuinely reads your feed.

- Endpoint: `GET /2/users/:id/timelines/reverse_chronological`, 100 posts a page,
  180 requests per 15 minutes per user.
- Auth: OAuth 2.0 Authorization Code with PKCE — you approve it once in a browser,
  and a refresh token lands at `C:\Users\David\.config\index\x-token`, the same
  shape as the nutrition key in `notes/nutrition-data.md`.
- Cost: X sells no tiers any more. Since September 2026 it is pay-per-use at
  **$0.005 per post read**. Basic ($200/month) and Pro were deprecated and existing
  subscribers force-migrated.

So the monthly bill is just arithmetic on how much of your feed gets read:

| posts read per day | per month |
| --- | --- |
| 100 | about $15 |
| 200 | about $30 |
| 500 | about $75 |

**Two catches worth knowing before paying.** This endpoint is *reverse
chronological* — it deliberately excludes algorithmic ranking, so it is not the
"For You" feed you actually read. It is the raw output of everyone you follow, which
is noisier, and all the filtering lands on the digest. And it reaches back only
3,200 posts or seven days, so a gap longer than a week is a gap.

**Cost:** $15–75/month. **Work:** a developer account, one OAuth consent, and a
job that pages the timeline.

**Falsification test:** run Phase 0 and Phase 2 side by side for a week and read
both. If the paid one tells you things the free one didn't, it's worth it. If it
mostly tells you the same things eight hours earlier, it isn't.

## Phase 3 — hand it to someone else

Several services do exactly this as a product: Twigest, Reduck, usedigest, and the
old IFTTT applets. They read your feed or your Lists and email you a summary.

Cheapest in effort, worst in control, and it means giving a third party standing
access to your X account. Listed for completeness; only worth it if Phases 0–2 all
turn out to annoy you.

## Rejected

- **X's own AI summaries (Grok Stories, the News tab).** They're good. They're also
  inside the app, which is the thing you said you hate opening.
- **The agent browser reading X.** It is signed in to Amazon, Walmart, H-E-B and
  Home Depot and is restricted to shopping by your own standing instruction. Using
  it to scrape X would need you to lift that rule, and scraping a logged-in X
  session is both against their terms and fragile. Not recommended; it is your rule
  to change, so it's named here rather than quietly assumed.
- **Email-to-self with no filtering.** The problem isn't delivery, it's the volume.

## Where this stands

Phase 0 is one line in `instructions.md` and can be live for tomorrow morning. It
hasn't been written: adding a section to your briefing changes every morning from
here on, so it waits on your yes.

Everything after Phase 0 waits on what Phase 0 misses.
