# Analyst Delivery Lifecycle

## Purpose

This document defines the common delivery lifecycle used across the
three Business/System Analysis case studies.

The lifecycle provides a consistent operating model from initiative
intake through production change. Individual cases may place different
emphasis on particular stages, but the underlying progression, ownership
discipline, traceability, and review expectations remain consistent.

The lifecycle is iterative. A release does not terminate analysis:
production feedback, defects, operational findings, or business changes
may trigger impact analysis and return work to earlier stages.

## Lifecycle Map

The canonical stage sequence is:

1.  **Initiative / Intake**
2.  **Discovery**
3.  **Domain Analysis**
4.  **Requirements Elicitation**
5.  **Process & Behavioral Analysis**
6.  **Solution / System Analysis**
7.  **Detailed Specification**
8.  **Refinement & Review**
9.  **Development Support**
10. **QA Support**
11. **Release Readiness**
12. **Production Feedback / Change**

The lifecycle does not operate as a one-way waterfall.
`Production Feedback / Change` includes Impact Analysis and may return
work to any affected earlier stage while preserving decision ownership,
traceability, and baseline discipline.

## Stage 1 --- Initiative / Intake

### Objective

Establish a clear understanding of the business initiative before
solution design begins.

### Key Activities

-   Clarify the business problem and motivation.
-   Identify the expected business outcome and initial success measures.
-   Capture the initial scope and known constraints.
-   Identify key stakeholders and decision owners.
-   Clarify priority and known timeline expectations.
-   Record initial assumptions, risks, dependencies, and open questions.

### Analyst Responsibilities

The analyst structures the intake information, separates known facts
from assumptions, identifies missing information, and ensures that
premature solution decisions are not treated as requirements.

### Stakeholder Collaboration

Primary collaboration typically includes Product Owner, Business/Domain
SME, Delivery Manager, and other initiative owners.

### Typical Outputs

Initiative Brief, Business Context, initial Stakeholder Map, Open
Questions, Assumptions, Constraints, Risks, and Dependencies.

### Exit Criteria

The business problem, expected outcome, initial boundaries, principal
stakeholders, and major unknowns are sufficiently clear to begin
Discovery.

Do not design API, database, or target architecture at this stage.

## Stage 2 --- Discovery

### Objective

Understand the current customer and operational context, pain points,
needs, and existing behavior.

### Key Activities

-   Examine the current customer or operational journey.
-   Understand the current process and known production behavior.
-   Identify pain points and user needs.
-   Capture known Business Rules and terminology.
-   Investigate relevant production problems.
-   Refine assumptions, risks, dependencies, and open questions.

### Analyst Responsibilities

The analyst elicits information without assuming a predetermined
solution, identifies contradictions and gaps, and maintains a clear
distinction between facts, stakeholder opinions, assumptions, and
unresolved questions.

### Stakeholder Collaboration

Collaboration may include Product Owner, Domain SME, Operations,
Support, UX/UI, external providers, and other stakeholders involved in
the current process.

### Typical Outputs

Discovery Notes, refined Business Context, Stakeholder information,
AS-IS findings where applicable, Glossary updates, Open Questions, and
initial problem decomposition.

### Exit Criteria

The current context and primary problems are sufficiently understood to
structure the domain and proceed with requirements elicitation.

## Stage 3 --- Domain Analysis

### Objective

Establish a consistent understanding of domain concepts, semantics,
ownership, and system context.

### Key Activities

-   Define important domain concepts and vocabulary.
-   Clarify entity semantics and relationships.
-   Identify Business Rules relevant to the domain.
-   Identify existing systems and integration context.
-   Determine ownership of business information and system
    responsibilities.
-   Resolve terminology conflicts between stakeholders.

### Analyst Responsibilities

The analyst maintains semantic consistency across requirements,
processes, contracts, and data models and ensures that the same business
concept is not represented ambiguously across artifacts.

### Stakeholder Collaboration

Typical participants include Domain SME, Product Owner, Solution
Architect, Developers, DBA/Data Engineer, and integration owners.

### Typical Outputs

Glossary, Domain Notes, conceptual models where justified, Business
Rules updates, system context findings, and ownership clarifications.

### Exit Criteria

Core domain concepts, terminology, ownership, and relevant system
context are sufficiently stable to support detailed requirements.

## Stage 4 --- Requirements Elicitation

### Objective

Transform business and stakeholder needs into structured, clear,
testable, consistent, feasible, and traceable requirements.

### Key Activities

-   Define Business Requirements.
-   Structure stakeholder requirements.
-   Define Functional Requirements.
-   Define Non-Functional Requirements where applicable.
-   Capture and refine Business Rules.
-   Create User Stories where they support delivery.
-   Define Acceptance Criteria.
-   Maintain traceability to business goals and decisions.

