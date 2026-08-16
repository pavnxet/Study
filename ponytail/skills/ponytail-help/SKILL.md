---
name: ponytail-help
description: >
  Compact reference for Ponytail modes and canonical skills. Use for questions
  about how the instruction set is organized or which skill to invoke.
---

# Ponytail Help

## Modes

| Mode | Meaning |
|---|---|
| `lite` | Build the request, while naming a simpler alternative when useful. |
| `full` | Enforce the Ponytail ladder. Default. |
| `ultra` | Strong YAGNI bias: deletion before addition and requirements are challenged. |

Mode persists until changed or the session ends. `stop ponytail` / `normal mode`
disables it.

## Canonical skills

- `ponytail` — core methodology and intensity modes.
- `ponytail-review` — review a diff for unnecessary complexity.
- `ponytail-audit` — audit a whole repository for over-engineering.
- `ponytail-debt` — collect deliberate `ponytail:` shortcuts and their upgrade triggers.
- `ponytail-mcp` — instruction contract for MCP hosts; behavior only, no server code.
- `ponytail-help` — this reference.

## Source of truth

The `skills/` directory is the only canonical instruction source. Platform-specific
copies, plugin manifests, installation guides, benchmarks, and runtime code are
not part of this repository.
