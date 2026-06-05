# Safe commerce agent demo pattern

Use this reference when Sharbel wants to build or film an agent that browses a shopping site, ranks products, or creates a “mystery shopper” / “AI bought me something” moment.

## Core pattern

The demo should create real stakes without giving an agent silent purchasing power.

1. Build a browser-search agent that reads a preference profile from config.
2. Search the marketplace with Playwright or a site API when available.
3. Extract candidates with title, price, rating, review count, and URL.
4. Score candidates against explicit preferences and avoid terms.
5. Print the top 3 plus a final purchase card.
6. Stop before checkout by default.
7. Require a human confirmation gate before any external action.
8. Prefer manual checkout on camera with sensitive fields blurred.

## Safety rules to bake into prompts and code

- Default to dry-run mode.
- Never enter card number, CVV, billing address, or account credentials automatically.
- Never print cookies, payment fields, address details, order tokens, or `.env` contents.
- Require both config opt-in and CLI opt-in before moving toward checkout.
- Require an explicit typed `yes` after showing the final purchase card.
- Stop clearly if price exceeds budget, shipping is wrong, checkout fails, or the site blocks automation.
- Blur account name, email, address, payment fields, and order details while filming.

## Good filming shape

- Hook: “I gave the agent $20 and told it to buy one thing I would actually like.”
- Screen proof: show config, queries, scoring, final card, and the blocked checkout gate.
- If buying for real, open the final URL manually and complete checkout yourself after blurring sensitive fields.
- The agent’s job is the decision layer, not secret payment execution.

## Playwright Amazon extraction notes from live build

Amazon search cards may contain product links in multiple places. Do not rely only on `h2 a`; some cards expose the title in `h2 span` but the link under an image or another `a.a-link-normal[href*='/dp/']` node.

Robust selector order:

```python
for link_sel in (
    "h2 a",
    "a.a-link-normal.s-line-clamp-2",
    "a.a-link-normal[href*='/dp/']",
    "a.a-link-normal[href*='/gp/']",
):
    link = card.locator(link_sel).first
```

Useful card selector:

```python
cards = page.locator('[data-component-type="s-search-result"]')
```

Useful title fallback:

```python
title = await card.locator("h2 span").first.inner_text()
if not title:
    title = await card.locator("img.s-image").first.get_attribute("alt")
```

Ratings and review counts are not always present in the search result. A demo can still rank using price, title relevance, and rating when present. If exact review filtering is part of the promise, visit product pages or use a more reliable product API.

## Session artifact

A working local implementation was created at:

`~/.hermes/mystery-shopper/`

It includes:

- `mystery_shopper.py`
- `config.example.json`
- `requirements.txt`
- `README.md`

Verified dry-run command:

```bash
cd ~/.hermes/mystery-shopper
. .venv/bin/activate
python mystery_shopper.py --config config.example.json --dry-run
```

The verified run found candidates on Amazon.nl and stopped with:

```text
Checkout blocked. Safe mode is active.
```
