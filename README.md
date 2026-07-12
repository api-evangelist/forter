# Forter (forter)

Forter is a fraud prevention and digital identity platform for online commerce. Its Decision API returns real-time trust-or-not decisions for orders, payments, account signups, and logins, drawing on a global identity graph and machine learning trained across a large network of merchants. Beyond fraud management, Forter covers chargeback recovery, abuse prevention, payment optimization, 3DS orchestration, and identity protection.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/forter/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/forter/refs/heads/main/apis.yml)

## Access Model (Honest Note)

Forter is an **enterprise, contact-sales** platform. There is **no self-service developer signup and no public price list** for the Decision API.

- API credentials - a per-account **site ID** and an **API key** - are **provisioned by Forter during onboarding**, once a contract is in place.
- Requests use **HTTP Basic authentication** (API key as the username, empty password) plus an `x-forter-siteid` header and an `api-version` header (for example `10.1`).
- Requests are sent to a **dedicated per-tenant host**: `https://{siteId}.api.forter.secure.com/{endpoint}`. The generic host `api.forter.secure.com` shown in this catalog is the documented form; the bare host does not resolve without the site-ID prefix.
- An implementation engineer may create a **customized version** of Forter's API for a given integration; the authoritative reference for a live account lives in the Forter Portal.

## Grounding Note

Endpoint **paths and HTTP methods** in this entry are grounded in Forter's public documentation at [docs.forter.com](https://docs.forter.com/). Request and response **body schemas** in the OpenAPI are **modeled** for orientation - Forter does not publish a machine-readable OpenAPI, and the real payloads are large and provisioned per integration. One path (dispute reporting) is flagged as a modeled path. See [`review.yml`](review.yml) for the confirmed-vs-modeled breakdown.

## Tags

- Fraud Detection
- Fraud Prevention
- Identity
- Trust
- Payments
- Chargebacks
- Account Protection
- E-commerce
- Risk
- Machine Learning

## Timestamps

- **Created:** 2026-07-12
- **Modified:** 2026-07-12

## APIs

### Forter Order Decision API

Send order and checkout information to receive a real-time fraud or abuse decision (approve / decline / not-reviewed), with optional payment optimization and abuse-policy recommendations. Includes the v2 and v3 order decision endpoints and the order status endpoint used to report the downstream lifecycle of an order back to Forter.

- **Human URL:** [https://docs.forter.com/reference/orders](https://docs.forter.com/reference/orders)
- **Base URL:** `https://api.forter.secure.com`

#### Tags

- Fraud Detection
- Orders
- Payments
- Risk

#### Properties

- [Documentation](https://docs.forter.com/docs/api-overview)
- [API Reference](https://docs.forter.com/reference/orders)
- [OpenAPI](openapi/forter-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/forter.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/forter.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Forter Account Protection API

Protect the account lifecycle - submit registration details at signup to get a fraud or abuse decision, and submit login attempt details to get an account takeover (ATO) decision. Built on Forter's cross-merchant identity graph.

- **Human URL:** [https://docs.forter.com/reference/signup](https://docs.forter.com/reference/signup)
- **Base URL:** `https://api.forter.secure.com`

#### Tags

- Account Protection
- Identity
- Account Takeover
- Trust

#### Properties

- [Documentation](https://docs.forter.com/docs/api-overview)
- [API Reference](https://docs.forter.com/reference/signup)
- [OpenAPI](openapi/forter-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/forter.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/forter.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Forter Chargeback and Compensation API

Report customer-initiated disputes (chargebacks) to feed Forter's decision model and enable chargeback recovery, and submit customer requests for compensation - refunds or reships, at the order or item level - to receive a fraud or abuse decision.

- **Human URL:** [https://docs.forter.com/reference/compensation-request](https://docs.forter.com/reference/compensation-request)
- **Base URL:** `https://api.forter.secure.com`

#### Tags

- Chargebacks
- Disputes
- Compensation
- Abuse Prevention

#### Properties

- [Documentation](https://docs.forter.com/docs/api-overview)
- [API Reference](https://docs.forter.com/reference/compensation-request)
- [OpenAPI](openapi/forter-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/forter.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/forter.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Forter Data Privacy API

Data-subject profile access endpoint used to support privacy and compliance workflows (for example, access requests) against the identity data Forter holds for an account.

- **Human URL:** [https://docs.forter.com/reference/profile-access](https://docs.forter.com/reference/profile-access)
- **Base URL:** `https://api.forter.secure.com`

#### Tags

- Data Privacy
- Identity
- Compliance

#### Properties

- [Documentation](https://docs.forter.com/docs/api-overview)
- [API Reference](https://docs.forter.com/reference/profile-access)
- [OpenAPI](openapi/forter-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/forter.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/forter.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Domain Security](security/forter-domain-security.yml)
- [Authentication](authentication/forter-authentication.yml)
- [LinkedIn](https://www.linkedin.com/company/forter)
- [Website](https://www.forter.com/)
- [Documentation](https://docs.forter.com/)
- [Plans](plans/forter-plans-pricing.yml)
- [Rate Limits](rate-limits/forter-rate-limits.yml)
- [Fin Ops](finops/forter-finops.yml)
- [Blog](https://www.forter.com/blog/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
