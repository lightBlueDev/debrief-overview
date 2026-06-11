# Overview

Debrief is a continuity runtime for AI-assisted software work.

It exists to make orchestration state durable, inspectable, and resumable across sessions, workflows, tools, and handoffs.

## Public Framing

This repository is a documentation-first overview of a private implementation effort. It is designed to show the runtime model clearly enough for serious evaluation while maintaining the distinction between public architecture and private build surface.

Debrief should not be interpreted as:

- a chat wrapper
- a prompt library
- a generalized multi-agent branding exercise
- a single-purpose analysis tool with persistence bolted on later

It should be understood as a runtime system concerned with continuity truth.

## Problem Statement

AI-assisted engineering often fails in the gap between sessions.

Typical breakdowns include:

- work that cannot be resumed cleanly
- artifacts that lose their relationship to the workflow that produced them
- failure states that are recorded informally instead of operationally
- handoffs that depend on memory instead of authoritative state

Debrief exists to close that gap by making runtime state the durable source of orchestration truth.
