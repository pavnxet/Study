# Master Agent Instructions & Project Protocol

> **Target Audience**: All AI Coding Assistants (Gemini Antigravity, Claude Code, Cursor, Copilot, Windsurf, Custom Agents).
> **Scope**: Mandatory operating rules, memory system protocol, decision logging, execution flow mapping, and change verification quiz.

---

## 1. Overview & Architecture

This repository uses a structured 5-file persistent memory and governance system:

| File | Purpose | Rule Type |
|---|---|---|
| **`AGENTS.md`** | Master instructions & system rules (this file). | **Binding Protocol** |
| **`learning.md`** | Distilled knowledge, conventions, user preferences, fixed mistakes. | **Persistent Memory** (Edit-in-place) |
| **`summary.md`** | Dated running log of session execution history. | **Append-Only Log** (Zero deletion) |
| **`DECISIONS.md`** | Architecture Decision Records (ADRs) and technical trade-offs. | **Decision Log** (Real-time updates) |
| **`EXECUTION_FLOW.md`** | Living map of entry points, call paths, and recent changes. | **Execution Map** (Living document) |

---

## 2. Session Start Protocol (MANDATORY & NON-NEGOTIABLE)

Before executing any code changes, running tools, or fulfilling tasks:

1. **READ `AGENTS.md` IN FULL**: Review these master directives completely.
2. **READ `learning.md` IN FULL**: Treat every entry inside `learning.md` as a **BINDING CONSTRAINT AND HARD RULE** (user preferences, bitrate settings, GUI guidelines, code conventions).
3. **SKIM `summary.md`**: Read the last 3–5 entries of `summary.md` to get context on recent momentum, active tasks, and open items.
4. **INSPECT `DECISIONS.md` & `EXECUTION_FLOW.md`**: Check existing architectural choices and execution call graphs before altering codebase structure.

---

## 3. Decision Logging Protocol (`DECISIONS.md`)

Maintain `DECISIONS.md` as a real-time Architecture Decision Record (ADR) log.

- **Trigger**: Every time a meaningful technical decision is made (selecting a library, choosing an architectural approach, altering a data schema, rejecting an alternative, balancing simplicity vs performance).
- **Rule**: Log the entry **in real-time during the turn the choice is made** — never retroactively or batched at session end.
- **Entry Requirements**:
  - What was decided.
  - Why this approach over obvious alternatives.
  - Why a specific library/tool was chosen (or avoided).
  - What alternatives were considered and why they lost out.
  - Known trade-offs and limitations.

---

## 4. Execution Flow Mapping Protocol (`EXECUTION_FLOW.md`)

Maintain `EXECUTION_FLOW.md` as a living map of how execution travels through the codebase.

- **Trigger**: Update whenever a change alters a call path, adds an entry point, or modifies function relationships.
- **Components**:
  1. **Entry Points**: All HTTP routes, CLI commands, main execution loops, cron triggers.
  2. **Call Graph**: Simple ASCII execution chain (e.g. `entry -> handler -> service -> db`).
  3. **Key Modules**: File ownership breakdown.
  4. **Recent Changes**: Living record of what was touched in the current cycle and where it sits in the call path.

---

## 5. Interactive Change Quiz Protocol

To prevent unreviewed auto-approvals and ensure user comprehension:

- **Trigger**: Before the user accepts any **major change** (new feature, architectural refactor, new dependency, multi-file behavior change).
- **Quiz Process**:
  1. Summarize the change and update `DECISIONS.md` & `EXECUTION_FLOW.md`.
  2. Quiz the user with 3–5 specific questions about the change (e.g., "What does function X do differently now?", "Why did we pick library Y over Z?").
  3. Do not treat the change as accepted until the user has answered the quiz.
  4. If an answer is incorrect, explain the actual logic clearly before proceeding.
- *Note*: Minor edits (typos, formatting, single-line config tweaks) do not require a quiz.

---

## 6. Session End & Memory Persistence Protocol (STOP HOOK ENFORCED)

Do NOT end a session without completing these 3 non-negotiable steps:

1. **Append to `summary.md`**:
   - Add a concise, dated entry using the template in `summary.md`.
   - **ZERO DELETION / NO OVERWRITING**: Never edit or delete past entries in `summary.md`.
   - Update `summary.md` ONLY for file/code processes (creation, modification, deletion). Do NOT log simple slash commands, mode toggles, or Q&A queries.
2. **Update `learning.md`**:
   - Persist any new user preference, technical correction, or fixed mistake.
   - **NO DUPLICATES**: Edit existing entries in place if new facts update or contradict old ones.
   - Consolidate and prune if `learning.md` exceeds 150 lines.
3. **Verify Compliance**: Ensure all 5 system files reflect the latest session state.
