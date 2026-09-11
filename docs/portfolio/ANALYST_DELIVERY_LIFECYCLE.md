# Analyst Delivery Lifecycle

## Purpose

This document defines the common analytical delivery lifecycle used
across the three Business/System Analysis case studies.

The lifecycle provides a consistent progression from initiative intake
through production change. Individual initiatives may place different
emphasis on particular stages, repeat stages, or run activities in
parallel, while preserving explicit Decision Ownership, traceability,
review discipline, and controlled change.

The lifecycle is iterative rather than a one-way waterfall. Production
feedback, defects, operational findings, new constraints, or business
changes may trigger Impact Analysis and return work to any affected
earlier stage.

The lifecycle defines **when and why** major analytical activities
occur. The Portfolio Working Model defines **how** analytical
information is clarified, classified, persisted, reviewed, traced, and
changed.

------------------------------------------------------------------------

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

``` text
Initiative / Intake
        ↓
Discovery
        ↓
Domain Analysis
        ↓
Requirements Elicitation
        ↓
Process & Behavioral Analysis
        ↓
Solution / System Analysis
        ↓
Detailed Specification
        ↓
Refinement & Review
        ↓
Development Support
        ↓
QA Support
        ↓
Release Readiness
        ↓
Production Feedback / Change
        ↓
Impact Analysis
        ↺
Affected Lifecycle Stage
```

Stage boundaries are analytical control points, not mandatory hand-off
gates. Work may move backward or forward as new information appears.

------------------------------------------------------------------------

## Stage 1 — Initiative / Intake

### Objective

Establish a sufficiently clear understanding of the business problem or
opportunity before detailed analysis or solution design begins.

### Key Activities

- Clarify the initial business problem, opportunity, and motivation.
- Identify the expected business outcome.
- Identify initial success measures where they are already known.
- Establish preliminary scope boundaries without treating them as final.
- Identify principal stakeholders and Decision Owners.
- Clarify priority, urgency, and known timeline expectations.
- Capture initial Open Questions, Assumptions, Constraints, Risks, and
  Dependencies.

### Analyst Responsibilities

The analyst structures incomplete intake information, separates
confirmed facts from assumptions, identifies material unknowns, and
prevents premature solution ideas from being treated as approved
requirements.

### Stakeholder Collaboration

Typical participants include Product Owner, Business Owner, Domain SME,
Delivery Manager, and other initiative owners.

### Typical Outputs

- Initiative / Business Context;
- initial Stakeholder information;
- preliminary Scope;
- relevant Analysis Register entries;
- initial success measures where available.

### Exit Criteria

The business problem or opportunity, expected outcome, preliminary
boundaries, principal stakeholders, and major unknowns are sufficiently
understood to begin Discovery.

Detailed API, database, integration, or target architecture design is
not expected at this stage.

------------------------------------------------------------------------

## Stage 2 — Discovery

### Objective

Understand the current customer, business, and operational context;
identify pain points, needs, existing behavior, rules, and evidence
relevant to the initiative.

### Key Activities

- Examine the current customer or operational journey.
- Understand existing processes and relevant production behavior.
- Identify pain points, user needs, and operational concerns.
- Elicit existing Business Rules and terminology.
- Investigate relevant production problems and supporting evidence.
- Identify contradictions between stakeholder perspectives.
- Refine Open Questions, Assumptions, Constraints, Risks, and
  Dependencies.
- Determine which areas require deeper domain or requirements analysis.

### Analyst Responsibilities

The analyst elicits information without assuming a predetermined
solution and maintains a clear distinction between confirmed facts,
stakeholder opinions, assumptions, decisions, and unresolved questions.

### Stakeholder Collaboration

Participants may include Product Owner, Domain SME, Operations, Support,
UX/UI, external providers, and other stakeholders involved in the
current process.

### Typical Outputs

- Discovery findings;
- refined Business Context;
- Stakeholder information;
- AS-IS findings where justified;
- Glossary updates;
- relevant Analysis Register updates;
- initial problem decomposition.

### Exit Criteria

