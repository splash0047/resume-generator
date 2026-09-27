---
name: Resume Bullet Writer
description: Write concise, evidence-backed resume bullets using concrete implementation detail and defensible outcomes. Metrics are optional and require provenance.
---

# Resume Bullet Writer

## Purpose

Turn verified experience/project evidence into readable, interview-defensible bullets.

A strong bullet does **not** need a number. A precise technical implementation is stronger than an invented metric.

## Bullet Patterns

### Direct Implementation
"Implemented RBAC with JWT and Express middleware across candidate and recruiter routes."

### Architecture / Technical Decision
"Built a FastAPI diagnostic pipeline combining integrity checks, drift detection, SHAP feature analysis, and historical-case retrieval."

### Measured Result
Use only with verified provenance:
"Reduced median search latency from 310 ms to 140 ms in a 1,000-query local benchmark by adding compound indexes."

### Research / Evaluation
"Achieved 0.84 macro F1 on the held-out test split using [model], evaluated on [dataset/scope]."

## PACTI — Optional

Use selectively:
- Problem
- Action
- Core technical decision
- Technical implementation
- Impact

Do not force all five parts into every bullet.

## Metric Rules

Use a number only when supported by:
- benchmark/test output;
- analytics/logs;
- evaluation report;
- repository-visible stable count;
- documented work record;
- candidate-provided measurement that can be explained.

For every metric ask:
- How was it measured?
- In what environment?
- On what sample or time period?
- Can the candidate reproduce or defend it?

If those answers are unavailable, remove the number.

## Impact Context

- **Production/operational** — only for real live operational measurements.
- **Research/evaluation** — state dataset/split/metric context.
- **Development benchmark** — explicitly say local/testing/development.
- **Descriptive** — implementation detail with no fabricated outcome.

## Writing Rules

- Start with a specific action.
- Name the system/technology when relevant.
- Keep ownership accurate.
- Prefer one core idea per bullet.
- Avoid vague filler.
- Avoid inflated verbs when a plain verb is more accurate.
- Do not repeat keywords for density.
- Keep bullets short enough to scan normally.

## Before / After

Weak:
"Worked on authentication."

Better:
"Implemented JWT authentication and role-based authorization middleware for candidate and recruiter routes."

Weak:
"Improved database performance by 70%."

Better when no benchmark exists:
"Added MongoDB indexes and revised application-search queries to reduce unnecessary scans."

Better when benchmark exists:
"Reduced median application-search latency from X to Y in a documented benchmark by adding compound indexes and revising query stages."

## Output

For each bullet provide:
- final wording;
- evidence source;
- ownership status;
- metric provenance (if any);
- likely interview follow-up question.

## Guardrails

- No mandatory metric per bullet.
- No conservative guessing of percentages.
- No user/traffic/uptime/latency claims without evidence.
- No production language for development projects.
- No unsupported causal wording ("resulting in", "increased", "reduced") unless measured or otherwise established.
