# Portfolio Working Model

## Purpose

This document defines the operating rules used to conduct, review,
persist, and change analytical work across the three Business/System
Analysis case studies.

It complements the Analyst Delivery Lifecycle. The lifecycle defines
**when** analytical activities occur; this Working Model defines **how**
information is obtained, clarified, classified, persisted, reviewed,
traced, and changed.

The objective is not maximum documentation volume or process ceremony.
The objective is a realistic, efficient, traceable analytical workflow
that turns incomplete information into verified specifications and
controlled delivery outcomes.

## 1. Progressive Disclosure

Business and technical information is not assumed to be fully known at
the start of a case.

Information becomes available through the analytical process:

1.  an initiative provides limited initial context;
2.  known information is separated from uncertainty;
3.  relevant stakeholders and Decision Owners are identified;
4.  clarification questions are formulated;
5.  stakeholder answers establish facts, constraints, decisions,
    assumptions, dependencies, risks, or additional questions;
6.  analytical conclusions are created only when supported by sufficient
    evidence;
7.  affected artifacts are created or updated when there is a justified
    analytical need.

Requirements, Business Rules, architecture constraints, API contracts,
event contracts, data models, target-state processes, and other
downstream specifications must not be invented before sufficient
evidence or an explicit decision exists.

The analyst identifies missing information rather than silently filling
gaps with undocumented assumptions.

Future case information must not be used before it becomes available
through the analytical process.

## 2. Production Artifact Rule

All analytical artifacts and working spaces must be suitable for use in
a real production project.

Their content must be professional, context-complete, semantically
consistent, and understandable to the intended project audience without
relying on external explanatory context.

This rule applies to Confluence pages, Jira work items, requirements,
Business Rules, process models, UML and C4 diagrams, API and event
specifications, data models, Test Scenarios, UAT materials,
traceability, Change Impact Analysis, and case-specific analytical
documentation.

## 3. Stakeholder and Decision Ownership

The analyst coordinates information across roles but does not replace
the owners of business, architecture, implementation, security, data,
quality, or operational decisions.

| Decision Area                                                                          | Typical Owner                  |
|----------------------------------------------------------------------------------------|--------------------------------|
| Business priority, value, scope trade-off                                              | Product Owner / Business Owner |
| Domain policy and operational rule                                                     | Domain SME / Business Owner    |
| Architecture and system boundary decision                                              | Solution Architect             |
| Implementation approach                                                                | Tech Lead / Developer          |
| Data platform or database-specific decision                                            | DBA / Data Engineer            |
| Security policy or security constraint                                                 | Security                       |
| Operational reliability decision                                                       | DevOps / SRE                   |
| Test strategy and QA implementation                                                    | QA / QA Automation             |
| Requirement quality, specification consistency, traceability, cross-role clarification | Business/System Analyst        |

Ownership may vary by project context, but it must remain explicit.

When a question falls outside analytical ownership, the analyst
identifies the appropriate stakeholder or Decision Owner, obtains
clarification or a decision, records the outcome in the appropriate
location, updates affected artifacts, and verifies downstream
consistency and traceability.

## 4. Analyst Responsibility Boundaries

The Business/System Analyst is responsible for:

- structuring incomplete information;
- identifying gaps, contradictions, dependencies, and risks;
- formulating clear questions;
- selecting the appropriate source of clarification;
- maintaining requirement and specification quality;
- coordinating cross-role clarification;
- modeling processes and system behavior where justified;
- maintaining semantic consistency across artifacts;
- maintaining meaningful traceability;
- supporting refinement, development, QA, and release readiness;
- performing cross-artifact Change Impact Analysis;
- ensuring accepted decisions are reflected in affected analytical
  knowledge.

The analyst does not silently make business, architecture,
implementation, security, data-platform, or operational decisions that
belong to another role.

A technical proposal created by the analyst remains a proposal until the
appropriate Decision Owner accepts it when such approval is required.

## 5. Persistence and Workspace Model

Information is persisted according to its responsibility and working
purpose.