The current context and primary problems are sufficiently understood to
structure the domain and formulate requirements without relying on
invented facts.

------------------------------------------------------------------------

## Stage 3 — Domain Analysis

### Objective

Establish a consistent understanding of domain concepts, semantics,
relationships, ownership, and relevant system context.

### Key Activities

- Define important domain concepts and vocabulary.
- Clarify entity semantics and relationships.
- Identify relevant Business Rules and invariants.
- Identify actors, responsibilities, and ownership.
- Identify existing systems and integration context where relevant.
- Clarify information ownership and system responsibilities.
- Resolve terminology conflicts between stakeholders.
- Identify lifecycle or state concepts where they materially affect the
  domain.

### Analyst Responsibilities

The analyst maintains semantic consistency across requirements,
processes, behavioral models, contracts, and data specifications and
prevents the same business concept from acquiring contradictory meanings
across artifacts.

### Stakeholder Collaboration

Typical participants include Domain SME, Product Owner, Solution
Architect, Developers, DBA/Data Engineer, and integration owners.

### Typical Outputs

- Glossary;
- Domain Notes;
- conceptual models where justified;
- Business Rule updates;
- ownership clarifications;
- relevant system-context findings.

### Exit Criteria

Core domain concepts, terminology, ownership, and relevant context are
sufficiently stable to support requirements and behavioral analysis.

------------------------------------------------------------------------

## Stage 4 — Requirements Elicitation

### Objective

Transform established business and stakeholder needs into structured,
clear, verifiable, consistent, feasible, and traceable requirements.

### Key Activities

- Define Business Requirements.
- Define Functional Requirements.
- Define Non-Functional Requirements where justified.
- Capture and refine Business Rules.
- Establish Scope and Out of Scope at the appropriate level.
- Create User Stories where they support delivery.
- Define Acceptance Criteria.
- Identify requirement dependencies and conflicts.
- Maintain traceability to business goals, source information, and
  accepted decisions.
- Identify unresolved information that must remain an Open Question
  rather than becoming a requirement.

### Analyst Responsibilities

The analyst owns requirement quality and consistency, identifies
conflicts and gaps, prevents business needs from being confused with
unsupported solution decisions, and ensures requirements are verifiable.

### Stakeholder Collaboration

Product Owner and Domain SME clarify business intent and policy.
Solution Architect and other technical stakeholders contribute
feasibility and constraints. QA contributes testability and verification
concerns.

### Typical Outputs

- Business Requirements;
- Functional Requirements;
- Non-Functional Requirements where applicable;
- Business Rules;
- Scope / Out of Scope;
- User Stories where useful;
- Acceptance Criteria;
- requirement dependencies;
- updated traceability;
- relevant Analysis Register updates.

### Exit Criteria

Requirements within the current analytical scope are sufficiently clear,
consistent, verifiable, feasible, prioritized where required, and
traceable to their business context.

------------------------------------------------------------------------

## Stage 5 — Process & Behavioral Analysis

### Objective

Make business and system behavior explicit across main, alternative,
exception, and state-dependent scenarios.

### Key Activities

- Analyze AS-IS and TO-BE behavior where justified.
- Model Main Flows.
- Identify Alternative Flows.
- Identify Exception Flows.
- Describe actor and system interactions.
- Model business decisions where useful.
- Identify relevant state transitions.
- Analyze boundary and failure scenarios.
- Validate behavior against Requirements and Business Rules.

### Analyst Responsibilities

The analyst ensures that behavioral models do not contradict
Requirements or Business Rules and that important decisions,
alternatives, exceptions, and state transitions are explicit enough for
review, specification, and verification.

### Stakeholder Collaboration

Typical participants include Product Owner, Domain SME, UX/UI, Solution
Architect, Developers, Operations, and QA.

### Typical Outputs

Depending on analytical need:

- AS-IS / TO-BE descriptions or models;
- BPMN;
- Use Cases;
- Use Case Diagram;
- Activity Diagram;
- Sequence Diagram;
- State Diagram;
- refined Business Rules and Requirements.

No diagram is mandatory solely because it appears in the Artifact
Coverage Matrix.

