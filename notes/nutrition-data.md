# Nutrition data: how to give me a real food database

Written September 18, 2026, from a ring note asking what it would take.

## Where things stand

When you say "two eggs and a slice of sourdough", the calories in the receipt are my
estimate from general knowledge. That is close enough for plain food and unreliable for
anything branded, packaged or restaurant-made. A real database fixes the second case and
lets every number carry a source.

Four ways to get there, cheapest first.

## Option 1 - USDA FoodData Central (do this one)

- Free, public domain (CC0), run by the US Department of Agriculture.
- Over 300,000 foods: Foundation Foods (lab-analysed raw ingredients), SR Legacy,
  Survey/FNDDS, and Branded (nutrition copied from manufacturer labels).
- Needs a free data.gov API key. Sign up at https://fdc.nal.usda.gov/api-key-signup/ -
  name and email, key arrives by email in a few minutes.
- Rate limit: 1,000 requests per hour per IP address; going over blocks the key for an
  hour. Higher limits on request. The public DEMO_KEY is 30 per hour and 50 per day,
  which is a test, not a daily driver.
- Calls are plain HTTPS GETs: `/v1/foods/search?query=...&api_key=...` to find a food,
  `/v1/food/{fdcId}` for its full nutrient panel.
- Weak spot: restaurant menu items are thin, and branded entries are label data, so the
  portion is whatever the label calls a serving.

**What you would do:** get the key, then save it on its own line in
`C:\Users\David\.config\index\nutrition-key`. The worker runs with its secrets stripped
out of the environment and reads its relay token from a file next door
(`~\.config\index\worker-token`), so a key file follows the pattern that already works
here. Tell me it exists and I will start using it for every meal note.

### How I would know to find the key there

Asked September 18, 2026. Saving the key is only half of it. Every capture starts fresh:
I get my standing prompt, the one event, and whatever I decide to go read. A file that
quietly appears in `~\.config\index\` is invisible to me until something I already read
on every note names it. The line has to live in the path a meal note takes.

- **The standing prompt, `worker\prompt.md` in the project-index clone.** The right
  place: it is loaded on every capture, so one line there turns a file on disk into a
  habit. Something like: "Food notes: if `C:\Users\David\.config\index\nutrition-key`
  exists, read it and price the meal from USDA FoodData Central, naming USDA in the
  receipt; if it is missing, estimate as now." I never write to your machine, so that
  edit is yours, or one a Claude Code session in the clone makes for you.
- **A `CLAUDE.md` in `C:\Users\David\.config\index\jobs`.** Jobs run from that folder
  rather than from the clone, so a `CLAUDE.md` there loads into every capture too. Same
  effect, kept out of the repository.
- **Telling me through the ring.** Reaches that one capture and nothing after it. The
  record survives in the table, but on an ordinary "track two eggs" I do not read the
  table first, so it would not fire.
- **This document.** Same problem. I am reading it now because you asked about it;
  nothing puts it in front of a meal note.

Put the fallback in that line on purpose: if the file is missing or the key has been
revoked, estimate the way I do today and say nothing about it, so a dead key degrades
quietly instead of showing an error on your wrist. The same holds for any future key -
the file is the secret, the prompt line is what makes it real.
