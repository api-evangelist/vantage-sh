# Vantage (vantage-sh)

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
