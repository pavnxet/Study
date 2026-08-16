# Ponytail Repository — Agent Instructions

This repository is the **canonical, instruction-only Ponytail knowledge base**.
Its purpose is to teach AI agents how to apply Ponytail methodology and its reusable skills. It is **not** a software package, runtime, MCP server implementation, plugin distribution, or installation project.

## 1. Mandatory behavior

When doing any work in this repository, **always use the canonical Ponytail skills**.

Do not bypass them because a task looks small. If a relevant skill exists, read and apply it before making the change.

The single source of truth is:

`ponytail/skills/`

## 2. Required workflow

For every repository task:

1. Identify the Ponytail skill(s) relevant to the task.
2. Read the complete applicable `SKILL.md` file(s) before editing.
3. Follow those instructions and their boundaries.
4. Make the smallest useful change that solves the request.
5. Check for duplication, contradictions, stale references, and unnecessary material.
6. Verify that the resulting instructions are clear enough for another AI agent to apply without guessing.
7. Keep the repository instruction-only and clean.

If multiple skills apply, use the smallest set that fully covers the task. When instructions conflict, prefer the more specific applicable skill.

## 3. Canonical skills

The canonical skills are:

- `ponytail/skills/ponytail/` — core Ponytail methodology
- `ponytail/skills/ponytail-audit/` — audit and compliance guidance
- `ponytail/skills/ponytail-review/` — review methodology
- `ponytail/skills/ponytail-debt/` — deliberate-shortcut/debt tracking
- `ponytail/skills/ponytail-help/` — Ponytail usage and guidance
- `ponytail/skills/ponytail-mcp/` — MCP-facing behavioral instructions only

These are the **only canonical skill locations**. Do not create parallel copies for Claude, Cursor, Codex, Cline, OpenCode, OpenClaw, or other platforms.

## 4. Repository scope

### Keep

- Reusable AI instructions
- Ponytail methodology and decision frameworks
- Canonical skill definitions
- Review, audit, verification, and debt-tracking instructions
- MCP behavioral/instruction definitions when they are useful to an AI agent
- Concise reference material that materially improves use of Ponytail

### Do not add back

- MCP/server implementation code
- Installation or setup guides
- Package managers or runtime dependencies
- `package.json`, lockfiles, build configuration, or deployment configuration
- CI/CD workflows
- Plugin manifests or platform-specific packaging
- Platform-specific duplicate instruction trees
- Executable hooks, scripts, or application code
- Benchmarks or implementation test suites
- Generated artifacts
- Unnecessary assets
- Marketing material
- Long human-oriented tutorials
- Duplicate or overlapping skill definitions

If something does not teach an AI agent **how Ponytail should behave or how to use Ponytail's canonical instructions**, it generally does not belong here.

## 5. Editing principles

- Prefer one canonical instruction over multiple variants.
- Preserve useful methodology when removing implementation or distribution material.
- When removing a runtime component, preserve its useful **behavioral contract/instructions** in the appropriate canonical skill.
- Keep skills self-contained, actionable, concise, and unambiguous.
- Do not leave references to files, tools, packages, or infrastructure that no longer exists.
- Do not add speculative features or operational complexity.
- Avoid rewriting working instructions merely for stylistic reasons.

## 6. Final verification

Before finishing a repository change, verify:

- The relevant canonical skill was consulted and followed.
- No duplicate instruction source was introduced.
- No installation, runtime, deployment, or packaging clutter was added.
- References point to files that actually exist.
- The changed instructions are internally consistent.
- The repository remains a focused AI-agent knowledge base.

**Default principle: keep the knowledge, remove the machinery.**
