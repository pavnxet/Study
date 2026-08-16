# Study — Academic Archive

`Study` is a long-term, GitHub-based academic archive for organizing university and study material as a navigable knowledge base rather than an unstructured collection of files.

## What belongs here

- University and program syllabi
- Previous-year question papers
- Question banks and important questions
- Notes and revision material
- Solutions and answer keys
- Assignments and mock papers
- Books and reference material when redistribution is permitted
- Lecture material
- OCR/transcriptions of scanned documents
- Images and supplementary resources
- Provenance and links to material that should remain hosted at its original source

## Architecture

The archive uses a hybrid hierarchy: institution → program → academic level → subject, with material categorized inside each subject. Programs may use `semesters/` or `years/`; do not force a semester structure onto an academic system that uses years.

```text
institutions/
└── <institution>/
    └── programs/
        └── <program>/
            ├── semesters/<semester>/subjects/<code>-<slug>/
            └── years/<year>/subjects/<code>-<slug>/
                ├── syllabus/
                ├── previous-papers/<year>/<session>/
                ├── question-banks/
                ├── notes/
                ├── solutions/
                ├── assignments/
                ├── mock-papers/
                ├── books/
                ├── lecture-material/
                ├── extra-material/
                ├── ocr/
                ├── images/
                └── links/
```

Use only the branch that matches the real academic hierarchy. The repository does not duplicate a subject merely to support different views.

## Finding material

Start with the relevant institution, program, semester/year, and subject. Use `indexes/` for cross-repository discovery. Filenames are deliberately descriptive so GitHub search and future AI/RAG tooling can work without a separate database.

## Naming

Use lowercase paths, stable subject codes, descriptive slugs, and ISO-like dates where useful. A previous paper should normally follow:

`YYYY-MM-<subject-code>-<subject-slug>.pdf`

Examples:

- `2025-12-mat-02-real-analysis-topology.pdf`
- `2024-06-mat-02-real-analysis-topology.pdf`

Do not use `final.pdf`, `new.pdf`, `scan123.pdf`, or other ambiguous names.

## Provenance and versions

Preserve original files. Never replace an original with OCR, cleanup, or transcription. Record source information in `metadata.yaml` when provenance materially matters. Clearly distinguish official, unofficial, OCR, corrected OCR, and verified transcription material.

If redistribution of a copyrighted work is questionable, store metadata, citation, and source URL instead of copying the work into the repository.

## Adding material

See [`instructions.md`](instructions.md) for the complete repository operating rules and [`CONTRIBUTING.md`](CONTRIBUTING.md) for the quick addition workflow. AI agents must read [`agents.md`](agents.md) before modifying the archive.

## Current state

This repository is intentionally shipped with the archive structure and documentation first. No fabricated academic documents are included. Real materials can be added incrementally without redesigning the hierarchy.
