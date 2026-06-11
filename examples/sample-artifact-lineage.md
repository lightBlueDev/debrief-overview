# Sample Artifact Lineage

This example shows how Debrief can represent the lineage of a published artifact without exposing private internal records.

## Purpose

Lineage matters because a reviewer should be able to understand how an artifact became trustworthy enough for downstream use.

## Sanitized Example

```yaml
artifact_id: "artifact.public.summary.01"
artifact_type: "canonical_summary"

upstream_inputs:
  - input_id: "input.public.repo-target"
    role: "workflow target"
  - input_id: "input.public.orientation-notes"
    role: "derived analysis input"

workflow_transitions:
  - step: "resolve_target"
    result: "completed"
  - step: "collect_public_inputs"
    result: "completed"
  - step: "derive_summary_draft"
    result: "completed"
  - step: "publish_canonical_summary"
    result: "completed"

publication_state:
  authority: "published"
  supersedes: null
  downstream_safe_for:
    - "reviewer orientation"
    - "public documentation linkage"
```

## Reviewer Interpretation

This lineage tells a reviewer that the artifact was not simply emitted. It was produced by a specific workflow, from known upstream inputs, and moved through explicit publication steps before being considered authoritative.
