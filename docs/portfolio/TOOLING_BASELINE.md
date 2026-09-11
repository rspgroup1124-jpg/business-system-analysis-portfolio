# Tooling Baseline

## Purpose

This document defines the approved workstation, collaboration platforms,
modeling tools, specification standards, verification utilities, data
technologies, runtime infrastructure, and automation capabilities
available to support the Business/System Analysis Portfolio.

The baseline separates two independent questions:

1.  **Environment Status** — whether a tool is available, configured, or
    practically verified.
2.  **Usage Classification** — whether the tool belongs to the normal
    working environment or should be introduced only when a specific
    analytical need justifies it.

A tool being installed, configured, or verified does **not** make its
use mandatory in any case.

> **Tool selection is driven by analytical need.**

------------------------------------------------------------------------

## 1. Tool Usage Principles

The following principles govern tooling decisions:

1.  A tool is used only when it supports a concrete analytical,
    modeling, specification, verification, delivery, or reproducibility
    need.
2.  Availability does not imply required usage.
3.  Case scope and analytical need determine the appropriate tool and
    depth of use.
4.  Canonical specifications and machine-readable artifacts must remain
    valid in their native formats.
5.  Tools must not replace explicit Decision Ownership.
6.  Verification tooling supports specifications; it does not become the
    specification itself.
7.  Information is stored according to the responsibility of the
    relevant workspace rather than copied across tools without need.
8.  Automation is introduced only after the underlying manual process is
    understood.
9.  Specialized technologies are introduced when the problem requires
    them, not merely because they are available.
10. Tooling must support analytical progress rather than become a
    separate delivery objective.

------------------------------------------------------------------------

## 2. Status Model

### 2.1 Environment Status

| Status         | Meaning                                                             |
|----------------|---------------------------------------------------------------------|
| **Available**  | Installed or otherwise accessible in the working environment.       |
| **Configured** | Available and configured sufficiently for intended use.             |
| **Verified**   | Configuration and essential behavior have been practically checked. |

A higher status implies the preceding states.

### 2.2 Usage Classification

| Classification                    | Meaning                                                                                                                                         |
|-----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| **Core**                          | Part of the normal working environment and expected to support multiple cases.                                                                  |
| **Case-Driven**                   | Used only when a case establishes a concrete analytical, modeling, specification, or verification need.                                         |
| **Optional / Need-Driven**        | Used for a specific task when it provides clear additional value.                                                                               |
| **Not Planned for Case Workflow** | Available or configured in the environment but intentionally excluded from the normal case workflow unless a future need changes that decision. |

Environment Status and Usage Classification must not be conflated.

For example, a tool may be fully configured while still being
`Not Planned for Case Workflow`.

------------------------------------------------------------------------

## 3. Core Workstation

**Purpose:** provide a stable and reproducible local working
environment.

| Tool       | Environment Status | Usage    | Analyst Use                                                                              |
|------------|--------------------|----------|------------------------------------------------------------------------------------------|
| Windows 11 | **Verified**       | **Core** | Primary workstation environment                                                          |
| PowerShell | **Verified**       | **Core** | Repository navigation, file operations, CLI execution, environment checks                |
| VS Code    | **Verified**       | **Core** | Edit Markdown, YAML, JSON, SQL, PlantUML, specifications, and other file-based artifacts |

Working directories, commands, file locations, and reproducible
operations should be explicit when local execution is part of the
analytical workflow.

------------------------------------------------------------------------

## 4. Repository and Versioning

**Purpose:** preserve Portfolio files, canonical file-based artifacts,
meaningful version history, and milestone states.

| Tool   | Environment Status | Usage    | Analyst Use                                                     | Typical Output / Evidence                             |
|--------|--------------------|----------|-----------------------------------------------------------------|-------------------------------------------------------|
| Git    | **Verified**       | **Core** | Inspect and version Portfolio file changes                      | Commits, diffs, tags, history                         |
| GitHub | **Verified**       | **Core** | Remote repository, Portfolio publication, repository navigation | Published repository, remote history, milestone state |