### Exit Criteria

The behavior relevant to the current scope is sufficiently explicit to
support system analysis and detailed specification.

------------------------------------------------------------------------

## Stage 6 — Solution / System Analysis

### Objective

Translate accepted business behavior into a coherent system view by
clarifying boundaries, responsibilities, interactions, ownership,
constraints, and failure considerations with the appropriate technical
stakeholders.

### Key Activities

- Clarify system and service boundaries.
- Define system responsibilities and ownership.
- Analyze synchronous and asynchronous interaction needs.
- Analyze integration dependencies.
- Clarify data ownership.
- Identify failure boundaries and resilience concerns.
- Capture architecture and security constraints.
- Analyze authorization and audit concerns where applicable.
- Determine which technical contracts and models are justified.

### Analyst Responsibilities

The analyst structures system-level requirements and interactions while
preserving Decision Ownership. Architecture and implementation decisions
remain with the appropriate architecture and engineering roles.

### Stakeholder Collaboration

Typical participants include Solution Architect, Tech Lead, Developers,
DBA/Data Engineer, Security, DevOps/SRE, and integration owners.

### Typical Outputs

Depending on need:

- system boundary descriptions;
- C4 Context / Container views;
- Integration Map;
- ownership clarifications;
- architecture constraints;
- integration decisions;
- relevant Analysis Register updates.

### Exit Criteria

System responsibilities, boundaries, ownership, major interaction
patterns, and relevant constraints are sufficiently defined for detailed
specification.

------------------------------------------------------------------------

## Stage 7 — Detailed Specification

### Objective

Produce the detailed analytical and technical specifications required
for implementation, integration, and verification.

### Key Activities

Where justified by the solution:

- specify REST/OpenAPI contracts;
- specify event contracts and AsyncAPI;
- define JSON Schema;
- define Error Model behavior;
- refine Sequence and State models;
- develop conceptual and logical Data Models;
- create ERD;
- define PostgreSQL DDL where required;
- specify validation behavior;
- specify security and permission requirements;
- specify audit requirements;
- specify logging, monitoring, and operational requirements;
- define Failure Scenarios;
- refine Acceptance Criteria;
- define Test Scenarios;
- maintain traceability across specifications.

### Analyst Responsibilities

The analyst maintains semantic consistency between Requirements,
Business Rules, behavioral models, interfaces, data, errors,
permissions, operational requirements, Acceptance Criteria, and
verifiable outcomes.

### Stakeholder Collaboration

Relevant specifications are reviewed with Solution Architect,
Developers, DBA/Data Engineer, Security, QA, QA Automation, DevOps/SRE,
and external integration owners.

### Typical Outputs

Depending on analytical need:

- OpenAPI;
- AsyncAPI;
- JSON Schema;
- API/Event contracts;
- Error Model;
- Sequence/State diagrams;
- Data Models;
- ERD;
- PostgreSQL DDL;
- Security / RBAC requirements;
- Audit requirements;
- NFR and operational requirements;
- Failure Scenarios;
- Test Scenarios;
- traceability updates.

### Exit Criteria

The specifications required for the current delivery scope are
sufficiently complete, internally consistent, reviewable, implementable,
and verifiable.

------------------------------------------------------------------------

## Stage 8 — Refinement & Review

### Objective

Validate analytical readiness with affected stakeholders and the
delivery team, resolving material ambiguity, contradictions, feasibility
concerns, and scope changes before implementation proceeds.

### Key Activities

- Review Requirements, Business Rules, models, and specifications.
- Capture material review questions.
- Classify unresolved questions and identify their Decision Owners.
- Resolve questions with the appropriate stakeholder.
- Update affected analytical artifacts.
- Recheck dependencies, traceability, and cross-artifact consistency.
- Refine Acceptance Criteria and delivery items where required.
- Assess readiness against the agreed Definition of Ready or equivalent
  readiness criteria.

### Analyst Responsibilities

The analyst coordinates cross-role clarification and ensures that
resolved questions propagate to all affected analytical artifacts
instead of remaining only in transient communication or review notes.

### Stakeholder Collaboration

