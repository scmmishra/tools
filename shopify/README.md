# Shopify Support Tools

Read-only Shopify tools for looking up an order by number and retrieving a customer by Shopify's numeric customer ID. The tools use Shopify's GraphQL Admin API.

## Included tools

- **Find Shopify Order** — returns basic order, payment, fulfillment, customer, total, and line-item information for a numeric order number.
- **Get Shopify Customer** — returns customer contact details, order count, and lifetime spend for a numeric customer ID.

## Requirements

- A Shopify store domain such as `example.myshopify.com`.
- A supported Shopify Admin API version. The manifest defaults to `2026-07`.
- An Admin API access token sent through `X-Shopify-Access-Token`.
- The `read_orders` and `read_customers` access scopes.

Shopify limits normal order access to the most recent 60 days. Looking up older orders also requires approved `read_all_orders` access.

## Setup

1. Create or select a Shopify app with the required read scopes.
2. Install the app on the store and obtain its Admin API access token.
3. Import `toolset.yml` into Captain.
4. Enter the shop domain without `https://` or a trailing slash.
5. Enter a currently supported Admin API version and the access token.
6. Review and enable the imported tools.

Use the numeric portion of an order number, such as `1001` for order `#1001`. Customer IDs are the numeric legacy resource IDs visible in Shopify Admin URLs and API responses.

## Permissions and data

These tools read protected customer and order data. Only enable them when that data is necessary for the assistant's support workflow. The access token should not include write scopes.

## References

- [Shopify API authentication](https://shopify.dev/docs/api/usage/authentication)
- [GraphQL Admin API queries](https://shopify.dev/docs/apps/build/graphql/basics/queries)
- [Orders query](https://shopify.dev/docs/api/admin-graphql/latest/queries/orders)
- [Customer query](https://shopify.dev/docs/api/admin-graphql/latest/queries/customer)
