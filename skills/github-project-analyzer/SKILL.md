---
name: GitHub Project Analyzer
description: Extract verifiable engineering evidence from a GitHub repository and grade its quality. Use this when a candidate provides a GitHub URL to generate evidence-backed resume bullets with confidence scores and source citations.
---

# GitHub Project Analyzer

## When to Use This Skill

Use this skill when the user provides one or more GitHub repository URLs. This runs as part of **Phase 1 (Evidence Extraction)** — before bullet generation, after JD Intelligence.

Trigger phrases: "here's my GitHub", "analyze my repo", "github.com/...", "extract bullets from my project", "read my repository"

## Core Capabilities

- Extract a verified tech stack from package files, imports, and configuration
- Understand architecture from directory structure, README, and entry points
- Generate evidence-backed resume bullets with file-level source citations
- Grade repository quality on 6 dimensions (0–10 each)
- Assign a confidence score to every extracted claim (100% / 65% / 25%)
- Flag repository weaknesses with actionable improvement recommendations

---

## Phase A: Evidence Extraction

When given a repository URL (or directory listing), analyze the following files in order:

### 1. Package / Dependency Files (Tech Stack)
| File | What to Extract |
|---|---|
| `requirements.txt` / `pyproject.toml` / `setup.py` | Python libraries, frameworks, ML/AI tools |
| `package.json` | Node.js frameworks, frontend libraries, tooling |
| `Dockerfile` / `docker-compose.yml` | Container strategy, services, ports, base images |
| `go.mod` / `Cargo.toml` / `pom.xml` | Go / Rust / Java dependencies |
| `.github/workflows/*.yml` | CI/CD tools, test runners, deployment targets |

### 2. Entry Points (Architecture)
| File Pattern | What to Extract |
|---|---|
| `main.py` / `app.py` / `server.py` / `index.js` | Framework used, routing structure, startup config |
| `src/` / `app/` / `api/` directory layout | Architectural pattern (MVC, microservice, layered, event-driven) |
| `models/` / `schemas/` / `db/` | Database layer, ORM usage, data modeling approach |
| `tests/` / `test_*.py` / `*.test.js` | Testing framework, coverage breadth |

### 3. README.md (Purpose + Architecture)
Extract:
- Project purpose (1–2 sentences)
- Architecture description or diagram references
- Setup / installation instructions (indicates deployment complexity)
- Usage examples (indicates API surface)
- Any stated metrics or benchmarks

### 4. Key Source Files (Algorithms + Patterns)
Scan imports and class/function names in core source files to identify:
- Specific algorithms (IsolationForest, LSTM, BFS, Dijkstra)
- Design patterns (Observer, Factory, Repository)
- Async patterns (asyncio, Celery, Kafka consumers)
- Security patterns (JWT, OAuth, bcrypt)

---

## Phase B: Confidence Score Assignment

Every claim extracted from the repository receives a confidence score before being used in a bullet.

| Confidence | Source Quality | Example |
|---|---|---|
| **100%** | Directly cited — specific file + import/class/function found | `from sklearn.ensemble import IsolationForest` in `detector.py` |
| **80%** | File exists with clear purpose, specific content verified | `Dockerfile` present with multi-stage build |
| **65%** | README description only — not verified in source code | README says "uses Redis for caching" but no source file checked |
| **25%** | Inferred from directory name or partial evidence | `/ml/` folder exists but no specific algorithm identified |
| **0%** | Cannot be sourced to any file or document | Do not generate this bullet |

**Rule:** Bullets with ≤40% confidence are **flagged for user review**, not automatically included. The user decides whether to include them with an explicit qualifier (e.g., "Explored..." or "Implemented basic...").

---

## Phase C: Repository Quality Scorecard

Grade the repository on 6 dimensions. Output a score (0–10) and a 1-line finding for each.

### Scoring Rubric

**Architecture (0–10)**
- 0–3: Flat structure, all files in root, no separation of concerns
- 4–6: Basic separation (api/, models/, utils/)
- 7–9: Clear layered architecture, domain-driven or service-based structure
- 10: Explicit architecture documentation + enforced patterns

**Documentation (0–10)**
- 0–3: No README or README is a template placeholder
- 4–6: README exists with basic setup instructions
- 7–9: README covers purpose, architecture, setup, usage, and examples
- 10: README + inline docstrings + API documentation (Swagger/OpenAPI)