### Analyst Responsibilities

The analyst owns requirement quality and consistency, identifies
conflicts and gaps, prevents solution details from being confused with
business needs, and ensures that requirements can be verified.

### Stakeholder Collaboration

Product Owner and Domain SME clarify business intent; Architect and
technical stakeholders contribute feasibility and constraints; QA
reviews testability.

### Typical Outputs

BR, FR, NFR, Business Rules, User Stories where useful, Acceptance
Criteria, requirement dependencies, and updated traceability.

### Exit Criteria

Requirements within the current scope are sufficiently clear,
consistent, testable, feasible, prioritized where required, and linked
to their business context.

## Stage 5 --- Process & Behavioral Analysis

### Objective

Describe how users, roles, and systems behave across main, alternative,
and exception scenarios.

### Key Activities

-   Model Main Flows.
-   Identify Alternative Flows.
-   Identify Exception Flows.
-   Describe user/system interactions.
-   Model business decisions.
-   Identify relevant state transitions.
-   Validate behavior against requirements and Business Rules.

### Analyst Responsibilities

The analyst ensures that behavioral models do not contradict
requirements and that edge cases, decisions, and state transitions are
explicit enough for review and verification.

### Stakeholder Collaboration

Typical collaboration includes Product Owner, Domain SME, UX/UI,
Architect, Developers, Operations, and QA.

### Typical Outputs

AS-IS/TO-BE models where applicable, BPMN, Use Cases,
Activity/Sequence/State diagrams where justified, and refined Business
Rules.

### Exit Criteria

The required business and system behavior is sufficiently explicit to
support solution analysis and detailed specification.

## Stage 6 --- Solution / System Analysis

### Objective

Collaborate with technical stakeholders to define system boundaries,
responsibilities, communication patterns, ownership, and constraints.

### Key Activities

-   Clarify system and service boundaries.
-   Define responsibilities and ownership.
-   Analyze synchronous and asynchronous communication needs.
-   Clarify data ownership.
-   Identify failure boundaries.
-   Capture security and architecture constraints.
-   Evaluate integration implications.

### Analyst Responsibilities

The analyst translates approved business behavior into consistent
system-level requirements and contracts while preserving decision
ownership. Architecture decisions remain owned by the appropriate
architecture or technical roles.

### Stakeholder Collaboration

Solution Architect, Tech Lead, Developers, DBA/Data Engineer, Security,
DevOps/SRE, and integration owners are primary participants.

### Typical Outputs

C4 and integration views where applicable, responsibility and ownership
matrices, architecture constraints, integration decisions, and Decision
Log updates.

### Exit Criteria

System responsibilities, boundaries, ownership, major interaction
patterns, and relevant constraints are sufficiently defined for detailed
specification.

## Stage 7 --- Detailed Specification

### Objective

Produce the contracts and technical specifications required for
implementation and verification.

### Key Activities

-   Specify REST/OpenAPI contracts where applicable.
-   Specify AsyncAPI and event contracts where applicable.
-   Define JSON Schemas.
-   Define Error Model behavior.
-   Refine Sequence and State models.
-   Develop Data Models and ERD.
-   Define DDL where required.
-   Specify NFR, Security, Logging, and operational requirements.
-   Define Test Scenarios and traceability.

### Analyst Responsibilities

The analyst maintains consistency between requirements, behavioral
models, interfaces, data, errors, acceptance criteria, and testable
outcomes.

### Stakeholder Collaboration

Architect, Developers, DBA/Data Engineer, Security, QA, QA Automation,
DevOps/SRE, and external integration owners review relevant
specifications.

### Typical Outputs

API/Event contracts, schemas, diagrams, data models, ERD/DDL, Error
Catalog, NFR, security and operational requirements, Test Scenarios, and
Traceability Matrix.

### Exit Criteria

The specification is sufficiently complete, consistent, reviewable, and
verifiable for delivery-team refinement and implementation.

## Stage 8 --- Refinement & Review

### Objective

Validate the specification with the delivery team and resolve gaps,
contradictions, feasibility issues, and scope changes.

### Key Activities

-   Capture review questions.
-   Determine the owner of each unresolved decision.
-   Resolve questions with the correct stakeholder.
-   Update affected requirements.
-   Update all affected artifacts and contracts.
-   Notify affected stakeholders.
-   Recheck traceability and consistency.

### Analyst Responsibilities

The analyst coordinates cross-role clarification and ensures that a
resolved question propagates to every affected artifact rather than
remaining only in meeting notes or chat.

### Stakeholder Collaboration

Product Owner, Architect, Tech Lead, Developers, QA, UX/UI, Mobile,
Security, DBA, and other affected roles participate as needed.

### Typical Outputs

