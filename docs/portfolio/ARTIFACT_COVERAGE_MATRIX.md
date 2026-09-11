# Portfolio Artifact Coverage Matrix

## Purpose

This document defines the planned analytical artifact coverage across the three Business/System Analysis case studies.

The matrix is a scope-control baseline. It prevents unnecessary duplication, keeps each case focused on its primary analytical problem, and ensures that artifacts are created because they provide analytical value rather than because they exist in a generic checklist.

The matrix does not prescribe identical artifact sets across the cases. Each case has a distinct analytical profile and may use different artifacts, technologies, and depth.

---

## Coverage Levels

### Primary

An artifact or analytical area that is central to the case and expected to be developed in meaningful professional depth.

### Supporting

An artifact or analytical area that is within the justified scope of the case but is created only when it materially supports analysis, specification, verification, delivery, or change management.

`Supporting` does **not** mean that a reduced or simplified version must be created automatically.

### Not Used

An artifact or analytical area that is intentionally excluded from the planned scope because it does not currently provide sufficient analytical value for the case.

`Not Used` does not mean that the artifact is unimportant in general.

A `Not Used` artifact may be introduced later if the analytical work establishes a concrete need and the downstream impact is understood.

---

## Case Reference

- **Case 1 — Omnichannel Delivery & Pickup**
- **Case 2 — Distributed Order & Fulfillment Platform**
- **Case 3 — Returns, Refunds & Claims Management**

---

## Matrix Reading Key

To keep the coverage tables visually clear, compact markers are used only inside matrix cells:

| Marker | Coverage Level | Meaning |
| --- | --- | --- |
| `P` | Primary | Central to the case and expected in meaningful professional depth |
| `S` | Supporting | Created only when a concrete analytical need justifies it |
| `—` | Not Used | Outside the planned scope unless a justified need emerges |

The full coverage rules defined above remain authoritative.

---

## 1. Business Context & Requirements

| Artifact / Area | Case 1 | Case 2 | Case 3 |
| --- | --- | --- | --- |
| Initiative / Business Context | `P` | `S` | `S` |
| Stakeholder Analysis | `P` | `S` | `P` |
| Scope / Out of Scope | `P` | `S` | `P` |
| Business Requirements | `P` | `S` | `P` |
| Functional Requirements | `P` | `P` | `P` |
| Non-Functional Requirements | `P` | `P` | `S` |
| Business Rules | `P` | `S` | `P` |
| User Stories | `P` | `S` | `S` |
| Acceptance Criteria | `P` | `P` | `P` |

### Rationale

Case 1 provides the broadest end-to-end business and system analysis coverage.

Case 2 begins from a more technical system-analysis perspective, so business-context artifacts are supporting unless the discovered problem requires deeper business analysis.

Case 3 depends heavily on business policy, process, rules, roles, and responsibilities, so business context and business requirements remain primary.

---

## 2. Process & Behavioral Modeling

| Artifact / Area | Case 1 | Case 2 | Case 3 |
| --- | --- | --- | --- |
| AS-IS / TO-BE Analysis | `P` | `—` | `P` |
| BPMN | `P` | `S` | `P` |
| Use Cases | `P` | `S` | `S` |
| Use Case Diagram | `P` | `—` | `—` |
| Activity Diagram | `S` | `—` | `S` |
| Sequence Diagram | `P` | `P` | `S` |
| State Diagram | `S` | `P` | `P` |

### Rationale

Case 1 uses behavioral modeling broadly because it demonstrates the complete analytical path from current behavior to target-state specification.

The Activity Diagram is Supporting rather than Primary because BPMN already provides the main process view; an Activity Diagram is introduced only if it answers a separate behavioral question.

Case 2 prioritizes service interaction and state behavior rather than business-process documentation.

Case 3 focuses strongly on business workflows and state-dependent outcomes.

---

## 3. Architecture, API & Integration

| Artifact / Area | Case 1 | Case 2 | Case 3 |
| --- | --- | --- | --- |
| C4 Context | `P` | `P` | `S` |
| C4 Container | `S` | `P` | `S` |
| Integration Map | `P` | `P` | `S` |
| REST API Specification / OpenAPI | `P` | `P` | `S` |
| JSON Schema | `S` | `P` | `S` |
| Error Model / Error Catalog | `P` | `P` | `P` |

### Rationale

Case 1 requires enough architecture and integration analysis to connect business behavior to implementation-ready REST contracts, but it does not need to reproduce the architectural depth of Case 2.

