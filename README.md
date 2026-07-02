# FieldGuide42

## Developer Workflow

This project uses a requirements-first workflow. Requirements, architecture, interface contracts, acceptance criteria, and traceability must be established before application code is written.

The purpose of this workflow is to prevent implementation drift, reduce AI context size, preserve architectural control, and make every Codex task traceable to approved requirements.

### Starting A New Development Session

This project uses a requirements-first workflow. Every new development or AI-assisted coding session must begin by loading only the documents needed to understand the current task.

Do not load the entire requirements repository by default.

#### Required For Every Session

Every session must review:

1. `requirements/00-project/session-bootstrap.md`

This file explains how to rehydrate the project context and identifies the current requirements-management workflow.

#### Required For An Implementation Session

Before writing or modifying application code, the session must also review:

1. The active Codex task packet for the work being performed.

2. The relevant subsystem requirements file, for example:

   ```text
   requirements/03-subsystems/<subsystem-name>/requirements.md
   ```

3. The relevant subsystem Codex context file, if it exists:

   ```text
   requirements/03-subsystems/<subsystem-name>/codex-context.md
   ```

4. Any interface contract documents referenced by the task packet, such as:

   ```text
   requirements/04-interfaces/api-contracts.md
   requirements/04-interfaces/event-contracts.md
   requirements/04-interfaces/database-contracts.md
   requirements/04-interfaces/file-format-contracts.md
   ```

5. Any global standards referenced by the task packet, such as:

   ```text
   requirements/02-global-requirements/coding-standards.md
   requirements/02-global-requirements/testing-standards.md
   requirements/02-global-requirements/error-handling.md
   requirements/02-global-requirements/security-requirements.md
   ```

#### Required For A Requirements Or Architecture Session

If the session is about capturing, decomposing, or changing requirements, review:

1. `requirements/00-project/session-bootstrap.md`
2. `requirements/00-project/project-operating-model.md`
3. `requirements/00-project/product-capabilities.md`
4. `requirements/06-traceability/capability-index.md`
5. Any relevant subsystem requirement files.

If the session may affect subsystem boundaries, also review:

```text
requirements/01-architecture/subsystem-map.md
requirements/01-architecture/data-ownership.md
```

#### Required For A Traceability Or Status Check

If the session is about requirement status, implementation readiness, test coverage, or completed work, review:

```text
requirements/06-traceability/requirement-index.md
requirements/06-traceability/requirement-status.md
requirements/06-traceability/test-matrix.md
requirements/05-codex/implementation-log.md
```

#### Conditional Reference Documents

These documents are not required for every session. Load them only when the task needs them:

| Document | Load When |
|---|---|
| `requirements/00-project/project-operating-model.md` | The workflow, decomposition process, or requirement rules are unclear. |
| `requirements/00-project/product-brief.md` | The task depends on product scope or project objectives. |
| `requirements/01-architecture/subsystem-map.md` | The task affects subsystem ownership, boundaries, or architecture. |
| `requirements/06-traceability/requirement-index.md` | The task needs to verify requirement IDs, status, ownership, or test coverage. |
| `requirements/02-global-requirements/security-requirements.md` | The task involves authentication, authorization, sensitive data, roles, permissions, or access control. |
| `requirements/02-global-requirements/error-handling.md` | The task changes failure behavior, validation, exceptions, or user-facing errors. |
| `requirements/02-global-requirements/testing-standards.md` | The task adds or modifies tests. |
| `requirements/04-interfaces/*` | The task crosses subsystem boundaries or changes an API, event, database, or file contract. |

#### Minimum Context Rule

For implementation work, the minimum context is:

```text
session-bootstrap.md
+ active Codex task packet
+ relevant subsystem requirements.md
+ relevant subsystem codex-context.md, if present
+ referenced interface contracts
+ referenced global standards
```

If those documents do not provide enough information to implement safely, stop and update the requirements or task packet before writing code.

### Requirements Before Code

No application code should be written until the work is tied to documented requirements.

Before implementation begins, confirm that the task has:

- One or more requirement IDs.
- Clear source requirement documents.
- Defined subsystem ownership or a documented reason ownership is still undecided.
- Acceptance criteria.
- Test expectations.
- Known files to inspect.
- Known files to create or modify.
- Explicit constraints and out-of-scope items.

If these items are missing, the correct next step is requirements capture, requirements decomposition, interface definition, or task-packet creation. The correct next step is not implementation.

### Development Workflow

Use this sequence:

1. Capture broad product capabilities in `requirements/00-project/product-capabilities.md`.
2. Track capabilities in `requirements/06-traceability/capability-index.md`.
3. Decompose capabilities into formal requirements with stable IDs.
4. Assign requirements to candidate or approved subsystems.
5. Define interface contracts where subsystem boundaries exist.
6. Add acceptance criteria and test expectations.
7. Create a Codex task packet using `requirements/05-codex/task-template.md`.
8. Implement only the approved task packet.
9. Add or update tests.
10. Update traceability documents after implementation.

### Codex Task Rule

Codex should receive only the minimum context needed for the current task.

A Codex implementation prompt should usually reference:

- The task objective.
- Relevant requirement IDs.
- Relevant subsystem documents.
- Relevant interface contracts.
- Applicable coding standards.
- Applicable testing standards.
- Files to inspect.
- Files to create or modify.
- Acceptance criteria.
- Tests required.
- Things not to change.

Codex must not infer broad architecture from vague instructions. If a requirement, interface, or subsystem boundary is unclear, clarify or document the ambiguity before implementation.

### Traceability Rule

Every durable requirement should be traceable from:

```text
Product Capability
   -> Requirement
      -> Subsystem
         -> Codex Task
            -> Test
               -> Implementation
```

When implementation work is completed, update the relevant traceability files.

### Current Project Phase

The project is currently in requirements capture, decomposition, architectural subsystem discovery, and Codex task preparation.

Application implementation should begin only after requirements are sufficiently decomposed and a Codex task packet is approved.
