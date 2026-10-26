# Forter (forter)

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