No platform is used merely because it is available. The same analytical
content should not be copied across systems without a concrete reason.

### Jira — Delivery Management

Jira is used for Epics, Stories, Tasks, Bugs, Change Requests, backlog,
sprint planning, prioritization, assignment, blockers, workflow state,
and delivery progress.

Jira is not the primary location for complete analytical specifications.

Delivery items are created when analysis establishes real delivery work.
Fictional Stories must not be created in advance merely to populate
Jira.

### Confluence — Working Analytical Knowledge

Confluence is the primary collaborative knowledge space for evolving
analytical content such as Initiative / Business Context, Discovery
material, stakeholder context, Scope, evolving requirements, Business
Rules, process descriptions, Meeting Notes, review material,
specifications, decisions and supporting rationale, and other
collaborative analytical knowledge.

Pages are created when a real knowledge responsibility appears. Empty
page hierarchies are not created in advance merely to anticipate
possible artifacts.

### Git / GitHub — Portfolio Repository and Versioning

Git and GitHub are used primarily for:

- storing file-based Portfolio artifacts;
- preserving version history;
- maintaining canonical technical files where appropriate;
- meaningful Portfolio commits;
- milestone tags;
- publishing and presenting the Portfolio;
- preserving repository state.

Examples of file-based artifacts that may naturally live in Git include
PlantUML source, OpenAPI, AsyncAPI, JSON Schema, SQL/DDL,
machine-readable specifications, and repository-native analytical
artifacts.

Git is **not** the mandatory system of record for all day-to-day
analytical knowledge.

A Git commit, merge, or tag does not by itself mean that a Requirement,
Business Rule, architecture decision, or other analytical statement has
been accepted by its Decision Owner.

Git workflow must support the Portfolio rather than become a separate
source of process ceremony.

### Persistence Summary

``` text
Delivery State
→ Jira

Working Analytical Knowledge
→ Confluence

Portfolio Files / Version History / Milestones
→ Git + GitHub

Local Modeling / Verification / Experimentation
→ Appropriate Specialized Tool
```

References and links should be used instead of unnecessary duplication.

## 6. Management Artifact Discipline

> **Each management artifact must have one clear responsibility, contain
> only the minimum information necessary for that responsibility, and
> reference other sources instead of duplicating their content.**

A management artifact must not become a secondary copy of Requirements,
Business Rules, Meeting Notes, process descriptions, API specifications,
data models, test specifications, or other analytical artifacts.

Management artifacts are created only when their responsibility is
needed by the case.

## 7. Analysis Register

Case 1 uses a consolidated **Analysis Register** for six types of living
management information:

- Open Questions — `OQ-NNN`;
- Assumptions — `ASM-NNN`;
- Constraints — `CON-NNN`;
- Decisions — `DEC-NNN`;
- Risks — `RSK-NNN`;
- Dependencies — `DEP-NNN`.

The current file is:

``` text
case-01-omnichannel-delivery/
└── docs/
    └── 00-management/
        └── analysis-register.md
```

The register is intentionally empty until real analytical information
appears.

An Open Question represents material uncertainty requiring a confirmed
answer.

An Assumption represents an unconfirmed proposition temporarily accepted
as a working basis.

A Constraint represents a confirmed condition restricting analysis or
the solution space.

A Decision represents a significant proposed or accepted decision with
an explicit Decision Owner.

A Risk represents an uncertain event or condition that may negatively
affect objectives, schedule, quality, or delivery.

A Dependency represents reliance on a participant, team, system,
supplier, external condition, or other required outcome.

Meeting Notes remain separate when a meeting or workshop creates
information that requires a meeting record.

Change Management is handled through the lifecycle and appropriate
change artifacts rather than being mechanically added as another
permanent section of the Analysis Register.

## 8. Question-to-Decision Flow

A material question follows a controlled path:

``` text
Question
→ Classification
→ Appropriate Stakeholder / Decision Owner
→ Answer / Decision
→ Persistence
→ Artifact Update
→ Traceability Review
```

