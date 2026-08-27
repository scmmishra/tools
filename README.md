# Captain tools

This directory is a repository-ready collection of toolsets for [Captain](https://www.chatwoot.com/captain). Each direct child directory contains an importable `toolset.yml` manifest and its documentation.

## Toolsets

| Toolset | Description |
| --- | --- |
| [Shopify](./shopify/) | Look up Shopify orders and customers through the REST Admin API. |
| [Stripe](./stripe/) | Look up Stripe customers, payments, and subscriptions. |
| [Linear](./linear/) | Look up Linear issues through the GraphQL API. |

## Install

Import the relevant `toolset.yml` in Captain and provide the requested credentials. Review the tools, endpoints, and permissions before enabling them.

These manifests contain no credentials. Captain substitutes the values collected during import and stores them with the installed custom tools.

## Publish

When this directory is moved into its own GitHub repository, add the `captain-toolsets` repository topic to make it discoverable by the proposed Captain tool catalog.

## Security

The included tools are read-only at the upstream API level. Use restricted credentials with only the permissions required by each toolset, rotate exposed credentials immediately, and test against non-production data before enabling a tool for an assistant.
