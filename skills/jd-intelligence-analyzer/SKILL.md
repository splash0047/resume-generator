---
name: JD Intelligence Analyzer
description: Convert a job description into hard eligibility conditions, required/preferred criteria, role responsibilities, and an evidence map without arbitrary weighted match scores.
---

# JD Intelligence Analyzer

## Phase 0 — Hard Eligibility

Extract:
- graduation batch / degree completion timing;
- student/new-grad status;
- degree discipline;
- location / relocation;
- work authorization / sponsorship;
- internship/full-time availability;
- mandatory years of experience;
- other explicit application conditions.

Classify each: **Meets / Does not meet / Unclear**.

## Phase 1 — Requirement Classification

Classify statements as:
- **Required** — explicit must-have qualification/responsibility;
- **Preferred** — desirable but not mandatory;
- **Context** — domain, team, culture, or secondary technology information.

Do not infer "critical" solely from keyword repetition. Repeated words may reflect writing style rather than hiring weight.

## Phase 2 — Responsibility Map

Extract the actual work:
- systems to build or support;
- users/stakeholders;
- data or infrastructure involved;
- quality/security/reliability expectations;
- collaboration responsibilities.

## Phase 3 — Evidence Map

For each criterion, mark:
- **Direct** — demonstrated in experience/project;
- **Indirect** — coursework/certification/adjacent work;
- **Missing** — no truthful evidence;
- **Unknown** — evidence not yet checked.

Example:

| Criterion | Type | Candidate evidence | Strength |
|---|---|---|---|
| Python | Required | FastAPI + ML projects | Direct |
| AWS | Preferred | AWS re/Start credential | Indirect |
| 2 years production experience | Required | Student internships | Missing |

## Phase 4 — Language for Tailoring

Identify terminology worth using exactly when truthful:
- official tool/product names;
- role-specific nouns;
- responsibility wording.

Do not target a fixed repetition count.

## Phase 5 — Ambiguities and Risks

Surface:
- contradictory experience requirements;
- unclear graduation eligibility;
- "preferred" items presented like requirements;
- role titles that do not match responsibilities;
- vague scope;
- unusual availability conditions.

## Output

### JD + Eligibility Briefing
1. hard eligibility table;
2. required criteria;
3. preferred criteria;
4. top responsibilities;
5. requirement-to-evidence matrix;
6. missing/unclear evidence;
7. role-family recommendation for selecting the correct resume variant.

You may summarize coverage as counts, e.g. "6 required criteria have direct evidence, 1 indirect, 1 missing." Do not label this an ATS score or hiring probability.