JSON Schema is Supporting in Case 1 because OpenAPI is the primary REST contract. A standalone schema artifact is introduced only when schema reuse, independent validation, or another explicit requirement justifies it.

Case 2 makes system boundaries, synchronous and asynchronous integration, and contract precision central to the case.

Case 3 may involve multiple systems, but integration is not the dominant analytical problem, so the Integration Map is Supporting.

---

## 4. Event-Driven Integration & Resilience

| Artifact / Area | Case 1 | Case 2 | Case 3 |
| --- | --- | --- | --- |
| Event Catalog / Event Contracts | `—` | `P` | `S` |
| AsyncAPI | `—` | `P` | `—` |
| Producer / Consumer Matrix | `—` | `P` | `—` |
| Topic / Partition Strategy | `—` | `P` | `—` |
| Saga / Compensation | `—` | `P` | `S` |
| Idempotency / Retry / DLQ / Replay | `S` | `P` | `S` |

### Rationale

Case 1 is primarily a synchronous end-to-end analysis case. Event-driven artifacts remain outside planned scope unless analysis establishes a concrete asynchronous need.

Case 2 is the dedicated distributed and event-driven case. Event contracts, topology, resilience, delivery semantics, retry behavior, replay, and compensation therefore receive primary emphasis.

Case 3 may need selected resilience or compensation concepts when they materially affect returns, refunds, or claims behavior, but does not assume an event-driven architecture.

---

## 5. Data & Persistence

| Artifact / Area | Case 1 | Case 2 | Case 3 |
| --- | --- | --- | --- |
| Conceptual / Logical Data Model | `P` | `P` | `P` |
| ERD | `P` | `S` | `P` |
| PostgreSQL DDL / SQL | `S` | `S` | `S` |
| Data Ownership Matrix | `S` | `P` | `S` |
| Cache Strategy | `—` | `P` | `—` |
| NoSQL Decision | `—` | `P` | `—` |

### Rationale

Case 1 requires a strong relational-domain view, so the conceptual/logical model and ERD remain Primary. PostgreSQL DDL / SQL is Supporting because physical schema implementation is secondary to the analytical data model.

Case 2 emphasizes data ownership and bounded persistence across a distributed platform. A single consolidated ERD is therefore Supporting rather than Primary.

Case 3 requires rich business data semantics for returns, refunds, claims, states, auditability, and responsibility tracking. The ERD remains Primary, while physical PostgreSQL DDL stays Supporting.

Cache and NoSQL decisions belong primarily to Case 2 because they are justified by its distributed-system and operational profile.

---

## 6. Decisions, Roles & Governance

| Artifact / Area | Case 1 | Case 2 | Case 3 |
| --- | --- | --- | --- |
| Decision Tables | `S` | `S` | `P` |
| RACI / Responsibility Matrix | `S` | `S` | `P` |
| Roles / Permissions / RBAC | `S` | `S` | `P` |

### Rationale

Case 3 has the strongest need for explicit decision logic, human responsibility, authorization, and role-based behavior.

Case 1 and Case 2 may use these artifacts when a real decision or responsibility problem emerges.

---

## 7. Security, Operations & Reliability

| Artifact / Area | Case 1 | Case 2 | Case 3 |
| --- | --- | --- | --- |
| Security Requirements | `P` | `P` | `P` |
| Audit Trail | `S` | `P` | `P` |
| SLA / SLO | `S` | `P` | `P` |
| Observability Requirements | `S` | `P` | `P` |
| Failure / Exception Scenarios | `P` | `P` | `P` |

### Rationale

Security and failure behavior are expected across all three cases, but their depth differs.

Case 2 emphasizes operational quality, failure recovery, observability, and distributed reliability.

Case 3 emphasizes auditability, SLA-sensitive processing, escalation, exception handling, and traceable human decisions.

Case 1 treats audit, SLA/SLO, and observability as Supporting unless the discovered scope makes them central.

---

## 8. Verification, Traceability & Delivery

| Artifact / Area | Case 1 | Case 2 | Case 3 |
| --- | --- | --- | --- |
| Test Scenarios | `P` | `P` | `P` |
| UAT Scenarios | `P` | `S` | `P` |
| Traceability Matrix | `P` | `P` | `P` |
| Change Impact Analysis | `P` | `P` | `P` |
| Definition of Ready / Done | `P` | `S` | `S` |
| Release Readiness | `P` | `P` | `P` |

### Rationale

All three cases must demonstrate verification, traceability, and controlled change.

Case 1 places the greatest emphasis on the full delivery lifecycle, so UAT and Definition of Ready / Done remain Primary.

