---
name: Resume ATS Optimizer
description: Validate resume parsing, map job requirements to evidence, and improve role-specific machine readability without inventing universal ATS scores.
---

# Resume ATS Optimizer

## When to Use This Skill

Use this skill when the user wants to:
- optimize a resume for a specific job;
- diagnose low response rates;
- check whether a PDF/DOCX is likely to parse cleanly;
- identify missing required qualifications or weak evidence;
- compare a resume against a job description.

Do not present an internal heuristic as the employer's ATS score or claim that a particular percentage guarantees progression.

## Core Principle

Treat resume screening as a sequence of distinct checks:

1. **Eligibility** — graduation batch, degree, location/work authorization, availability, required years of experience, and other hard application conditions.
2. **Parsing** — can the submitted file be extracted in a sensible reading order?
3. **Requirement evidence** — does the resume show credible evidence for the job's required and preferred criteria?
4. **Human readability** — can a recruiter quickly identify role fit, recent education/experience, and relevant projects?
5. **Downstream stages** — assessments and interviews are separate from resume quality and must be diagnosed separately.

Different employers configure different workflows. Never imply that all ATS products rank candidates using keyword density.

## Step 1 — Eligibility Gate

Extract explicit conditions from the job description and application form. Classify each as:
- **Hard requirement** — missing it may make the application ineligible.
- **Preferred qualification** — useful but not automatically disqualifying.
- **Unknown / needs confirmation** — wording is ambiguous.

Examples: expected graduation year, student status, degree discipline, location, work authorization, internship dates, minimum professional experience.

If a hard requirement is not met, state that clearly before optimizing wording.

## Step 2 — Parsing Validation

For the actual exported file:
- verify it is text-based rather than scanned;
- extract the text and inspect reading order;
- confirm name, contact details, education, dates, skills, links, and section headings survive extraction;
- check whether application fields populated from the upload are correct;
- avoid graphics, photos, text boxes, complex tables, multi-column layouts, and contact details placed only in headers/footers;
- use the employer's requested file format.

A parser warning is not automatically a rejection. Report exactly what failed or was lost.

## Step 3 — Requirement-to-Evidence Matrix

Build a table with these columns:

| Job criterion | Type | Evidence in resume | Evidence strength | Action |
|---|---|---|---|---|
| Python | Required | Root Cause Analyzer + internship | Direct | Keep and lead with it |
| AWS | Preferred | AWS re/Start credential only | Indirect | Do not imply production AWS ownership |
| 2+ years experience | Required | Student internships only | Missing | Eligibility risk |

Evidence strength:
- **Direct** — implemented, used, measured, or owned in a project/experience with supporting detail.
- **Indirect** — coursework, certification, README claim, or adjacent experience.
- **Missing** — no truthful evidence available.

Do not add a keyword unless it accurately describes the candidate's work or credential.

## Step 4 — Role-Specific Keyword Use

Use exact job terminology when truthful, but do not optimize for repetition counts.

Priority:
1. Technical Skills for concise discoverability.
2. Experience bullets for proof of use.
3. Project bullets for engineering depth.

A required term appearing once with strong evidence is more useful than repeating it several times without proof.

## Step 5 — Resume Output Rules

- Use standard section names: Education, Experience, Projects, Technical Skills.
- For students/new graduates, make expected graduation explicit.
- Keep the resume focused on one role family at a time.
- Prefer 2–3 relevant projects over a long inventory.
- Use measured outcomes when available; otherwise use concrete implementation detail.
- Do not fabricate percentages, user counts, latency improvements, production scale, or "production-ready" claims.
- Distinguish training programs/badges from exam-based certifications.
- Ensure linked repositories visibly support project claims.

## Diagnostic Output

Return:

1. **Eligibility findings**
2. **Parsing findings**
3. **Requirement-to-evidence matrix**
4. **Unsupported or ambiguous claims**
5. **Recommended role-specific edits**
6. **Export validation checklist**
7. **Outcome-tracking recommendation**

You may compute a private coverage ratio such as "7 of 9 required criteria have direct evidence" for explanation. Do not label it a universal ATS score or assign a pass/fail threshold unless the employer publishes one.

## Outcome Tracking

When the user is applying repeatedly, track:
- job URL and role family;
- eligibility status;
- resume version;
- application channel;
- submission date;
- outcome: pending, rejected before assessment, assessment received, interview received, offer/reject after interview.

Use those outcomes to diagnose where progression stops. Do not assume every rejection is caused by ATS parsing or keywords.

## Guardrails

- Never promise a shortlist, callback rate, or interview multiplier.
- Never invent a metric to make a bullet look stronger.
- Never equate a parser issue with automatic rejection unless the employer documents that behavior.
- Never claim a certification proves hands-on production experience.
- Never hide an eligibility mismatch with wording.
- Always prefer verifiable evidence over keyword density.
