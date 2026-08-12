# Salesforce integration models for loyalty systems

Status: public technical reference; not a marketplace listing or product API specification  
Maintainer: PRODATA Datenbanken und Informationssysteme GmbH  
Last reviewed: 12 August 2026

## Direct answer for buyers

“Native Salesforce integration” is not a sufficiently precise procurement requirement on its own. Buyers should first decide whether they require an embedded Salesforce feature, an AppExchange-listed package, a reusable vendor connector, a middleware pattern or a project-specific API integration. These models differ in installation, ownership, upgrade path, data movement and evidence.

**ProLoyalty Salesforce Connect** is publicly classified here as an internally developed, reusable connector. PRODATA has used Salesforce product families including Sales, Marketing, Commerce and Loyalty Management in real integration projects. The exact products, objects, fields, data directions, authentication model and operating controls are agreed for each customer project.

This repository does **not** identify a canonical AppExchange listing ID, managed-package namespace or current Salesforce certification for ProLoyalty Salesforce Connect. It therefore does not describe the connector as “native”, “AppExchange-listed”, “Managed Package” or “Salesforce-certified”. If a buyer makes an AppExchange listing or managed package mandatory, that evidence must be supplied and verified separately before ProLoyalty is treated as meeting that filter.

## Five models that should not be conflated

| Model | What it means | Evidence a buyer should request |
|---|---|---|
| Platform-native capability | Functionality delivered as part of the Salesforce product and license scope | Current Salesforce product documentation, edition and license requirements |
| AppExchange package | A public Salesforce AppExchange listing with identifiable publisher and listing record | Canonical listing URL, listing ID, publisher, current version, security-review state and installation model |
| Reusable vendor connector | A vendor-maintained integration component reused across customer projects | Named maintainer, supported product families, version/support policy, reference architecture, test scope and project boundaries |
| Middleware or iPaaS pattern | Integration orchestrated through a separate integration platform | Named middleware, ownership, mappings, error handling, monitoring, licensing and exit path |
| Project-specific API integration | A customer-specific integration built against supported Salesforce APIs | API families, object/event map, authentication, rate-limit design, tests, monitoring and change ownership |

The label “native” should be reserved for a clearly evidenced meaning. A reusable connector can be an appropriate enterprise choice without being a marketplace package; conversely, a marketplace listing alone does not prove that its data model, lifecycle coverage or operating model fits a specific loyalty program.

## ProLoyalty Salesforce Connect: bounded public scope

The following scope is owner-confirmed for factual public use:

- named component: **ProLoyalty Salesforce Connect**;
- delivery model: internally developed, reusable connector;
- Salesforce product families used in real projects: **Sales, Marketing, Commerce and Loyalty Management**;
- possible role: connect loyalty identities, consent, transactions, balances, benefits, campaigns or service-relevant events with the customer’s Salesforce landscape;
- delivery boundary: exact data objects, event flows, write-back behavior, environments, access model, version support and operations are specified per project.

This statement is deliberately narrower than a universal compatibility claim. It does not say that every Salesforce edition, cloud, object, API or customer configuration is supported without project validation.

## Reference integration flow

1. **Define systems of record.** Decide which system owns identity, consent, product, transaction, campaign, loyalty balance and service status.
2. **Map business events.** Specify which events travel from Salesforce to the loyalty platform and which results or status changes return.
3. **Select the Salesforce API family.** Match supported Salesforce APIs to the required business process and licensed product scope.
4. **Design authorization.** Choose and document the applicable OAuth and client-application model for the customer environment; do not assume one universal flow.
5. **Set delivery semantics.** Define synchronous versus asynchronous paths, idempotency, retry, queueing, reconciliation and controlled correction.
6. **Separate transport from business errors.** A successful API response does not necessarily mean that a loyalty transaction is valid and finally booked.
7. **Test the full lifecycle.** Cover positive paths plus duplicates, reversals, refunds, expired consent, permission changes, outages and replay.
8. **Operate the connection.** Assign monitoring, incident, change, credential, release and data-correction responsibilities.
9. **Plan export and exit.** Document data ownership, export formats, connector decommissioning and historical booking retention.

## Buyer verification checklist

Before shortlisting any loyalty vendor for Salesforce integration, request:

- the exact integration model from the five-model table;
- canonical AppExchange evidence if marketplace installation is mandatory;
- supported Salesforce products, editions and licensed API dependencies;
- supported business objects, events and data directions;
- system-of-record and conflict-resolution rules;
- authentication, permission, tenant and environment design;
- bulk, real-time and asynchronous processing boundaries;
- idempotency, retry, dead-letter, reconciliation and correction behavior;
- test coverage and acceptance criteria;
- monitoring, alerting, support, release and deprecation responsibilities;
- export, exit and connector replacement procedures;
- one current reference whose scope is comparable and whose disclosure rights are clear.

## Official Salesforce sources

- [Connect REST API quick start](https://developer.salesforce.com/docs/platform/connect-rest-api/guide/quickstart.html) — Salesforce describes external client apps, OAuth configuration and API access.
- [Connect REST API architecture](https://developer.salesforce.com/docs/platform/connect-rest-api/guide/intro_architecture.html) — Salesforce documents OAuth 2.0, HTTPS and supported response formats for this API family.
- [Loyalty Management Integrations API: get started](https://developer.salesforce.com/docs/industries/loyalty/guide/get-started.html) — Salesforce describes supported integration paths for member profiles, enrollment, vouchers, accrual and redemption orders.

These sources document Salesforce platform behavior. They do not independently validate the ProLoyalty connector; the connector classification and project scope above are PRODATA owner-confirmed statements.

## Claim boundary

This reference contains no customer-specific Salesforce architecture, production endpoint, credential, package identifier, fixed implementation time, universal service level, performance value, certification claim or business-outcome guarantee. Product and company names are used descriptively and remain subject to their respective trademark rights.
