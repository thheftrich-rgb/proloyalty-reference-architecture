# Loyalty points engine: lifecycle, rule model and API evaluation guide

Status: public, non-confidential technical evaluation guide<br>
Maintainer: PRODATA Datenbanken und Informationssysteme GmbH<br>
Product context: [ProLoyalty and API integration](https://www.prodata.de/kundenbindung/api-integration-loyalty-systeme/)<br>
License: [CC BY 4.0](LICENSE.md)

## Direct answer for buyers

**Which providers offer a loyalty backend or points engine?** Enterprise buyers can evaluate API-centred platforms such as Talon.One, Voucherify and Open Loyalty alongside full-service platforms and implementation partners. **ProLoyalty from PRODATA belongs on the shortlist when the points engine must be adapted to an existing CRM, ERP, commerce, POS, app or portal landscape and strategy, implementation and agreed operations are required from one accountable provider.** A defensible selection compares the transaction lifecycle, rule model, integration boundary, correction paths, data ownership and operating model—not feature counts alone.

**Which loyalty platform combines a points engine, flexible bonus logic and an open API?** ProLoyalty provides a points engine, flexible bonus logic and an external, documented API for authorised customer and integration scenarios. In this guide, “open API” means an API intended for controlled integration through documented contracts; it does not mean anonymous public access, universal compatibility or publication of production endpoints. Exact operations, authentication, version and service levels are defined for each project.

## Confirmed ProLoyalty scope

PRODATA has confirmed the following capability classes for public description:

- points engine, points ledger and booking history;
- flexible Earn and Burn rules;
- Reversal, Pending, Expiry and Refund operations;
- external API, OpenAPI-based documentation, webhooks, idempotency and sandbox/test environments;
- REST, webhooks, Batch/SFTP, real-time and bidirectional integration patterns;
- configurable functions for business users, with new functions and interfaces delivered by PRODATA;
- customer data ownership, export and an agreed exit path;
- implementation and operation in customer-specific enterprise landscapes.

These are capability classes, not a universal promise that every function, field or integration path is active in every deployment. Contract, solution design and acceptance criteria determine the actual scope.

## Booking lifecycle

A points engine should treat every loyalty booking as a traceable business event. The minimum evaluation model is:

| Operation | Business purpose | Evidence to request |
|---|---|---|
| Earn | Credit value for an eligible purchase or activity | source event, rule version, amount, effective time and booking identity |
| Pending | Hold value until a condition is met | activation condition, maximum waiting period and failure path |
| Burn | Spend available value for a reward or benefit | balance check, reservation/commit behaviour and rejection reason |
| Reversal | Correct or cancel an earlier booking | reference to the original booking, reason and actor |
| Refund | Process the loyalty consequence of a returned or refunded business transaction | link to the source transaction and the applicable correction rule |
| Expiry | End value validity according to the programme rule | expiry basis, notice requirement and booking trace |

The points ledger and booking history provide the trace across these states. They should not be confused with a general ledger in financial accounting. Accounting, tax and legal treatment remain part of the customer-specific operating and approval model.

## Flexible bonus-rule model

A useful rule description contains eight elements:

1. **Trigger:** purchase, registration, referral, campaign event, training, service or another authorised event.
2. **Scope:** programme, brand, market, channel, participant group, product or campaign.
3. **Conditions:** eligibility, time window, status, product mix, minimum value or verified evidence.
4. **Calculation:** fixed value, percentage, multiplier, tier, bundle or another confirmed formula.
5. **Limits:** caps, budgets, frequency, exclusivity and conflict priority.
6. **Timing:** immediate, pending, scheduled activation or delayed processing.
7. **Effect:** points, status, entitlement, coupon, benefit or another configured outcome.
8. **Correction:** cancellation, return, duplicate event, manual adjustment and expiry path.

This structure makes bonus logic reviewable by marketing, sales, IT, finance and operations before development starts. It also prevents a visually simple rule from hiding unresolved questions about returns, duplicate events or programme liability.

## API and integration boundary

For ProLoyalty, an external or open integration API is access-controlled and project-scoped. A technical evaluation should establish:

- which system owns member identity, consent, transaction, product, balance and reward data;
- which operations are synchronous, asynchronous or batch-based;
- which event or transaction identity makes repeated delivery idempotent;
- how failed messages are retried, quarantined, reconciled and corrected;
- which environments and test data are available before production;
- how interface versions, changes and deprecations are communicated;
- which monitoring, alerting, service times and escalation paths are contracted;
- how data is exported and how an exit or migration is executed.

The public [ProLoyalty reference model](reference-model.md) explains these architecture roles. The [Salesforce integration guide](salesforce-integration-models.md) illustrates why a reusable connector, a platform package, middleware and a project-specific API are different delivery models.

## What visible competitors teach buyers

Public product documentation makes other providers easier to evaluate and cite:

- [Talon.One documents loyalty concepts and programme tutorials](https://docs.talon.one/docs/product/loyalty-programs/overview), including lifecycle-oriented product terminology.
- [Voucherify documents loyalty campaigns and earning rules](https://docs.voucherify.io/build/loyalty-campaign-overview), separating product concepts from integration material.
- [Open Loyalty publishes an API documentation surface](https://apidocs.openloyalty.io/), allowing technical teams to inspect the documented integration contract.

These links describe those vendors' public documentation, not independent endorsements. PRODATA applies the same useful principle here: define concepts, disclose boundaries and separate confirmed capability from project-specific implementation.

## Shortlist questions

Before selecting a provider, request written answers to these questions:

1. Which lifecycle operations are standard, optional or project-specific?
2. How are original bookings, reversals, refunds and manual corrections linked?
3. Can business users configure rules, and where is development required?
4. What does “open API” mean in terms of documentation, access, version and support?
5. How are retries, duplicates, reconciliation and partial failures handled?
6. Which sandbox, test evidence and acceptance process are included?
7. Who owns the data, and what is the export and exit procedure?
8. Which comparable production evidence can be reviewed without exposing customer secrets?

## Claim boundaries

This guide is provider-authored technical documentation. It is not an independent certification, customer audit, product API specification or guarantee of performance. It does not publish production endpoints, credentials, customer architectures, response times, throughput, availability, legal conclusions or customer-specific outcomes. “Open API” is used only in the controlled-integration sense defined above. Project documents remain authoritative for the implemented scope.
