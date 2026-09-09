# Tooling Baseline

## Purpose

This document defines the approved workstation and toolset used across
the Business/System Analysis Portfolio.

The baseline describes why each tool or standard is used, what
analytical activity it supports, and what artifact or verification
evidence it may produce.

Presence in this baseline does not require use in every case.

**Tool selection is driven by analytical need.**

## 1. Tool Usage Principles

The portfolio follows these rules:

1.  A tool is introduced only when it supports a concrete analytical,
    specification, collaboration, or verification task.
2.  Tool usage must produce analytical value or verification evidence.
3.  A tool is not used solely to create portfolio screenshots or
    increase apparent technology coverage.
4.  Case-specific tooling must remain consistent with the Portfolio
    Artifact Coverage Matrix.
5.  Standard and machine-readable artifacts must remain valid in their
    canonical formats.
6.  Accepted analytical baselines are version-controlled where
    appropriate.
7.  Automation is introduced only after the underlying manual analytical
    process is understood.

## 2. Tool Status Model

Tools are classified by expected usage.

  -----------------------------------------------------------------------
  Status                              Meaning
  ----------------------------------- -----------------------------------
  **Core**                            Part of the normal portfolio
                                      operating environment and expected
                                      to be used across multiple cases.

  **Case-Driven**                     Introduced when the scope and
                                      analytical needs of a specific case
                                      justify it.

  **Optional / Need-Driven**          Used only when it provides clear
                                      value for a specific task. Presence
                                      in the baseline does not imply
                                      mandatory usage.
  -----------------------------------------------------------------------

## 3. Core Workstation

**Purpose:** create and maintain a reproducible local analytical working
environment.

  --------------------------------------------------------------------------
  Tool                    Status        Analyst Use         Typical Output /
                                                            Evidence
  ---------------- -------------------- ------------------- ----------------
  Windows 11             **Core**       Primary workstation Reproducible
                                        environment         local working
                                                            environment

  PowerShell             **Core**       Repository          Reproducible
                                        navigation, file    project
                                        operations, CLI     operations and
                                        execution,          command history
                                        environment checks

  VS Code                **Core**       Edit Markdown,      Analytical and
                                        YAML, JSON, SQL,    technical source
                                        PlantUML, and other files
                                        source-controlled
                                        artifacts
  --------------------------------------------------------------------------

File locations, commands, and project operations should be explicit and
reproducible.

## 4. Version Control

**Purpose:** maintain durable, reviewable history of accepted analytical
states.

  -----------------------------------------------------------------------
  Tool                    Status        Analyst Use      Typical Output /
                                                         Evidence
  ---------------- -------------------- ---------------- ----------------
  Git                    **Core**       Version accepted Commits, diffs,
                                        analytical       branches, tags,
                                        baselines and    history
                                        inspect changes

  GitHub                 **Core**       Remote           Repository
                                        repository,      history, pull
                                        portfolio        requests where
                                        navigation,      applicable,
                                        review, and      published
                                        publication of   portfolio
                                        accepted states
  -----------------------------------------------------------------------

Git is the durable accepted-baseline layer.

A commit records a meaningful versioned state, but it does not replace
stakeholder approval where approval is required.

## 5. Collaboration & Delivery

**Purpose:** separate delivery workflow from evolving collaborative
knowledge and durable accepted baselines.

  -----------------------------------------------------------------------
  Tool                    Status        Analyst Use      Typical Output /
                                                         Evidence
  ---------------- -------------------- ---------------- ----------------
  Jira                   **Core**       Manage delivery  Epics, Stories,
                                        work and         Tasks, Bugs,
                                        workflow state   Change Requests

  Confluence             **Core**       Maintain         Discovery notes,
                                        evolving         working
                                        collaborative    requirements,
                                        knowledge        meeting notes,
                                                         review material
  -----------------------------------------------------------------------

The persistence model is:

``` text
Jira
└── Delivery State

Confluence
└── Evolving Team Knowledge

Git
└── Durable Accepted Baseline
```

Complete analytical specifications should not be fragmented across tools
without a clear ownership and persistence rule.

## 6. Modeling