Questions may represent missing specification detail, business or domain
clarification, business or architecture decisions, implementation
questions, security decisions, data ownership questions, operational
constraints, or quality concerns.

The answer must come from an appropriate source.

A significant accepted answer must not remain only in transient
communication or meeting memory when it affects analytical or delivery
knowledge.

## 9. Decision Propagation

A decision is not complete when it is merely recorded.

After an accepted decision, the analyst determines which artifacts and
delivery items are affected.

Potentially affected areas include:

- Business Requirements;
- Functional Requirements;
- Non-Functional Requirements;
- Business Rules;
- Scope;
- processes and behavioral models;
- Use Cases;
- architecture views;
- API or Event Contracts;
- Error Model;
- data models;
- security requirements;
- Acceptance Criteria;
- Test Scenarios;
- Jira backlog;
- operational requirements;
- release documentation.

The analyst updates relevant artifacts and verifies that contradictory
information does not remain active.

## 10. Traceability

Traceability connects business intent to specified and verifiable
behavior.

``` text
Business Problem / Goal
→ Business Requirement
→ Functional / Non-Functional Requirement
→ Business Rule
→ Process / Use Case / Behavior
→ System Interaction
→ API / Event Contract
→ Data
→ Acceptance Criteria
→ Test Scenario
→ Jira Delivery Item
→ Change Impact
```

Not every chain requires every artifact type.

Traceability should be sufficient to answer why a requirement exists,
which decision or rule supports it, which specification is affected, how
behavior is verified, which delivery item implements it, and what is
affected if the source information changes.

Traceability must reflect real dependencies rather than artificial
one-to-one linking.

## 11. Change Management

Accepted analytical knowledge is not changed silently.

When a meaningful change appears:

1.  capture the Change Request, production feedback, or other change
    source;
2.  identify the appropriate Decision Owner;
3.  determine whether the change is accepted, rejected, deferred, or
    requires clarification;
4.  perform Change Impact Analysis;
5.  identify affected requirements, Business Rules, processes,
    architecture views, contracts, data, security, tests, monitoring,
    dependencies, and backlog items;
6.  update affected artifacts after the necessary decision;
7.  update traceability;
8.  verify cross-artifact consistency;
9.  establish the resulting analytical state.

A change to one artifact is a trigger to inspect its actual
dependencies.

Each case should contain at least one meaningful change demonstrating
cross-artifact Change Impact Analysis.

## 12. Artifact Creation Rule

Artifacts exist because they solve concrete analytical problems.

The Portfolio Artifact Coverage Matrix defines expected emphasis using
Primary, Supporting, and Not Used.

The matrix is a scope-control baseline, not a mechanical production
checklist.

> **Analytical Need → Justified Artifact → Appropriate Depth → Traceable
> Value**

An artifact is justified when it meaningfully supports clarification,
communication, decision-making, behavioral modeling, specification,
consistency, verification, delivery, release readiness, or change
analysis.

An artifact must not exist solely to increase Portfolio size,
demonstrate a tool, fill a pre-created folder, satisfy a template, or
reproduce information already owned elsewhere.

An artifact classified as `Not Used` may be introduced if analysis
establishes a concrete need and its impact is understood.

## 13. Tool Selection Rule

Tool selection is driven by analytical need.

``` text
Discovery / Requirements
→ Confluence + Jira

Process Modeling
→ Camunda Modeler / BPMN

UML / C4 / ERD
→ PlantUML / draw.io

REST API
→ OpenAPI + Bruno / Postman

Relational Data
→ PostgreSQL + DBeaver

Event-Driven Integration
→ Kafka + Kafka UI + AsyncAPI

Cache
→ Redis + Redis Insight

Document Persistence
→ MongoDB + MongoDB Compass

Portfolio Versioning
→ Git + GitHub

Repeatable Analytical Operations
→ Python when automation is justified
```

A technology must not be introduced merely because it is installed or
because the Portfolio aims to demonstrate broad tooling.

## 14. Manual First, Automation Second