**Testing (0–10)**
- 0–3: No test files found
- 4–6: Some test files exist (< 30% of source files covered)
- 7–9: Tests present for core functionality, test runner configured
- 10: High coverage, CI enforces tests on PRs, integration tests present

**CI/CD (0–10)**
- 0–3: No `.github/workflows/` or equivalent
- 4–6: Basic CI (lint or test on push)
- 7–9: CI + CD pipeline (automated deployment on merge)
- 10: Full pipeline: lint → test → build → deploy with environment separation

**Code Quality (0–10)**
- 0–3: Inconsistent style, commented-out code, no linter config
- 4–6: Mostly consistent, `.flake8` / `.eslintrc` present
- 7–9: Consistent style, type hints / TypeScript, clear naming
- 10: Type safety enforced, pre-commit hooks, code review evidence

**README Quality (0–10)**
- 0–3: Missing or default template
- 4–6: Basic description and setup
- 7–9: Purpose, architecture, demo/screenshot, setup, usage
- 10: All of the above + badges, contribution guide, live demo link

### Quality Score Output

```markdown
## Repository Quality Report: [Project Name]

### Overall Score: 7.2 / 10

| Dimension | Score | Finding |
|---|---|---|
| Architecture | 9/10 | Clear api/ → services/ → models/ layered structure |
| Documentation | 8/10 | README covers purpose, architecture, and setup |
| Testing | 3/10 | ⚠️ Only 2 test files found for 18 source files |
| CI/CD | 4/10 | ⚠️ Basic GitHub Actions lint check only, no deployment |
| Code Quality | 8/10 | Type hints present, consistent naming, flake8 configured |
| README | 9/10 | Architecture diagram, setup steps, and usage examples |

### Recommendations Before Applying
- Add pytest tests for at least core API endpoints (Testing: 3 → 7+)
- Add a deployment workflow to GitHub Actions (CI/CD: 4 → 7+)
- These improvements take 2–4 hours and significantly strengthen your application
```

---

## Phase D: Evidence-Backed Bullet Generation

Generate resume bullets only from verified evidence. Every bullet must include:
1. The bullet text (using PACTI formula where possible)
2. The confidence score
3. The source file citation

### Output Format

```markdown
## Evidence-Backed Bullets: [Project Name]

### Verified Tech Stack
- Python 3.11, FastAPI, SQLAlchemy (from requirements.txt)
- PostgreSQL via asyncpg (from requirements.txt + db/connection.py)
- Docker + docker-compose (from Dockerfile, docker-compose.yml)
- Isolation Forest for anomaly detection (from src/anomaly/detector.py, line 12)
- FAISS for vector search (from src/retrieval/store.py, line 8)

### Generated Bullets

| Bullet | Confidence | Source |
|---|---|---|
| Designed a log anomaly detection pipeline using Isolation Forest on unlabeled infrastructure logs — chose unsupervised method because labeled ground truth was unavailable; reduced false positive rate by ~27% during benchmarking | 95% | src/anomaly/detector.py |
| Built async REST API with FastAPI and SQLAlchemy handling log ingestion from 3 microservices, with structured error handling and request validation | 100% | src/api/main.py, requirements.txt |
| Containerized the application using Docker with a multi-stage build, separating dev and production environments | 80% | Dockerfile |
| Implemented semantic log retrieval using FAISS vector store to provide relevant historical context to the LLM RCA agent | 95% | src/retrieval/store.py |

### Flagged for Review (Confidence ≤ 40%)
| Claim | Confidence | Issue |
|---|---|---|
| "Reduced incident investigation time from 20 to 3 minutes" | 25% | README mentions this metric but no benchmark script found |
> ⚠️ Include this bullet only if you can verify the metric and defend it in an interview.
```

---

## Rules

1. **Every bullet must cite its source.** If a claim cannot be traced to a file, import, README section, or configuration entry, it must be flagged — not included.

2. **Confidence is assigned per claim, not per project.** A single project can have bullets at 100% and 25% simultaneously.

3. **Never fabricate deployment metrics.** If the project was never in production, classify its impact as `development` or `research` and qualify any metrics with "during local benchmarking" or "on test dataset."

4. **Repository quality scores are actionable.** If Testing or CI/CD scores below 5, always recommend improvements before the application — these are visible signals to hiring managers who review GitHub.

5. **Bullet wording must match evidence strength.** A `Dockerfile` present = "Containerized using Docker." It does NOT equal "Designed a scalable containerized deployment pipeline." See Truthfulness Gate in `resume-critic`.