**Purpose:** express business processes, system behavior, boundaries,
interactions, and explanatory views using the notation appropriate to
the analytical problem.

  ------------------------------------------------------------------------
  Tool                    Status        Analyst Use       Typical Output /
                                                          Evidence
  ---------------- -------------------- ----------------- ----------------
  draw.io            **Case-Driven**    Visual modeling   Architecture,
                                        where manual      process,
                                        layout control    context, or
                                        adds value        explanatory
                                                          diagrams

  PlantUML               **Core**       Canonical         `.puml` source
                                        diagram-as-code   and derived
                                        for supported     visualization
                                        analytical
                                        diagrams

  Camunda Modeler    **Case-Driven**    BPMN modeling and BPMN process
                                        validation        model and BPMN
                                                          source
  ------------------------------------------------------------------------

Tool choice depends on analytical purpose and notation.

Where PlantUML is selected as the canonical representation for a diagram
artifact, the artifact maintains three semantically consistent views:

1.  textual description;
2.  canonical PlantUML source;
3.  visualization derived from the canonical source.

The visualization must not become an independent source of analytical
facts.

For BPMN, Camunda Modeler may be preferred when BPMN-specific modeling
and validation provide more value than generic diagram tooling. In that
case, the BPMN model and its standard semantics form the canonical
representation.

## 7. API & Integration

**Purpose:** specify and verify synchronous and asynchronous system
contracts.

### Contract Specification

  -----------------------------------------------------------------------
  Tool / Standard         Status        Analyst Use      Typical Output /
                                                         Evidence
  ---------------- -------------------- ---------------- ----------------
  OpenAPI            **Case-Driven**    Specify REST API OpenAPI YAML
                                        contracts        specification

  AsyncAPI           **Case-Driven**    Specify          AsyncAPI
                                        asynchronous and specification
                                        event-driven
                                        contracts
  -----------------------------------------------------------------------

### Interaction & Verification

  --------------------------------------------------------------------------
  Tool                    Status        Analyst Use         Typical Output /
                                                            Evidence
  ---------------- -------------------- ------------------- ----------------
  Bruno              **Case-Driven**    Execute and verify  Request
                                        API requests using  collections and
                                        source-controlled   verification
                                        collections         evidence

  Postman            **Case-Driven**    Explore, execute,   Collections,
                                        and verify API      requests,
                                        behavior where      responses,
                                        useful              verification
                                                            evidence
  --------------------------------------------------------------------------

OpenAPI and AsyncAPI define contracts.

Bruno and Postman support interaction and verification; they do not
replace contract specifications.

The verification client is selected by task. Using both clients for the
same work is not required.

## 8. Data & Distributed Systems

**Purpose:** analyze and verify persistence, messaging, ownership, and
runtime data behavior when these concerns are justified by the case.

### Relational Data

  -----------------------------------------------------------------------
  Tool /                  Status        Analyst Use      Typical Output /
  Technology                                             Evidence
  ---------------- -------------------- ---------------- ----------------
  PostgreSQL         **Case-Driven**    Validate         Schemas, DDL,
                                        relational data  queries, test
                                        structures and   data
                                        SQL behavior

  DBeaver            **Case-Driven**    Inspect and work Schema
                                        with relational  inspection,
                                        databases        query results,
                                                         data
                                                         verification
  -----------------------------------------------------------------------

### Messaging, Cache & Document Persistence

  -----------------------------------------------------------------------------
  Tool /                  Status        Analyst Use         Typical Output /
  Technology                                                Evidence
  ---------------- -------------------- ------------------- -------------------
  Kafka              **Case-Driven**    Analyze and verify  Topics, messages,
                                        event-driven        producer/consumer
                                        communication       verification
                                        concepts

  Redis              **Case-Driven**    Analyze             Cache structures,
                                        cache-related       TTL and behavior
                                        behavior where      verification
                                        justified

  MongoDB            **Case-Driven**    Analyze             Collections,
                                        document-oriented   document
                                        persistence where   structures, query
                                        justified           evidence
  -----------------------------------------------------------------------------

These technologies are not introduced for technology coverage:

-   **PostgreSQL** --- when relational data modeling or SQL verification
    is required.
-   **Kafka** --- when asynchronous or event-driven communication is
    justified.
-   **Redis** --- when cache behavior is part of the system problem.
-   **MongoDB** --- when a document-oriented persistence decision is
    relevant.

The Artifact Coverage Matrix controls expected depth by case.

## 9. Runtime & Local Environment