Git/GitHub are used for:

- Portfolio repository content;
- file-based analytical artifacts;
- canonical technical files where appropriate;
- meaningful version history;
- milestone tags;
- publication and presentation of the Portfolio.

Git is **not** the mandatory system of record for all day-to-day
analytical knowledge.

A commit, merge, or tag records repository state. It does not replace
stakeholder approval, a business decision, architecture approval, or
another form of Decision Ownership.

------------------------------------------------------------------------

## 5. Collaboration and Delivery

**Purpose:** separate delivery management from collaborative analytical
knowledge.

| Platform         | Environment Status | Usage    | Analyst Use                                 | Typical Output                                                                                               |
|------------------|--------------------|----------|---------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| Jira Cloud       | **Verified**       | **Core** | Manage delivery work and workflow state     | Epics, Stories, Tasks, Bugs, Change Requests, backlog state                                                  |
| Confluence Cloud | **Verified**       | **Core** | Maintain collaborative analytical knowledge | Initiative, Discovery, Scope, Requirements, Business Rules, Meeting Notes, review and specification material |

Current collaboration environment includes:

- Jira workspace `Analyst Portfolio`;
- configured Scrum workflow;
- Confluence Portfolio space;
- Case 1 Confluence workspace.

### Persistence Model

``` text
Jira
└── Delivery Management

Confluence
└── Working Analytical Knowledge

Git / GitHub
└── Portfolio Files / Version History / Milestones
```

Complete analytical content should not be fragmented across platforms
without a clear responsibility or reference model.

### Configured Communication Environment

Slack is installed and configured, and Jira integration has been
verified.

| Tool                 | Environment Status | Usage                             |
|----------------------|--------------------|-----------------------------------|
| Slack                | **Verified**       | **Not Planned for Case Workflow** |
| Jira Cloud for Slack | **Verified**       | **Not Planned for Case Workflow** |

These capabilities are recorded as part of the prepared environment
only. They are not part of the planned analytical workflow for the three
cases.

------------------------------------------------------------------------

## 6. Modeling

**Purpose:** express processes, behavior, boundaries, interactions, data
relationships, and explanatory views using the notation appropriate to
the analytical problem.

| Tool            | Environment Status | Usage           | Analyst Use                                                 | Typical Output                                         |
|-----------------|--------------------|-----------------|-------------------------------------------------------------|--------------------------------------------------------|
| PlantUML        | **Verified**       | **Core**        | Canonical diagram-as-code for supported analytical diagrams | `.puml` source and derived visualization               |
| draw.io         | **Verified**       | **Case-Driven** | Manual visual modeling where layout control adds value      | Architecture, context, process, or explanatory diagram |
| Camunda Modeler | **Verified**       | **Case-Driven** | BPMN modeling and validation                                | BPMN model and source                                  |
| Graphviz        | **Verified**       | **Supporting**  | Rendering support for diagram tooling where required        | Rendered graph/diagram support                         |
| Java            | **Verified**       | **Supporting**  | Runtime support for PlantUML and related tooling            | Reproducible diagram generation                        |

`Supporting` in this section means a technical dependency of an
analytical tool rather than a standalone case activity.

### Diagram Artifact Standard

Where PlantUML is selected as the canonical representation, a diagram
artifact maintains three semantically consistent views:

1.  textual description;
2.  canonical PlantUML source;
3.  visualization derived from the canonical source.

The visualization must not become an independent source of analytical
facts.

For BPMN, Camunda Modeler may be preferred when BPMN-specific notation
and validation provide greater analytical value. In that case, the BPMN
model and BPMN semantics form the canonical representation.

------------------------------------------------------------------------

## 7. API and Integration

**Purpose:** specify and verify synchronous and asynchronous system
contracts.

### Contract Specification

