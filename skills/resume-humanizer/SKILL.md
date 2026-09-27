---
name: Resume Humanizer
description: Rewrite resume bullets into natural engineering prose while preserving evidence, ownership, and technical meaning. Uses qualitative checks rather than AI-detection scores.
---

# Resume Humanizer

## Purpose

Make evidence-backed bullets concise, natural, and interview-defensible.

Do not optimize for AI-detector scores. AI-detection tools are not a reliable measure of whether a resume is good or authentic.

## Checks

### Natural Language
Prefer:
- direct verbs;
- normal sentence structure;
- specific nouns;
- concrete technologies;
- plain explanations of impact.

Avoid inflated wording such as:
- cutting-edge;
- revolutionary;
- seamless;
- world-class;
- results-driven;
- passionate (when used as resume filler);
- orchestrated / spearheaded when a simpler verb is more accurate.

### Specificity
A technical bullet should name the actual system, technology, algorithm, API, database, or artifact when relevant.

### Evidence Preservation
Do not add:
- new metrics;
- new technologies;
- new scale;
- new ownership;
- production claims;
- causal impact unsupported by evidence.

### Readability
Keep bullets compact. Split a bullet when multiple unrelated claims make it hard to read.

### Technical Density
Include architecture/technical decisions only when they help explain the work; do not force a "why X over Y" comparison into every bullet.

### Interview Defensibility
The candidate should be able to explain every noun, number, and technical decision.

## Output

For each rewritten bullet:
- original;
- revised;
- evidence preserved;
- any removed exaggeration or unsupported language.

Then run this checklist:
- Natural language: Pass / Needs revision
- Specificity: Pass / Needs revision
- Evidence preservation: Pass / Needs revision
- Readability: Pass / Needs revision
- Technical relevance: Pass / Needs revision
- Interview defensibility: Pass / Needs revision

## Guardrails

- No AI-writing score.
- No forced metric density.
- No keyword repetition target.
- Never trade truthfulness for stronger-sounding prose.
