# Study Repository Instructions

## Purpose

`Study` is a long-term academic archive. Treat it as a structured knowledge base whose primary goals are preservation, discoverability, provenance, and maintainability. It is not a generic file dump and it is not an academic-management application.

## 1. Canonical information architecture

Use this hierarchy by default:

```text
institutions/
└── <institution>/
    └── programs/
        └── <program>/
            ├── semesters/
            │   └── <semester>/
            │       └── subjects/
            │           └── <subject-code>-<subject-slug>/
            └── years/
                └── <year>/
                    └── subjects/
                        └── <subject-code>-<subject-slug>/
```

A program uses either `semesters/` or `years/` as appropriate. If the source institution has another stable hierarchy, adapt the structure at the academic-level boundary instead of inventing duplicate copies of the same subject.

Inside every subject, use these categories when they are actually needed:

```text
syllabus/
previous-papers/<year>/<session>/
question-banks/
notes/
solutions/
assignments/
mock-papers/
books/
lecture-material/
extra-material/
ocr/
images/
links/
```

Do not create empty category folders merely for visual completeness. Git does not track empty directories; use `.gitkeep` only for intentional template directories where seeing the future structure is useful.

## 2. Subject identity

A subject directory is the canonical storage identity. Use the official/stable subject code whenever one exists, followed by a lowercase descriptive slug:

`<subject-code>-<subject-slug>`

Example: `mat-02-real-analysis-topology`.

Do not create another copy of a subject simply because it appears in another semester/year view. If the same material genuinely belongs to multiple contexts, prefer a clear reference/link rather than duplication.

## 3. Previous-year papers

Store papers under the subject that the paper belongs to, then by examination year and session:

```text
previous-papers/2025/december/2025-12-mat-02-real-analysis-topology.pdf
```

Use a session directory such as `june`, `december`, `may`, `november`, or the actual official session name when required.

Recommended filename pattern:

`YYYY-MM-<subject-code>-<subject-slug>[-<paper-id>].<ext>`

The filename must communicate enough information to identify the paper without opening it.

## 4. Syllabus rules

Keep syllabus material separate from notes and question papers. Where multiple versions exist, preserve them:

```text
syllabus/
├── official/
├── revised/
├── previous/
└── archived/
```

Use metadata when version, effective academic year, issuer, or source matters. Never silently overwrite an older syllabus.

## 5. Notes and study material

Use `notes/` for actual explanatory study material. Unit/topic organization is encouraged when it improves navigation:

```text
notes/unit-01/
notes/unit-02/
```

Clearly label materially different origins such as personal, class, teacher, AI-generated, textbook-derived, or revision notes. Do not imply that AI-generated or unofficial material is university-issued.

## 6. Question banks and solutions

Use `question-banks/` for collections of questions and `solutions/` for worked answers or answer keys. Organize question banks by unit/topic/type when that improves retrieval.

Solutions should use the same stable source identity as the questions. For a paper, a solution may be named:

`2025-12-mat-02-real-analysis-topology-solution.md`

Do not duplicate the source paper inside the solutions directory.

## 7. OCR and transcriptions

Original scans are authoritative source files. OCR is derived data.

Use `ocr/` for machine-readable output and clearly distinguish stages, for example:

- `original` — the source document in its original format
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

Do not fabricate unknown values. Omit a field or use an explicit unknown value rather than guessing.

## 9. Provenance

For externally sourced material, preserve the original source where practical. Record institution, author, publication/effective year, source URL, and whether the item is official or unofficial when known.

If a file has been modified, OCR'd, transcribed, or cleaned, say so. Provenance is part of the archive, not optional decoration.

## 10. Copyright and distribution

Do not assume that online availability grants redistribution rights. For copyrighted books or questionable third-party PDFs, prefer an index entry containing citation and source URL. Personal notes and openly licensed/public-domain material can be stored according to their applicable rights.

Do not remove copyright notices or alter attribution.

## 11. Naming conventions

Repository paths:

- lowercase
- stable separators (`-` for slugs)
- no meaningless words such as `final`, `new`, `latest`, or `copy`
- stable subject codes where available
- ISO-like dates for dates that need sorting

Examples:

- good: `2025-12-mat-02-real-analysis-topology.pdf`
- bad: `December paper final.pdf`

Keep extensions lowercase and preserve the original format unless conversion is needed for a derived artifact.

## 12. Indexes

`indexes/` is the human- and machine-friendly cross-repository navigation layer. Keep it concise and accurate. At minimum maintain:

- `subjects.md`
- `syllabus.md`
- `previous-papers.md`
- `notes.md`
- `question-banks.md`
- `resources.md`

Do not maintain redundant databases when directory paths already provide the needed information. If indexes become burdensome, automate them rather than creating more manual metadata.

## 13. Missing material

Missing resources should be visible rather than silently invented. Subject READMEs may use a simple status table such as:

| Resource | Status |
| --- | --- |
| Syllabus | available / missing |
| Previous papers | available / partial / missing |
| Notes | available / partial / missing |
| Solutions | available / partial / missing |

Never create placeholder academic content that looks like a real document.

## 14. Repository hygiene

Never commit API keys, passwords, tokens, private credentials, or unrelated personal secrets. Keep `.gitignore` focused on editor, OS, cache, temporary, and generated local files.

Avoid binary duplication. Do not add application frameworks, databases, or services unless the repository's purpose explicitly changes.

## 15. Large files

Use normal Git for ordinary PDFs, Markdown, text, and modest images. Consider Git LFS only when real repository size or file-size constraints justify it. Very large books, video, or datasets should generally remain external or in a dedicated archival system when GitHub is not an appropriate distribution layer.

Do not introduce Git LFS preemptively.

## 16. AI-agent behavior

Before changing this repository, an AI agent must read `agents.md` and follow these instructions. Agents should inspect the existing tree before adding files, use stable paths, preserve originals, avoid duplicates, and verify that links and metadata remain internally consistent.

Agents must not invent academic documents, source URLs, official status, authorship, dates, or verification claims.

## 17. Adding a new item

Use this order:

1. Identify institution and program.
2. Identify whether the program uses semester or year organization.
3. Identify the subject and stable subject code.
4. Choose the correct material category.
5. Choose a deterministic filename.
6. Preserve the original file format.
7. Add provenance/metadata when useful.
8. Add OCR as a separate derived artifact when appropriate.
9. Update the relevant index/README.
10. Check for duplicates and accidental secrets.

## 18. Validation before commit

For every meaningful archive change, verify:

- the path matches the academic hierarchy;
- the filename is deterministic;
- the source is not duplicated unnecessarily;
- original and derived files are distinguishable;
- provenance is not fabricated;
- Markdown links point to real paths;
- no secrets or private credentials were added;
- the relevant index/README is not stale.

## 19. Scope control

Prefer the smallest structure that solves the problem. Do not add a database, web app, CI system, semantic-search layer, or complex metadata schema merely because it might be useful someday.

The repository should remain a clean academic archive first and an automation-friendly data source second.

## 20. Final audit

Before declaring a structural change complete, compare the result against this file and `agents.md`. Specifically check discoverability, scalability, naming, provenance, copyright handling, OCR separation, duplicate avoidance, and AI-agent readability.
