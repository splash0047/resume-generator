---
name: Resume Quantifier
description: Add defensible measurements to resume bullets when real evidence exists; otherwise strengthen bullets with concrete implementation detail.
---

# Resume Quantifier

## When to Use This Skill

Use when a candidate wants stronger impact statements, has real measurements to surface, or needs help deciding whether a number is defensible.

## Core Rule

**Do not invent, reverse-engineer, or casually estimate a metric for a resume.**

A precise implementation detail is better than an unsupported percentage.

Evidence hierarchy:
1. measured production or operational result;
2. reproducible benchmark or held-out evaluation;
3. measured development/test result with an explicit qualifier;
4. concrete implementation scale that can be counted from the project;
5. descriptive engineering detail with no number.

## Acceptable Sources of Numbers

Use a metric only when one of these is available:
- benchmark output or experiment report;
- analytics/logs/dashboard;
- test results;
- dataset size or evaluation sample count;
- repository-visible counts that are meaningful and stable;
- documented business/project record;
- user-provided measurement the candidate can explain.

If the user gives an approximate but genuinely observed value, mark it as approximate and preserve its context.

## Metric Classification

| Type | Example wording |
|---|---|
| Production/operational | "Reduced P95 latency from 420 ms to 260 ms in production monitoring" |
| Research/evaluation | "Achieved 0.84 macro F1 on the held-out test split" |
| Development benchmark | "Reduced local inference time from ~800 ms to ~300 ms in a 100-request benchmark" |
| Repository-visible scale | "Implemented 6 protected API routes with role-based middleware" |
| No defensible metric | "Implemented RBAC with JWT and Express middleware" |

Do not relabel a development benchmark as a production result.

## Discovery Questions

When evidence is missing, help the user locate it rather than manufacturing it:
- Do you have a benchmark notebook, CI output, analytics screenshot, or test report?
- Can the repository count routes, tests, supported modules, or datasets?
- Was the result measured before/after the change?
- What environment and sample size produced the number?
- Can you reproduce the measurement today?

If the answer is no, omit the metric.

## Safe Transformations

Weak:
"Optimized MongoDB performance."

Better without a metric:
"Added compound indexes and rewrote aggregation queries for the application-search path."

Better with a verified benchmark:
"Reduced median application-search latency from 310 ms to 140 ms in a 1,000-query local benchmark by adding compound indexes and revising aggregation stages."

## Guardrails

- No invented percentages.
- No guessed user counts, uptime, request volume, time savings, cost savings, or conversion.
- No multiplying a guessed daily rate into an annual total.
- No claim such as "production-ready" based solely on deployment.
- No model accuracy without dataset, split, metric, and reproducible evaluation context.
- Prefer "built", "implemented", "tested", "deployed", and specific technical detail when measured impact is unavailable.

## Output

For each candidate bullet return:
- proposed wording;
- metric source;
- environment/context;
- whether it is reproducible;
- interview defense note ("How was this measured?").

If no defensible metric exists, explicitly return a strong non-quantified version instead.
