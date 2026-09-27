---
name: Engineering Evidence Database
description: Structured evidence schema for capturing project and experience context before generating resume bullets. Separates implementation, execution, ownership, and impact evidence.
---

# Engineering Evidence Database

## Purpose

Build the factual source of truth used by resume generation and interview preparation.

The evidence database must preserve what is known, what is measured, and what is still unverified. Do not collapse evidence into a single numeric confidence score.

## Evidence Record

For each project or experience capture:

### Identity
- name
- dates
- role
- repository/demo/document links
- candidate ownership/contribution

### Problem
- user/system problem
- constraints
- why the work mattered

### Implementation
- languages/frameworks
- architecture
- algorithms
- databases
- APIs
- security/reliability features
- deployment/containerization

### Execution Evidence
Classify each material feature:
- **Source-verified**
- **Test/CI-verified**
- **Demo-visible**
- **README-only**
- **Candidate-confirmed**
- **Unverified**

### Ownership Evidence
- documented contribution;
- candidate-confirmed personal contribution;
- team contribution with scope;
- unknown.

Do not assume repository ownership means the candidate personally implemented every component.

### Impact Evidence
Classify:
- **Production/operational measurement**
- **Research/evaluation result**
- **Development benchmark**
- **Repository-visible scale/count**
- **Descriptive only**
- **Unverified**

For every number store:
- value;
- metric definition;
- source;
- environment;
- sample/evaluation scope;
- date/version;
- whether reproducible.

### Decisions and Trade-offs
Capture only decisions the candidate can explain:
- alternatives considered;
- chosen approach;
- reason;
- consequences.

### Failures and Debugging
Record:
- issue;
- diagnosis;
- fix;
- validation.

### Interview Defense
For each resume-worthy claim, prepare:
- What did you personally implement?
- How does it work?
- Why this approach?
- How did you test it?
- What limitation remains?

## Resume Claim Matrix

| Proposed claim | Implementation | Execution | Ownership | Impact | Source | Use? |
|---|---|---|---|---|---|---|
| Containerized backend with Docker | Direct | Build/test evidence if present | Confirmed | Descriptive | Dockerfile | Yes |
| Reduced latency 40% | Direct | Benchmark required | Confirmed | Unverified | none | No until measured |

## Rules

1. An import proves the dependency is referenced; it does not prove successful end-to-end use.
2. A README claim is documentation evidence, not execution evidence.
3. A deployment link proves public accessibility only if it works; it does not prove production readiness.
4. Metrics without provenance must not appear in final resume bullets.
5. Development/research measurements must keep their environment/evaluation qualifier.
6. If ownership is unclear, confirm it before using first-person resume wording.
7. Repository changes can invalidate old resume descriptions; re-audit when architecture changes.

## Output

Produce:
- verified technology list;
- claim matrix;
- metric provenance table;
- unresolved evidence questions;
- interview-defense questions;
- bullets safe to generate;
- claims that must be removed or confirmed.