| Tool / Standard | Environment Status | Usage           | Analyst Use                                       | Typical Output                               |
|-----------------|--------------------|-----------------|---------------------------------------------------|----------------------------------------------|
| OpenAPI tooling | **Verified**       | **Case-Driven** | Specify and validate REST API contracts           | OpenAPI YAML                                 |
| AsyncAPI CLI    | **Verified**       | **Case-Driven** | Validate asynchronous/event-driven specifications | AsyncAPI specification and validation output |

OpenAPI and AsyncAPI are canonical contract formats when their
respective interaction styles are justified.

### Interaction and Verification

| Tool    | Environment Status | Usage           | Analyst Use                                                  | Typical Output / Evidence        |
|---------|--------------------|-----------------|--------------------------------------------------------------|----------------------------------|
| Bruno   | **Verified**       | **Case-Driven** | Execute and verify API requests using file-based collections | Requests, collections, responses |
| Postman | **Verified**       | **Case-Driven** | Explore, execute, and verify API behavior where useful       | Collections, requests, responses |

Bruno and Postman support interaction and verification. They do not
replace OpenAPI or another canonical contract specification.

Using both API clients for the same task is not required. The client is
selected according to the task.

------------------------------------------------------------------------

## 8. Relational Data

**Purpose:** model, inspect, and verify relational data behavior when
justified by the case.

| Tool / Technology | Environment Status | Usage           | Analyst Use                                                        | Typical Output / Evidence                           |
|-------------------|--------------------|-----------------|--------------------------------------------------------------------|-----------------------------------------------------|
| PostgreSQL        | **Verified**       | **Case-Driven** | Validate relational structures, constraints, DDL, and SQL behavior | Schemas, DDL, queries, test data                    |
| DBeaver           | **Verified**       | **Case-Driven** | Inspect schemas and execute database operations                    | Schema inspection, query results, data verification |

PostgreSQL is introduced when relational modeling, persistence behavior,
or SQL verification is part of the analytical problem.

------------------------------------------------------------------------

## 9. Event-Driven Messaging

**Purpose:** analyze and practically verify event-driven communication
when asynchronous behavior is justified.

| Tool / Technology | Environment Status | Usage           | Analyst Use                                                             | Typical Output / Evidence                    |
|-------------------|--------------------|-----------------|-------------------------------------------------------------------------|----------------------------------------------|
| Kafka 4.3.1       | **Verified**       | **Case-Driven** | Analyze and verify event-driven communication                           | Topics, messages, producer/consumer behavior |
| Kafka UI          | **Verified**       | **Case-Driven** | Inspect topics, partitions, messages, consumer groups, offsets, and lag | Runtime inspection evidence                  |
| AsyncAPI CLI      | **Verified**       | **Case-Driven** | Validate event contract specifications                                  | AsyncAPI validation                          |

The environment has been practically verified for:

- producer / consumer interaction;
- partitions and keys;
- consumer groups;
- offsets;
- lag.

Kafka is introduced only when asynchronous or event-driven communication
is part of the system problem.

Before detailed event specification, relevant concerns should include
event meaning, producer, consumer, ownership, trigger, ordering
requirements, delivery semantics, idempotency, retry/failure handling,
replay, and observability where applicable.

------------------------------------------------------------------------

## 10. Cache

**Purpose:** analyze cache-related behavior when caching is a justified
system concern.

| Tool / Technology   | Environment Status | Usage           | Analyst Use                                      | Typical Output / Evidence           |
|---------------------|--------------------|-----------------|--------------------------------------------------|-------------------------------------|
| Redis 8             | **Verified**       | **Case-Driven** | Analyze and verify cache structures and behavior | Keys, values, TTL, runtime behavior |
| Redis Insight 3.4.2 | **Verified**       | **Case-Driven** | Inspect Redis data and behavior                  | Visual inspection and verification  |

Redis is introduced only when caching, expiration, temporary state, or
another Redis-appropriate concern is relevant to the analyzed solution.

------------------------------------------------------------------------

## 11. Document Persistence

**Purpose:** analyze document-oriented persistence when the case
establishes a justified need.

