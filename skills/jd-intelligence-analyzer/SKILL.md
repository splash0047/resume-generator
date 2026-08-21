---
name: JD Intelligence Analyzer
description: Transform a raw job description into a weighted keyword requirement graph and infer the writing style profile from JD content (not company name). Use this before any resume generation task.
---

# JD Intelligence Analyzer

## When to Use This Skill

Use this skill as **Phase 0** — the very first step — whenever the user provides a job description. This skill must run before:
- Resume tailoring
- Bullet generation
- Evidence database population
- Humanizer style selection

Trigger phrases: "I have a JD", "here's the job posting", "I'm applying to", "optimize for this role", "tailor my resume"

## Core Capabilities

- Build a weighted keyword requirement graph from any job description
- Classify keywords into importance tiers (Critical / Major / Minor)
- Infer the correct writing style profile from JD content — never from company name
- Detect company type and audience tier from verbs, responsibilities, and domain terms
- Output a structured briefing that all downstream pipeline stages consume

---

## Step 1: Keyword Importance Graph

Parse the full JD text and extract every technical term, skill, methodology, and domain word. Then assign each an importance tier based on frequency and placement.

### Importance Tiers

| Tier | Criteria | Resume Impact |
|---|---|---|
| **Critical** | ≥5 mentions OR appears in "Required" / "Must have" / "You have" | MUST appear in resume. Missing = likely rejection. |
| **Major** | 3–4 mentions OR appears in "Preferred" / "Nice to have" / "Bonus" | SHOULD appear. Absence is a significant gap. |
| **Minor** | 1–2 mentions, not emphasized | Nice to include. Absence is acceptable. |

### Output Format

```markdown
## Keyword Importance Graph

### Critical Keywords (must appear in resume)
| Keyword | Mentions | JD Section |
|---|---|---|
| Python | 12 | Required, Responsibilities (×8), Preferred |
| FastAPI | 7 | Required, Tech Stack, Responsibilities |
| Docker | 5 | Required, Tech Stack |

### Major Keywords (should appear)
| Keyword | Mentions | JD Section |
|---|---|---|
| Kubernetes | 4 | Preferred, Tech Stack |
| PostgreSQL | 3 | Preferred |

### Minor Keywords (nice to have)
| Keyword | Mentions | JD Section |
|---|---|---|
| Redis | 1 | Bonus |
| GraphQL | 1 | Bonus |

### Weighted Match Score Formula
Overall Match = (Critical Present% × 0.60) + (Major Present% × 0.30) + (Minor Present% × 0.10)
Target: ≥85% overall
```

---

## Step 2: Writing Style Inference (2D Matrix)

Infer the writing style from **JD content only**. Never use the company name as the primary signal — the same company may post very different roles requiring very different styles.

### Dimension 1: Audience Tier

Detect the primary reader of the resume from the responsibilities and interview framing in the JD.

| Audience | JD Signals |
|---|---|
| **Recruiter** | High-level role descriptions, broad skill lists, "culture fit" language, salary mentioned, benefits emphasized |
| **Engineering Manager** | "You will design / lead / architect", code review mentions, system design references, team collaboration language |
| **Researcher** | "Co-author", "publish", "benchmark", "experiment", "literature review", conference mentions |

### Dimension 2: Company Type

Detect from domain vocabulary, product references, and action verbs.

| Company Type | JD Signals |
|---|---|
| **Startup / Open Source** | "Ship", "own it", "iterate", "move fast", "small team", "wear many hats", "open-source contribution", "PRs", "community" |
| **Enterprise / Big Tech** | "Scale", "SLA", "compliance", "stakeholder", "roadmap", "10M+ users", "distributed systems", "reliability", "on-call" |
| **Research** | "Training", "model", "fine-tuning", "inference", "paper", "benchmark", "experiment", "dataset", "GPU", "CUDA" |
| **DevTools / API-first** | "Developer experience", "SDK", "API design", "DX", "documentation", "adoption", "integration", "CLI" |

### The 2D Writing Style Matrix

| | Startup / Open Source | Enterprise / Big Tech | Research | DevTools / API-first |
|---|---|---|---|---|
| **Recruiter** | Concise, action verbs, shipped products | Scale + reliability + team impact | Clear summaries of results | Adoption metrics, integrations |
| **Engineering Manager** | Architecture decisions, velocity, ownership | System design, fault tolerance, SLA | Experiment design, methodology | API contracts, extensibility, DX |
| **Researcher** | Novel approaches, contribution to field | Scalable research infra | Rigorous methodology, benchmarks | Research tools, reproducibility |

### Inferred Profile Output

