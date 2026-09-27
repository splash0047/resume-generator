---
name: Resume Version Manager
description: Track resume variants, job applications, evidence changes, and observed outcomes so tailoring decisions can be evaluated from real data.
---

# Resume Version Manager

## Goals

Maintain:
- a clean master profile;
- role-family base resumes;
- job-specific variants;
- application outcome history;
- evidence/version traceability.

## Recommended Structure

### Master Profile
Keep factual source data only:
- education;
- experience;
- projects;
- skills;
- credentials;
- verified metrics with provenance;
- links.

### Base Variants
Examples:
- Backend_FullStack
- Applied_AI_ML
- ERP_Data

### Job-Specific Variant Record

| Field | Example |
|---|---|
| Company | ExampleCo |
| Role | Backend Intern |
| Job URL | https://... |
| Variant | Backend_FullStack |
| Submitted file | Pinak_ExampleCo_Backend.pdf |
| Date | 2026-09-28 |
| Channel | Direct / Referral / Campus / Recruiter |
| Eligibility | Meets / Unclear / Mismatch |
| Required evidence | 6 direct / 1 indirect / 1 missing |
| Outcome | Pending / Assessment / Interview / Rejected / Offer / Withdrawn |
| Notes | ... |

Do not store a universal "match score" column.

## Outcome Definitions

- **Pending** — no decision yet.
- **Assessment** — assessment received.
- **Interview** — interview stage reached.
- **Rejected** — explicit rejection received.
- **Offer** — offer received.
- **Withdrawn** — candidate withdrew.
- **Closed/Unknown** — role closed or outcome unknown.

Do **not** automatically convert "no response after N weeks" into rejection. Keep it Pending or Closed/Unknown depending on evidence.

## Versioning Rules

- Never overwrite the master profile with speculative job keywords.
- Store measured metrics with source/context.
- When project repositories change materially, re-audit their resume descriptions.
- Preserve the exact submitted PDF for each important application when practical.

## Analysis

After enough observations, compare:
- role families;
- channels;
- eligibility patterns;
- pre-assessment vs post-assessment stops;
- which project combinations appeared in interview-generating applications.

Treat these as descriptive observations. Do not claim causal relationships from small samples.

## Guardrails

- No callback probability.
- No invented causal conclusions.
- No "no response = rejected" rule.
- No ATS score history.
