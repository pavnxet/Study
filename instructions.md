# Study Repository Instructions

## Purpose

`Study` is a long-term academic archive. Treat it as a structured knowledge base whose primary goals are preservation, discoverability, provenance, and maintainability. It is not a generic file dump and it is not an academic-management application.

## 1. Canonical information architecture

Use this hierarchy by default for university/program material:

```text
institutions/
└── <institution>/
    └── programs/
        └── <program>/
            ├── semesters/
            │   └── <semester>/subjects/<subject-code>-<subject-slug>/
            └── years/
                └── <year>/subjects/<subject-code>-<subject-slug>/
```

A program uses either `semesters/` or `years/` as appropriate. If the source institution has another stable hierarchy, adapt it at the academic-level boundary instead of inventing duplicate copies.

For competitive/public examinations that are not naturally represented as a university program, use the separate exam archive:

```text
exams/
└── <region-or-state>/
    └── <exam-family>/
        └── <level-or-variant>/
            └── <year>/
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

This allows CET, state recruitment, entrance, eligibility, and other examination archives to coexist without forcing them into a university-semester hierarchy.

## 2. Subject identity

A subject directory is the canonical storage identity. Use the official/stable subject code whenever one exists, followed by a lowercase descriptive slug:

`<subject-code>-<subject-slug>`

Example: `mat-02-real-analysis-topology`.

Do not create another copy of a subject simply because it appears in another semester/year view. Prefer references/links rather than duplication.

## 3. Previous-year papers

Store papers under the subject or exam they belong to, then by examination year and session:

```text
previous-papers/2025/december/2025-12-mat-02-real-analysis-topology.pdf
```

Use a session directory such as `june`, `december`, `may`, `november`, or the actual official session name when required.

Recommended filename pattern:

`YYYY-MM-<subject-code>-<subject-slug>[-<paper-id>].<ext>`

For exams without a subject code, use a stable exam/paper slug instead:

`YYYY-<exam-slug>-<paper-name>.<ext>`

## 4. Syllabus rules

Keep syllabus material separate from notes and question papers. Where multiple versions exist, preserve them:

```text
syllabus/
├── official/
├── revised/
├── previous/
└── archived/
```

For a standalone competitive-exam archive, `syllabus.md` may be the canonical formatted syllabus when no original PDF is stored. Metadata must record provenance and whether the text has been transcribed or cleaned.

Never silently overwrite an older syllabus.

## 5. Notes and study material

Use `notes/` for explanatory study material. Unit/topic organization is encouraged when it improves navigation. For competitive exams, topic-based folders are often more appropriate than units.

Clearly label materially different origins such as personal, class, teacher, AI-generated, textbook-derived, or revision notes. Do not imply that unofficial material is institution-issued.

## 6. Question banks and solutions

Use `question-banks/` for collections of questions and `solutions/` for worked answers or answer keys. Organize question banks by unit/topic/type when that improves retrieval.

Solutions should use the same stable source identity as the questions. Do not duplicate the source paper inside `solutions/`.

## 7. OCR and transcriptions

Original scans are authoritative source files. OCR is derived data.

Use `ocr/` for machine-readable output and distinguish:

- `original` — source document in its original format
- `ocr` — raw machine OCR
- `corrected-ocr` — manually corrected OCR
- `verified-transcription` — human-checked transcription

Never overwrite an original PDF/image with OCR output.

## 8. Metadata

Do not require metadata files for every tiny note. Add `metadata.yaml` when it materially improves provenance, automation, version tracking, or searchability.

Recommended fields:

```yaml
title:
subject:
subject_code:
program:
institution:
academic_level:
year:
exam_session:
document_type:
language:
source:
source_url:
date_added:
author:
official:
ocr_available:
verified:
tags: []
```

Exam-specific metadata may additionally include `exam_name`, `conducting_body`, `question_count`, `total_marks`, `duration`, and `negative_marking`.

Do not fabricate unknown values.

## 9. Provenance

For externally sourced material, preserve the original source where practical. Record institution/conducting body, author, publication/effective year, source URL, and whether the item is official or unofficial when known.

If a file has been modified, OCR'd, transcribed, or cleaned, say so. Provenance is part of the archive.

## 10. Copyright and distribution

Do not assume that online availability grants redistribution rights. For copyrighted books or questionable third-party PDFs, prefer citation, metadata, and source URL instead of copying the work.

Do not remove copyright notices or alter attribution.

## 11. Naming conventions

Repository paths must use lowercase, stable separators (`-` for slugs), stable subject/exam codes where available, and ISO-like dates where sorting matters. Avoid meaningless words such as `final`, `new`, `latest`, or `copy`.

Examples:

- good: `2025-12-mat-02-real-analysis-topology.pdf`
- bad: `December paper final.pdf`

Keep extensions lowercase and preserve original formats unless a derived artifact is needed.

## 12. Indexes

`indexes/` is the human- and machine-friendly cross-repository navigation layer. At minimum maintain:

- `subjects.md`
- `syllabus.md`
- `previous-papers.md`
- `notes.md`
- `question-banks.md`
- `resources.md`

Exam archives may receive dedicated indexes when the collection becomes large enough. Do not create redundant indexes prematurely.

## 13. Missing material

Missing resources should be visible rather than silently invented. Subject/exam READMEs may use a simple status table showing available, partial, or missing resources.

Never create placeholder academic content that looks like a real document.

## 14. Repository hygiene

Never commit API keys, passwords, tokens, private credentials, or unrelated personal secrets. Keep `.gitignore` focused on editor, OS, cache, temporary, and generated local files.

Avoid binary duplication. Do not add application frameworks, databases, or services unless the repository's purpose explicitly changes.

## 15. Large files

Use normal Git for ordinary PDFs, Markdown, text, and modest images. Consider Git LFS only when real repository size or file-size constraints justify it. Very large books, video, or datasets should generally remain external or in a dedicated archival system when GitHub is not appropriate.

Do not introduce Git LFS preemptively.

## 16. AI-agent behavior

Before changing this repository, an AI agent must read `agents.md` and follow these instructions. Agents should inspect the existing tree before adding files, use stable paths, preserve originals, avoid duplicates, and verify that links and metadata remain internally consistent.

Agents must not invent academic documents, source URLs, official status, authorship, dates, or verification claims.

## 17. Adding a new item

1. Identify the institution/program **or** exam family/region.
2. Determine whether it belongs in the university hierarchy or under `exams/`.
3. Identify the subject/exam and stable code/name.
4. Choose the correct material category.
5. Choose a deterministic filename.
6. Preserve the original format.
7. Add provenance/metadata when useful.
8. Add OCR separately when appropriate.
9. Update the relevant index/README.
10. Check for duplicates and accidental secrets.

## 18. Validation before commit

Verify that:

- the path matches the academic or exam hierarchy;
- the filename is deterministic;
- the source is not unnecessarily duplicated;
- original and derived files are distinguishable;
- provenance is not fabricated;
- Markdown links point to real paths;
- no secrets were added;
- relevant indexes/READMEs are not stale;
- formatting/transcription notes are present when source text was cleaned.

## 19. Scope control

Prefer the smallest structure that solves the problem. Do not add a database, web app, CI system, semantic-search layer, or complex metadata schema merely because it might be useful someday.

The repository should remain a clean academic/exam archive first and an automation-friendly data source second.

## 20. Final audit

Before declaring a structural change complete, compare the result against this file and `agents.md`. Check discoverability, scalability, naming, provenance, copyright handling, OCR separation, duplicate avoidance, and AI-agent readability.
