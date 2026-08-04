# Vantage (vantage-sh)

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

Vantage is a cloud cost management and FinOps platform that gives engineering and finance teams visibility into and control over cloud spend across AWS, Azure, GCP, Kubernetes, Datadog, Snowflake, MongoDB, and other providers. Its public REST API (base `https://api.vantage.sh/v2`) exposes Costs and Cost Reports, Resources, Recommendations, Budgets, Cost and Anomaly Alerts, Segments, Dashboards, Financial Commitments, and more, so teams can query normalized cost data, automate cost reporting, and wire cloud optimization into their own tooling. Vantage publishes a full OpenAPI 3.0.1 specification and authenticates with OAuth2 (client-credentials bearer tokens) scoped for read and write.

**Access model:** Vantage the platform is commercial hosted SaaS - not open source. A free **Starter** tier covers small cloud footprints (up to $2,500 tracked monthly spend); paid **Pro** and **Business** tiers scale tracked spend, users, and retention; **Enterprise** is custom. Optimization automation (**Autopilot**) is billed separately at 5% of the savings it generates. The public REST API is available across tiers with no separate per-call fee. Vantage does open-source its API client libraries (`vantage-python`, `vantage-js`) and a Terraform provider, and publishes the API contract openly at `https://api.vantage.sh/v2/oas_v3.json`.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/vantage-sh/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/vantage-sh/refs/heads/main/apis.yml)

## Tags

- Cloud Cost
- FinOps
- Cost Management
- Cloud Optimization
- Cost Visibility
- Cloud Spend
- Multi-Cloud

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## Authentication

Vantage uses an OAuth2 client-credentials bearer token. Generate or copy a token from the Vantage console under Account / Profile (`console.vantage.sh/account/profile`) and pass it as `Authorization: Bearer YOUR_API_TOKEN`. Tokens carry `read` and/or `write` scopes. See [authentication/vantage-sh-authentication.yml](authentication/vantage-sh-authentication.yml).

## APIs

### Vantage Costs API

Query normalized cloud cost data across providers. Retrieve costs by cost report or VQL filter, grouped and date-binned, with credits and refunds settings - the core surface for the "cloud cost" use case. Base endpoint `GET /costs` plus data-export support at `POST /costs/data_exports`.

