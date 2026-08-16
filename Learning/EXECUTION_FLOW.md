# Execution Flow Map (`EXECUTION_FLOW.md`)

This file is a living map of how execution travels through this codebase. It allows project owners and AI agents to maintain an accurate mental model of execution paths.

## Rules for Maintaining This File
- **Keep Current**: Update whenever a change alters a call path, adds an entry point, or modifies component interactions.
- **Be Concrete**: Use exact file paths and function/route names.
- **Track Session Changes**: Keep the "Recent Changes" section updated with current session edits.

---

## 1. Entry Points
List every execution entry point (HTTP routes, CLI commands, main loops, worker fetch handlers, cron triggers).

- `src/index.ts` — Main server entry point / HTTP request handler

---

## 2. Execution Order & Call Graph
Describe execution flow as a clean call chain:

```
request
  -> router.match(request)         [src/router.ts]
  -> handleRequest(request)        [src/handlers/main.ts]
       -> validateInput()          [src/utils/validation.ts]
       -> executeLogic()           [src/services/logic.ts]
  -> response returned
```

---

## 3. Key Modules & Responsibilities
Short overview of key directories and files:

- `src/router.ts` — Route matching and dispatch.
- `src/handlers/` — HTTP request handlers per feature.
- `src/services/` — Core business logic.

---

## 4. Recent Changes (Current Cycle)
Living record of what was modified in the current work session and how it affects the flow:

- `[YYYY-MM-DD]` Updated `path/to/file` — modified step N in the call graph.