**Purpose:** provide reproducible local infrastructure when hands-on
verification requires real dependencies.

  ---------------------------------------------------------------------------
  Tool                    Status        Analyst Use      Typical Output /
                                                         Evidence
  ---------------- -------------------- ---------------- --------------------
  Docker             **Case-Driven**    Run local        Containers and
                                        infrastructure   reproducible service
                                        required for     environment
                                        analysis or
                                        verification

  Docker Compose     **Case-Driven**    Coordinate       Version-controlled
                                        multiple local   multi-service
                                        dependencies     environment
                                                         definition
  ---------------------------------------------------------------------------

Docker is infrastructure support, not an analytical deliverable by
itself.

A local container environment is justified when it enables contract,
database, messaging, cache, or integration verification.

## 10. Analytical Automation

**Purpose:** automate repetitive analytical or verification work only
after the underlying process is understood.

  -----------------------------------------------------------------------
  Tool                    Status        Analyst Use      Typical Output /
                                                         Evidence
  ---------------- -------------------- ---------------- ----------------
  Python               **Optional /     Automate         Scripts,
                      Need-Driven**     repetitive       generated
                                        analytical or    checks,
                                        verification     transformation
                                        tasks            or validation
                                                         output

  -----------------------------------------------------------------------

The governing sequence is:

``` text
Manual analytical process
        ↓
Process understood
        ↓
Stable inputs and outputs
        ↓
Repetitive task identified
        ↓
Automation justified
        ↓
Python
```

Python supports the analyst's workflow. It does not replace analytical
reasoning, stakeholder decisions, or ownership.

The portfolio remains separate from NovaMarket Toolkit and must not
evolve into another general-purpose analytical platform.

## 11. Tool Selection by Analytical Need

The mapping below is a practical lookup guide. It is grouped by work
area so that related tasks do not merge into one long undifferentiated
table.

### Repository & Collaboration

  Analytical Need                                   Preferred Tooling
  ------------------------------------------------- -------------------
  Edit and review source-controlled documentation   VS Code
  Execute local project and repository commands     PowerShell
  Inspect accepted changes and history              Git / GitHub
  Manage backlog and delivery state                 Jira
  Maintain evolving collaborative knowledge         Confluence

### Modeling & Contracts

  Analytical Need                              Preferred Tooling
  -------------------------------------------- -------------------
  Create canonical UML-style diagram source    PlantUML
  Model BPMN processes                         Camunda Modeler
  Create manually controlled visual diagrams   draw.io
  Specify REST contracts                       OpenAPI
  Specify asynchronous contracts               AsyncAPI
  Execute API requests                         Bruno or Postman

### Data, Integration & Runtime

  Analytical Need                    Preferred Tooling
  ---------------------------------- -------------------------
  Model and verify relational data   PostgreSQL / DBeaver
  Analyze event-driven messaging     Kafka
  Analyze cache behavior             Redis
  Analyze document persistence       MongoDB
  Run local infrastructure           Docker / Docker Compose

### Automation

  Analytical Need                      Preferred Tooling
  ------------------------------------ -------------------
  Automate justified repetitive work   Python

This mapping is a default, not a prohibition against other justified
choices.

## 12. Verification Evidence

**Purpose:** ensure that hands-on tool usage produces evidence that
another person can understand and, where applicable, reproduce.

Depending on the task, evidence may include:

-   version-controlled specification;
-   command and expected result;
-   request and response example;
-   SQL query and result;
-   schema inspection;
-   message or event example;
-   validated diagram source;
-   test data;
-   concise screenshot where visual evidence is genuinely useful;
-   recorded issue, defect, or decision resulting from verification.

Screenshots are supporting evidence, not a substitute for canonical
specifications or reproducible steps.

## 13. Tool Introduction Rule

Before introducing a new tool into a case, answer five questions:

1.  **Analytical problem** --- What problem are we solving?
2.  **Need** --- Why is the existing toolset insufficient?
3.  **Activity** --- What will the analyst do with the tool?
4.  **Result** --- What artifact, decision, or verification evidence
    will result?
5.  **Baseline impact** --- Does the tool affect the accepted
    workstation or case baseline?

If these questions cannot be answered, the tool should not be introduced
yet.

## 14. Baseline Evolution

This tooling baseline may evolve as the cases reveal justified needs.

A new tool or technology should be added only when its role is explicit.
A tool may also be removed if it no longer provides analytical value.

Changes to the baseline should preserve:

-   reproducibility;
-   clear tool ownership and purpose;
-   compatibility with the Working Model;
-   compatibility with the Localization Policy;
-   consistency with the Artifact Coverage Matrix.

The governing principle is:

**Analytical need → appropriate tool → reproducible activity →
meaningful artifact or verification evidence.**
