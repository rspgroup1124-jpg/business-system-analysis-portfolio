# Portfolio Overview

## Purpose

This document defines the portfolio-level structure and analytical
positioning of the three Business/System Analysis case studies.

The cases share one operating model, delivery lifecycle, localization
policy, tooling baseline, and scope-control approach. At the same time,
each case focuses on a different analytical problem domain and uses only
the artifacts justified by its scope.

The portfolio is designed as one coherent body of professional
analytical work rather than three isolated sets of documents.

## Portfolio Structure

The portfolio contains three complementary case studies:

1.  **Omnichannel Delivery & Pickup**
2.  **Distributed Order & Fulfillment Platform**
3.  **Returns, Refunds & Claims Management**

Together they cover business analysis, system analysis, process and
behavioral modeling, integration contracts, data, distributed systems,
operational concerns, verification, traceability, and controlled change.

The cases intentionally differ in analytical emphasis. They are not
expected to contain identical artifact sets or use the same
technologies.

## Case 1 --- Omnichannel Delivery & Pickup

### Analytical Profile

Case 1 represents a full-cycle Business/System Analysis initiative in
which an initially incomplete business problem must be transformed into
a consistent, development-ready system specification.

The case emphasizes:

-   initiative and business context;
-   stakeholder analysis;
-   scope definition;
-   discovery and domain clarification;
-   Business and Functional Requirements;
-   Business Rules;
-   User Stories and Acceptance Criteria;
-   AS-IS / TO-BE analysis;
-   BPMN and behavioral modeling;
-   Use Cases and Use Case Diagram;
-   system context and integrations;
-   REST API specification;
-   relational data modeling;
-   security and failure scenarios;
-   testability, traceability, release readiness, and change impact.

### Analytical Objective

Transform incomplete and progressively disclosed business information
into a coherent set of traceable requirements, behavioral models, system
specifications, data definitions, and verification criteria.

Case 1 establishes the broad end-to-end analytical workflow used
throughout the portfolio.

## Case 2 --- Distributed Order & Fulfillment Platform

### Analytical Profile

Case 2 focuses on System Analysis for a distributed, high-load order and
fulfillment environment with multiple services and asynchronous
communication.

The case emphasizes:

-   Functional and Non-Functional Requirements;
-   service and system boundaries;
-   C4 views;
-   synchronous and asynchronous integrations;
-   REST and event contracts;
-   OpenAPI and AsyncAPI;
-   JSON Schema;
-   Error Model;
-   Event Catalog;
-   Producer / Consumer relationships;
-   topic and partition strategy;
-   state transitions;
-   saga and compensation;
-   idempotency, retry, DLQ, and replay;
-   data ownership;
-   cache and NoSQL decisions;
-   security, auditability, SLA/SLO, and observability;
-   failure scenarios, verification, traceability, and release
    readiness.

### Analytical Objective

Specify distributed-system behavior and contracts so that independent
teams can implement and integrate services consistently while preserving
correct behavior under failures, retries, asynchronous processing, and
operational constraints.

Case 2 deepens the system and integration analysis introduced in Case 1.

## Case 3 --- Returns, Refunds & Claims Management

### Analytical Profile

Case 3 focuses on enterprise workflow analysis where outcomes depend on
business rules, roles, permissions, state transitions, exceptions, data,
auditability, and human decisions.

The case emphasizes:

-   business context and stakeholder analysis;
-   scope and Business Requirements;
-   Functional Requirements and Business Rules;
-   AS-IS / TO-BE process analysis;
-   BPMN;
-   decision tables;
-   state modeling;
-   responsibility and RACI analysis;
-   roles, permissions, and RBAC;
-   integration and error behavior;
-   relational data and DDL;
-   security and audit trail;
-   SLA/SLO and observability;
-   exception scenarios;
-   Acceptance Criteria;
-   Test and UAT Scenarios;
-   traceability and Change Impact Analysis.

### Analytical Objective

Transform a complex business process with multiple roles, decisions,
rules, states, and exceptions into an unambiguous, traceable, and
verifiable system model.

Case 3 deepens process, rule, governance, and human-workflow analysis.

## Complementary Coverage

The cases are deliberately complementary.

### Case 1 --- End-to-End Analysis

Primary emphasis:

-   discovery;
-   requirements;
-   process and behavioral analysis;
-   system specification;
-   REST integration;
-   relational data;
-   traceability;
-   delivery support.

### Case 2 --- Distributed System Analysis

Primary emphasis:

-   system boundaries;
-   microservices;
-   event-driven integration;
-   asynchronous contracts;
-   resilience;
-   data ownership;
-   operational quality.

### Case 3 --- Enterprise Process and Rules

Primary emphasis:

-   complex workflows;
-   business rules;
-   decisions;
-   states;
-   roles and permissions;
-   auditability;
-   exception handling;
-   human/system interaction.

This separation prevents unnecessary duplication and allows each case to
explore its primary analytical problem in sufficient depth.

## Common Operating Model

All three cases follow the same portfolio-level working principles.

### Progressive Disclosure

Business and technical information is not assumed to be complete at the
beginning of a case.

The analyst identifies gaps, asks targeted questions, routes decisions
to the appropriate owners, and updates the analytical baseline as
accepted information becomes available.

### Explicit Decision Ownership

The System Analyst coordinates clarification but does not silently
assume ownership of business, architecture, implementation, security,
data, or operational decisions that belong to other roles.

### Controlled Persistence

The portfolio uses the following persistence model:

-   **Jira** --- delivery state;
-   **Confluence** --- evolving collaborative knowledge;
-   **Git** --- durable accepted analytical baseline.

### Traceability and Change Propagation

Accepted decisions and changes are propagated to affected requirements,
Business Rules, models, contracts, data specifications, Acceptance
Criteria, tests, backlog items, and traceability.

A change to one artifact triggers review of dependent artifacts where
applicable.

## Common Delivery Lifecycle

The cases use a shared analytical lifecycle:

1.  Initiative / Intake
2.  Discovery
3.  Domain Analysis
4.  Requirements Elicitation
5.  Process & Behavioral Analysis
6.  Solution / System Analysis
7.  Detailed Specification
8.  Refinement & Review
9.  Development Support
10. QA Support
11. Release Readiness
12. Production Feedback / Change

The lifecycle is iterative. Production feedback or an approved Change
Request may return analysis to any affected earlier stage.

## Artifact Strategy

The portfolio does not use an artifact checklist.

Artifact selection is controlled by `ARTIFACT_COVERAGE_MATRIX.md`, which
classifies artifacts for each case as:

-   **Primary** --- central to the case;
-   **Supporting** --- used when it materially supports the analysis;
-   **Not Used** --- excluded from the planned scope because it does not
    currently provide sufficient analytical value.

A `Not Used` artifact may be introduced later only when a concrete
analytical need is established and the scope impact is understood.

## Tooling Strategy

Tools are selected by analytical need rather than technology coverage.

The portfolio workstation includes tools for:

-   repository and source-controlled documentation;
-   collaboration and delivery management;
-   process and system modeling;
-   API and event specification;
-   API verification;
-   relational and non-relational data analysis;
-   messaging and cache analysis;
-   reproducible local infrastructure;
-   justified analytical automation.

A tool should produce a meaningful artifact, decision, or reproducible
verification result.

## Localization Strategy

Repository-level public and governance documents are maintained in
English.

Case-level analytical content is primarily written in natural
professional Russian.

Established professional terminology may remain in English where it
improves precision, while standard syntax and technical identifiers
remain canonical and English-based.

Localization must not create artificial mixed-language phrasing or
change analytical meaning.

## Relationship to NovaMarket Toolkit

This portfolio is an independent project.

NovaMarket Toolkit may be evaluated later as an external analytical tool
only after relevant workflows have been established manually and its use
provides concrete value.

The portfolio must not be shaped around NovaMarket Toolkit capabilities,
and NovaMarket Toolkit is not the implementation target of the case
studies.

## Portfolio Outcome

The portfolio should provide evidence of a controlled professional
analytical process in which:

-   incomplete information is progressively clarified;
-   decisions have explicit owners;
-   requirements are traceable to business intent;
-   models and contracts remain semantically consistent;
-   technical specifications are verifiable;
-   tools are used for concrete analytical purposes;
-   changes are assessed across affected artifacts;
-   accepted analytical states are version-controlled.

The governing principle is:

**Analytical decision + traceable requirement + verifiable contract +
clear team workflow + controlled change impact.**
