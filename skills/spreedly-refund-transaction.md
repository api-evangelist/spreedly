---
name: Refund or credit a settled transaction
description: Return funds to a cardholder by crediting a captured transaction, or issue a general (unreferenced) credit.
api: openapi/spreedly-api-v1.json
operations: [credit-transaction, general-credit-transaction, show-transactions]
auth: HTTP Basic — environment key as username, access secret as password, over HTTPS
---

# Refund or credit a settled transaction

## Steps

1. **Referenced refund** — `POST /transactions/{transaction_token}/credit` (`credit-transaction`) against the original capture/purchase `transaction_token`. Omit `amount` for a full refund or pass a smaller `amount` for a partial refund (support varies by gateway).
2. **Unreferenced credit** — when there is no originating transaction, use `POST /gateways/{gateway_token}/general_credit` (`general-credit-transaction`) with `payment_method_token`, `amount`, `currency_code` (gateway must permit general credits).
3. **Confirm** — `GET /transactions/{transaction_token}` (`show-transactions`) to verify the credit `succeeded` and read its `state`.

## Rules

- A transaction can only be voided before settlement and refunded after — check the original transaction's `state` first.
- Declines/failures carry a normalized `failure_reason` (`errors/spreedly-decline-codes.yml`).
- Partial and multiple refunds are gateway-dependent; consult the changelog for gateway-specific support (e.g. PayPal partial capture/refund).
