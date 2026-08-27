# Shopify Support Tools

Read-only Shopify tools for retrieving orders and customers by their numeric resource IDs. The tools use Shopify's REST Admin API so each lookup can be represented as a URL-only GET request.

## Included tools

- **Get Shopify Order** (`get_shopify_order`) — sends a URL-only `GET` request to `/admin/api/{api_version}/orders/{order_id}.json` and returns order, payment, fulfillment, customer, total, and line-item information.
- **Get Shopify Customer** (`get_shopify_customer`) — sends a URL-only `GET` request to `/admin/api/{api_version}/customers/{customer_id}.json` and returns customer contact details, order count, and lifetime spend.

## Requirements

- A Shopify store domain such as `example.myshopify.com`.
- A supported Shopify Admin API version. The manifest shows `2026-07` as the input placeholder.
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

Order and customer IDs are the numeric resource IDs visible in Shopify Admin URLs and API responses. An order ID is different from its customer-facing order name, such as `#1001`.

Shopify classifies the REST Admin API as legacy. These tools use it because Captain catalog v1 supports URL-only requests and cannot represent a GraphQL POST body.

## Permissions and data

These tools read protected customer and order data. Only enable them when that data is necessary for the assistant's support workflow. The access token should not include write scopes.

## References

- [Shopify API authentication](https://shopify.dev/docs/api/usage/authentication)
- [REST Admin API](https://shopify.dev/docs/api/admin-rest)
- [Order resource](https://shopify.dev/docs/api/admin-rest/latest/resources/order)
- [Customer resource](https://shopify.dev/docs/api/admin-rest/latest/resources/customer)
