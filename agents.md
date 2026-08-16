# Agent Instructions — Study Academic Archive

## Mission

This repository is a structured academic archive and knowledge base for university study material and Rajasthan competitive-exam preparation material.

## Mandatory first step

Before modifying the repository, read these files in full:

1. `agents.md` — binding instructions.
2. `instructions.md` — repository architecture and operating rules.
3. `learning.md` — persistent reusable lessons, preferences, and fixed mistakes.
4. `summary.md` — recent repository-processing history; skim the latest entries.
5. `DECISIONS.md` — meaningful architecture decisions.
6. `EXECUTION_FLOW.md` — current processing workflow.
7. Relevant README files and existing tree paths for the material being changed.

## Root governance and post-processing protocol — MANDATORY

The repository root is the canonical location for the governance/memory files below. Do not create a second competing governance system under another directory unless explicitly requested.

| File | Role | Maintenance rule |
|---|---|---|
| `agents.md` | Binding repository/AI-agent rules | Edit when a durable operating rule changes |
| `instructions.md` | Detailed architecture and operating instructions | Keep synchronized with actual repository behavior |
| `learning.md` | Persistent reusable knowledge, user preferences, corrections | Edit in place; consolidate conflicts |
| `summary.md` | Session history for file/code/repository processing | **Append-only; never delete/overwrite past entries** |
| `DECISIONS.md` | Architecture Decision Record | Log meaningful decisions in the same session |
| `EXECUTION_FLOW.md` | Living processing/workflow map | Update when processing structure/workflow materially changes |

### Strict post-processing rule

After **every substantial post-processing operation** on academic/exam material, agents must complete the governance update pass before declaring the task complete:

1. Update the processed material and its README/metadata as required.
2. Update `DECISIONS.md` if a meaningful architecture, naming, metadata, provenance, or workflow decision was made.
3. Update `learning.md` with any new reusable rule, user preference, correction, or mistake fix. Edit existing facts in place instead of creating duplicates/conflicts.
4. Append a concise entry to `summary.md` for file/code/repository processing work. Never rewrite old entries.
5. Update `EXECUTION_FLOW.md` if the processing workflow, archive path, or automation flow changed.
6. Re-read the relevant root governance files and verify consistency before reporting completion.

Do not declare a substantial repository-processing task complete while required governance updates are missing.

## Rajasthan exam archive rules — MANDATORY

Rajasthan is the fixed scope of `exams/`. Therefore:

- **Never create `exams/rajasthan/`.**
- **Do not create a recruitment-type subfolder** such as `direct-recruitment/` or `recruitment/` unless the user explicitly asks for it.
- **Do not create a year subfolder** such as `2024/` unless the user explicitly asks for it.
- Use the **actual exam/post name supplied by the user** as the archive directory whenever practical. Do not arbitrarily translate a supplied Hindi name into an English slug.
- Year, recruitment mode, level, and similar distinctions belong in `README.md` and `metadata.yaml` by default.

### Correct default pattern

```text
exams/
└── <actual-exam-or-post-name>/
    ├── README.md
    ├── syllabus.md
    ├── metadata.yaml
    ├── previous-papers/
    ├── notes/
    ├── question-banks/
    ├── solutions/
    ├── mock-papers/
    ├── current-affairs/
    ├── ocr/
    ├── resources/
    └── links/
```

For the current exam, the canonical directory is:

`exams/पर्यवेक्षक (महिला) सीधी भर्ती/`

The supplied year **2024** and recruitment mode **सीधी भर्ती / Open Market** are metadata, not mandatory path components.

## University/program architecture

```text
institutions/
└── <institution>/
    └── programs/
        └── <program>/
            ├── semesters/<semester>/subjects/<subject-code>-<subject-slug>/
            └── years/<year>/subjects/<subject-code>-<subject-slug>/
```

Use the actual academic system; do not invent semesters.

## Core preservation rules

1. Never replace originals with OCR, cleanup, compression, or transcription.
2. Never fabricate documents, dates, sources, official status, or metadata.
3. Preserve provenance and distinguish official from unofficial material only when supported.
4. Respect copyright; when redistribution is questionable, prefer metadata/citation/source links.
5. Avoid duplicate copies; use links to canonical material.
6. Use metadata when it materially improves provenance, search, or automation.
7. Keep indexes and READMEs accurate without creating redundant documentation.
8. Do not add databases, web apps, AI/RAG systems, CI/CD, or Git LFS without demonstrated need.
9. Never commit secrets or credentials.

## Naming

Use stable, descriptive names. Avoid `final`, `new`, `latest`, `copy`, `scan123`, etc.

For Rajasthan exam directories, preserve the actual supplied exam/post name. For files, use predictable descriptive names.

## OCR lifecycle

`original → OCR → corrected OCR → verified transcription`

Derived stages must remain separate from the original.

## Adding a Rajasthan exam

1. Identify the exact supplied exam/post name.
2. Create `exams/<actual-exam-or-post-name>/`.
3. Do not add `rajasthan/`, recruitment-type, or year folders by default.
4. Put year/recruitment/level information in metadata and README.
5. Add only useful categories.
6. Preserve provenance and source treatment.

## AI change governance

The repository previously used a five-file agent memory pattern. It is now integrated at the repository root. Agents must treat the root files as the canonical system and may not silently fork their rules into `Learning/` or another duplicate location.

A major architecture change may require a user-facing explanation before acceptance. Minor formatting or single-file metadata fixes do not require an interactive quiz.

## Review checklist

Before finishing, verify:

- exact exam/post identity preserved;
- no `exams/rajasthan/` directory;
- no unnecessary recruitment-type folder;
- no unnecessary year folder;
- correct material category;
- original preserved;
- OCR/transcription separated;
- provenance accurate;
- no duplicate or stale path;
- documentation matches the actual tree;
- `learning.md` updated when a reusable lesson/correction was created;
- `DECISIONS.md` updated for meaningful architecture choices;
- `summary.md` appended for file/code processing;
- `EXECUTION_FLOW.md` updated when workflow changed;
- no secrets added.

**Default principle: Preserve → organize → label → link → verify → post-process governance.**
