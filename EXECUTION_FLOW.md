# Execution Flow Map (`EXECUTION_FLOW.md`)

This is a living map of how repository work is performed. It helps humans and AI agents understand the processing flow even though `Study` is primarily an archive rather than an application.

## Rules for Maintaining This File
- **Keep current**: Update when repository structure, processing workflow, validation flow, or automation changes.
- **Be concrete**: Use exact repository paths and workflow stages.
- **Post-processing is mandatory**: After a substantial material-processing session, update the recent-changes section when the workflow materially changed.

## 1. Archive Processing Entry Points

- User-provided academic/exam material enters through an agent or maintainer session.
- Existing repository tree and `agents.md`/`instructions.md` are inspected first.
- Material is classified into an exam archive, university archive, shared archive, or external link entry.

## 2. Standard Processing Flow

```text
user material
  -> inspect existing repository rules
  -> identify canonical archive path
  -> preserve original/source status
  -> post-process / normalize / transcribe when requested
  -> create or update README + metadata
  -> update indexes where applicable
  -> update DECISIONS.md when a meaningful architecture decision occurred
  -> update learning.md with new reusable rules/corrections
  -> append summary.md for file/code processing work
  -> validate paths, links, metadata, naming, duplicates, and provenance
```

## 3. Rajasthan Exam Flow

```text
supplied exam/post name
  -> exams/<actual-exam-or-post-name>/
  -> syllabus / papers / notes / question-banks / solutions / etc.
  -> year + recruitment mode stored in metadata/README by default
  -> no `rajasthan/`, recruitment-type, or year folder unless explicitly requested
```

## 4. OCR / Transcription Flow

```text
original source
  -> raw OCR (when needed)
  -> corrected OCR
  -> verified transcription
```

Derived artifacts never replace the original source.

## 5. Key Repository Responsibilities

- `agents.md` — binding agent and repository rules.
- `instructions.md` — detailed operating instructions and architecture.
- `DECISIONS.md` — meaningful architectural decisions.
- `learning.md` — reusable lessons, preferences, and fixed mistakes.
- `summary.md` — append-only file/code session history.
- `indexes/` — human- and machine-friendly navigation.
- `exams/` — Rajasthan competitive-exam archive.
- `institutions/` — university/program archive.

## 6. Recent Changes

### 2026-08-16
- Promoted governance/memory documents from `Learning/` toward repository root.
- Added explicit post-processing documentation requirements.
- Standardized Rajasthan exam archive naming and non-nested year/recruitment structure.
