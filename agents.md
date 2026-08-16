# Agent Instructions — Study Academic Archive

## Mission

This repository is a structured academic archive and knowledge base. It stores and organizes study material for long-term discovery, preservation, provenance, and future machine-assisted analysis.

It is **not** a generic file dump, application, database, or AI system. Do not introduce unrelated infrastructure.

## Mandatory first step

Before modifying the repository, read:

1. `agents.md`
2. `instructions.md`
3. the relevant README(s) for the institution/program/subject being changed

Then inspect the existing repository tree before deciding where a new file belongs.

## Canonical architecture

The preferred hierarchy is:

```text
institutions/
└── <institution>/
    └── programs/
        └── <program>/
            ├── semesters/<semester>/subjects/<subject-code>-<subject-slug>/
            └── years/<year>/subjects/<subject-code>-<subject-slug>/
```

The program should use either `semesters/` or `years/` according to its real academic system. Do not invent a semester for a year-based program.

Subject material belongs below the subject identity and is categorized as:

- `syllabus/`
- `previous-papers/`
- `question-banks/`
- `notes/`
- `solutions/`
- `assignments/`
- `mock-papers/`
- `books/`
- `lecture-material/`
- `extra-material/`
- `ocr/`
- `images/`
- `links/`

Create only categories that are actually needed.

## Core rules

### 1. Preserve source material

Never replace an original document with OCR, cleanup, compression, or transcription. Derived material is separate and explicitly labeled.

### 2. Never fabricate

Do not invent:

- academic documents;
- question papers;
- official status;
- authors;
- dates;
- source URLs;
- metadata values;
- verification claims.

Unknown information must remain unknown.

### 3. Use deterministic names

Use lowercase paths, stable subject codes, descriptive slugs, and ISO-like dates.

Preferred paper filename:

`YYYY-MM-<subject-code>-<subject-slug>.pdf`

Avoid `final`, `new`, `latest`, `copy`, `scan123`, or other ambiguous names.

### 4. Keep provenance

For external material, preserve the source URL and institution/author information when known. Mark official vs unofficial status only when supported by evidence.

### 5. Respect copyright

Do not assume online availability means redistribution is permitted. When redistribution is questionable, prefer metadata, citation, notes, and a source link instead of copying the copyrighted work.

### 6. Avoid unnecessary duplication

Do not copy the same paper into several folders just to make it appear in multiple indexes. Prefer links or a canonical source location.

### 7. Metadata should earn its keep

Use `metadata.yaml` when it materially improves provenance, automation, versioning, or searchability. Do not require metadata for every small note.

### 8. Keep indexes useful

When adding or removing material, update the relevant index when it is part of the repository's established indexing scheme. Do not create redundant indexes.

### 9. README hierarchy

Use READMEs where they provide real navigation or context:

- root repository README;
- institution/program overview when useful;
- semester/year overview when useful;
- subject README for substantial subjects.

Do not create meaningless README files just to fill directories.

## Adding a new subject

1. Confirm institution.
2. Confirm program.
3. Determine whether the program uses semesters or years.
4. Confirm the subject code/name from an actual source.
5. Create `<subject-code>-<subject-slug>/`.
6. Add only required material categories.
7. Add a subject README if the subject has enough material to benefit from one.
8. Add provenance and metadata where appropriate.
9. Update indexes as required.

## Adding a previous-year paper

1. Place it under the correct subject.
2. Use `previous-papers/<year>/<session>/`.
3. Name it `YYYY-MM-<subject-code>-<subject-slug>[-<paper-id>].ext`.
4. Preserve the original format.
5. Record provenance if externally sourced.
6. Check whether the same content already exists by filename and, when practical, by hash.
7. Add OCR separately if needed.
8. Update the previous-paper index when applicable.

## OCR rules

Use the following conceptual lifecycle:

`original → OCR → corrected OCR → verified transcription`

Do not collapse these stages into one file. OCR is derived material and must never destroy the source.

## Solutions and relationships

A solution should be traceable to its source question/paper through stable naming and/or links. Do not duplicate the source paper inside `solutions/`.

## Links and external resources

Use `links/` for resources that should remain at their original host. Include a short description and source URL. Do not represent an external resource as locally archived unless it actually is.

## Changes to repository architecture

Architecture changes are high-impact. Before making one:

1. Explain the problem the current structure cannot solve.
2. Check whether a smaller change is sufficient.
3. Preserve existing valid material.
4. Update `instructions.md` and relevant READMEs.
5. Check for broken links and stale paths.
6. Avoid migration unless it materially improves long-term maintainability.

## Automation policy

Automation is allowed when it provides clear value, such as index generation, metadata validation, duplicate detection, link checking, or archive statistics. Do not add CI/CD, databases, web applications, AI/RAG systems, or Git LFS without a demonstrated need.

Any automation that is added must be documented and actually testable. Never claim it was tested when it was not.

## Security

Never commit API keys, passwords, access tokens, authentication secrets, or private credentials. Keep `.gitignore` focused on local/editor/temporary artifacts.

## Review checklist

Before finishing a change, verify:

- correct institution/program/academic level;
- correct subject identity;
- correct material category;
- deterministic filename;
- no unnecessary duplicate;
- original preserved;
- derived OCR clearly separated;
- provenance accurate;
- copyright concerns considered;
- indexes/links are not stale;
- no secrets were added;
- documentation still describes the actual tree.

## Default behavior

**Preserve → organize → label → link → verify.**

Prefer a simple, durable archive over clever infrastructure. The directory structure is part of the knowledge model and should remain understandable to both humans and AI agents.
