# Study Repository Instructions

## Purpose

`Study` is a long-term academic archive for study material and Rajasthan examinations. It prioritizes preservation, discoverability, provenance, and maintainability.

## Root governance files — mandatory

The following files at the repository root form the canonical governance and memory system:

| File | Purpose | Rule |
|---|---|---|
| `agents.md` | Binding AI-agent and repository rules | Keep synchronized with durable rules |
| `instructions.md` | Detailed operating instructions | Keep synchronized with actual architecture |
| `learning.md` | Reusable lessons, preferences, corrections | Edit in place; no conflicting duplicate facts |
| `summary.md` | Processing-session history | Append-only; never rewrite old entries |
| `DECISIONS.md` | Architecture decision record | Log meaningful decisions during the same session |
| `EXECUTION_FLOW.md` | Living archive-processing flow | Update when workflow/path/automation changes |

Do not create a second competing `Learning/` governance system without an explicit request.

### Mandatory post-processing pass

After every substantial post-processing operation on material, the agent must:

1. Finish the material/README/metadata update.
2. Update `DECISIONS.md` for meaningful architecture, naming, metadata, provenance, storage, or workflow decisions.
3. Update `learning.md` for new reusable lessons, user preferences, corrections, or mistakes fixed. Edit existing facts in place where appropriate.
4. Append a concise file/code-processing entry to `summary.md`. **Never delete, rewrite, or overwrite historical entries.**
5. Update `EXECUTION_FLOW.md` when the workflow, processing path, archive structure, or automation changed.
6. Re-check the relevant root governance files for consistency before declaring completion.

A substantial material-processing task is not complete until this post-processing governance pass is complete, unless a specific update is genuinely not applicable.

## Rajasthan exam archive rule

Rajasthan is the fixed scope of `exams/`; therefore **never create an `exams/rajasthan/` folder**.

For Rajasthan exams, the default archive directory is the **actual exam/post name supplied by the user**, preserving the Hindi name when supplied. Do not arbitrarily rename it to an English slug.

Also, **do not create recruitment-type subfolders** such as `direct-recruitment/` and **do not create year subfolders** such as `2024/` unless the user explicitly requests those hierarchy levels.

Year, recruitment mode, level, and similar information should normally be stored in `README.md` and `metadata.yaml`.

### Canonical pattern

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

For example:

```text
exams/पर्यवेक्षक (महिला) सीधी भर्ती/
```

with `year: 2024` and `recruitment_type: "Direct Recruitment / Open Market"` in metadata.

## University/program architecture

```text
institutions/
└── <institution>/
    └── programs/
        └── <program>/
            ├── semesters/<semester>/subjects/<subject-code>-<subject-slug>/
            └── years/<year>/subjects/<subject-code>-<subject-slug>/
```

Use the actual academic system rather than inventing semesters or years.

## Preservation and provenance

- Never replace originals with OCR, cleanup, compression, or transcription.
- Keep `original → OCR → corrected OCR → verified transcription` as distinct stages.
- Never fabricate documents, sources, dates, official status, authorship, or metadata.
- Preserve source URLs and conducting-body/institution information when known.
- Clearly state when supplied text has been formatted or normalized.
- Respect copyright and prefer source links/metadata where redistribution is questionable.

## Naming

Use stable, descriptive names. Avoid `final`, `new`, `latest`, `copy`, `scan123`, etc. Preserve actual supplied Hindi exam/post names for exam archive directories.

## Metadata

Use `metadata.yaml` when it materially improves provenance, search, or automation. Exam metadata can include:

```yaml
exam_name:
conducting_body:
year:
recruitment_type:
level:
question_count:
total_marks:
duration:
negative_marking:
```

Do not fabricate unknown values.

## Indexes and READMEs

Keep relevant indexes and READMEs accurate. Do not create redundant documentation. Missing material may be indicated, but never fabricate placeholder academic content that looks real.

## Security and scope

Never commit credentials or secrets. Do not introduce databases, web apps, AI/RAG systems, CI/CD, or Git LFS without a demonstrated need.

## AI-agent rule

Before modifying the repository, agents must read the root governance files, relevant READMEs, and inspect the existing tree. The directory structure is part of the knowledge model and must not be changed casually.

## Validation

Before committing, verify hierarchy, naming, provenance, original/derived separation, duplicate avoidance, links, indexes, documentation, and absence of secrets. Then perform the mandatory post-processing governance pass described above.
