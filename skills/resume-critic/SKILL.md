---
name: Resume Critic
description: Final quality gate for generated resumes. Scores the complete resume on 9 dimensions (including Truthfulness), runs 3 recruiter personas, generates a Resume Audit Report, and loops back to the Humanizer if any dimension fails. Use as the last step before PDF generation.
---

# Resume Critic

## When to Use This Skill

Use this skill as **Phase 6** — the final quality gate — after ATS validation and before PDF generation. If any dimension scores below its target, the pipeline loops back to the Humanizer with specific rewrite instructions.

Trigger phrases: "review my resume", "final check", "quality gate", "score my resume", "audit report", "is this ready to send"

---

## Core Principle

> **The resume does not ship until all 10 dimensions pass.**
> The Critic is not advisory — it controls whether the pipeline outputs a final PDF or loops back for revision.
> One failing dimension triggers a targeted rewrite, not a full regeneration.

---

## 10-Dimension Scorecard

| # | Dimension | Target | Fail Condition |
|---|---|---|---|
| 1 | ATS Compatibility | Pass/Fail | Non-standard section headers; tables or images in body; `\pdfgentounicode=1` missing |
| 2 | Technical Specificity | ≥8/10 | Any bullet with no named technology, algorithm, system, or design pattern |
| 3 | Evidence Coverage | 100% | Any bullet without a traceable field in the Engineering Evidence Database or GitHub source |
| 4 | AI Writing Score | ≤2/10 | More than 2 flagged cliché words across the full resume OR any word from the "should never appear" list |
| 5 | Recruiter Readability | ≥9/10 | Any bullet longer than 2 rendered lines; jargon used without context; unclear what the candidate did |
| 6 | Interview Defensibility | 100% | Any bullet without a corresponding Q&A pair in the evidence database |
| 7 | JD Match | Match-Gap Report | Any Critical-tier keyword from the JD Intelligence Briefing absent from the resume; report shows Required X/Y, Preferred X/Y, Missing list |
| 8 | One-Page Compliance | Pass | LaTeX line estimate overflows a single US Letter page |
| 9 | **Truthfulness** | **100%** | **Any bullet where wording overstates or misrepresents its evidence** |
| 10 | **Candidate Positioning** | **Clear** | **Resume does not communicate a single role identity in 6 seconds; skills section has >15 technologies; projects not ordered by role relevance** |

---

## Dimension 9: Truthfulness Gate

This is the most nuanced dimension and requires explicit evaluation.

### Truthfulness ≠ Confidence

| | Confidence | Truthfulness |
|---|---|---|
| **Question it answers** | Is there evidence for this claim? | Does the wording accurately reflect the evidence? |
| **Example** | Dockerfile found → 80% confidence | "Designed a scalable containerized deployment pipeline" → OVERSTATEMENT |
| **Correct version** | Dockerfile found → "Containerized using Docker" → 100% truthful |

### Truthfulness Failure Patterns

**Pattern 1: Scope Overstatement**
- Evidence: `Dockerfile` exists in repo
- ❌ Overstatement: "Designed a scalable, production-ready containerized deployment pipeline"
- ✅ Accurate: "Containerized the application using Docker with multi-stage build"

**Pattern 2: Impact Fabrication**
- Evidence: Manual testing on 15 synthetic cases
- ❌ Fabrication: "Reduced incident investigation time by 85% in production"
- ✅ Accurate: "Reduced simulated incident investigation time from ~20 min to under 3 min during development testing"

**Pattern 3: Scale Inflation**
- Evidence: Tool ran on developer's local machine
- ❌ Inflation: "Handled 10K+ log events in real-time"
- ✅ Accurate: "Processed batches of ~500 log entries during local performance testing"

**Pattern 4: Role Overstatement**
- Evidence: Candidate followed a tutorial and extended it
- ❌ Inflation: "Architected a multi-agent LLM system from scratch"
- ✅ Accurate: "Extended a LangGraph tutorial to build a custom 3-agent RCA pipeline with additional error handling and PostgreSQL persistence"

