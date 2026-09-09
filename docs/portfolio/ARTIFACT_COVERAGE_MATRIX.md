# Portfolio Artifact Coverage Matrix

## Purpose

This document defines the planned analytical artifact coverage across
the three Business/System Analysis case studies.

The matrix is a scope-control baseline. It prevents unnecessary
duplication, keeps each case focused on its primary analytical problem,
and ensures that artifacts are created because they provide analytical
value rather than because they exist in a generic checklist.

## Coverage Levels

-   **Primary** --- central to the analytical scope of the case and
    expected to be developed in meaningful depth.
-   Supporting --- used when it materially supports the analysis,
    specification, verification, or delivery workflow.
-   Not Used --- excluded from the planned scope because it does not
    currently provide sufficient analytical value for the case.

`Not Used` does not mean that an artifact is unimportant in general. It
means that the artifact is not justified by the current scope of that
specific case.

## Case Reference

-   **Case 1** --- Omnichannel Delivery & Pickup
-   **Case 2** --- Distributed Order & Fulfillment Platform
-   **Case 3** --- Returns, Refunds & Claims Management

The shorter case labels are used in the tables below to improve
readability.

## 1. Business Context & Requirements

  -------------------------------------------------------------------------
  Artifact / Area        Case 1             Case 2             Case 3
  ---------------- ------------------ ------------------ ------------------
  Initiative /        **Primary**         Supporting         Supporting
  Business Context

  Stakeholder         **Primary**         Supporting        **Primary**
  Analysis

  Scope / Out of      **Primary**         Supporting        **Primary**
  Scope

  Business            **Primary**         Supporting        **Primary**
  Requirements

  Functional          **Primary**        **Primary**        **Primary**
  Requirements

  Non-Functional      **Primary**        **Primary**         Supporting
  Requirements

  Business Rules      **Primary**         Supporting        **Primary**

  User Stories        **Primary**         Supporting         Supporting

  Acceptance          **Primary**        **Primary**        **Primary**
  Criteria
  -------------------------------------------------------------------------

## 2. Process & Behavioral Modeling

  Artifact / Area             Case 1        Case 2        Case 3
  ------------------------ ------------- ------------- -------------
  AS-IS / TO-BE Analysis    **Primary**    Not Used     **Primary**
  BPMN                      **Primary**   Supporting    **Primary**
  Use Cases                 **Primary**   Supporting    Supporting
  Use Case Diagram          **Primary**    Not Used      Not Used
  Activity Diagram          **Primary**    Not Used     Supporting
  Sequence Diagram          **Primary**   **Primary**   Supporting
  State Diagram             Supporting    **Primary**   **Primary**

## 3. Architecture, API & Integration

  ------------------------------------------------------------------------
  Artifact / Area       Case 1             Case 2             Case 3
  --------------- ------------------ ------------------ ------------------
  C4 Context         **Primary**        **Primary**         Supporting

  C4 Container        Supporting        **Primary**         Supporting

  Integration Map    **Primary**        **Primary**        **Primary**

  REST API           **Primary**        **Primary**         Supporting
  Specification /
  OpenAPI

  JSON Schema        **Primary**        **Primary**         Supporting

  Error Model /      **Primary**        **Primary**        **Primary**
  Error Catalog
  ------------------------------------------------------------------------

## 4. Event-Driven Integration & Resilience

  -----------------------------------------------------------------------
  Artifact /           Case 1             Case 2             Case 3
  Area
  -------------- ------------------ ------------------ ------------------
  Event Catalog       Not Used         **Primary**         Supporting
  / Event
  Contracts

  AsyncAPI            Not Used         **Primary**          Not Used

  Producer /          Not Used         **Primary**          Not Used
  Consumer
  Matrix

  Topic /             Not Used         **Primary**          Not Used
  Partition
  Strategy

  Saga /              Not Used         **Primary**         Supporting
  Compensation

  Idempotency /      Supporting        **Primary**         Supporting
  Retry / DLQ /
  Replay
  -----------------------------------------------------------------------

## 5. Data & Persistence

  -----------------------------------------------------------------------
  Artifact /           Case 1             Case 2             Case 3
  Area
  -------------- ------------------ ------------------ ------------------
  Conceptual /      **Primary**        **Primary**        **Primary**
  Logical Data
  Model

  ERD               **Primary**        **Primary**        **Primary**

  PostgreSQL DDL    **Primary**         Supporting        **Primary**
  / SQL

  Data Ownership     Supporting        **Primary**         Supporting
  Matrix

  Cache Strategy      Not Used         **Primary**          Not Used

  NoSQL Decision      Not Used         **Primary**          Not Used
  -----------------------------------------------------------------------

## 6. Decisions, Roles & Governance

  Artifact / Area                   Case 1       Case 2       Case 3
  ------------------------------ ------------ ------------ -------------
  Decision Tables                 Supporting   Supporting   **Primary**
  RACI / Responsibility Matrix    Supporting   Supporting   **Primary**
  Roles / Permissions / RBAC      Supporting   Supporting   **Primary**

## 7. Security, Operations & Reliability

  ------------------------------------------------------------------------
  Artifact / Area       Case 1             Case 2             Case 3
  --------------- ------------------ ------------------ ------------------
  Security           **Primary**        **Primary**        **Primary**
  Requirements

  Audit Trail         Supporting        **Primary**        **Primary**

  SLA / SLO           Supporting        **Primary**        **Primary**

  Observability       Supporting        **Primary**        **Primary**
  Requirements

  Failure /          **Primary**        **Primary**        **Primary**
  Exception
  Scenarios
  ------------------------------------------------------------------------

## 8. Verification, Traceability & Delivery

  Artifact / Area                 Case 1        Case 2        Case 3
  ---------------------------- ------------- ------------- -------------
  Test Scenarios                **Primary**   **Primary**   **Primary**
  UAT Scenarios                 **Primary**   Supporting    **Primary**
  Traceability Matrix           **Primary**   **Primary**   **Primary**
  Change Impact Analysis        **Primary**   **Primary**   **Primary**
  Definition of Ready / Done    **Primary**   Supporting    Supporting
  Release Readiness             **Primary**   **Primary**   **Primary**

## Coverage Interpretation

The matrix highlights the distinct analytical profile of each case.

### Case 1 --- Omnichannel Delivery & Pickup

Case 1 has the broadest end-to-end coverage. Its primary scope spans
business context, requirements, process and behavioral modeling, REST
integration, relational data, verification, traceability, and delivery
readiness.

### Case 2 --- Distributed Order & Fulfillment Platform

Case 2 concentrates on distributed-system analysis. Event-driven
contracts, resilience, data ownership, cache and NoSQL decisions,
observability, and operational quality receive substantially greater
emphasis than business-process documentation.

### Case 3 --- Returns, Refunds & Claims Management

Case 3 concentrates on enterprise workflow complexity. Business Rules,
process modeling, state behavior, decision logic, responsibilities,
permissions, auditability, exception handling, and UAT receive the
strongest emphasis.

## Governance Rule

This matrix is a scope-control baseline, not an artifact checklist.

The planned classification may change only when the analytical work
establishes a concrete need. Any such change should make the reason
explicit and consider downstream effects on scope, traceability,
tooling, and related specifications.

An artifact should not be introduced solely to increase portfolio
breadth or technology coverage.

The governing principle is:

**Analytical need → justified artifact → appropriate depth → traceable
value.**
