# Session Bootstrap

This project uses a modular requirements repository.

## Primary Objectives

- Keep root context small.
- Decompose requirements progressively.
- Store detailed requirements in subsystem-specific files.
- Store cross-subsystem boundaries in interface contract files.
- Track every durable requirement using stable IDs.
- Convert requirements into Codex tasks only when they are testable.
- Give Codex only the minimum relevant context for the current task.

## Canonical Documents

Start new sessions by reviewing these documents first:

- `requirements/00-project/product-brief.md`
- `requirements/00-project/project-operating-model.md`
- `requirements/01-architecture/subsystem-map.md`
- `requirements/02-global-requirements/non-functional-requirements.md`
- `requirements/06-traceability/requirement-index.md`

## Working Rule

Do not load every requirements document by default. Load the smallest set of documents needed for the current question or task.

## Current Project Phase

Requirements capture, decomposition, architectural subsystem discovery, and Codex task preparation.
