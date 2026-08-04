# Spreedly (spreedly)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
