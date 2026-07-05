<!-- generated: DO NOT EDIT BY HAND — produced by apps/web/scripts/export-github-repos.ts from content/platforms/accommodation-api.ts. Edit the config + re-run. -->

# Travel API — search, availability & price data in one schema (2026)

**[Get a free API key →](https://scoutingapi.com/signup)** — free tier, no credit card.

Every other option covers half the map — hotels-only (LiteAPI, Hotelbeds) or short-term-rental-only (AirDNA, AirROI). ScoutingAPI returns live search, availability, and price for hotels and short-term rentals alike — Airbnb, Booking.com, Vrbo, and Google Hotels — in one unified schema.

This repository is a resource hub for the modern **Travel API**: REST endpoints, working code samples in six languages, and recipes you can copy in under five minutes. It is not a maintained SDK (the official typed client is [`@scoutingapi/sdk`](https://scoutingapi.com/docs/sdk)) — it is a curated set of examples and references that match the machine contract at [openapi.json](https://api.scoutingapi.com/openapi.json). Every response is the same unified schema across Airbnb, Booking.com, Vrbo and Google Hotels, so one integration covers them all.

`99.9% uptime SLA` · `Failed calls cost 0 credits` · `Native MCP for AI agents` · `One unified schema`

---

## Quick start

Search live Accommodation stays with one HTTPS call — a bearer token, no SDK, no partner approval.

```bash
curl -s "https://api.scoutingapi.com/v1/search" \
  -G --data-urlencode "location=Split, HR" \
  --data-urlencode "platforms=airbnb" \
  --data-urlencode "limit=5" \
  -H "Authorization: Bearer $SCOUTINGAPI_KEY" \
  | jq '.data[] | {platform, name, price}'
```

You get back the unified `{ "data": [...], "meta": {...} }` envelope. [Sign up](https://scoutingapi.com/signup) for a free key, set `SCOUTINGAPI_KEY`, and the request runs as-is. Prefer to try before signing up? A `scout_test_` sandbox key returns deterministic fixtures at **zero cost**.

---

## What you can pull

The Accommodation data surface maps to these REST endpoints — each one HTTPS call, returning the unified schema, billed only on success:

- **Search** — `GET /v1/search` — Cross-platform property discovery, merged into one schema.
- **Price** — `GET /v1/price` — A real price quote for one listing, for your dates and occupancy.
- **Price compare** — `GET /v1/price-compare` — Cross-OTA price comparison for one property — the flagship endpoint.
- **Availability** — `GET /v1/availability` — Day-by-day availability for a known listing over a date window.
- **Listing** — `GET /v1/listing/{platform}/{id}` — Full listing detail — amenities, photos, host, and optional live price.
- **Reviews** — `GET /v1/reviews` — Normalized, paginated reviews for one listing.
- **Account** — `GET /v1/account` — Check your plan, credit balance and rate limit — programmatically.

Full machine contract: [openapi.json](https://api.scoutingapi.com/openapi.json). Per-endpoint references: [`endpoints/`](endpoints/).

**Ready to try?** [Get a free ScoutingAPI key →](https://scoutingapi.com/signup).

---

## What you can build

- **Cross-vertical travel search** — Let users search hotels and short-term rentals side-by-side for the same destination and dates — one call, one schema, ranked together.
- **Cross-OTA rate shopping** — Show the cheapest rate for a property across every OTA with /v1/price-compare — hotels and rentals alike — with computed min/median.
- **Market & investment intelligence** — Pull live rates and availability across both verticals to underwrite a market or benchmark a portfolio against the full competitive set.
- **Hotelier & host competitive pricing** — Benchmark a property against comparable hotels and rentals for the same dates and feed a pricing engine that doesn’t guess.
- **Availability & price-drop monitoring** — Poll /v1/availability or /v1/price-compare and fire a Slack, email, or Telegram alert on a change — shippable from /workflows in minutes.
- **Accommodation agents** — Give your AI agent one dependable tool for the whole market: “villa or hotel near Split, July 13–20, 2 adults + 2 kids” → normalized results via the native MCP server.

---

## Code examples by language

Six languages, each in its own folder under [`examples/`](examples/). Every snippet is one screen, uses the language's standard library or a single zero-friction dependency, and resolves to the same unified envelope.

- [curl](examples/curl/) · [Node.js](examples/node/) · [Python](examples/python/) · [Go](examples/go/) · [Ruby](examples/ruby/) · [PHP](examples/php/)

---

## Recipes

Ready-made automations built on Accommodation data — importable n8n workflows and portable AI-agent skills. See [`recipes/`](recipes/) and the full [travel-workflows](https://github.com/scoutingapi/travel-workflows) repo, or browse them rendered at [https://scoutingapi.com/workflows](https://scoutingapi.com/workflows).

---

## Pricing & credits

Every call bills against a credit balance. **Failed, empty and blocked calls are never billed**, and `scout_test_` sandbox calls are always free. The exact, current per-endpoint costs live on the [pricing page](https://scoutingapi.com/pricing) and in the machine-readable [openapi.json](https://api.scoutingapi.com/openapi.json) — this repo stays number-free so it never drifts.

---

## FAQ

### What is an accommodation API?

An API that returns accommodation data — listings, availability, and price — programmatically. ScoutingAPI is a unified accommodation API: it covers both halves of the market (hotels and short-term rentals) across Airbnb, Booking.com, Vrbo, and Google Hotels, and returns them in one normalized schema so you integrate once.

### Does it cover both hotels and short-term rentals?

Yes — that’s the whole point. Most options cover only one half: hotel APIs (LiteAPI, Hotelbeds) skip Airbnb and Vrbo, and STR-analytics tools (AirDNA, AirROI) skip hotels. ScoutingAPI returns a hotel and a short-term rental in the same call, with an identical object shape.

### Which platforms are live today?

Airbnb, Booking.com, Vrbo, and Google Hotels are live now. Expedia, Hotels.com, and TripAdvisor are on the roadmap via the same unified schema — we state coverage honestly rather than claiming platforms before they ship.

### How do I get accommodation data in Python?

Call GET /v1/search with requests, or use the SDK — see the Python sample above. Pass a location, dates, occupancy, and a comma-separated platforms list; you get back normalized JSON with price, rating, amenities, and host info for every platform in one array.

---

## Related repositories

Part of the ScoutingAPI open resource set — one unified accommodation-data API across Airbnb, Booking.com, Vrbo and Google Hotels, with a REST API, a native MCP server, and importable workflows.

- [airbnb-api](https://github.com/scoutingapi/airbnb-api)
- [booking-com-api](https://github.com/scoutingapi/booking-com-api)
- [vrbo-api](https://github.com/scoutingapi/vrbo-api)
- [google-hotels-api](https://github.com/scoutingapi/google-hotels-api)
- [hotel-api](https://github.com/scoutingapi/hotel-api)
- [travel-skills](https://github.com/scoutingapi/travel-skills)
- [hotel-mcp](https://github.com/scoutingapi/hotel-mcp)
- [travel-workflows](https://github.com/scoutingapi/travel-workflows)
- [airbnb-skills](https://github.com/scoutingapi/airbnb-skills)
- [booking-com-skills](https://github.com/scoutingapi/booking-com-skills)
- [vrbo-skills](https://github.com/scoutingapi/vrbo-skills)
- [google-hotels-skills](https://github.com/scoutingapi/google-hotels-skills)

- Website: <https://scoutingapi.com> · Docs: <https://scoutingapi.com/docs> · Status: <https://status.scoutingapi.com>

---

**Get your free key — no card → <https://scoutingapi.com/signup>** · [Docs](https://scoutingapi.com/docs) · [Pricing](https://scoutingapi.com/pricing) · [Status](https://status.scoutingapi.com)

Built with [ScoutingAPI](https://scoutingapi.com) — trusted, ToS-clean, real-time accommodation data across Airbnb, Booking.com, Vrbo and Google Hotels, normalized to one schema. REST + a native MCP server.

> ScoutingAPI is an independent service and is not affiliated with or endorsed by any booking platform. Platform names are trademarks of their respective owners.
