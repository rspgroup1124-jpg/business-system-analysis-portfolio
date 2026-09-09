# Localization Policy

## Purpose

This document defines the language and localization rules for the
Business/System Analysis Portfolio.

The objective is to keep analytical content natural and professionally
readable while preserving the precision of standard notation, technical
contracts, identifiers, and established professional terminology.

Localization must support clarity. It must not create artificial
Russian/English mixtures or reduce technical accuracy.

## 1. Core Principle

Analytical content should read as natural professional Russian.

English terminology is retained selectively, not automatically. It is
appropriate when a term is:

-   the established name of a role or artifact;
-   the name of a standard, technology, protocol, or product;
-   a stable professional term whose translation would reduce precision
    or sound unnatural;
-   a machine-readable construct;
-   a technical identifier.

If a concept has a clear, natural, and unambiguous Russian equivalent,
the Russian form should normally be used in analytical prose.

For example:

-   delivery option → способ доставки;
-   checkout → оформление заказа;
-   pickup point → пункт выдачи;
-   delivery address → адрес доставки;
-   payment method → способ оплаты;
-   order status → статус заказа.

The objective is semantic consistency and readability, not maximum
preservation of English vocabulary.

## 2. Analytical Content

Business-facing and analytical narrative is written primarily in
Russian.

This includes, where applicable:

-   Business Requirements;
-   Functional Requirements;
-   Non-Functional Requirements;
-   Business Rules;
-   Acceptance Criteria;
-   process descriptions;
-   scenario descriptions;
-   meeting and workshop notes;
-   decision rationale;
-   assumptions;
-   constraints;
-   risks;
-   dependencies;
-   change-impact explanations.

Example:

> Пользователь должен иметь возможность увидеть доступные способы
> доставки для указанного адреса до подтверждения заказа.

Avoid unnecessary mixed-language phrasing when a natural Russian
formulation exists.

## 3. Professional Terminology

English professional terms may remain in the text when they are
established and useful for precise communication.

Examples may include:

-   Product Owner;
-   System Analyst;
-   Stakeholder;
-   Discovery;
-   Scope;
-   User Story;
-   Acceptance Criteria;
-   Change Request;
-   Impact Analysis;
-   API;
-   endpoint;
-   payload;
-   retry;
-   DLQ.

This is not a mandatory English-term list. Context and readability take
precedence.

A term should not remain in English merely because it is commonly used
in IT if its use makes the sentence harder to read.

Terminology adopted within a case should be used consistently and, where
necessary, defined in the case Glossary.

## 4. Artifact and Entity Names

Established artifact, role, issue-type, standard, and technology names
may remain in English when that form is established, precise, and
natural in the working context.

`May remain in English` does not mean `must remain in English`. The
choice should follow the Core Principle: preserve English where it
improves precision or reflects a canonical name, and prefer natural
Russian where translation preserves meaning and improves readability.

For example:

-   User Story;
-   Product Owner;
-   OpenAPI;
-   AsyncAPI;
-   BPMN;
-   Jira Story.

The content inside the artifact may still be Russian.

Example:

**Story**

Отображение доступных способов доставки при оформлении заказа.

Example User Story:

> Как покупатель, я хочу видеть доступные способы доставки для моего
> адреса, чтобы выбрать подходящий вариант до оформления заказа.

The artifact name and its content therefore follow different
localization rules when appropriate.

## 5. Standard and Machine-Readable Syntax

Standard syntax is not localized.

This includes:

-   PlantUML syntax;
-   Mermaid syntax where used;
-   OpenAPI keywords;
-   AsyncAPI keywords;
-   JSON and JSON Schema keywords;
-   SQL syntax;
-   HTTP methods and status codes;
-   BPMN element types where required by the notation or tool;
-   machine-readable configuration and contract syntax.

Examples:

``` yaml
openapi: 3.1.0
paths:
  /delivery-options:
    get:
```

``` sql
CREATE TABLE delivery_option (
    id BIGINT PRIMARY KEY
);
```

``` text
@startuml
actor Customer
@enduml
```

Localization must never make a standard or machine-readable artifact
invalid.