- **Human URL:** [https://docs.vantage.sh/api](https://docs.vantage.sh/api)
- **Base URL:** `https://api.vantage.sh/v2`

#### Tags

- Cloud Cost
- Costs
- Cost Reporting

#### Properties

- [Documentation](https://docs.vantage.sh/api)
- [API Reference](https://vantage.readme.io/reference/general)
- [OpenAPI](openapi/vantage-sh-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/vantage-sh.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vantage-sh.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Vantage Cost Reports API

Create, list, get, update, and delete Cost Reports - saved, filtered views of cloud spend - and retrieve forecasted costs for a report. CRUD under `/cost_reports` with `GET /cost_reports/{cost_report_token}/forecasted_costs`.

- **Human URL:** [https://docs.vantage.sh/api](https://docs.vantage.sh/api)
- **Base URL:** `https://api.vantage.sh/v2`

#### Tags

- Cost Management
- Cost Reports
- Forecasting

#### Properties

- [Documentation](https://docs.vantage.sh/api)
- [API Reference](https://vantage.readme.io/reference/general)
- [OpenAPI](openapi/vantage-sh-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/vantage-sh.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vantage-sh.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Vantage Resources API

List and inspect the active cloud resources Vantage tracks across connected accounts, with per-resource cost attribution. `GET /resources` and `GET /resources/{resource_token}`, plus Resource Reports for saved resource views.

- **Human URL:** [https://docs.vantage.sh/api](https://docs.vantage.sh/api)
- **Base URL:** `https://api.vantage.sh/v2`

#### Tags

- Cloud Optimization
- Resources
- Inventory

#### Properties

- [Documentation](https://docs.vantage.sh/api)
- [Documentation](https://www.vantage.sh/blog/vantage-launches-api-resource-costs)
- [OpenAPI](openapi/vantage-sh-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/vantage-sh.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vantage-sh.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Vantage Recommendations API

Retrieve cost-optimization recommendations and the resources they apply to. `GET /recommendations`, `GET /recommendations/{recommendation_token}`, `/resources` subpaths, and recommendations by type - the programmatic feed behind cloud cost optimization.

- **Human URL:** [https://docs.vantage.sh/api](https://docs.vantage.sh/api)
- **Base URL:** `https://api.vantage.sh/v2`

#### Tags

- Cloud Optimization
- Recommendations
- Savings

#### Properties

- [Documentation](https://docs.vantage.sh/api)
- [OpenAPI](openapi/vantage-sh-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/vantage-sh.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vantage-sh.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Vantage Budgets API

Create and manage cloud spend budgets and their alerts. CRUD under `/budgets` and `/budget_alerts` so teams can codify spend limits and get notified as actual and forecasted costs approach them.

- **Human URL:** [https://docs.vantage.sh/api](https://docs.vantage.sh/api)
- **Base URL:** `https://api.vantage.sh/v2`

#### Tags

- FinOps
- Budgets
- Cost Governance

#### Properties

- [Documentation](https://docs.vantage.sh/api)
- [OpenAPI](openapi/vantage-sh-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/vantage-sh.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vantage-sh.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Vantage Cost Alerts API

Define and manage cost alerts and inspect the events they fire. CRUD under `/cost_alerts` with `GET /cost_alerts/{cost_alert_token}/events` for the triggered-alert history.

- **Human URL:** [https://docs.vantage.sh/api](https://docs.vantage.sh/api)
- **Base URL:** `https://api.vantage.sh/v2`

#### Tags

- FinOps
- Cost Alerts
- Monitoring

#### Properties

- [Documentation](https://docs.vantage.sh/api)
- [OpenAPI](openapi/vantage-sh-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/vantage-sh.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vantage-sh.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Vantage Anomaly Alerts API

Retrieve and manage cost anomaly alerts and their notification configurations. `GET`/`PUT` under `/anomaly_alerts` and CRUD under `/anomaly_notifications` for automated detection of abnormal cloud spend.

- **Human URL:** [https://docs.vantage.sh/api](https://docs.vantage.sh/api)
- **Base URL:** `https://api.vantage.sh/v2`

#### Tags

- Cost Management
- Anomaly Detection
- Alerts

#### Properties

- [Documentation](https://docs.vantage.sh/api)
- [OpenAPI](openapi/vantage-sh-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/vantage-sh.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vantage-sh.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Vantage Segments API

Create and manage Segments - allocation groupings that slice cloud cost by team, product, or cost center. CRUD under `/segments`, the backbone of cost allocation and showback/chargeback in Vantage.

- **Human URL:** [https://docs.vantage.sh/api](https://docs.vantage.sh/api)
- **Base URL:** `https://api.vantage.sh/v2`

#### Tags

- FinOps
- Segments
- Cost Allocation

#### Properties

- [Documentation](https://docs.vantage.sh/api)
- [OpenAPI](openapi/vantage-sh-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/vantage-sh.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vantage-sh.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Vantage Financial Commitments API

Track Reserved Instances, Savings Plans, and Committed Use Discounts. `GET /financial_commitments` and CRUD under `/financial_commitment_reports` for commitment coverage and utilization reporting.

- **Human URL:** [https://docs.vantage.sh/api](https://docs.vantage.sh/api)
- **Base URL:** `https://api.vantage.sh/v2`

#### Tags

- Cloud Cost
- Commitments
- Reserved Instances

#### Properties

- [Documentation](https://docs.vantage.sh/api)
- [OpenAPI](openapi/vantage-sh-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/vantage-sh.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vantage-sh.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Vantage Dashboards API

Assemble Cost Reports and other widgets into shareable dashboards. CRUD under `/dashboards`, plus Folders and Saved Filters for organizing cost visibility across the organization.

- **Human URL:** [https://docs.vantage.sh/api](https://docs.vantage.sh/api)
- **Base URL:** `https://api.vantage.sh/v2`

#### Tags

- Cost Visibility
- Dashboards
- Reporting

#### Properties

- [Documentation](https://docs.vantage.sh/api)
- [OpenAPI](openapi/vantage-sh-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/vantage-sh.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/vantage-sh.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Domain Security](security/vantage-sh-domain-security.yml)
- [Authentication](authentication/vantage-sh-authentication.yml)
- [GitHub Organization](https://github.com/vantage-sh)
- [LinkedIn](https://www.linkedin.com/company/vantage-sh)
- [Website](https://www.vantage.sh)
- [Documentation](https://docs.vantage.sh/api)
- [Plans](plans/vantage-sh-plans-pricing.yml)
- [Rate Limits](rate-limits/vantage-sh-rate-limits.yml)
- [Fin Ops](finops/vantage-sh-finops.yml)
- [Blog](https://www.vantage.sh/blog)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
