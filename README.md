# Captain tools

This directory is a repository-ready collection of toolsets for [Captain](https://www.chatwoot.com/captain). Each direct child directory contains an importable `toolset.yml` manifest and its documentation.

## Toolsets

| Toolset | Category | Description |
| --- | --- | --- |
| [Shopify](./shopify/) | Commerce | Look up Shopify orders and customers through the REST Admin API. |
| [Stripe](./stripe/) | Payments & billing | Look up Stripe customers, payments, and subscriptions. |
| [Linear](./linear/) | Engineering & status | Look up Linear issues through the GraphQL API. |
| [Statuspage](./statuspage/) | Engineering & status | Check Statuspage incidents and component health. |
| [Better Stack Uptime](./betterstack-uptime/) | Engineering & status | Check Better Stack monitors and active incidents. |
| [Context.dev](./context-dev/) | Business data & research | Scrape pages, look up brand data, search the web, and check monitor status through the Context.dev API. |

## Install

Import the relevant `toolset.yml` in Captain and provide the requested credentials. Review the tools, endpoints, and permissions before enabling them.

These manifests contain no credentials. Captain substitutes the values collected during import and stores them with the installed custom tools.

## Publish

Add the `captain-toolsets` topic to the public GitHub repository to make it discoverable by the Captain tool catalog. See the [publishing guide](https://captain-tools.engineering-314.workers.dev/publish.md) for the manifest contract and validation instructions.

Each manifest declares a catalog category. Its folder also contains a `logo.svg` or `logo.png` sourced from the service's official website: [Shopify](https://www.shopify.com), [Stripe](https://stripe.com), [Linear](https://linear.app), [Statuspage](https://www.atlassian.com/software/statuspage), [Better Stack](https://betterstack.com), and [Context.dev](https://context.dev). The catalog discovers these files automatically and uses the regular logo for both themes unless a `logo-dark` variant is provided.

## Security

The included tools are read-only at the upstream API level. Use restricted credentials with only the permissions required by each toolset, rotate exposed credentials immediately, and test against non-production data before enabling a tool for an assistant.
