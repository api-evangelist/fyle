# Fyle (fyle)

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

Fyle (now Sage Expense Management) is a spend and expense management platform known for real-time corporate card feeds that text employees for a receipt the moment a card is swiped, then auto-code the expense. The Fyle Platform APIs expose the same objects the product runs on - expenses, expense reports, advances, categories, projects, cost centers, employees, merchants, corporate cards and their transactions, files/receipts, and webhook subscriptions - as role-scoped REST resources (admin, spender, approver, common) under `https://api.fylehq.com/platform/v1`. Access is authenticated with OAuth 2.0 (refresh-token grant issuing short-lived Bearer access tokens), and list endpoints use PostgREST-style filtering with mandatory `offset`, `limit`, and `order` pagination.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/fyle/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/fyle/refs/heads/main/apis.yml)

## Tags

- Expense Management
- Spend Management
- Corporate Cards
- Fintech
- Accounting
- Receipts

## Timestamps

- **Created:** 2026-07-03
- **Modified:** 2026-07-03

## APIs

### Fyle Expenses API

List, filter, retrieve, and upsert expenses across the organization. Admins read every employee's expenses (with rich filtering and pagination); spenders create their own expenses, create an expense from a receipt, and attach receipts. Base path uses the role segment - `/admin/expenses` or `/spender/expenses`.