Participants may include Product Owner, Domain SME, Solution Architect,
Tech Lead, Developers, QA, UX/UI, Security, DBA/Data Engineer,
Operations/SRE, and other affected roles.

### Typical Outputs

- resolved Open Questions;
- accepted Decisions;
- updated Requirements and specifications;
- scope adjustments;
- review notes where useful;
- updated Jira delivery items;
- updated traceability;
- readiness assessment.

### Exit Criteria

Material review findings are resolved or explicitly tracked with
ownership, affected artifacts are consistent, and the delivery scope is
sufficiently ready for implementation.

------------------------------------------------------------------------

## Stage 9 — Development Support

### Objective

Support implementation by clarifying the accepted analytical baseline
and controlling changes that emerge during development.

### Question Classification

Typical implementation questions are classified as:

- **Specification Gap** → analyst coordinates clarification or resolves
  it within analytical ownership;
- **Business Decision** → Product Owner / Business Owner / Domain SME;
- **Architecture Decision** → Solution Architect;
- **Implementation Detail** → Tech Lead / Developer;
- **Security Decision** → Security;
- **Data-Platform Decision** → DBA / Data Engineer;
- **Operational Decision** → DevOps / SRE.

### Analyst Responsibilities

The analyst:

- clarifies approved behavior;
- identifies specification gaps;
- routes decisions to the correct owner;
- records significant outcomes in the appropriate source;
- updates affected artifacts when clarification changes the analytical
  baseline;
- checks downstream consistency and traceability.

### Typical Outputs

- clarifications;
- updated specifications;
- relevant Decisions and Open Questions;
- Jira updates where delivery is affected;
- traceability updates;
- Change Request when the requested behavior changes accepted scope or
  baseline.

### Exit Criteria

Implementation questions affecting analytical scope are resolved, owned,
or explicitly tracked without undocumented changes to expected behavior.

------------------------------------------------------------------------

## Stage 10 — QA Support

### Objective

Support verification by determining expected behavior from the accepted
analytical baseline and resolving discrepancies between specification
and observed behavior.

### Verification Chain

A typical verification path is:

``` text
Requirement
→ Business Rule
→ Process / Behavior
→ Contract / Data
→ Acceptance Criteria
→ Test Scenario
```

Not every verification path requires every artifact type.

### Issue Classification

Observed behavior may be classified as:

- **Bug**;
- **Requirement Gap**;
- **Specification Gap**;
- **Expected Behavior**;
- **Change Request**.

### Analyst Responsibilities

The analyst clarifies intended behavior, identifies inconsistencies or
missing analytical knowledge, coordinates decisions when necessary, and
updates affected artifacts only after the expected behavior is
established.

### Stakeholder Collaboration

Typical participants include QA, QA Automation, Developers, Product
Owner, Domain SME, and relevant technical owners.

### Typical Outputs

- defect clarification;
- Requirement or specification corrections;
- updated Acceptance Criteria;
- updated Test Scenarios;
- Change Requests where applicable;
- traceability updates;
- UAT support materials where justified.

### Exit Criteria

Material QA questions are classified and resolved or explicitly tracked,
and analytical specifications remain aligned with accepted behavior.

------------------------------------------------------------------------

## Stage 11 — Release Readiness

### Objective

Confirm that the analyzed scope is ready for release from requirements,
verification, dependency, and operational perspectives.

### Key Activities

- Confirm release scope and analytical completeness.
- Review unresolved critical Open Questions.
- Review material Risks and Dependencies.
- Review critical defects and known limitations.
- Confirm Acceptance Criteria and relevant UAT outcomes.
- Verify monitoring, logging, alerting, audit, and support readiness
  where applicable.
- Confirm external dependency readiness.
- Review rollback or recovery considerations where they affect
  requirements or operational readiness.
- Verify release-relevant traceability.

### Analyst Responsibilities

The analyst verifies analytical completeness and coordinates unresolved
release-impacting questions with their owners. Release approval remains
with the appropriate business and delivery roles.

### Typical Outputs

