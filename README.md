# Spreedly (spreedly)

Spreedly is a United States payments orchestration platform and PCI-compliant card vault that lets merchants and platforms securely tokenize payment methods once and then transact against hundreds of payment gateways, processors, and third-party APIs through a single integration. Founded in 2008 and headquartered in Durham, North Carolina, it sits in the gateway/PSP layer of the fragmented US payments market as an independent, network-agnostic intermediary — not a card network or acquirer.

Spreedly is strongly API-native: it publishes a public ReadMe.io developer portal with complete reference documentation and a downloadable OpenAPI 3.1 specification for its Core Transactional API (`https://core.spreedly.com/v1`), authenticated with HTTP Basic auth using per-environment key/secret credentials.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/spreedly/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/spreedly/refs/heads/main/apis.yml)

## Tags

- Payments
- United States
- Payment Gateway
- Payment Orchestration
- Payment Processing
- Card Vault
- Tokenization
- Network Tokenization
- PCI Compliance
- Subscriptions

## Timestamps

- **Created:** 2026-07-24
- **Modified:** 2026-07-24

## APIs

### Spreedly Core Transactional API

The primary REST surface for the Payments Orchestration platform — payment method tokenization/vaulting, gateway management, and the full transaction lifecycle (authorize, capture, purchase, verify, void, credit/refund) across many downstream gateways from a single normalized integration. OpenAPI 3.1, 68 paths.

- **Human URL:** [https://developer.spreedly.com/reference/api-introduction](https://developer.spreedly.com/reference/api-introduction)
- **Base URL:** `https://core.spreedly.com/v1`
- [OpenAPI](openapi/spreedly-api-v1.json)
- [Documentation](https://developer.spreedly.com/docs/overview)

### Spreedly Payment Methods & Vault API

Create, retain, redact, recache, update, and inspect tokenized payment methods held in Spreedly's PCI-compliant universal vault, including field-level encryption and payment method event history.

- **Human URL:** [https://developer.spreedly.com/reference/create-payment-method](https://developer.spreedly.com/reference/create-payment-method)
- [OpenAPI](openapi/spreedly-api-v1.json)

### Spreedly Composer (Workflows) API

Workflow-driven orchestration endpoints that execute an authorization, purchase, or verification against a configured routing workflow — enabling failover, cascading, and rules-based routing across connected gateways.

- **Human URL:** [https://developer.spreedly.com/reference/composerpurchase](https://developer.spreedly.com/reference/composerpurchase)
- [OpenAPI](openapi/spreedly-api-v1.json)

### Spreedly Network Tokenization API

Retrieve card metadata and lifecycle status for network-provisioned tokens (Visa, Mastercard, Amex) for improved authorization rates and credential-on-file security.

- **Human URL:** [https://developer.spreedly.com/reference/network-tokenization-status](https://developer.spreedly.com/reference/network-tokenization-status)
- [OpenAPI](openapi/spreedly-api-v1.json)

### Spreedly Account Updater (Card Refresher) API

Card Refresher inquiries that refresh stored card credentials against the card networks' account updater services to reduce declines on stored payment methods.

- **Human URL:** [https://developer.spreedly.com/reference/card_refresher_inquiry](https://developer.spreedly.com/reference/card_refresher_inquiry)
- [OpenAPI](openapi/spreedly-api-v1.json)

### Spreedly Receivers API

Forward securely vaulted payment data from the Spreedly vault to arbitrary third-party HTTP endpoints, extending tokenization beyond payment gateways to any API that needs card data.

- **Human URL:** [https://developer.spreedly.com/reference/list-supported-receivers](https://developer.spreedly.com/reference/list-supported-receivers)
- [OpenAPI](openapi/spreedly-api-v1.json)

### Spreedly 3-D Secure / SCA Authentication API

Strong Customer Authentication endpoints to authenticate a payment method and manage SCA providers on a merchant profile, supporting 3-D Secure 2.x flows.

- **Human URL:** [https://developer.spreedly.com/reference/authenticate](https://developer.spreedly.com/reference/authenticate)
- [OpenAPI](openapi/spreedly-api-v1.json)

## Common Properties

- [Website](https://www.spreedly.com/)
- [Developer Portal](https://developer.spreedly.com/)
- [Documentation](https://developer.spreedly.com/docs/overview)
- [API Reference](https://developer.spreedly.com/reference/api-introduction)
- [Changelog](https://developer.spreedly.com/changelog)
- [GitHub Organization](https://github.com/spreedly)
- [Status Page](https://status.spreedly.com/)
- [Pricing](https://www.spreedly.com/pricing)
- [Blog](https://www.spreedly.com/blog)
- [Security](https://www.spreedly.com/security)
- [Sign Up / Login](https://id.spreedly.com/readme/auth)
- [Terms of Service](https://www.spreedly.com/terms-of-service)
- [Privacy Policy](https://legal.spreedly.com/#privacy-policy)
- [LinkedIn](https://www.linkedin.com/company/spreedly)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