**Pattern 5: Contribution Ambiguity**
- Evidence: Team project; candidate's contribution unclear
- ❌ Ambiguous: "Built distributed data pipeline processing 1M events/day"
- ✅ Accurate: "Built the ingestion and normalization layer of a distributed pipeline handling 1M events/day (team project)"

---

## Dimension 10: Candidate Positioning Check

This dimension verifies that the resume communicates a clear role identity.

### Positioning Fail Conditions

1. **Skills section has >15 technologies** — Signal dilution. The recruiter can't identify what this candidate is good at.
2. **Projects are not ordered by role relevance** — The first project should be the strongest match for the JD role family.
3. **No clear primary technology area** — The resume spreads across AI/ML, Full Stack, DevOps, Cloud, and Data without depth in any.
4. **Certifications don't align with role** — 5 AI certifications on an SDE resume, or AWS certs on a frontend role.
5. **The 6-second test fails** — A recruiter scanning for 6 seconds cannot identify: (a) what role this candidate fits, (b) their primary tech stack, (c) their strongest project.

### Positioning Check Output

```markdown
### Candidate Positioning Check

**Role Identity (6-second test):** [CLEAR / UNCLEAR]
**Primary tech visible in 6s:** [Yes / No — what's visible instead?]
**Skills count:** [N technologies — Pass if ≤15, Fail if >15]
**Project order:** [Correct for role / Incorrect — should be reordered]
**Certification alignment:** [Aligned / Misaligned]
```

---

## 3 Recruiter Personas

After scoring the 10 dimensions, simulate three independent readers. Each reads the resume for 30 seconds (6-second scan + re-read) and answers 3 questions.

> **Fresher Calibration:** When the candidate has ≤2 years experience, all personas must calibrate expectations to entry-level. Do not penalize for lack of production-scale metrics, limited team leadership, or narrow experience breadth. DO penalize for fake metrics, scope overstatement, and unclear positioning.

### Persona 1: Technical Recruiter
*Primary concern: Is this resume readable in 6 seconds? Does the tech stack match the JD?*

Questions:
1. Can I identify the candidate's primary tech stack within 6 seconds?
2. Is every bullet readable without a technical background?
3. Are there any words or phrases that will confuse a non-technical screener?

### Persona 2: Engineering Manager
*Primary concern: Can I trust this candidate built what they claim? Is the architecture credible?*

Questions:
1. Does the architecture described make technical sense?
2. Does the candidate demonstrate understanding of *why* (not just *what*)?
3. Would I be comfortable asking this candidate to whiteboard what's on this resume?

### Persona 3: Hiring Manager
*Primary concern: Does this candidate solve the problems we actually have?*

Questions:
1. Do the project domains and scale match the role requirements?
2. Does the candidate show evidence of impact (even if learning-stage)?
3. Is there a clear technical growth trajectory?

---

## Resume Audit Report (Primary Output)

This report is delivered alongside the LaTeX file. It serves as the candidate's interview preparation tool — every claim on the resume is pre-loaded with its evidence source and the questions they'll face.