- Release Readiness assessment;
- known limitations;
- unresolved risk/dependency visibility;
- final analytical and traceability updates;
- accepted release scope.

### Exit Criteria

Release-impacting analytical gaps are resolved or explicitly accepted by
the appropriate owner, critical dependencies are visible, and the
release scope is traceable.

------------------------------------------------------------------------

## Stage 12 — Production Feedback / Change

### Objective

Assess production feedback, defects, operational findings, and business
changes and determine their impact on accepted analytical knowledge and
delivery scope.

### Key Activities

- Capture the feedback, defect, or Change Request.
- Identify the source and appropriate Decision Owner.
- Determine whether clarification or a decision is required.
- Perform Change Impact Analysis.
- Identify affected Requirements and Business Rules.
- Identify affected processes, behavior, and states.
- Identify affected system boundaries, integrations, API/Event
  contracts, and data.
- Identify affected security, audit, and operational requirements.
- Identify affected Acceptance Criteria, Test Scenarios, and UAT.
- Identify affected Risks and Dependencies.
- Update Jira delivery items when accepted change creates delivery work.
- Update affected analytical artifacts and traceability after approval.

### Analyst Responsibilities

The analyst owns cross-artifact Impact Analysis and traceability of
accepted change. The analyst does not silently modify accepted
analytical knowledge before the relevant business or technical decision
is established.

### Typical Outputs

Depending on the change:

- Change Request;
- Impact Analysis;
- relevant Analysis Register updates;
- updated Requirements and Business Rules;
- updated models and specifications;
- updated contracts and data specifications;
- updated Acceptance Criteria and Test Scenarios;
- updated operational requirements;
- Jira delivery updates;
- traceability updates.

### Exit Criteria

The change is rejected, deferred, or accepted with its impact
understood, Decision Ownership clear, and all affected artifacts and
delivery items identified for update.

------------------------------------------------------------------------

## Cross-Stage Governance

Throughout the lifecycle:

- meaningful accepted decisions must be persisted in the appropriate
  source rather than remain only in transient communication or meeting
  memory;
- Decision Ownership must remain explicit;
- Open Questions, Assumptions, Constraints, Decisions, Risks, and
  Dependencies are maintained through the Analysis Register where
  applicable;
- Meeting Notes are created separately when a meeting or workshop
  requires a record;
- Requirements and downstream artifacts remain traceable;
- an update to one artifact triggers review of actual dependent
  artifacts;
- artifacts are created because they resolve an analytical need, not to
  satisfy a documentation checklist;
- Jira is used for delivery management;
- Confluence is used for working analytical knowledge;
- Git/GitHub is used for Portfolio files, version history, and
  milestones;
- specialized tools are used only when justified by analytical need;
- accepted analytical knowledge is not equated with a Git commit, Jira
  status, or storage location;
- professionally sufficient infrastructure, formatting, or templates
  must not block progression of analytical work.

The lifecycle therefore operates as a controlled loop:

**Initiative / Intake → Discovery → Domain Analysis → Requirements
Elicitation → Process & Behavioral Analysis → Solution / System Analysis
→ Detailed Specification → Refinement & Review → Development Support →
QA Support → Release Readiness → Production Feedback / Change → Impact
Analysis → affected lifecycle stage.**

------------------------------------------------------------------------

## Lifecycle Principles

1.  **Progressive disclosure over invented completeness.**
2.  **Business problem before solution design.**
3.  **Explicit Decision Ownership throughout the lifecycle.**
4.  **Analytical need determines artifact creation and depth.**
5.  **Requirements, models, contracts, data, and tests remain
    semantically consistent.**
6.  **Traceability follows real dependencies rather than documentation
    formality.**
7.  **Accepted decisions propagate to all affected artifacts.**
8.  **Changes are assessed through Impact Analysis rather than silent
    editing.**
9.  **Tooling supports analytical work and does not determine it.**
10. **Lifecycle stages guide work without becoming waterfall gates.**
11. **Meaningful analytical increments take priority over unnecessary
    process ceremony.**
12. **Speed does not justify unsupported requirements, hidden
    assumptions, or loss of analytical quality.**