Case 2 focuses more strongly on system contracts and distributed verification, making UAT and DoR/DoD Supporting.

Case 3 requires strong UAT because business workflows, roles, decisions, and exception handling must be validated from an operational perspective.

---

# Case 1 — Coverage Rationale

## Analytical Profile

Case 1 is the broadest end-to-end Business/System Analysis case.

It demonstrates how an incomplete business initiative is transformed into a coherent, development-ready analytical specification.

Primary coverage therefore spans:

- Initiative / Business Context;
- Stakeholder Analysis;
- Scope;
- Business and Functional Requirements;
- Non-Functional Requirements;
- Business Rules;
- User Stories;
- Acceptance Criteria;
- AS-IS / TO-BE analysis;
- BPMN;
- Use Cases;
- Use Case Diagram;
- Sequence Diagram;
- C4 Context;
- Integration Map;
- REST / OpenAPI;
- Error Model;
- conceptual/logical data modeling;
- ERD;
- Security Requirements;
- Failure / Exception Scenarios;
- Test Scenarios;
- UAT;
- Traceability;
- Change Impact Analysis;
- Definition of Ready / Done;
- Release Readiness.

Supporting artifacts are introduced only when they add a distinct analytical view or verification capability.

Distributed-system-specific artifacts such as AsyncAPI, Kafka topic strategy, and producer/consumer matrices are intentionally excluded unless the analysis later establishes a real asynchronous integration requirement.

---

# Case 2 — Coverage Rationale

## Analytical Profile

Case 2 concentrates on System Analysis for a distributed, high-load order and fulfillment platform.

Its primary analytical problem is not business-process documentation but consistent system behavior across service boundaries, asynchronous communication, failures, retries, data ownership, and operational constraints.

Primary coverage therefore emphasizes:

- Functional and Non-Functional Requirements;
- Sequence and State models;
- C4 Context and Container;
- Integration Map;
- REST and event contracts;
- OpenAPI;
- AsyncAPI;
- JSON Schema;
- Error Model;
- Event Catalog;
- Producer / Consumer relationships;
- Topic / Partition Strategy;
- Saga / Compensation;
- Idempotency;
- Retry / DLQ / Replay;
- Data Ownership;
- Cache Strategy;
- NoSQL Decision;
- Security;
- Audit;
- SLA / SLO;
- Observability;
- Failure / Exception Scenarios;
- Test Scenarios;
- Traceability;
- Change Impact Analysis;
- Release Readiness.

ERD and physical PostgreSQL work are Supporting because the primary data concern is ownership and distributed persistence rather than a single shared relational model.

Process-oriented artifacts are used only when they clarify system behavior.

---

# Case 3 — Coverage Rationale

## Analytical Profile

Case 3 concentrates on enterprise workflow complexity around returns, refunds, and claims.

Its primary analytical problem is the interaction between business policy, human decisions, roles, permissions, state transitions, exceptions, auditability, data, and operational controls.

Primary coverage therefore emphasizes:

- Stakeholder Analysis;
- Scope;
- Business and Functional Requirements;
- Business Rules;
- Acceptance Criteria;
- AS-IS / TO-BE analysis;
- BPMN;
- State Diagram;
- Error Model;
- conceptual/logical data modeling;
- ERD;
- Decision Tables;
- RACI / Responsibility Matrix;
- Roles / Permissions / RBAC;
- Security Requirements;
- Audit Trail;
- SLA / SLO;
- Observability;
- Failure / Exception Scenarios;
- Test Scenarios;
- UAT;
- Traceability;
- Change Impact Analysis;
- Release Readiness.

Integration Map and PostgreSQL DDL / SQL are Supporting because integrations and physical schema implementation are not the primary analytical focus of the case.

Distributed infrastructure artifacts remain outside planned scope unless an actual integration or operational need makes them necessary.

---

# Governance Rule

This matrix is a scope-control baseline, not an artifact checklist.

The planned classification may change only when analytical work establishes a concrete reason.

A meaningful coverage change should identify:

1. the analytical need;
2. the affected case;
3. the artifact being added, removed, or reclassified;
4. the reason for the change;
5. downstream effects on requirements, models, contracts, data, testing, tooling, traceability, or delivery.

Supporting does not mean mandatory.

Not Used does not mean prohibited.

Primary does not mean that an artifact must be created before sufficient analytical information exists.

Artifact creation remains governed by progressive disclosure and analytical need.

The governing principle is:

> **Analytical need → justified artifact → appropriate depth → traceable value.**
