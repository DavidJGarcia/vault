# Getting Claude to add things to my Walmart cart

Researched October 3, 2026, from "Research how I can get Claude to add things to
my Walmart cart directly."

## The constraint

There is no public consumer cart API at Walmart. Walmart's developer APIs are the
Marketplace APIs (for sellers: catalog, inventory, orders, settlements) and the
affiliate/product-search APIs (read-only lookups). None of them can touch the cart
on a shopper's account. So "directly" means one of two things: a browser driven on
my behalf while I am logged in, or waiting for Walmart's own agent to arrive inside
Claude.

## Route 1 - Claude in Chrome (works today, least setup)

The official Anthropic browser extension. Generally available since August 26,
2026, included in every paid Claude plan at no extra charge, Chrome and Edge only.
It reads the page, clicks and types, so on a Walmart tab where I am already signed
in it can search, open an item and press Add to cart. I keep checkout.

- Install from the Chrome Web Store, sign in with the Claude account.
- Turn **auto-approval off** for this. It is on by default; with it off every click
  waits for mine, which is what I want on a site holding a payment method.
- The extension has a safety classifier and scans pages for prompt injection, but
  that is risk managed, not removed. Build the cart with it, check out myself.

## Route 2 - a browser-automation MCP server (works today, unattended)

For having a job do it rather than watching it happen. `@striderlabs/mcp-walmart`
on npm is an MCP server that drives Chromium through Playwright and exposes an
`add_to_cart` tool (product URL or item ID, plus quantity), alongside search and
order history. There is also a "Walmart shopping assistant" Claude Code skill on
MCPMarket that wraps the same browser approach with basket planning and
substitution rules.

What this costs: it is third party and unofficial; it stores my logged-in Walmart
session on disk (`~/.striderlabs/walmart/cookies.json` and `auth.json`); and it
ships stealth patches to get past bot detection, which is against Walmart's terms
and can get an account flagged. It also breaks whenever Walmart changes its pages.
Worth it only if a job needs to do this without me present.

For the other half of the problem - deciding what to buy, comparing prices - the
read-only Walmart MCP servers (HasData, and the affiliate-API one by taazkareem)
are safe and need no login. They cannot add anything to a cart.

## Route 3 - Walmart's own agent (not here yet)

Walmart's assistant is Sparky, and the strategy now is to put Sparky inside other
companies' assistants rather than let them drive Walmart.com.

- October 2025: Walmart partnered with OpenAI for Instant Checkout in ChatGPT.
- March 2026: Walmart ended that, citing accuracy and integration problems, and
  began embedding Sparky into ChatGPT (paid tiers first) instead.
- July 2026: Gemini, through Google's Universal Commerce Protocol, covering
  walmart.com, the marketplace and store lanes.
- Claude: reported to be in discussion with Anthropic. Nothing shipped as of
  October 3, 2026.

When that lands it is the route with no automation to maintain. Until then, Route 1.

## Not this

Anthropic's `anthropics/commerce-agents` (Apache-2.0, September 2026) is a
blueprint for retailers building their own shopping and merchant agents. It is for
the store's side of the counter, not for shopping someone else's store.

## Sources

- https://www.npmjs.com/package/@striderlabs/mcp-walmart
- https://mcpmarket.com/tools/skills/walmart-shopping-assistant
- https://thepaypers.com/payments/news/walmart-drops-openai-checkout-and-deploys-sparky-on-ai-platforms
- https://novadata.io/resources/news/walmart-google-gemini-universal-commerce-protocol-checkout-july-2026
- https://github.com/HasData/walmart-mcp
- https://www.layer3labs.io/guides/claude-in-chrome