Resolved Open Questions, updated requirements and specifications,
Decision Log entries, scope adjustments, review notes, and updated
traceability.

### Exit Criteria

Material review findings are resolved or explicitly accepted as open
items, and the affected baseline is internally consistent.

## Stage 9 --- Development Support

### Objective

Support implementation without taking ownership of decisions that belong
to business, architecture, or engineering roles.

### Question Classification

-   **Specification Gap** → System Analyst coordinates or resolves
    within analytical ownership.
-   **Business Decision** → Product Owner / Domain SME.
-   **Architecture Decision** → Solution Architect.
-   **Implementation Detail** → Tech Lead / Developer.

### Analyst Responsibilities

The analyst clarifies approved behavior, identifies specification gaps,
routes decisions to the correct owner, records meaningful decisions, and
updates affected artifacts when clarification changes the baseline.

### Typical Outputs

Clarifications, updated specifications, Decision Log entries, Change Log
entries, and additional traceability where required.

### Exit Criteria

Implementation questions affecting analytical scope are resolved, owned,
or explicitly tracked without undocumented changes to expected behavior.

## Stage 10 --- QA Support

### Objective

Support verification by determining expected behavior from the approved
analytical baseline.

### Analysis Chain

Requirement → Business Rule → Contract → Acceptance Criteria

### Classification

Observed behavior is classified as one of:

-   Bug;
-   Requirement Gap;
-   Expected Behavior;
-   Change Request.

### Analyst Responsibilities

The analyst clarifies intended behavior, identifies inconsistencies or
missing requirements, coordinates business decisions when necessary, and
updates affected artifacts when the approved behavior changes.

### Stakeholder Collaboration

QA, QA Automation, Developers, Product Owner, Domain SME, and relevant
technical owners participate depending on the issue.

### Typical Outputs

Defect clarification, requirement corrections, updated Acceptance
Criteria, Change Requests, Test Scenario updates, and traceability
changes.

### Exit Criteria

Material QA questions are classified and resolved or tracked, and the
specification remains aligned with accepted behavior.

## Stage 11 --- Release Readiness

### Objective

Confirm that the analyzed scope is ready for release from requirements,
verification, operational, and dependency perspectives.

### Key Activities

-   Confirm scope completion.
-   Review critical defects and known limitations.
-   Verify monitoring, logging, and alert readiness.
-   Confirm Support/Operations readiness.
-   Check external dependency readiness.
-   Review rollback considerations.
-   Verify release-relevant traceability.

### Analyst Responsibilities

The analyst verifies analytical completeness and coordinates unresolved
release-impacting questions with their owners. Release approval itself
remains with the appropriate delivery and business roles.

### Typical Outputs

Release Readiness assessment, known limitations, unresolved risk
visibility, final traceability updates, and accepted release baseline.

### Exit Criteria

Release-impacting analytical gaps are resolved or explicitly accepted,
critical dependencies are visible, and the final scope is traceable.

## Stage 12 --- Production Feedback / Change

### Objective

Assess production feedback and business or operational changes and
determine their impact on the accepted baseline.

### Key Activities

-   Capture the feedback or Change Request.
-   Identify the decision owner.
-   Perform Impact Analysis.
-   Identify affected requirements and Business Rules.
-   Identify affected processes and states.
-   Identify affected architecture, API/Event contracts, and data.
-   Identify affected Acceptance Criteria and tests.
-   Identify monitoring and operational impact.
-   Update backlog and baselines after approval.

### Analyst Responsibilities

The analyst owns cross-artifact impact analysis and traceability of the
accepted change. The analyst does not silently modify the baseline
before the relevant business or technical decision is approved.

### Typical Outputs

Change Request, Impact Analysis, updated requirements, models,
contracts, data specifications, tests, monitoring requirements, backlog
items, and Change Log entries.

### Exit Criteria

The change is rejected, deferred, or approved with its impact understood
and all affected artifacts identified for update.

## Cross-Stage Governance

Throughout the lifecycle:

-   meaningful accepted decisions must not exist only in chat or meeting
    memory;
-   decision ownership must remain explicit;
-   Open Questions, Assumptions, Constraints, Risks, Dependencies,
    Decisions, Meeting Notes, and Changes are maintained as living
    records;
-   requirements and downstream artifacts must remain traceable;
-   an update to one artifact must trigger review of dependent
    artifacts;
-   artifacts are created because they resolve an analytical need, not
    to satisfy a documentation checklist.

The lifecycle therefore operates as a controlled loop using the
canonical stage names:

**Initiative / Intake → Discovery → Domain Analysis → Requirements
Elicitation → Process & Behavioral Analysis → Solution / System Analysis
→ Detailed Specification → Refinement & Review → Development Support →
QA Support → Release Readiness → Production Feedback / Change → Impact
Analysis → affected lifecycle stage.**
