# Sample Canonical Summary

This example shows the public-facing shape of a canonical summary artifact produced by the runtime.

## Purpose

The canonical summary is the artifact a downstream reviewer should be able to trust as the current authoritative high-level statement of a run's result.

## Sanitized Example

```yaml
artifact_id: "artifact.public.summary.01"
artifact_type: "canonical_summary"
run_id: "run_public_2026_06_11_03"
published_at: "2026-06-11T15:43:12Z"
authority_state: "published"

summary:
  target: "sanitized repository snapshot"
  outcome: "public-facing architecture summary drafted"
  reviewer_use: "orientation and downstream evaluation"

high_level_findings:
  - "workflow completed repository orientation before summary generation"
  - "artifact publication remained tied to durable run state"
  - "resume boundary was preserved when human confirmation was required"

limitations:
  - "summary excludes private implementation details"
  - "artifact reflects the public-scope run, not the full private workspace"
```

## What Makes It Canonical

An artifact becomes more useful when the runtime can tell a reviewer:

- why it exists
- what run produced it
- whether it is authoritative
- what its limitations are

That is the difference between a durable runtime artifact and an orphaned output blob.
