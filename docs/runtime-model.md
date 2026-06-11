# Runtime Model

Debrief is designed so the runtime, not the chat log, is authoritative for orchestration state.

## Runtime Responsibilities

The runtime is intended to own:

- run identity
- workflow identity
- step and task progression
- artifact publication
- failure recording
- safe resume boundaries

This separation keeps workflow logic from quietly becoming the system's only source of truth.

## Architectural Shape

```text
Debrief Runtime
    ->
Workflow
    ->
Artifacts, State, Resume Boundaries
```

The runtime should be able to explain what is happening even when no active session is present. That expectation is central to the project's value.