- **Human URL:** [https://docs.fylehq.com/docs/fyle-platform-docs/1381169eb4baa-list-expenses](https://docs.fylehq.com/docs/fyle-platform-docs/1381169eb4baa-list-expenses)
- **Base URL:** `https://api.fylehq.com/platform/v1/admin`

#### Tags

- Expenses
- Receipts
- Spend

#### Properties

- [Documentation](https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is)
- [API Reference](https://docs.fylehq.com/docs/fyle-platform-docs/1381169eb4baa-list-expenses)
- [OpenAPI](openapi/fyle-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fyle.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fyle.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fyle Reports API

Manage expense reports - the containers employees submit for approval and reimbursement. Spenders create reports, add expenses to a report, and submit them; admins bulk mark reports as paid once reimbursed.

- **Human URL:** [https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is](https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is)
- **Base URL:** `https://api.fylehq.com/platform/v1/admin`

#### Tags

- Reports
- Approvals
- Reimbursement

#### Properties

- [Documentation](https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is)
- [API Reference](https://docs.fylehq.com/docs/fyle-platform-docs/8f79171ef2cb5-spender-ap-is)
- [OpenAPI](openapi/fyle-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fyle.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fyle.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fyle Advances API

List, retrieve, and upsert advance requests - the money employees ask for ahead of spending. Exposed under `/admin/advance_requests` for programmatic reconciliation with payroll and accounting systems.

- **Human URL:** [https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is](https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is)
- **Base URL:** `https://api.fylehq.com/platform/v1/admin`

#### Tags

- Advances
- Advance Requests
- Reimbursement

#### Properties

- [Documentation](https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is)
- [OpenAPI](openapi/fyle-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fyle.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fyle.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fyle Categories API

List, upsert, and bulk-upsert expense categories, typically synced from an accounting system's chart of accounts so expenses code correctly. Available at `/admin/categories` with a bulk endpoint for large imports.

- **Human URL:** [https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is](https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is)
- **Base URL:** `https://api.fylehq.com/platform/v1/admin`

#### Tags

- Categories
- Chart of Accounts
- Coding

#### Properties

- [Documentation](https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is)
- [OpenAPI](openapi/fyle-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fyle.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fyle.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fyle Projects API

List, upsert, and bulk-upsert projects used to tag and allocate expenses to client work or internal initiatives. Served at `/admin/projects` with a bulk endpoint for syncing from external systems.

- **Human URL:** [https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is](https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is)
- **Base URL:** `https://api.fylehq.com/platform/v1/admin`

#### Tags

- Projects
- Cost Allocation
- Coding

#### Properties

- [Documentation](https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is)
- [OpenAPI](openapi/fyle-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fyle.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fyle.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fyle Cost Centers API

List, upsert, and bulk-upsert cost centers that map spend to departments, teams, or business units for reporting and accounting export. Available at `/admin/cost_centers`.

- **Human URL:** [https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is](https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is)
- **Base URL:** `https://api.fylehq.com/platform/v1/admin`

#### Tags

- Cost Centers
- Cost Allocation
- Coding

#### Properties

- [Documentation](https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is)
- [OpenAPI](openapi/fyle-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fyle.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fyle.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fyle Employees API

List, retrieve, upsert, and bulk-invite employees - typically synced from an HRMS so approval hierarchies, departments, and reimbursement details stay current. Available at `/admin/employees`.

- **Human URL:** [https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is](https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is)
- **Base URL:** `https://api.fylehq.com/platform/v1/admin`

#### Tags

- Employees
- HRMS
- Users

#### Properties

- [Documentation](https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is)
- [OpenAPI](openapi/fyle-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fyle.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fyle.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fyle Merchants API

List the merchant/vendor values available to a spender and bulk-add new merchants, keeping the merchant field consistent across expenses. Served at `/spender/merchants`.

- **Human URL:** [https://docs.fylehq.com/docs/fyle-platform-docs/8f79171ef2cb5-spender-ap-is](https://docs.fylehq.com/docs/fyle-platform-docs/8f79171ef2cb5-spender-ap-is)
- **Base URL:** `https://api.fylehq.com/platform/v1/spender`

#### Tags

- Merchants
- Vendors
- Spend

#### Properties

- [Documentation](https://docs.fylehq.com/docs/fyle-platform-docs/8f79171ef2cb5-spender-ap-is)
- [OpenAPI](openapi/fyle-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fyle.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fyle.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fyle Corporate Cards & Transactions API

List enrolled corporate cards and read the real-time card transactions that flow in from Fyle's direct card feeds, then match them to expenses. Exposed at `/admin/corporate_cards` and `/admin/corporate_card_transactions` (cards are also listable under `/spender`).

- **Human URL:** [https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is](https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is)
- **Base URL:** `https://api.fylehq.com/platform/v1/admin`

#### Tags

- Corporate Cards
- Card Transactions
- Real-Time Feeds

#### Properties

- [Documentation](https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is)
- [OpenAPI](openapi/fyle-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fyle.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fyle.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fyle Webhooks API

Register and manage webhook subscriptions and scheduled callbacks so your application receives HTTP POSTs when expenses, reports, and other objects change - Fyle's outbound integration mechanism (server-to-endpoint HTTP, not WebSocket). Managed at `/admin/subscriptions` and `/admin/scheduled_callbacks`.

- **Human URL:** [https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is](https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is)
- **Base URL:** `https://api.fylehq.com/platform/v1/admin`

#### Tags

- Webhooks
- Subscriptions
- Callbacks

#### Properties

- [Documentation](https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is)
- [OpenAPI](openapi/fyle-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fyle.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fyle.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fyle Files & Receipts API

Create file records and generate pre-signed upload/download URLs for receipts and other attachments, then bulk-generate URLs for many files at once. Available at `/admin/files` (and `/spender/files`) with a `/files/generate_urls/bulk` helper.

- **Human URL:** [https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is](https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is)
- **Base URL:** `https://api.fylehq.com/platform/v1/admin`

#### Tags

- Files
- Receipts
- Attachments

#### Properties

- [Documentation](https://docs.fylehq.com/docs/fyle-platform-docs/d72728ede9b0e-admin-ap-is)
- [OpenAPI](openapi/fyle-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/fyle.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fyle.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/fylein)
- [LinkedIn](https://www.linkedin.com/company/fyle)
- [Website](https://www.fylehq.com)
- [Documentation](https://docs.fylehq.com)
- [Plans](plans/fyle-plans-pricing.yml)
- [Rate Limits](rate-limits/fyle-rate-limits.yml)
- [Fin Ops](finops/fyle-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
