---
name: Fresher Signal Analyzer
description: Evaluate new-grad hiring evidence across education, DSA, projects, repositories, deployment, internships, and role alignment without inventing a universal fresher score.
---

# Fresher Signal Analyzer

## Purpose

Identify which parts of a new-grad profile are strong, weak, missing, or irrelevant for a target role.

Do not assign a universal 1-10 score or imply a specific signal predicts callbacks.

## Evidence Areas

### Education
Record degree, expected graduation, CGPA/percentage when supplied, and relevant coursework only if it helps the role.

### DSA / Problem Solving
Evidence can include:
- verified coding profiles;
- contest results;
- coursework/projects with algorithmic depth;
- interview-assessment performance supplied by the candidate.

Do not assume lack of a public profile means lack of DSA ability.

### Internship / Work Evidence
Check:
- clarity of employer/program naming;
- actual responsibilities;
- tools used;
- deliverables;
- measured results with provenance.

### Project Depth
For the top relevant projects, check:
- implemented architecture;
- meaningful technical decisions;
- tests;
- failure handling;
- deployment;
- documentation;
- current repository consistency.

### GitHub Quality
Check repository hygiene qualitatively:
- setup works;
- README reflects current code;
- secrets are not exposed;
- meaningful commits/files exist;
- tests/CI where appropriate;
- no obviously fabricated benchmark claims.

### Deployment Evidence
Classify as:
- local only;
- publicly deployed demo;
- production/operational only when supported by real evidence.

### Certifications
Separate:
- exam-based professional certifications;
- training completions / badges;
- courses.

### Communication of Role Identity
Check whether the profile consistently supports one target role family rather than listing unrelated tools.

### Application Readiness
Check hard eligibility first: graduation batch, degree, dates, experience requirements, location/work authorization, and availability.

## Output

| Signal | Status | Evidence | Gap | Next action |
|---|---|---|---|---|
| Education | Strong / Adequate / Weak / Unknown | ... | ... | ... |
| DSA | ... | ... | ... | ... |
| Internship | ... | ... | ... | ... |
| Project depth | ... | ... | ... | ... |
| GitHub quality | ... | ... | ... | ... |
| Deployment | ... | ... | ... | ... |
| Certifications | ... | ... | ... | ... |
| Role identity | ... | ... | ... | ... |
| Application readiness | ... | ... | ... | ... |

Then provide:
- strongest 3 signals;
- weakest 3 signals;
- highest-leverage improvements before the next application cycle.

## Guardrails

- No callback-rate claims.
- No universal fresher score.
- No requirement for public LeetCode/GitHub metrics unless the role or user specifically values them.
- Evidence strength matters more than quantity.
