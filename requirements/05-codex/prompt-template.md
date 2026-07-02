# Codex Prompt Template

Use this template when directing Codex.

```text
Implement TASK-AREA-000.

Objective:
[Describe the implementation objective.]

Use these requirement sources:
- requirements/...

Requirement IDs:
- REQ-AREA-000
- NFR-...

Relevant interface contracts:
- requirements/04-interfaces/...

Applicable standards:
- requirements/02-global-requirements/coding-standards.md
- requirements/02-global-requirements/testing-standards.md
- requirements/02-global-requirements/error-handling.md

Files to inspect:
- [List files]

Files to create or modify:
- [List files]

Acceptance criteria:
- [List criteria]

Tests required:
- [List tests]

Constraints:
- Do not modify unrelated subsystems.
- Do not infer requirements not present in the referenced documents.
- Ask for clarification only when implementation would otherwise be unsafe or materially ambiguous.
```
