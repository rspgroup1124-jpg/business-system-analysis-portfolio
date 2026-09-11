# Business/System Analysis Portfolio

## Overview

This repository contains three production-style Business/System Analysis case studies covering complementary areas of a realistic e-commerce environment.

The Portfolio captures the end-to-end analytical workflow: initiative intake, discovery, stakeholder collaboration, domain analysis, requirements, process and behavioral modeling, system analysis, detailed specification, traceability, development and QA support, release readiness, and Change Impact Analysis.

The emphasis is not on producing the maximum number of artifacts. Each artifact is introduced only when it provides concrete analytical value for the scope of a case.

## Role

**Business/System Analyst**

The cases follow progressive disclosure of business and technical information, reflecting how analytical knowledge develops through stakeholder interaction, clarification, explicit decisions, review, and controlled change.

Decision Ownership remains with the appropriate business or technical role. The analyst structures information, coordinates clarification, maintains analytical consistency and traceability, and supports the delivery lifecycle.

## Case Studies

1. **Omnichannel Delivery & Pickup** — full-cycle Business/System Analysis from an incomplete business initiative to a development-ready specification.
2. **Distributed Order & Fulfillment Platform** — System Analysis focused on distributed systems, high-load concerns, service boundaries, event-driven integration, resilience, data ownership, and system contracts.
3. **Returns, Refunds & Claims Management** — Business/System Analysis focused on enterprise processes, Business Rules, states, roles, permissions, data, exceptions, auditability, and human workflows.

## Working Approach

The common analytical lifecycle is:

**Initiative / Intake → Discovery → Domain Analysis → Requirements Elicitation → Process & Behavioral Analysis → Solution / System Analysis → Detailed Specification → Refinement & Review → Development Support → QA Support → Release Readiness → Production Feedback / Change**

The Portfolio uses a responsibility-based workspace model:

- **Jira** — Delivery Management.
- **Confluence** — Working Analytical Knowledge.
- **Git / GitHub** — Portfolio files, version history, and milestones.

The storage location does not determine whether an analytical decision has been accepted. Business, architecture, implementation, security, data, operational, and other decisions remain with their appropriate Decision Owners.

Meaningful accepted decisions are propagated to affected requirements, Business Rules, models, contracts, data specifications, tests, delivery items, and traceability.

## Tooling

The working environment supports collaboration and delivery management, diagram and process modeling, API and event specification, relational and document data analysis, messaging and cache verification, local runtime infrastructure, and analytical automation.

Core tools include Jira, Confluence, Git/GitHub, VS Code, and PowerShell. Specialized tools and technologies are introduced only when a concrete analytical, modeling, specification, or verification need justifies their use.

The complete environment inventory, status model, and usage classifications are defined in `docs/portfolio/TOOLING_BASELINE.md`.

## Portfolio Documentation

The Portfolio-wide operating baseline is defined by:

- `docs/portfolio/PORTFOLIO_OVERVIEW.md` — Portfolio scope, positioning, and case profiles.
- `docs/portfolio/WORKING_MODEL.md` — operating rules for analytical work, persistence, traceability, and controlled change.
- `docs/portfolio/ANALYST_DELIVERY_LIFECYCLE.md` — common 12-stage analytical lifecycle.
- `docs/portfolio/ARTIFACT_COVERAGE_MATRIX.md` — planned artifact coverage and scope control across the three cases.
- `docs/portfolio/LOCALIZATION_POLICY.md` — language, terminology, syntax, and identifier rules.
- `docs/portfolio/TOOLING_BASELINE.md` — available tooling, environment status, and usage rules.

## Repository Structure

- `docs/portfolio/` — Portfolio-wide documentation and operating baselines.
- `case-01-omnichannel-delivery/` — Omnichannel Delivery & Pickup.
- `case-02-distributed-order-fulfillment/` — Distributed Order & Fulfillment Platform.
- `case-03-returns-refunds-claims/` — Returns, Refunds & Claims Management.

Case-specific analytical materials are added progressively as analysis establishes a justified need.

## Current Status

The Portfolio foundation, operating model, tooling environment, and repository baseline are established.

Case-level analysis has not started yet.
