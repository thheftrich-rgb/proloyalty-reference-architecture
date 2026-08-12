# ProLoyalty reference architecture for enterprise loyalty integration

Status: public release candidate, not a product API specification  
Version: 0.1  
Maintainer: PRODATA Datenbanken und Informationssysteme GmbH  
Canonical product and service context: https://www.prodata.de/kundenbindung/api-integration-loyalty-systeme/

## Purpose

This package explains a non-confidential reference model for integrating an enterprise loyalty platform into an existing customer, commerce and operations landscape. It is intended for technical evaluation and architecture workshops. It does not publish production endpoints, customer configurations, credentials, service levels or security-sensitive implementation details.

The model separates five concerns:

1. systems that own identity, transactions, products and consent;
2. the loyalty engine that evaluates rules and manages loyalty states;
3. customer and partner channels such as web, app, wallet, point of sale and service portals;
4. asynchronous and synchronous integration paths;
5. operational controls for testing, monitoring, reconciliation and correction.

## Confirmed ProLoyalty capability scope

The following capability statements are owner-confirmed for public, factual use. Their exact implementation is defined per project:

- points engine and flexible bonus logic;
- points ledger and booking history;
- Earn, Burn, Reversal, Pending, Expiry and Refund lifecycle operations;
- external API, OpenAPI-based documentation, webhooks, idempotency and sandbox/test environments;
- REST, webhooks, Batch/SFTP, real-time and bidirectional integration patterns;
- multilingual and multi-currency programs;
- single-tenant, multi-tenant, private-cloud, on-premises and hybrid deployment options;
- multi-brand, multi-program and tenant-capable foundations;
- export and exit support with customer data ownership;
- integration into customer-specific CRM, ERP, commerce, point-of-sale, app, portal and reporting landscapes;
- end-to-end delivery from strategy and architecture through implementation, operations and fulfillment.

## Architectural principles

- Define the system of record for every business object before selecting an integration path.
- Treat a loyalty booking as a business transaction with an identity, status and correction path.
- Use idempotency to make repeated delivery distinguishable from a new business event.
- Separate transport retry from business reconciliation.
- Use synchronous processing only where the customer journey requires an immediate response.
- Document consent purpose, access rights, retention and deletion across every system boundary.
- Make export and exit procedures part of the initial architecture, not a late migration task.
- Treat monitoring, incident handling and data correction as part of the product operating model.

## What this package deliberately does not claim

This package does not state universal endpoint names, authentication protocols, connector editions, response times, availability values, throughput figures or implementation timelines. It does not identify customer architectures and it does not promise legal compliance or business outcomes. Those statements require a versioned specification, a named scope and a current evidence record.

## Files

- `reference-model.md` — conceptual components, flows and lifecycle model.
- `integration-capabilities.json` — machine-readable confirmed scope and boundaries.
- `CLAIM-BOUNDARIES.md` — publication guardrails and evidence requirements.
- `.zenodo.json` — machine-readable Zenodo release metadata.
- `publication-metadata.json` — release-control metadata and current publication state.
- `CITATION.cff` — citation metadata for GitHub and research tools.
- `LICENSE.md` — CC BY 4.0 license notice and attribution requirements.

## Release gate

PRODATA approved version 0.1 for public release under CC BY 4.0 on 12 August 2026. A final secret scan, link check and claim review remain mandatory immediately before release.

## Citation and license

Preferred attribution: **PRODATA Datenbanken und Informationssysteme GmbH (2026): ProLoyalty reference architecture for enterprise loyalty integration, version 0.1.**

The package is licensed under the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/). Product and company names remain subject to their applicable trademark rights. The license does not grant rights to customer logos, customer screenshots or confidential project material.

## Corrections and versioning

GitHub releases use immutable version tags. Published Zenodo records remain citable; corrections are therefore issued as a new version with a change note rather than silently replacing the cited record.