Analytical semantics and workflow are established manually before
automation is introduced.

``` text
Understand Manually
→ Perform Manually
→ Verify Semantics
→ Identify Repetition / Risk / Inefficiency
→ Automate When Useful
```

Automation may be added when the manual process is understood, inputs
and outputs are sufficiently stable, repeated work creates a meaningful
opportunity, and automation improves quality, speed, repeatability, or
consistency without obscuring analytical reasoning or Decision
Ownership.

Python and other automation tools support the analytical workflow; they
do not replace analysis or specialized professional tools.

## 15. Review and Acceptance Discipline

Analytical content is reviewed at a level appropriate to its impact.

Review may involve Product Owner / Business Owner, Domain SME, Solution
Architect, Developers / Tech Lead, DBA / Data Engineer, Security, QA,
and Operations / SRE according to their responsibilities.

The analyst coordinates review and incorporates accepted outcomes.

Acceptance is determined by the appropriate owner or review process, not
by the storage platform.

A Confluence page, Jira status, Git commit, merge, or tag must not be
treated as a substitute for stakeholder approval where stakeholder
approval is required.

## 16. Execution Efficiency Rule

> **Do not stop case progression to perfect infrastructure, templates,
> folder structures, governance mechanisms, or formatting when the
> current state is already sufficient for professional analytical
> work.**

Prefer meaningful analytical increments:

``` text
Lifecycle Stage
→ Stakeholder Interaction
→ Analysis
→ Related Analytical Outcomes
→ Necessary Artifact Updates
→ Verification
→ Next Meaningful Step
```

Avoid fragmentation such as:

``` text
One Small Question
→ Separate Governance Discussion
→ Template Redesign
→ New Empty Artifact
→ Separate Git Ceremony
→ Next Small Question
```

Efficiency rules:

- combine related analytical actions belonging to the same meaningful
  increment;
- do not create empty folders or pages in anticipation of future work;
- do not create templates before a real use case requires them;
- do not polish professionally sufficient wording through unnecessary
  iterations;
- do not perform Git ceremony after every minor edit;
- do not introduce integrations without an immediate need;
- do not repeat accepted Portfolio rules unless new evidence requires a
  change;
- move to the next analytical step after sufficient verification.

Speed does not justify invented requirements, undocumented assumptions,
incorrect Decision Ownership, weak traceability, contradictory
artifacts, semantically incorrect models, or artificial use of
technologies.

## 17. Operational Working Loop

``` text
Incomplete Context
        ↓
Known vs Unknown
        ↓
Current Lifecycle Stage
        ↓
Analyst Objective
        ↓
Stakeholder / Decision Owner
        ↓
Question
        ↓
Answer / Decision
        ↓
Classification
        ↓
Persistence
        ↓
Justified Artifact Update
        ↓
Traceability / Consistency Review
        ↓
Practical Verification
        ↓
Next Meaningful Step
        ↓
Feedback / Change
        ↺
```

Feedback or change may reopen questions, invalidate assumptions, require
a new decision, or trigger Change Impact Analysis.

The Working Model complements rather than duplicates the Analyst
Delivery Lifecycle:

- the lifecycle determines the stage of work;
- the Working Model determines how analytical knowledge moves through
  that stage;

The quality target is not maximum documentation volume.

The target is:

> **Analytical Decision + Traceable Requirement + Verifiable
> Specification + Clear Delivery Workflow + Controlled Change Impact**

## 18. Operating Principles

1.  **Progressive disclosure over invented completeness.**
2.  **Explicit Decision Ownership over analyst overreach.**
3.  **Analytical need over artifact checklist.**
4.  **Single responsibility over duplicated management documentation.**
5.  **Purpose-driven persistence over copying information between
    tools.**
6.  **Traceability over isolated artifacts.**
7.  **Manual understanding over premature automation.**
8.  **Demand-driven tooling over technology demonstration.**
9.  **Meaningful analytical increments over process ceremony.**
10. **Speed without sacrificing semantic quality.**
