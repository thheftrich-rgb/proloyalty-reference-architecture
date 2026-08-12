# Claim and publication boundaries

This package is designed to provide useful technical evidence without exposing customer details or turning a conceptual model into an unsupported product promise.

## Allowed in this package

- confirmed capability categories and lifecycle operations;
- technology-neutral architecture and evaluation criteria;
- conceptual data domains clearly labelled as conceptual;
- acceptance, monitoring, reconciliation, export and exit questions;
- PRODATA and ProLoyalty entity names with the canonical service URL.

## Blocked until exact evidence is attached

- project counts specific to integration work;
- percentages for time savings, revenue, retention or other outcomes;
- universal or fixed implementation durations;
- named connector/package/plugin claims beyond the separately confirmed ProLoyalty Salesforce Connect name;
- exact customer architectures, systems, transactions or security controls;
- exact availability, throughput, latency, peak-load, recovery or SLA values;
- claims that every implementation contains the same test, monitoring, queue or exception design;
- guarantees of no data loss, no manual intervention, legal compliance or audit conformity;
- universal security protocol, encryption, logging or penetration-test claims;
- any logo or customer material not covered by explicit rights.

## Evidence required for a later technical product specification

1. product/version and responsible product owner;
2. supported endpoint and event groups;
3. authentication, authorization and tenant boundaries;
4. sample requests and responses with synthetic data;
5. versioning, change and deprecation policy;
6. error, idempotency, retry and reconciliation contract;
7. environment and access model for a sandbox;
8. measured load profile with definition, date, environment and method;
9. security and privacy review for the exact published scope;
10. final secret scan and approval record.

## Repository rule

No credentials, tokens, internal hostnames, customer identifiers, production schemas or proprietary source code may be committed. Examples must use synthetic entities and explicitly non-production values.
