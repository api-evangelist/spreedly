---
name: Run a purchase through a Composer routing workflow
description: Execute a purchase against a Composer workflow (rules-based routing, failover, cascading) instead of a single named gateway.
api: openapi/spreedly-api-v1.json
operations: [composer.purchase, show-transactions]
auth: HTTP Basic — environment key as username, access secret as password, over HTTPS
---

# Run a purchase through a Composer routing workflow

Composer runs the transaction against a configured routing workflow rather than one hard-coded gateway, enabling failover and cascading across connected gateways.

## Steps

1. **Purchase via workflow** — `POST /transactions/purchase` (`composer.purchase`). Reference the configured workflow and pass `payment_method_token`, `amount`, `currency_code`. Composer selects the gateway per the workflow's routing rules.
2. **Inspect the result** — `GET /transactions/{transaction_token}` (`show-transactions`) to see which gateway executed, the `state`, and normalized outcome data. (`composer.authorize` and `composer.verify` are the auth/verify siblings.)

## Rules

- The workflow is defined in the Spreedly app; the API only invokes it — see the Workflow / Routing-rules user guides.
- On a decline, Composer may cascade to the next gateway automatically; the final `failure_reason` reflects the last attempt.
- Idempotency remains gateway-specific (`conventions/spreedly-conventions.yml`).
