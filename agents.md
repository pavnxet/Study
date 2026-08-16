# Agent Instructions — Study Academic Archive

## Mission

This repository is a structured academic archive and knowledge base for university study material and Rajasthan competitive-exam preparation material.

## Mandatory first step

Before modifying the repository, read `agents.md`, `instructions.md`, relevant READMEs, and inspect the existing tree.

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

```text
exams/पर्यवेक्षक (महिला) सीधी भर्ती/
```

The supplied year **2024** and recruitment mode **सीधी भर्ती / Open Market** are metadata, not mandatory path components.

If different editions of the same post later need coexistence, first inspect the existing archive and choose the least-nested documented solution.

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
- no secrets added.

**Default principle: Preserve → organize → label → link → verify.**
