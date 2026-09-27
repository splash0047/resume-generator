---
name: Resume Tailor
description: Tailor an evidence-grounded resume to a specific job by reordering and rewriting true experience, without arbitrary match scores or keyword-density targets.
---

# Resume Tailor

## Inputs

- target job description;
- eligibility + requirement analysis;
- candidate master profile;
- verified project/experience evidence;
- selected role-family resume.

## Tailoring Rules

### 1. Eligibility First
Do not hide a hard requirement mismatch with wording.

### 2. Reorder Before Rewriting
First:
- choose the correct role variant;
- lead with the most relevant experience/project;
- reorder skills;
- remove low-relevance content.

### 3. Rewrite Only With Evidence
Use job terminology where it accurately describes existing work.

### 4. Required Criteria
For each required criterion:
- direct evidence -> make visible;
- indirect evidence -> represent accurately;
- missing -> do not fabricate.

### 5. Preferred Criteria
Use when relevant and supported, but do not crowd out required evidence.

### 6. Metrics
Use only measured or reproducible metrics with provenance. Otherwise use concrete implementation detail.

### 7. Skills
Keep skills the candidate can explain. Do not add a tool merely because it appears in the JD.

## Tailoring Output

### Requirement-to-Resume Map

| Requirement | Evidence | Resume location | Action |
|---|---|---|---|
| REST APIs | Job Portal + RCA | Projects | Lead with concrete endpoints / auth |
| AWS | Training credential only | Certifications | Keep credential; do not imply production use |

### Change Log
- moved project X above project Y;
- removed irrelevant skills;
- rewrote bullet with verified terminology;
- removed unsupported metric;
- made expected graduation explicit.

### Final Validation
- all required claims truthful;
- no forced keyword repetition;
- one role identity;
- links consistent;
- exported PDF still parses correctly.

## Guardrails

- No estimated new match score.
- No keyword-density objective.
- No unsupported technology injection.
- No rewriting that changes ownership, scope, environment, or measurement context.