```markdown
## Resume Audit Report
**Candidate:** [Name]
**Role:** [Title] at [Company]
**Generated:** [Date]

---

### Bullet-by-Bullet Evidence Table

| # | Bullet (truncated) | Evidence Source | Confidence | Impact Type | Interview Question | Keep? |
|---|---|---|---|---|---|---|
| 1 | Designed anomaly detection with Isolation Forest... | src/anomaly/detector.py | 95% | Development | Why Isolation Forest over DBSCAN? | ✅ Keep |
| 2 | Built async FastAPI backend for log ingestion | src/api/main.py | 100% | Development | Why FastAPI over Flask? | ✅ Keep |
| 3 | Containerized using Docker with multi-stage build | Dockerfile | 80% | Development | What does each build stage do? | ✅ Keep |
| 4 | Reduced investigation time from 20 to 3 minutes | README metrics claim | 25% | Development | How was this measured? | ⚠️ Rewrite: add "during testing" qualifier |
| 5 | Implemented scalable deployment pipeline | No source found | 0% | N/A | N/A | ❌ Remove or replace with evidence |

---

### 10-Dimension Scores

| Dimension | Score | Status |
|---|---|---|
| ATS Compatibility | Pass | ✅ Pass |
| Technical Specificity | 9.5/10 | ✅ Pass |
| Evidence Coverage | 80% | ❌ FAIL — Bullet 5 uncited |
| AI Writing Score | 1/10 | ✅ Pass |
| Recruiter Readability | 9/10 | ✅ Pass |
| Interview Defensibility | 80% | ❌ FAIL — Bullet 4 missing Q&A |
| JD Match | Required: 8/10, Preferred: 4/6, Missing: [list] | ✅ Pass |
| One-Page Compliance | Pass | ✅ Pass |
| Truthfulness | 80% | ❌ FAIL — Bullet 4 overstates scope |
| Candidate Positioning | Clear | ✅ Pass |

**Dimensions Passed: 7/10**

---

### Loop-Back Instructions

**Failing dimensions: Evidence Coverage, Interview Defensibility, Truthfulness**

Actions required before re-running Critic:
1. **Bullet 4:** Add impact qualifier → "...during development testing on 15 simulated incidents"
2. **Bullet 4:** Add Q&A pair to evidence database: "How was the 20-to-3 minute improvement measured?"
3. **Bullet 5:** Remove entirely — no evidence source exists. Replace with a bullet grounded in evidence.

After revisions: re-run Humanizer (verify no new readability issues) → re-run ATS Validator → re-run Critic.

---

### Recruiter Persona Feedback

**Technical Recruiter:**
> Tech stack is immediately visible. Python, FastAPI, Docker clear in first scan. Bullet 4 latency claim may raise a flag with a skeptical screener — consider softening.

**Engineering Manager:**
> Architecture reasoning in bullet 1 (Isolation Forest choice) is strong. Bullet 5 makes a vague deployment claim with no specifics — I'd question this in an interview. Remove or substantiate.

**Hiring Manager:**
> Clear AI/ML and backend engineering profile. The project domains match the JD well. One missing piece: no deployment context. Even a simple "deployed locally" is better than silence.

---

### Interview Preparation Pack

For each kept bullet, the Q&A pairs from the evidence database are surfaced here:

**Bullet 1 — Isolation Forest anomaly detection**
- Q: Why Isolation Forest over DBSCAN?
- A: The log data was entirely unlabeled. DBSCAN requires density-based assumptions that don't generalize well to varying log volumes, whereas Isolation Forest works well on high-dimensional unlabeled data and is more robust to sparse distributions.

**Bullet 2 — FastAPI backend**
- Q: Why FastAPI over Flask?
- A: Native async support and automatic OpenAPI generation — both critical for a high-throughput log ingestion API.

[...continues for each kept bullet]
```

---

## Loop-Back Logic

If any of the 10 dimensions fails:

1. Output the failing dimension name and the specific bullets causing the failure
2. Output targeted rewrite instructions (do NOT regenerate the entire resume)
3. Send rewrites back to the Humanizer skill for re-scoring
4. After Humanizer pass: re-run ATS Validator
5. After ATS Validator pass: re-run Critic
6. Repeat until all 10 dimensions pass

**Maximum loops:** 3. If dimensions still fail after 3 loops, flag for human review with a note explaining what evidence is missing or insufficient.

---

## Rules

1. **Do not ship if any dimension fails.** The Audit Report is the output of a failing run — the LaTeX file is the output of a passing run.
2. **Targeted rewrites only.** Never regenerate the entire resume because one bullet fails. Identify exactly which bullet fails and why.
3. **Truthfulness overrides Confidence.** A bullet at 100% confidence can still fail Truthfulness if the wording exaggerates the evidence.
4. **The Audit Report is always generated**, even on a passing run. It serves as the candidate's interview prep document regardless of pass/fail status.
5. **Persona feedback is opinion, not score.** Persona opinions do not affect the 10-dimension scores — they provide qualitative signal on top of quantitative scoring.
6. **For fresher candidates, calibrate persona expectations.** Don't penalize for lack of production metrics or team leadership. DO penalize for fake metrics and scope overstatement.
