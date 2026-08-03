---
name: Resume Humanizer
description: Score and rewrite resume bullets to remove AI writing patterns and apply engineering prose. Uses a 7-dimension scoring system — not a hard banned-word filter. Writing style is inferred from the JD Intelligence Briefing, not from company name.
---

# Resume Humanizer

## When to Use This Skill

Use this skill as **Phase 3** — after bullet generation (PACTI), before LaTeX formatting. Run it on all bullets before they enter the LaTeX template.

Trigger phrases: "humanize my resume", "remove AI language", "make this sound more natural", "style check", "review my bullets"

Also use proactively when you detect:
- Any of the flagged words (leveraged, spearheaded, pioneered, etc.) appearing in bullets
- Bullets that read like marketing copy rather than engineering notes
- Bullets with no technology or system name
- Bullets with adjectives but no concrete nouns

---

## Core Principle

> **This is a style checker, not a word filter.**
> Words are not banned. They are penalized when overused or when they substitute for specific technical content.
> "Leveraged Kubernetes autoscaling" is perfectly natural.
> "Leveraged cutting-edge AI to deliver innovative solutions" is not.
> The difference is specificity, not the word itself.

---

## 7-Dimension Scoring System

Score the full set of resume bullets on each dimension (0–10). All dimensions must meet their target before the resume proceeds to LaTeX generation.

| # | Dimension | Target Score | What's Measured |
|---|---|---|---|
| 1 | AI Buzzword Score | ≤2/10 | Frequency and clustering of AI-cliché words |
| 2 | Specificity Score | ≥8/10 | Every bullet names ≥1 technology, algorithm, system, or proper noun |
| 3 | Evidence Score | 10/10 | Every bullet traceable to the evidence database or GitHub source |
| 4 | Metric Density | ≥7/10 | ≥1 measurable outcome per bullet (%, time, users, latency, count) |
| 5 | Technical Density | ≥8/10 | Architecture / algorithm / design reasoning present in technical bullets |
| 6 | Readability | ≥8/10 | Max 1 adjective per bullet; no filler words; ≤2 lines when rendered |
| 7 | Interview Defensibility | 10/10 | Every bullet has a Q&A pair in the evidence database that the candidate can answer |

---

## Dimension 1: AI Buzzword Score (target ≤2/10)

### Flagged Words — Penalized When Overused

These words are **not banned**. They are penalized if:
- Used more than once across the full resume, OR
- Used as a substitute for specific technical content (i.e., the word is the only content)

| Word | Acceptable Use | Flagged Use |
|---|---|---|
| leveraged | "Leveraged Kubernetes autoscaling to handle traffic spikes" | "Leveraged cutting-edge AI techniques" |
| spearheaded | "Spearheaded migration to microservices (once, specific)" | Used 3× across resume |
| pioneered | "Pioneered adoption of Rust in the team's backend codebase" | "Pioneered innovative solutions" |
| orchestrated | "Orchestrated LangGraph multi-agent pipeline" | "Orchestrated seamless collaboration" |
| championed | Used once, describing specific advocacy | Used as vague leadership claim |
| utilized | Almost always replaceable with "used" | "Utilized various technologies" |
| seamless | Should never appear — always vague | Any usage |
| cutting-edge | Should never appear — always vague | Any usage |
| innovative | Should never appear — claims are hollow | Any usage |
| robust | Should never appear — show it, don't say it | Any usage |
| passionate | Should never appear in technical bullets | Any usage |
| dynamic | Should never appear — always vague | Any usage |
| results-driven | Should never appear — should be evident | Any usage |
| synergy | Should never appear | Any usage |
| state-of-the-art | Should never appear — use specific benchmark | Any usage |

### Preferred Replacements

| Instead of | Use |
|---|---|
| leveraged, utilized | built, used, applied |
| spearheaded | led, initiated, designed |
| pioneered | introduced, created, first to implement |
| orchestrated | coordinated, built, structured |
| championed | advocated for, proposed, implemented |
| seamless | (delete — describe what was smooth instead) |
| cutting-edge | name the specific technology |
| innovative | describe what was novel specifically |

---

## Dimension 2: Specificity Score (target ≥8/10)

Every bullet must contain at least one of:
- A named technology (FastAPI, LangGraph, Isolation Forest, PostgreSQL, React)
- A named algorithm or model (Isolation Forest, LSTM, BFS, Transformer)
- A named system or service (GitHub Actions, Celery, Redis, Kafka)
- A named design pattern (event-driven, microservice, CQRS)
- A specific metric with units (40%, 3 minutes, 500ms, 100K requests)

