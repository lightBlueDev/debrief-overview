# Workflow Model

Debrief treats workflows as explicit runtime constructs rather than loose conventions.

## Workflow Identity

A workflow should be identifiable, inspectable, and resumable on its own terms. That includes knowing where it started, what state it reached, and what artifacts it produced along the way.

## Progression

Progression matters because continuity is not just about storing data. It is about preserving the meaning of where work stands.

The workflow model is designed to make it possible to answer:

- what step is active
- what step completed
- what failed
- what can safely resume next

## Resume Boundaries

Debrief emphasizes explicit resume boundaries over informal continuation. A strong resume boundary is anchored to authoritative state and artifacts rather than operator recollection.