## 6. Technical Identifiers

Technical identifiers are written in English and use the conventions
appropriate to their technical context.

Examples:

-   `delivery_option`;
-   `pickup_point_id`;
-   `order_id`;
-   `DeliveryOption`;
-   `OrderCreated`;
-   `DELIVERY_NOT_AVAILABLE`;
-   `GET /delivery-options`.

This rule applies to:

-   API paths;
-   schema properties;
-   database tables and columns;
-   event names;
-   message fields;
-   error codes;
-   service and component identifiers;
-   code-facing names.

Cyrillic identifiers are not used in technical contracts.

A Russian specification may naturally reference an English identifier:

> Endpoint `GET /delivery-options` возвращает доступные способы доставки
> для указанного адреса.

## 7. Diagrams

Diagram localization depends on the semantic role of each element.

General rule:

-   canonical notation and syntax → standard English syntax;
-   business-facing labels → Russian where appropriate;
-   technical component names → English;
-   technical identifiers → English.

Business labels should remain readable to the target team without
changing the semantics of the notation.

Where PlantUML is selected as the canonical representation for a diagram
artifact, the canonical PlantUML source uses valid standard syntax and
the visualization is derived from that source.

Where another notation or modeling tool is the justified canonical
representation, its own standard syntax and semantic rules take
precedence.

In all cases, the visual representation must remain semantically
consistent with the canonical source or model.

Localization must not create a separate interpretation of the diagram.

## 8. Jira

Jira preserves standard issue types, workflow concepts, statuses, and
technical terminology where appropriate.

Issue summaries and descriptions should use natural Russian analytical
language unless there is a specific reason to use English.

Example:

**Issue Type:** Story

**Summary:** Отображение доступных способов доставки при оформлении
заказа

Avoid:

> Отображение доступных Delivery Options на Checkout

Technical identifiers inside Jira issues remain unchanged.

## 9. Confluence

Confluence working knowledge is written primarily in natural
professional Russian.

English terms are retained where they represent established professional
concepts, artifact names, technologies, standards, or technical
identifiers.

The same terminology rules used in accepted Git baselines should be
applied to evolving Confluence content to reduce semantic drift.

## 10. Git and Public Portfolio Layer

Repository-level public and governance documents may be maintained in
English when their primary purpose is external portfolio presentation or
repository navigation.

This includes the current portfolio-level baseline documents such as:

-   root `README.md`;
-   `PORTFOLIO_OVERVIEW.md`;
-   `ARTIFACT_COVERAGE_MATRIX.md`;
-   `ANALYST_DELIVERY_LIFECYCLE.md`;
-   `WORKING_MODEL.md`;
-   `LOCALIZATION_POLICY.md`;
-   `TOOLING_BASELINE.md`.

Case-level analytical content is primarily Russian unless the artifact
itself requires standard English syntax or technical identifiers.

The choice of English for repository-level presentation does not require
case analysis to be conducted in English.

## 11. Glossary and Terminology Consistency

Localization Policy and Glossary serve different purposes.

Localization Policy defines how language is selected and how standard or
technical terminology is preserved.

A case Glossary defines what domain terms mean in that specific context.

When a domain term has been normalized in the Glossary, the approved
term should be used consistently across:

-   requirements;
-   Business Rules;
-   processes;
-   diagrams;
-   API descriptions;
-   data models;
-   Acceptance Criteria;
-   test scenarios;
-   Jira;
-   Confluence;
-   Git baselines.

Terminology changes should trigger review of affected artifacts when
they may alter meaning or create ambiguity.

## 12. Quality Rules

Before accepting an analytical artifact, verify that:

1.  the text reads naturally in its primary language;
2.  English terminology is used intentionally rather than mechanically;
3.  a clear Russian equivalent is preferred where it improves
    readability without losing precision;
4.  standard syntax remains valid and unchanged;
5.  technical identifiers remain stable and English-based;
6.  the same domain concept is named consistently across artifacts;
7.  translation or localization has not changed the analytical meaning.

The governing principle is:

**Natural analytical language + consistent domain terminology +
canonical technical syntax + stable technical identifiers.**
