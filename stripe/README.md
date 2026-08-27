# Stripe Support Tools

Read-only Stripe tools for retrieving common support records by their Stripe IDs.

## Included tools

- **Get Stripe Customer** — retrieves customer identity, contact, balance, currency, and delinquency information.
- **Get Stripe Payment** — retrieves a PaymentIntent's amount, currency, status, customer, and description without returning its client secret.
- **Get Stripe Subscription** — retrieves subscription status, customer, currency, cancellation, and trial information.

## Requirements

- A Stripe secret or restricted API key.
- Read access to Customers, PaymentIntents, and Subscriptions.

Prefer a restricted key granting only the read permissions needed by these tools. Test-mode keys work with test-mode objects; live-mode keys access live data.

## Setup

1. Create a restricted Stripe API key with the required read permissions.
2. Import `toolset.yml` into Captain.
3. Enter the API key when prompted.
4. Review and enable the imported tools.

The tools accept standard Stripe object IDs such as `cus_...`, `pi_...`, and `sub_...`.

## References

- [Stripe API authentication](https://docs.stripe.com/api/authentication)
- [Retrieve a customer](https://docs.stripe.com/api/customers/retrieve)
- [Retrieve a PaymentIntent](https://docs.stripe.com/api/payment_intents/retrieve)
- [Retrieve a subscription](https://docs.stripe.com/api/subscriptions/retrieve)
