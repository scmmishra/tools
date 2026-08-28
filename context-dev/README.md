# Context.dev Support Tools

Read-only Context.dev tools for scraping pages, retrieving brand intelligence, searching the web, and inspecting monitor status during support conversations.

[Context.dev](https://www.context.dev) is the web context API for AI agents: it scrapes and crawls the web, extracts structured data, retrieves brand intelligence, and monitors websites for changes.

## Included tools

- **Scrape Page Markdown** (`scrape_page_markdown`) — `GET /v1/web/scrape/markdown?url=...` scrapes any URL into clean, LLM-ready Markdown. Use it to inspect a page a customer is reporting or referencing.
- **Capture Page Screenshot** (`capture_page_screenshot`) — `GET /v1/web/screenshot?directUrl=...` captures a viewport screenshot of an exact URL and returns a public image URL. Use it to visually verify a page's current state.
- **Retrieve Brand by Domain** (`retrieve_brand_by_domain`) — `GET /v1/brand/retrieve?domain=...` retrieves a brand profile (logo, colors, description, socials, industry) for a company domain. Use it to identify or enrich the company a customer works for.
- **Search Brands** (`search_brands`) — `GET /v1/brand/search?query=...` searches indexed brands by name or domain with prefix matching. Use it to resolve a partial or uncertain company name to a domain.
- **Web Search** (`web_search`) — `POST /v1/web/search` with `{"query":"..."}` searches the live web and returns URLs, titles, and snippets. Use it for current public information Captain has not seen, such as release notes or status pages.
- **List Monitors** (`list_monitors`) — `GET /v1/monitors` lists the organization's monitors with target, status, and schedule.
- **Get Monitor** (`get_monitor`) — `GET /v1/monitors/{monitor_id}` retrieves one monitor's full configuration, status, schedule, and baseline.
- **List Monitor Runs** (`list_monitor_runs`) — `GET /v1/monitors/{monitor_id}/runs` lists a monitor's run history with status, timing, and credits charged.
- **List Monitor Changes** (`list_monitor_changes`) — `GET /v1/monitors/{monitor_id}/changes` lists the changes a monitor has detected, with timestamps.

All tools are read-only at the upstream API level. The first version intentionally excludes write operations (monitor creation, updates, deletion, immediate runs, webhook secret rotation, batch submission, and WebDBs).

## Requirements

- A Context.dev API key from the [dashboard](https://context.dev/dashboard). Keys start with `ctxt_secret_`.
- A plan that permits the endpoints above. Monitors tools require at least one monitor in the organization; some scraping features are plan-gated upstream.

Use a key dedicated to the assistant with the least access that still serves these tools, and monitor credit usage: scraping, screenshots, and web search consume API credits per request.

## Setup

1. Copy an API key from the Context.dev dashboard's "API Keys" section.
2. Import `toolset.yml` into Captain.
3. Enter the API key when prompted.
4. Review and enable the imported tools.

All tools authenticate with an HTTP Bearer header (`Authorization: Bearer <API_KEY>`) against the base URL `https://api.context.dev/v1`.

## Notes

- `page_url` and `directUrl` values must be complete URLs including the `http://` or `https://` protocol.
- The screenshot tool takes `directUrl`, which screenshots the exact URL given; domain-level screenshotting with page-type heuristics is intentionally not exposed.
- The web search tool sends only the `query` field; the API defaults to 10 results with no domain filtering.
- Upstream requests are subject to per-minute rate limits; expect HTTP 429 under bursts and HTTP 408 on cold-hit timeouts.

## References

- [Context.dev quickstart](https://docs.context.dev/quickstart)
- [Scrape Markdown API reference](https://docs.context.dev/api-reference/web-scraping/markdown)
- [Capture Screenshot API reference](https://docs.context.dev/api-reference/web-scraping/screenshot)
- [Retrieve Brand Data API reference](https://docs.context.dev/api-reference/brand-intelligence/brand)
- [Search Brands API reference](https://docs.context.dev/api-reference/brand-intelligence/search)
- [Search the Web API reference](https://docs.context.dev/api-reference/web-scraping/search)
- [Monitors API reference](https://docs.context.dev/llms.txt)
- [Rate limits and troubleshooting](https://docs.context.dev/optimization/rate-limits)
