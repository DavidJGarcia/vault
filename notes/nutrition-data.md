# Nutrition data: how to give me a real food database

Written September 18, 2026, from a ring note asking what it would take.

## Where things stand

When you say "two eggs and a slice of sourdough", the calories in the receipt are my
estimate from general knowledge. That is close enough for plain food and unreliable for
anything branded, packaged or restaurant-made. A real database fixes the second case and
lets every number carry a source.

Four ways to get there, cheapest first.

## Scale: one person, tracking his own food

Asked September 18, 2026. This is a private food log for one man in Manor, Texas - no
app, no users, no product. That settles more of the question than it looks like.

- **Rate limits stop mattering.** Ten to fifteen meals and snacks a day, a few lookups
  each, is under 50 calls. USDA allows 1,000 an hour. There is no volume story here, so
  no tier above the free key ever needs buying.
- **Licences stop mattering.** USDA data is public domain (CC0). Open Food Facts is
  ODbL, whose share-alike terms bite on redistributing a database, not on reading your
  own numbers off one. Attribution obligations attach to apps that show data to other
  people; a log on your own wrist shows it to you.
- **Option 4 loses its main argument.** A local mirror was insurance against rate limits
  and cost. At your volume neither is a threat, so it is only worth building if you want
  meal tracking to work with no network.
- **Nutritionix gets further away, not closer** - see Option 3. Personal use is the one
  case it no longer sells to.

The recommendation below does not change, and personal-only use makes it firmer: the
free USDA key covers it, indefinitely, with nothing to pay and nothing to renew.

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

**What you would do:** nothing beyond Option 1. Naming packaged food out loud starts
working the moment the key file exists.

## Option 3 - Nutritionix (closed to personal use)

- Around 1.9 million foods, including roughly 202,000 restaurant menu items across
  209,000 US locations - the part USDA is weakest at.
- Its natural-language endpoint turns "two slices of pizza and a coke" into structured
  items with quantities, which is the shape of what you say to the ring. Reported
  accuracy on casual descriptions is about 85 percent.
- **The public free tier is gone.** After a decade of open developer signups Nutritionix
  closed it, citing misuse of trial accounts. Trial keys now go only to commercial,
  research and enterprise evaluations, by request. A one-person food log is none of
  those, so there is no door to walk through.
- Paid entry is listed by third parties at around 50 dollars a month for a hobby tier,
  with production plans from roughly 500 to 2,000 dollars and up. The 299 figure first
  written here was older published pricing; treat all of these as approximate, since
  Nutritionix does not post a public price list.
- So for you it is not a cost question but an access one, and the two things it sells you
  already have: parsing your sentence is my job, and restaurant meals I price from the
  chain's own published nutrition, which is how the McDonald's cone and nuggets on
  September 18 got their numbers. Slower per meal, free, accurate for the big chains, and
  thin for independent restaurants - the one real gap that stays open.
