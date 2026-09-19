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
2. I use USDA for whole foods and Open Food Facts for anything with a barcode.
3. Nutritionix only if restaurant meals keep coming back as guesses.
4. The local SQLite mirror only if you want food tracking to work with no network.

## What changes on the wrist

Receipts start naming the source: "2 eggs, 1 slice sourdough: 320 kcal (USDA)". A number
with no source named is still my estimate, and you can tell the difference at a glance.

## Sources

- USDA FoodData Central API guide and key signup: https://fdc.nal.usda.gov/api-guide
- USDA data documentation and bulk downloads: https://fdc.nal.usda.gov/data-documentation/
- Open Food Facts data and API: https://world.openfoodfacts.org/data
- Nutritionix API: https://www.nutritionix.com/api
