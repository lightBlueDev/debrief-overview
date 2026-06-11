# Sample Run State

This example shows a public-facing shape for durable run state in Debrief.

## Purpose

A run record should let a reviewer understand:

- what workflow is active
- what state it reached
- what artifacts exist
- what failed or paused
- where safe resumption begins

## Sanitized Example

```yaml
run_id: "run_public_2026_06_11_03"
created_at: "2026-06-11T15:04:00Z"
updated_at: "2026-06-11T15:42:18Z"
runtime_status: "paused"

workflow:
  workflow_id: "repo-analysis-public"
  workflow_version: "public-slice-1"
  phase: "artifact_publication"
  active_step: "publish_canonical_summary"

progression:
  completed_steps:
    - "resolve_target"
    - "collect_public_inputs"
    - "derive_summary_draft"
  pending_steps:
    - "publish_canonical_summary"
    - "mark_run_complete"

artifacts:
  canonical_summary:
    artifact_id: "artifact.public.summary.01"
    authority: "draft_ready"
  lineage_record:
    artifact_id: "artifact.public.lineage.01"
    authority: "published"

failure_surface:
  last_failure: null
  warnings:
    - "publication paused awaiting reviewer confirmation"

resume_boundary:
  resumable: true
  resume_from: "publish_canonical_summary"
  required_inputs:
    - "approved summary content"
```

## Why This Matters

This kind of state makes the runtime authoritative even when the original session is gone. A new operator or tool can orient from state instead of reconstructing context from memory.