| Tool / Technology      | Environment Status | Usage           | Analyst Use                                            | Typical Output / Evidence          |
|------------------------|--------------------|-----------------|--------------------------------------------------------|------------------------------------|
| MongoDB 8.0.29         | **Verified**       | **Case-Driven** | Analyze and verify document structures and persistence | Collections, documents, queries    |
| MongoDB Compass 1.50.0 | **Verified**       | **Case-Driven** | Inspect collections, documents, and query behavior     | Visual inspection and verification |

The environment has been practically verified through connectivity and
document operations.

MongoDB is introduced only when document-oriented persistence is
justified by the system problem or an accepted technical decision.

------------------------------------------------------------------------

## 12. Runtime Infrastructure

**Purpose:** provide reproducible local dependencies for hands-on
verification.

| Tool           | Environment Status | Usage           | Analyst Use                                                    | Typical Output / Evidence             |
|----------------|--------------------|-----------------|----------------------------------------------------------------|---------------------------------------|
| Docker Desktop | **Verified**       | **Case-Driven** | Run local infrastructure required for analysis or verification | Containers and runtime environment    |
| Docker Compose | **Verified**       | **Case-Driven** | Coordinate multiple local dependencies                         | Reproducible multi-service definition |

Docker is infrastructure support, not an analytical deliverable.

A local container environment is justified when it enables contract,
database, messaging, cache, document persistence, or integration
verification.

------------------------------------------------------------------------

## 13. Supporting CLI and Runtime Toolchain

**Purpose:** provide supporting runtime and command-line capabilities
required by analytical tools and reproducible verification workflows.

| Tool         | Environment Status | Usage                        | Purpose                                              |
|--------------|--------------------|------------------------------|------------------------------------------------------|
| Node / npm   | **Verified**       | **Case-Driven / Supporting** | Runtime/package support for CLI tooling              |
| Java         | **Verified**       | **Supporting**               | PlantUML and related runtime support                 |
| Graphviz     | **Verified**       | **Supporting**               | Diagram rendering support                            |
| jq           | **Verified**       | **Case-Driven / Supporting** | Inspect and transform JSON in verification workflows |
| AsyncAPI CLI | **Verified**       | **Case-Driven**              | AsyncAPI validation and related CLI operations       |

Supporting tools are not independent analytical deliverables. They are
used when another justified activity requires them.

------------------------------------------------------------------------

## 14. Analytical Automation

**Purpose:** automate repetitive analytical or verification work after
the underlying process is understood.

| Tool   | Environment Status | Usage                      | Analyst Use                                          | Typical Output                                                |
|--------|--------------------|----------------------------|------------------------------------------------------|---------------------------------------------------------------|
| Python | **Verified**       | **Optional / Need-Driven** | Automate repetitive analytical or verification tasks | Scripts, validation output, transformations, generated checks |

The governing sequence is:

``` text
Manual Analytical Process
        ↓
Process Understood
        ↓
Stable Inputs and Outputs
        ↓
Repetition / Risk / Inefficiency Identified
        ↓
Automation Justified
        ↓
Python
```

Python supports analytical work. It does not replace analytical
reasoning, stakeholder decisions, canonical specifications, or
specialized tools.

Automation must have a concrete benefit such as improved repeatability,
consistency, speed, validation, or reduction of error-prone manual work.

------------------------------------------------------------------------

## 15. Tool Selection by Analytical Need

The following mapping is a practical default.

### Analytical Knowledge and Delivery

| Analytical Need                               | Preferred Tooling |
|-----------------------------------------------|-------------------|
| Maintain collaborative analytical knowledge   | Confluence        |
| Manage backlog and delivery state             | Jira              |
| Edit file-based artifacts                     | VS Code           |
| Execute local commands and verification steps | PowerShell        |
| Preserve Portfolio files and version history  | Git / GitHub      |

### Modeling

| Analytical Need                            | Preferred Tooling |
|--------------------------------------------|-------------------|
| Create canonical UML-style diagram source  | PlantUML          |
| Model BPMN processes                       | Camunda Modeler   |
| Create manually controlled visual diagrams | draw.io           |

