# Architectural Decisions (`DECISIONS.md`)

This file is a running log of meaningful decisions made while building or changing this repository. It exists so human reviewers and future AI agents understand *why* the archive is structured the way it is.

## Rules for Maintaining This File
- **Log in real-time**: Record meaningful architecture decisions during the same session they are made.
- **Meaningful decisions only**: Architecture, hierarchy, naming, metadata, provenance, automation, storage, and workflow choices. Skip trivial formatting.
- **Newest entries go at the top.**
- **Post-processing is mandatory**: After processing a substantial repository change, update this file when a meaningful decision was made.

## Entry Template

### [YYYY-MM-DD] Short Title of Decision

**What changed:** One or two sentences describing the implementation change.

**Why this approach:** The reasoning and the problem solved.

**Alternatives considered:** Important alternatives and why they were rejected.

**Trade-offs & limitations:** What the decision costs or leaves unresolved.

---

<!-- New entries go above this line -->

### [2026-08-16] Rajasthan Exam Archive Scope and Naming

**What changed:** Rajasthan exams became the fixed scope of `exams/`, with no redundant `rajasthan/`, recruitment-type, or year directory by default. Exam/post directories preserve the supplied exam/post name when practical.

**Why this approach:** Avoids unnecessary nesting and preserves recognizable official naming for a human- and AI-readable archive.

**Alternatives considered:** English slugs, `rajasthan/` grouping, recruitment-type folders, and year folders were rejected as redundant default structure.

**Trade-offs & limitations:** Distinctions such as year and recruitment mode must be maintained in metadata and README files instead of path components.
