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

## Option 2 - Open Food Facts (barcodes and packaged food)

- No key, no signup, no rate limit for reasonable use. Open data under the ODbL licence.
- Over 3 million products by barcode: name, brand, nutrition per 100 g or 100 ml,
  ingredients, allergens, Nutri-Score, NOVA group.
- Documented call: `https://world.openfoodfacts.org/api/v2/product/{barcode}.json`
- Coverage is strongest in Europe, good in North America, and any single field can be
  missing on any product.
- Nothing for you to set up. It complements USDA rather than replacing it, and it is the
  answer if you ever want to read a barcode off a package.

## Packaged foods when you only say the name

Asked September 18, 2026: what happens for packaged food if you never scan a barcode and
just tell me what it is. Mostly it works, and USDA's Branded set is what makes it work.

- The same search endpoint takes plain words and can be limited to label data:
  `/v1/foods/search?query=clif bar chocolate chip&dataType=Branded&api_key=...`, with
  `brandOwner=` to narrow to one manufacturer when a product name is generic.
- Branded entries are the manufacturer's own label panel, so "Chobani nonfat plain" comes
  back with the numbers printed on the cup instead of my estimate, and the receipt can
  name USDA as the source.
- What decides whether it lands is how you say it. Brand, product and flavour resolve to
  one entry: "Clif Bar chocolate chip" is exact, "a protein bar" is not. When it is
  ambiguous I will take the closest match and say on the wrist which one I took.
- Label numbers are per the label's serving, which is often not the package. Say "the
  whole bag" or "two bars" when it matters; otherwise I will assume one serving and say so.
- Discontinued and reformulated products stay in the set, so an old entry can carry a
  panel the current package no longer prints. Uncommon, worth knowing when a number looks
  wrong.

Open Food Facts is the weaker half here. Its v2 API searches structured fields - brand,
category, nutrient - and has no full-text search; free text lives in the older
`cgi/search.pl` endpoint and in the newer Search-a-licious service. It stays the right
tool for a barcode and for imported products USDA missed, not the first thing tried on a
spoken name.

Nutritionix (Option 3) is the one built for this exact sentence, parsing "two slices of
pizza and a coke" into items, and it carries restaurant menus USDA does not. That is the
paid answer if naming things out loud keeps coming back wrong.

**What you would do:** nothing beyond Option 1. Naming packaged food out loud starts
working the moment the key file exists.

## Option 3 - Nutritionix (natural language, costs money at scale)

- Around 1.9 million foods, including roughly 202,000 restaurant menu items across
  209,000 US locations - the part USDA is weakest at.
- Its natural-language endpoint turns "two slices of pizza and a coke" into structured
  items with quantities, which is exactly the shape of what you say to the ring.
  Reported accuracy on casual descriptions is about 85 percent.
- There is a free developer tier; paid plans start around $299/month, with higher tiers
  at $999 and enterprise from about $1,850.
- Worth revisiting only if restaurant meals are a real share of what you eat and the free
  tier's limits turn out to be too small. The parsing it sells is work I already do.

## Option 4 - a local copy (no network, no limits)

- USDA publishes the whole database as CSV: `food_nutrient.csv` about 1.3 GB,
  `branded_food.csv` about 745 MB, `food.csv` about 140 MB.
- Loaded into SQLite on this machine it answers instantly, offline, with no rate limit,
  and I can query it with ordinary SQL instead of one HTTP call per food.
- Costs a few GB of disk, an hour of setup, and a reload when USDA republishes, which is
  a couple of times a year.
- Sensible later, once the API version has proven it earns its keep.

## Suggested order

1. Get the USDA key and drop it in the file above. Five minutes, free, no card.
2. I use USDA for whole foods and for packaged food you name out loud, and Open Food Facts
   for anything with a barcode.
3. Nutritionix only if restaurant meals keep coming back as guesses.
4. The local SQLite mirror only if you want food tracking to work with no network.

## What changes on the wrist

Receipts start naming the source: "2 eggs, 1 slice sourdough: 320 kcal (USDA)". A number
with no source named is still my estimate, and you can tell the difference at a glance.

## Sources

- USDA FoodData Central API guide and key signup: https://fdc.nal.usda.gov/api-guide
- USDA data documentation and bulk downloads: https://fdc.nal.usda.gov/data-documentation/
- USDA search parameters, dataType=Branded and brandOwner: https://fdc.nal.usda.gov/help
- Open Food Facts data and API: https://world.openfoodfacts.org/data
- Open Food Facts search API v2, structured fields and no full text:
  https://wiki.openfoodfacts.org/Open_Food_Facts_Search_API_Version_2
- Nutritionix API: https://www.nutritionix.com/api
## How I would know to find the key there

Asked September 18, 2026, about the key file above. Saving it is only half of it. Every
capture starts fresh: I get my standing prompt, the one event, and whatever I decide to
go read. A file that quietly appears in `~\.config\index\` is invisible to me until
something I already read on every note names it. The line has to live in the path a meal
note takes.
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