### API and Integration

| Analytical Need                       | Preferred Tooling |
|---------------------------------------|-------------------|
| Specify REST contracts                | OpenAPI           |
| Execute REST requests                 | Bruno or Postman  |
| Specify asynchronous contracts        | AsyncAPI          |
| Inspect event-driven runtime behavior | Kafka / Kafka UI  |

### Data and Runtime

| Analytical Need                  | Preferred Tooling         |
|----------------------------------|---------------------------|
| Model and verify relational data | PostgreSQL / DBeaver      |
| Analyze cache behavior           | Redis / Redis Insight     |
| Analyze document persistence     | MongoDB / MongoDB Compass |
| Run local dependencies           | Docker / Docker Compose   |

### Automation

| Analytical Need                               | Preferred Tooling |
|-----------------------------------------------|-------------------|
| Automate justified repetitive analytical work | Python            |

This mapping is a default. A different tool may be used when a concrete
analytical need justifies it.

------------------------------------------------------------------------

## 16. Verification Evidence

Hands-on tool usage should produce evidence appropriate to the
analytical question being verified.

Depending on the task, evidence may include:

- canonical specification;
- validated source file;
- reproducible command and result;
- API request and response;
- SQL query and result;
- schema inspection;
- event or message example;
- consumer-group or runtime inspection;
- cache behavior;
- document query;
- test data;
- concise screenshot where visual evidence materially helps;
- issue, defect, clarification, or decision resulting from verification.

Evidence must be proportional to the task.

Screenshots are supporting evidence. They do not replace canonical
specifications, reproducible steps, or structured analytical
conclusions.

------------------------------------------------------------------------

## 17. Tool Introduction Rule

Before introducing a tool or technology into a case, establish:

1.  **Analytical Need** — What problem or uncertainty requires it?
2.  **Role** — What activity will the tool support?
3.  **Owner / User** — Which role uses or reviews the result?
4.  **Output** — What artifact, specification, verification result, or
    decision will it support?
5.  **Alternatives** — Can the need already be satisfied adequately by
    the current toolset?
6.  **Case Impact** — Does introducing it affect scope, dependencies,
    specifications, or the working environment?

If no concrete analytical value can be established, the tool should not
be introduced into the case.

------------------------------------------------------------------------

## 18. Baseline Evolution

This baseline may evolve when a case establishes a justified need.

A tool may be:

- added;
- configured further;
- practically verified;
- reclassified;
- removed from planned case usage.

Baseline changes should preserve:

- reproducibility;
- explicit purpose;
- compatibility with the Working Model;
- compatibility with the Localization Policy;
- consistency with the Artifact Coverage Matrix;
- separation between environment readiness and actual case usage.

The governing principle is:

> **Analytical need → appropriate tool → reproducible activity →
> meaningful artifact or verification evidence.**

------------------------------------------------------------------------

## Current Baseline Summary

The current environment is prepared for the planned analytical work
across the three cases.

### Verified Core Environment

- Windows 11;
- PowerShell;
- VS Code;
- Git / GitHub;
- Jira Cloud;
- Confluence Cloud.

### Verified Case-Driven Capabilities

- Docker Desktop / Docker Compose;
- PostgreSQL / DBeaver;
- Bruno / Postman;
- OpenAPI tooling;
- PlantUML / draw.io;
- Camunda Modeler;
- AsyncAPI CLI;
- Kafka 4.3.1 / Kafka UI;
- Redis 8 / Redis Insight 3.4.2;
- MongoDB 8.0.29 / MongoDB Compass 1.50.0;
- Node/npm;
- Java;
- Graphviz;
- jq.

### Verified Optional Automation Capability

- Python.

### Configured but Not Planned for Case Workflow

- Slack;
- Jira Cloud for Slack.

The existence of these capabilities does not predetermine which
technologies will appear in a case. Each case introduces only the tools
justified by discovered requirements, accepted decisions, modeling
needs, or verification needs.
