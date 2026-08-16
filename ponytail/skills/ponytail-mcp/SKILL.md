---
name: ponytail-mcp
description: >
  Canonical instruction contract for MCP hosts exposing Ponytail. Selects one
  Ponytail intensity and serves the same canonical methodology as the
  `ponytail` skill. This file contains instructions only; it is not an MCP
  implementation or installation guide.
---

# Ponytail MCP Instruction Contract

The MCP-facing behavior must be instruction-only and must reuse the canonical
Ponytail methodology from `skills/ponytail/SKILL.md`. Do not duplicate or
rewrite the methodology in host-specific code.

## Modes

Supported modes: `lite`, `full`, `ultra`.

- `full` is the default.
- A valid requested mode is used directly.
- An empty, unknown, or `off` request falls back to the configured default;
  if that is unavailable or `off`, use `full`.
- `off` is therefore a control value, not a fourth instruction mode.

## Served instructions

For the selected mode, serve:

1. `PONYTAIL MODE ACTIVE — level: <mode>`.
2. The canonical Ponytail skill instructions, filtered only for the selected
   intensity where the canonical skill defines mode-specific content.
3. No MCP/SDK implementation details, installation steps, package commands,
   host-specific setup, or duplicated methodology.

## Consistency rule

The MCP representation and the canonical `skills/` representation must stay
semantically identical. If the methodology changes, update the canonical skill
first and treat this contract as the integration-facing selection rule.

## Boundaries

This skill defines behavior only. It does not define transport, authentication,
server code, dependencies, deployment, packaging, or installation.
