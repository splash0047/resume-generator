---
name: Resume Critic
description: Final evidence, clarity, parsing, and defensibility gate for generated resumes. Produces a qualitative audit rather than arbitrary numeric quality scores.
---

# Resume Critic

## Purpose

Use this as the final quality gate before PDF delivery.

The resume should not be declared ready while a material issue remains unresolved. Do not convert editorial judgment into a universal score.

## Final Gates

### 1. Eligibility Visibility
Check that the resume clearly and accurately shows relevant graduation timing, degree, location, availability, and other hard criteria when the job requires them.

### 2. Parsing Safety
Check standard section names, text-based PDF output, readable extraction order, and absence of unnecessary layout complexity.

### 3. Evidence Coverage
Every substantive bullet must trace to one or more of:
- verified repository implementation;
- internship/work record;
- project documentation;
- reproducible benchmark/test;
- candidate-confirmed contribution.

### 4. Truthfulness
Flag wording that exceeds evidence. Examples:
- Dockerfile -> containerized, not automatically "scalable production platform";
- import -> dependency referenced, not automatically end-to-end integration;
- deployment -> publicly deployed, not automatically production-ready;
- score -> diagnostic score unless calibrated probability is actually established.

### 5. Metric Provenance
For every metric record:
- source;
- environment;
- sample size or evaluation scope when relevant;
- whether it can be reproduced or explained.

If provenance is absent, remove the number or rewrite descriptively.

### 6. Role Relevance
The resume should emphasize one role family. Remove low-value technologies and projects that dilute the target.

### 7. Readability
Check concise bullets, consistent tense, dates, section hierarchy, links, and enough whitespace for normal reading.

### 8. Interview Defensibility
For every project/experience bullet, ask:
- What did you personally implement?
- Why this approach?
- How was it tested?
- What failed?
- What would you change?

If the candidate could not answer from actual work, the bullet needs revision.

### 9. Repository Consistency
Linked repositories should visibly support project titles, current architecture, and stated technologies.

### 10. Export Validation
Compile/export the actual PDF and verify:
- one-page target when appropriate for the candidate;
- no clipping or overlap;
- correct text extraction order;
- name/contact/education/dates/skills/links survive extraction.

## Audit Output

| Gate | Status | Evidence / issue | Required fix |
|---|---|---|---|
| Eligibility visibility | Pass / Needs revision | ... | ... |
| Parsing safety | Pass / Needs revision | ... | ... |
| Evidence coverage | Pass / Needs revision | ... | ... |
| Truthfulness | Pass / Needs revision | ... | ... |
| Metric provenance | Pass / Needs revision | ... | ... |
| Role relevance | Pass / Needs revision | ... | ... |
| Readability | Pass / Needs revision | ... | ... |
| Interview defensibility | Pass / Needs revision | ... | ... |
| Repository consistency | Pass / Needs revision | ... | ... |
| Export validation | Pass / Needs revision | ... | ... |

A resume is ready only when no material "Needs revision" item remains.

## Guardrails

- No ATS score.
- No AI-writing score.
- No arbitrary percentage threshold for truthfulness or evidence.
- No simulated recruiter approval as a quality certificate.
- Targeted revisions are preferred over regenerating unrelated content.