**Specificity check — rewrite triggers:**

```
❌ "Built a system to handle large amounts of data efficiently"
✅ "Built a batch processing pipeline with Apache Kafka consuming 50K events/hour"

❌ "Implemented machine learning for anomaly detection"
✅ "Implemented Isolation Forest anomaly detection on unlabeled infrastructure logs"

❌ "Improved system performance significantly"
✅ "Reduced API response time from 850ms to 210ms by adding Redis caching"
```

---

## Dimension 5: Technical Density (target ≥8/10)

Technical bullets must contain engineering reasoning, not just facts. The PACTI structure enforces this — specifically the "Core Technical Decision" step.

**Low technical density (rewrite):**
> Built an anomaly detection system using Isolation Forest.

**High technical density (keep):**
> Chose Isolation Forest over DBSCAN for anomaly detection because the log data lacked labels; the unsupervised nature of IF made it robust to varying log densities across microservices.

The difference: the second bullet explains *why*, not just *what*. A recruiter reading the second bullet immediately understands the candidate thinks like an engineer, not a feature-lister.

---

## Dimension 6: Readability (target ≥8/10)

### Filler Word Removal

Delete on sight:
- "successfully" (if you did it, it was successful)
- "effectively" (same logic)
- "various" (name them)
- "multiple" (count them)
- "many" (count or estimate: "10+", "~50")
- "several" (same)
- "cutting-edge", "state-of-the-art" (name the tech)

### Adjective Budget

**Maximum 1 adjective per bullet.** Adjectives that add specificity are fine ("asynchronous", "distributed", "real-time"). Adjectives that are opinions are not ("innovative", "robust", "efficient" without a metric).

### Line Length

**Maximum 2 lines when rendered in LaTeX.** If a bullet is longer:
1. Split into two bullets (each must still meet all 7 dimensions independently)
2. Or cut to the most impactful single fact + metric

---

## Writing Style Application

The style profile from the JD Intelligence Briefing is applied here. The tone, verb choices, and emphasis shift based on the 2D matrix output.

| Profile | Tone Guidance |
|---|---|
| Startup/OS × Eng Manager | Ownership language: "designed", "built end-to-end", "shipped". Architecture reasoning required. |
| Enterprise × Eng Manager | Reliability and scale: SLA, fault tolerance, distributed system context. |
| Research × Researcher | Methodology and rigor: experiment design, datasets used, evaluation metrics |
| DevTools × Recruiter | Developer experience: API design quality, adoption metrics, documentation |
| Big Tech × Eng Manager | Scale and impact: users served, requests/sec, latency, infra cost |
| Open Source × Recruiter | Contribution clarity: PRs merged, stars, community impact |

---

## Humanizer Pass Output Format

Run the 7-dimension scorecard on the full bullet set. Output:

```markdown
## Humanizer Report

### Scores
| Dimension | Score | Status |
|---|---|---|
| AI Buzzword | 1/10 | ✅ Pass |
| Specificity | 9/10 | ✅ Pass |
| Evidence | 10/10 | ✅ Pass |
| Metric Density | 7/10 | ✅ Pass |
| Technical Density | 8/10 | ✅ Pass |
| Readability | 9/10 | ✅ Pass |
| Interview Defensibility | 10/10 | ✅ Pass |

### Applied Style Profile
[Startup/OS × Eng Manager]

### Flags
- Bullet 3: "utilized various techniques" → No specific technology named. Rewrite required.
- Bullet 7: "spearheaded" used twice across resume. Second usage flagged. Rewrite one.

### Rewrites
**Original:** "Utilized various NLP techniques for text processing"
**Revised:** "Applied spaCy for tokenization and entity extraction on 50K Hinglish support tickets"

**Original (Bullet 7 second use):** "Spearheaded data pipeline improvements"
**Revised:** "Redesigned the ingestion pipeline to process logs asynchronously, reducing backlog from 4 hours to under 10 minutes"
```

---

## Rules

1. **Style rules are checks, not blocks.** Flag and suggest; never silently delete content.
2. **Writing style comes from the JD Intelligence Briefing.** If no briefing exists, default to [Enterprise × Eng Manager].
3. **All 7 dimensions must pass before proceeding to LaTeX.** If any fail, rewrite and re-score.
4. **Do not invent specificity.** If a bullet lacks a technology name and the evidence database has no source for one, flag it — do not fabricate a technology name.
5. **Readability beats cleverness.** A simple, precise bullet beats a sophisticated but confusing one.
