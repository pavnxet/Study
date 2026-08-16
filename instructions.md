# Study Repository Instructions

## Purpose

`Study` is a long-term academic archive for study material and Rajasthan examinations. It prioritizes preservation, discoverability, provenance, and maintainability.

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

Before modifying the repository, agents must read `agents.md`, this file, relevant READMEs, and inspect the existing tree. The directory structure is part of the knowledge model and must not be changed casually.

## Validation

Before committing, verify hierarchy, naming, provenance, original/derived separation, duplicate avoidance, links, indexes, documentation, and absence of secrets.
