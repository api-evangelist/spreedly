---
name: Authorize then capture a payment
description: Place an authorization hold against a gateway, then capture it later (or void it) using the transaction token.
api: openapi/spreedly-api-v1.json
operations: [authorize, capture-transaction, void-transaction]
auth: HTTP Basic — environment key as username, access secret as password, over HTTPS
---

# Authorize then capture a payment

Split the auth and capture for delayed fulfilment (ship-then-charge) flows.

## Steps

1. **Authorize** — `POST /gateways/{gateway_token}/authorize` (`authorize`). Pass `payment_method_token`, `amount`, `currency_code`. The response returns a `transaction_token` for a successful hold.
2. **Capture** — `POST /transactions/{transaction_token}/capture` (`capture-transaction`) using the authorization's `transaction_token`. Omit `amount` for a full capture, or pass a smaller `amount` for a partial capture (support varies by gateway).
3. **Or void** — if you will not capture, release the hold with `POST /transactions/{transaction_token}/void` (`void-transaction`).

## Rules

- Check `succeeded` and `state` on each transaction response before proceeding.
- A declined authorization carries a normalized `failure_reason` (`errors/spreedly-decline-codes.yml`); `network_advice_code` tells you whether/when to retry.
- Inspect the raw gateway conversation with `GET /transactions/{transaction_token}/transcript` (`transcript-transactions`) when debugging.
