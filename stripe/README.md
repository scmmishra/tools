# Stripe Support Tools

Read-only Stripe tools for retrieving common support records by their Stripe IDs.

## Included tools

- **Get Stripe Customer** (`get_stripe_customer`) — sends a URL-only `GET` request to `/v1/customers/{customer_id}` and retrieves customer identity, contact, balance, currency, and delinquency information.
- **Get Stripe Charge** (`get_stripe_charge`) — sends a URL-only `GET` request to `/v1/charges/{charge_id}` and retrieves charge amount, currency, status, customer, payment method, and refund information. This tool retrieves a Charge rather than a PaymentIntent so the raw response does not expose a PaymentIntent client secret.
- **Get Stripe Subscription** (`get_stripe_subscription`) — sends a URL-only `GET` request to `/v1/subscriptions/{subscription_id}` and retrieves subscription status, customer, currency, cancellation, and trial information.

## Requirements

- A Stripe secret or restricted API key.
- Read access to Customers, Charges, and Subscriptions.

Prefer a restricted key granting only the read permissions needed by these tools. Test-mode keys work with test-mode objects; live-mode keys access live data.

## Setup

1. Create a restricted Stripe API key with the required read permissions.
2. Import `toolset.yml` into Captain.
3. Enter the API key when prompted.
4. Review and enable the imported tools.

The tools accept standard Stripe object IDs such as `cus_...`, `ch_...`, and `sub_...`.

## References

- [Stripe API authentication](https://docs.stripe.com/api/authentication)
- [Retrieve a customer](https://docs.stripe.com/api/customers/retrieve)
- [Retrieve a charge](https://docs.stripe.com/api/charges/retrieve)
- [Retrieve a subscription](https://docs.stripe.com/api/subscriptions/retrieve)
