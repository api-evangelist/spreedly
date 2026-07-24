---
name: Vault a card and charge it
description: Tokenize a payment method into Spreedly's PCI-compliant vault, retain it, then run a purchase against a gateway.
api: openapi/spreedly-api-v1.json
operations: [create-payment-method, retain-payment-method, purchase]
auth: HTTP Basic — environment key as username, access secret as password, over HTTPS
---

# Vault a card and charge it

Use Spreedly's universal vault to tokenize a card once, then transact against any connected gateway.

## Steps

1. **Tokenize the card** — `POST /payment_methods` (`create-payment-method`). Submit the card in a `payment_method` object (or capture it client-side with Spreedly Express/iFrame so raw PAN never touches your server). The response returns a `payment_method_token`.
2. **Retain the payment method** — `PUT /payment_methods/{payment_method_token}/retain` (`retain-payment-method`). By default new payment methods are transient; retaining stores it in the vault for reuse.
3. **Charge it** — `POST /gateways/{gateway_token}/purchase` (`purchase`). Pass the `payment_method_token`, `amount`, and `currency_code`. The response `transaction` includes `succeeded`, the `transaction_token`, and, on failure, a normalized `payment_outcome_data.failure_reason`.

## Rules

- **Testing**: create a Test gateway (no credentials) and use the published test cards in `sandbox/spreedly-sandbox.yml` (e.g. Visa `4111111111111111` succeeds, `4012888888881881` declines). Test calls are metered/billed.
- **Idempotency** is gateway-specific — pass `order_data.gateway_idempotency_key` when the downstream gateway supports it (see `conventions/spreedly-conventions.yml`).
- **Errors**: 422 returns an `errors[]` array; declines surface a normalized `failure_reason` + `network_advice_code` — see `errors/spreedly-decline-codes.yml` to decide whether to retry.