```markdown
## Inferred Writing Style Profile

**Audience Tier:** Engineering Manager
**Company Type:** Startup / Open Source
**Combined Profile:** [Startup/OS × Eng Manager]

**Writing Guidance:**
- Lead with architecture decisions and technical reasoning
- Emphasize ownership and end-to-end delivery
- Open-source contributions are high signal — cite GitHub activity
- Avoid corporate language; write as an engineer, not a marketer
- Use verbs: built, designed, shipped, contributed, optimized, measured
```

---

## Step 2.5: Role Family Classification

Classify the JD into a role family. This classification drives project selection and skill ordering from the Candidate Position Brief.

### Role Family Detection

| Role Family | JD Signals |
|---|---|---|
| **SDE / Software Engineer** | "DSA", "algorithms", "data structures", "system design", "OOP", "clean code", language-specific requirements (Java, C++, Python), "coding round" |
| **AI/ML Engineer** | "machine learning", "deep learning", "NLP", "LLMs", "model training", "inference", "RAG", "AI agents", "MLOps", "data pipeline" |
| **Full Stack Developer** | "React", "Angular", "Vue", "Node.js", "REST API", "responsive design", "frontend + backend", "full stack" |
| **DevOps / Cloud Engineer** | "CI/CD", "Kubernetes", "Docker", "Terraform", "cloud infrastructure", "monitoring", "SRE", "deployment" |
| **Data Engineer** | "ETL", "Spark", "Kafka", "data warehouse", "BigQuery", "Airflow", "data pipeline", "streaming" |

### Output

```markdown
## JD Role Family

**Classified as:** [Role Family]
**Confidence:** [High / Medium / Low]
**Signals:** [List of JD phrases that led to classification]

**Comparison to Candidate Position Brief:**
- Candidate primary: [Role Family]
- JD role family: [Role Family]
- Alignment: [Match / Adjacent / Mismatch]

If mismatch: Consider switching to candidate's secondary role positioning.
```

---

## Step 3: Red Flag Detection

Scan the JD for signals that indicate a poor role fit or unrealistic expectations.

| Red Flag | Signal | Action |
|---|---|---|
| Scope creep | "Wear many hats", "rockstar", "ninja", "10x" | Note: role may have undefined scope |
| Compensation mismatch | Extremely wide salary range (e.g. ₹8L–₹30L) | Flag for offer comparison analysis |
| Tech stack mismatch | >40% Critical keywords absent from candidate profile | Flag as stretch role; note gaps |
| Vague requirements | No specific technologies in "Required" | JD may be poorly written; proceed with caution |

---

## Step 4: Project Selection Briefing

Based on the keyword importance graph, rank the candidate's projects by relevance:

```markdown
## Project Selection Priority

For this JD, rank your projects in this order:

1. **[Project A]** — covers 4/5 Critical keywords (Python, FastAPI, Docker, PostgreSQL)
2. **[Project B]** — covers 2/5 Critical keywords (Python, PostgreSQL)
3. **[Project C]** — covers only Minor keywords (Redis)

Recommendation: Lead with Project A and Project B. Drop Project C unless space permits.
```

### Technologies to Remove/Minimize

Based on the keyword importance graph and JD role family, output technologies from the candidate's profile that should be DE-EMPHASIZED on this resume:

```markdown
## Technologies to Remove/Minimize

For this JD, the following candidate skills should NOT appear in Technical Skills
(or appear only if space permits after all relevant skills are listed):

| Technology | Reason |
|---|---|
| [Tech] | Not mentioned in JD; dilutes SDE specialization signal |
| [Tech] | Mentioned once as Minor; don't lead with it |
| [Tech] | Domain mismatch — this is an AI/ML technology for an SDE role |

**Skills section should have ≤15 technologies total.**
**Order by:** JD Critical → JD Major → JD Minor → Candidate core identity
```

---

## Full Output Delivered to Downstream Stages

Every downstream skill (Bullet Generator, Humanizer, Resume Critic) receives:

```markdown
## JD Intelligence Briefing

**Role:** [Title] at [Company]
**Date:** [Date]

### Keyword Importance Graph
[Critical / Major / Minor tables]

### Inferred Style Profile
Audience: [Recruiter | Eng Manager | Researcher]
Company Type: [Startup/OS | Enterprise/Big Tech | Research | DevTools]
Combined Profile: [e.g., Enterprise × Eng Manager]

### Project Priority Order
1. [Project name] — [reason]
2. [Project name] — [reason]

### Red Flags
[Any detected | None]

### Weighted Match Score (Current)
Before resume tailoring: X%
Target after tailoring: ≥85%
```

---

## Rules

1. **Never use company name as the primary style signal.** Always infer from JD content.
2. **Keyword counting must be exhaustive.** Read the full JD text, including benefits and about-the-company sections (they sometimes contain repeated skill signals).
3. **Critical keywords must appear in the resume** — missing even one is a significant risk.
4. **The briefing is consumed by every downstream stage** — format it clearly so Bullet Generator, Humanizer, and Critic can reference it without re-reading the JD.
