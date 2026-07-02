# Project Operating Model

## Purpose

This document defines how requirements, architecture, interface contracts, implementation tasks, and test traceability are managed for the Construction Software project.

## Core Principle

Keep the root context small, push detail into subsystem documents, and provide Codex only the minimum relevant context required for the current task.

## Document Layers

### Root Project Documents

Root project documents define the product vision, glossary, assumptions, system boundaries, and unresolved questions.

### Architecture Documents

Architecture documents define the current architectural understanding, subsystem boundaries, integration patterns, data ownership, deployment assumptions, and architectural decisions.

### Global Requirements

Global requirements apply across the system. These include security, observability, error handling, testing, coding standards, and non-functional requirements.

### Subsystem Requirements

Each subsystem should eventually have its own requirements document, design notes, interface notes, test notes, and Codex context.

### Interface Contracts

Any boundary between subsystems should have an explicit contract document. This may include APIs, events, database ownership, file formats, schemas, and error behavior.

### Codex Task Packets

Codex should not receive the full repository as context unless necessary. Codex should receive the specific task, relevant requirement IDs, relevant subsystem documents, applicable interface contracts, coding standards, and test expectations.

### Traceability

Every durable requirement should have a stable ID. Requirements should be traceable to subsystem ownership, implementation tasks, acceptance criteria, and tests.

## Requirement ID Convention

Use stable IDs.

Examples:

- `REQ-PROD-001`
- `REQ-PROJECT-001`
- `REQ-DOCUMENT-001`
- `REQ-INVOICE-001`
- `REQ-SCHEDULE-001`
- `REQ-USER-001`
- `REQ-AUTH-001`
- `REQ-AUDIT-001`
- `REQ-REPORT-001`
- `NFR-SEC-001`
- `NFR-PERF-001`
- `NFR-OBS-001`
- `ADR-0001`
- `TASK-PROJECT-001`

Child requirements should preserve parent traceability.

Example:

```text
REQ-DOCUMENT-001
REQ-DOCUMENT-001.1
REQ-DOCUMENT-001.2
```

## Requirement Status Values

Use these statuses:

- Draft
- Needs Review
- Approved
- Decomposed
- Ready for Implementation
- In Implementation
- Implemented
- Tested
- Deferred
- Rejected
- Superseded

## Requirement Metadata

Each formal requirement should use this metadata block:

```markdown
ID:
Title:
Status:
Priority:
Owner:
Parent:
Source:
Risk:
Implementation Readiness:
Test Coverage:
```

## Requirement Decomposition Process

Use progressive elaboration.

1. Capture broad business capabilities.
2. Group capabilities into likely domains.
3. Identify subsystem boundaries.
4. Decompose broad requirements into functional requirements.
5. Add acceptance criteria.
6. Convert ready requirements into Codex tasks.
7. Implement only against approved task packets.
8. Update traceability after implementation.

## Subsystem Creation Rule

Create a subsystem when it has at least one of the following:

- Its own data ownership.
- Its own business rules.
- Its own security rules.
- Its own lifecycle.
- Its own external integration.
- Its own scaling or performance concern.
- A clear reason to isolate it from other responsibilities.

## Codex Context Rule

Each Codex task should include:

1. Task objective.
2. Relevant requirement IDs.
3. Relevant subsystem documents.
4. Relevant interface contracts.
5. Applicable coding standards.
6. Existing files to inspect.
7. Expected files to create or modify.
8. Acceptance criteria.
9. Tests to add or update.
10. Things not to change.

Codex must avoid modifying unrelated subsystems unless the task explicitly requires it.

## Source of Truth Rule

Do not treat one large document as the source of truth. Use the smallest applicable set of requirement, architecture, interface, and task documents.
