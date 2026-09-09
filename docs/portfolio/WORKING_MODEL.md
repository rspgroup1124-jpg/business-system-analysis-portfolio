# Portfolio Working Model

## Purpose

This document defines the operating rules used to conduct, review,
persist, and change analytical work across the three Business/System
Analysis case studies.

It complements the Analyst Delivery Lifecycle. The lifecycle defines
when analytical activities occur; this Working Model defines how
information is obtained, how decisions are owned, where knowledge is
persisted, and how changes propagate across the analytical baseline.

## 1. Progressive Disclosure

Business and technical information is not assumed to be fully known at
the start of a case.

Information becomes available through the analytical process:

1.  an initiative provides limited initial context;
2.  the analyst identifies what is known and unknown;
3.  questions are directed to the appropriate stakeholder;
4.  stakeholder answers create facts, constraints, decisions,
    assumptions, or additional questions;
5.  approved information is propagated into affected analytical
    artifacts.

Requirements, Business Rules, architecture constraints, API contracts,
data models, and other downstream specifications must not be invented
before sufficient evidence or an explicit decision exists.

The analyst is expected to identify missing information rather than fill
gaps with undocumented assumptions.

## 2. Stakeholder and Decision Ownership

The analyst coordinates information across roles but does not replace
the owners of business, architecture, implementation, security, data, or
quality decisions.

Typical ownership follows these boundaries:

  -----------------------------------------------------------------------
  Decision Area                       Typical Owner
  ----------------------------------- -----------------------------------
  Business priority, value, scope     Product Owner
  trade-off

  Domain policy and operational rule  Domain SME / Business Owner

  Architecture and system boundary    Solution Architect
  decision

  Implementation approach             Tech Lead / Developer

  Data platform or database-specific  DBA / Data Engineer
  decision

  Security policy or security         Security
  constraint

  Operational reliability decision    DevOps / SRE

  Test strategy and QA implementation QA / QA Automation

  Requirement quality, specification  System Analyst
  consistency, traceability,
  cross-role clarification
  -----------------------------------------------------------------------

Ownership may vary by project context, but it must remain explicit.

When a question falls outside analytical ownership, the analyst
identifies the correct decision owner, obtains the decision, records it,
and updates affected artifacts.

## 3. Analyst Responsibility Boundaries

The System Analyst is responsible for:

-   structuring incomplete information;
-   identifying gaps, contradictions, dependencies, and risks;
-   formulating clear questions;
-   maintaining requirement and specification quality;
-   coordinating cross-role clarification;
-   maintaining semantic consistency across artifacts;
-   maintaining traceability;
-   performing cross-artifact Change Impact Analysis;
-   ensuring accepted decisions are reflected in affected baselines.

The System Analyst does not silently make business, architecture,
implementation, security, or operational decisions that belong to
another role.

## 4. Persistence Model

Analytical information is persisted according to its purpose and
maturity.

### Jira --- Delivery State

Jira is used for delivery-oriented work such as:

-   Epics;
-   Stories;
-   Tasks;
-   Bugs;
-   Change Requests;
-   delivery status;
-   prioritization;
-   assignment and workflow state.

Jira is not the primary location for complete analytical specifications.

### Confluence --- Evolving Team Knowledge

Confluence is used for collaborative and evolving knowledge such as:

-   Discovery notes;
-   workshop and meeting notes;
-   stakeholder context;
-   working process descriptions;
-   evolving requirements;
-   unresolved questions;
-   review material;
-   draft decisions and collaborative analysis.

Confluence content may change frequently while analysis is active.

### Git --- Durable Accepted Baseline

Git is used for durable, reviewable, version-controlled analytical
baselines such as:

-   accepted requirements;
-   approved Business Rules;
-   canonical diagrams and diagram source;
-   API and event contracts;
-   schemas;
-   data models and DDL;
-   traceability artifacts;
-   accepted decision records;
-   change-impact artifacts;
-   release-relevant analytical documentation.

Git history provides explicit versioning of accepted analytical states.

## 5. Living Registers

Each case maintains a set of living management records as required by
its scope.

Core registers include:

-   Open Questions;
-   Assumptions;
-   Constraints;
-   Decision Log;
-   Risk Register;
-   Dependency Register;
-   Change Log;
-   Meeting Notes.

These records evolve throughout the lifecycle and are not treated as
one-time documents.

A meaningful item should have enough context to understand its origin,
current status, owner where applicable, and effect on the analysis.

## 6. Question-to-Decision Flow

A question follows a controlled path:

**Question → Classification → Decision Owner → Answer / Decision →
Persistence → Artifact Update → Traceability Review**

The analyst first determines what kind of question exists.

Examples:

-   missing specification detail;
-   business decision;
-   domain clarification;
-   architecture decision;
-   implementation detail;
-   security decision;
-   data ownership question;
-   operational constraint.

The answer must come from the appropriate source.

A significant accepted answer must not remain only in chat, email, or
meeting memory.

## 7. Decision Propagation

A decision is not complete when it is merely recorded.

After an accepted decision, the analyst determines which artifacts are
affected.

Potentially affected areas include:

-   Business Requirements;
-   Functional Requirements;
-   Non-Functional Requirements;
-   Business Rules;
-   Scope;
-   processes and behavioral models;
-   Use Cases;
-   API or Event Contracts;
-   Error Model;
-   data models;
-   security requirements;
-   Acceptance Criteria;
-   Test Scenarios;
-   Jira backlog;
-   release documentation.

The analyst updates the relevant artifacts and verifies that no
contradictory baseline remains.

## 8. Traceability

Traceability connects business intent to implementation-verifiable
behavior.

Depending on the case, traceability may include relationships such as:

**Business Goal → Business Requirement → Functional Requirement →
Business Rule → Process / Use Case → Contract / Data → Acceptance
Criteria → Test Scenario**

Not every artifact requires a link to every other artifact. Traceability
should be meaningful and sufficient to answer:

-   Why does this requirement exist?
-   Which business decision or rule supports it?
-   Which specification implements or constrains it?
-   How is the expected behavior verified?
-   What is affected if it changes?

## 9. Change Management

Accepted baselines are not modified silently.

When a meaningful change appears:

1.  capture the Change Request or production feedback;
2.  identify the decision owner;
3.  determine whether the change is approved, rejected, or deferred;
4.  perform Impact Analysis;
5.  identify affected requirements, rules, processes, architecture,
    contracts, data, tests, monitoring, and backlog items;
6.  update affected artifacts after approval;
7.  update traceability and Change Log;
8.  establish a new accepted baseline where appropriate.

A change to one artifact is treated as a trigger to inspect dependent
artifacts.

## 10. Artifact Creation Rule

Artifacts are created because they solve a concrete analytical problem.

The Portfolio Artifact Coverage Matrix defines the expected emphasis for
each case using:

-   Primary;
-   Supporting;
-   Not Used.

The matrix is a scope-control baseline, not a requirement to produce
documents mechanically.

An artifact classified as Not Used may be introduced only when the
analysis establishes a concrete need. The reason and downstream impact
should be explicit.

No artifact should exist solely to increase portfolio size.

## 11. Manual First, Automation Second

Analytical semantics and workflow are established manually before
automation is introduced.

Automation may be added when:

-   the manual process is understood;
-   the inputs and outputs are stable enough to define;
-   repeated work creates a meaningful automation opportunity;
-   automation does not obscure analytical reasoning or decision
    ownership.

Python and other automation tools support the analytical workflow; they
do not replace analysis.

The portfolio remains separate from NovaMarket Toolkit and must not
evolve into another general-purpose analytical platform.

## 12. Review and Baseline Discipline

Before analytical content becomes an accepted baseline, it should be
reviewed at a level appropriate to its impact.

Review may involve:

-   Product Owner for business intent and scope;
-   Domain SME for domain correctness;
-   Solution Architect for architecture and boundaries;
-   Developers or Tech Lead for implementability;
-   DBA/Data Engineer for data concerns;
-   Security for security requirements;
-   QA for testability and expected behavior;
-   Operations/SRE for operational requirements.

The analyst coordinates review and incorporates accepted outcomes.

A Git commit or merge represents a meaningful versioned state; it must
not be treated as a substitute for stakeholder approval where
stakeholder approval is required.

## 13. Operational Working Loop

The Working Model is expressed as a controlled operational loop:

**Known Information → Open Question → Classification → Decision Owner →
Accepted Answer / Decision → Persistence → Artifact Update →
Traceability Review → Accepted Baseline → Feedback / Change**

Feedback or change may reopen questions, require a new decision, or
trigger Change Impact Analysis across dependent artifacts.

This loop complements rather than duplicates the Analyst Delivery
Lifecycle. The lifecycle determines the stage of work; the Working Model
determines how analytical knowledge moves from uncertainty to an
accepted, traceable baseline within and across those stages.

The quality target is not maximum documentation volume.

The target is:

**Analytical Decision + Traceable Requirement + Verifiable Contract +
Clear Team Workflow + Controlled Change Impact.**
