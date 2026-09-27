---
name: Recruiter Rejection Simulator
description: Review a resume from several reader perspectives to identify likely comprehension or evidence risks. This is qualitative editorial feedback, not a prediction of hiring outcomes.
---

# Recruiter Rejection Simulator

## Purpose

Use this skill after the evidence and parsing checks to stress-test how clearly the resume communicates role fit.

This skill does **not** predict whether a recruiter will reject or interview the candidate. It simulates reader questions so weaknesses can be fixed before submission.

## Perspective 1 — Quick Recruiter Scan

Check whether a reader can quickly identify:
- current degree / graduation timing;
- target role family;
- strongest recent experience;
- strongest relevant project;
- core technologies;
- location or work-status information when relevant.

Flag issues such as:
- unclear graduation date;
- crowded skills inventory;
- irrelevant project ordering;
- vague company/program naming;
- claims that require too much interpretation.

Output: **Clear / Needs revision**, with specific reasons.

## Perspective 2 — Detailed Recruiter Review

Check:
- hard eligibility is visible and accurate;
- required job criteria have direct or indirect evidence;
- employment/program names are not misleading;
- dates and chronology are consistent;
- credentials are described by their official titles;
- links support the claims made beside them.

For each concern, give:
1. what the reader may misunderstand;
2. the exact text causing it;
3. a concrete rewrite or removal.

## Perspective 3 — Engineering Manager Review

Check:
- implementation depth;
- architecture and debugging evidence;
- testing / validation evidence;
- whether the candidate can explain each technical claim;
- whether project claims match repositories;
- whether metrics have measurement provenance.

Classify each concern as:
- **Ready to defend**
- **Needs evidence**
- **Overstated**
- **Irrelevant to this role**

## Combined Output

### Reader Risk Review

| Area | Status | Evidence / issue | Recommended action |
|---|---|---|---|
| Role identity | Clear / Needs revision | ... | ... |
| Eligibility visibility | Clear / Needs revision | ... | ... |
| Project credibility | Clear / Needs revision | ... | ... |
| Technical depth | Clear / Needs revision | ... | ... |
| Metrics | Clear / Needs revision | ... | ... |
| Links | Clear / Needs revision | ... | ... |

Then provide:
- top 3 issues to fix before submission;
- claims to remove or verify;
- strongest content to preserve.

## Guardrails

- Never output "Interview", "Reject", "Shortlist", or a hiring probability as your own verdict.
- Never claim a universal recruiter attention span.
- Never treat this simulation as validation of real employer behavior.
- Treat the review as qualitative editorial feedback only.
