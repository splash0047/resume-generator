---
name: Engineering Evidence Database
description: Structured evidence schema for capturing rich project context before generating resume bullets. Use this to build the evidence foundation that all bullet generation, confidence scoring, and interview defensibility checks depend on. Technology-agnostic — works for any engineering domain.
---

# Engineering Evidence Database (Evidence Engine)

## When to Use This Skill

Use this skill to build the **evidence foundation** for a project before any bullets are written. This is Phase 1 of the pipeline — it runs after GitHub analysis and before bullet generation.

Trigger phrases: "document my project", "fill out evidence for", "build evidence for", "capture my project details", "evidence database"

Also use this skill when the candidate has evidence that is NOT on GitHub:
- Internship project documentation
- Architecture diagrams (Figma, draw.io, Miro)
- PRDs or design specs (Notion, Confluence, Google Docs)
- Screenshots or demo recordings
- API specifications (Swagger, Postman collections)
- Issue trackers (JIRA, GitHub Issues, Linear)
- Manager feedback documents

---

## The Core Rule

> **`resume_bullets` is always the last field filled.**
> No bullet is written until the evidence above it is documented.
> Every resume bullet must be traceable to at least one field in this schema.

---

## Evidence Schema (15 Fields)

Fields marked **REQUIRED** must be filled. All others are optional — fill them only if the project has meaningful data for that dimension.

```json
{
  "project_name": "AI Root Cause Analyzer",

  // ============================================================
  // REQUIRED (minimum viable evidence — fill these for every project)
  // ============================================================

  "problem": "Infrastructure alerts required 20+ minutes of manual log analysis per incident. Engineers had no structured way to identify which service was the root cause when multiple alerts fired simultaneously.",

  "metrics": "Reduced mean investigation time from ~20 minutes to under 3 minutes across 15 simulated incidents during development testing.",

  "impact_type": "development",
  // Options: "production" | "research" | "development" | "learning"
  // production  → exact numbers from live systems are acceptable
  // research    → benchmark numbers on datasets are acceptable
  // development → qualify all numbers with "during development/testing/benchmarking"
  // learning    → no hard metrics; describe what was learned and how it was applied

  // ============================================================
  // STRONGLY RECOMMENDED (fill if the project has this information)
  // ============================================================

  "architecture": "FastAPI REST endpoint receives raw log batches → preprocessing layer normalizes log format → Isolation Forest scores each log for anomaly probability → flagged logs are passed to a LangGraph multi-agent pipeline (Analyzer → Reviewer → Summarizer) → final RCA report written to PostgreSQL → served back via FastAPI response",

  "key_decisions": "Chose FastAPI over Flask for native async support and automatic OpenAPI generation. Chose PostgreSQL over SQLite to practice production-grade database patterns. Chose LangGraph over a single-prompt LLM call because multi-agent pipelines allow independent review and revision of the analysis.",
  // Technology-agnostic: use this for algorithm choices, architecture decisions,
  // framework selections, database choices, protocol choices, etc.

  "tradeoffs": "Isolation Forest was chosen over DBSCAN because the log data was entirely unlabeled — DBSCAN requires density assumptions that don't hold well in sparse log distributions. Trade-off: Isolation Forest is less interpretable per-anomaly but more robust to varying log volumes.",
  // Why X over Y — the single most important field for interview defensibility

  "constraints": "No labeled dataset available for supervised anomaly detection. Time constraint of 3 weeks. No cloud infrastructure budget — all components must run locally or on a free tier.",
  // Budget, time, team size, infra limits, compliance requirements, data availability

  "validation_method": "Manual spot-checking of 15 representative incident scenarios. Compared output RCA against engineer-written post-mortems. No automated test suite — this is a known gap.",
  // How correctness was verified: unit tests, integration tests, benchmarks,
  // A/B tests, human evaluation, paper comparison, etc.

  "challenges": "False positive rate of ~40% with default Isolation Forest contamination parameter (0.1). Solved by running a grid search over contamination values (0.05–0.2) on the synthetic test set and selecting the value that minimized false positives while keeping recall above 80%. Also encountered token limit issues with LangGraph when passing full log dumps to the LLM — solved by pre-filtering to top 20 anomalous logs before passing to the agent.",
  // Hard bugs, scaling bottlenecks, algorithmic challenges, edge cases, failures

  "data_flow": "Raw syslog lines (plaintext) → regex normalization → sentence-transformer embeddings (FAISS index) → Isolation Forest scoring → top-N anomalies → LangGraph context window → structured RCA output",

  // ============================================================
  // OPTIONAL (fill only if the project has meaningful data here)
  // ============================================================

  "database": "",
  // Storage choices and reasoning. Leave empty if not applicable.

  "repo_structure": "",
  // Key directories and what they contain. Leave empty if standard structure.

  "deployment": "",
  // How the project is deployed: Docker, cloud provider, CI/CD, serverless.
  // Leave empty if local-only project without deployment.

  "scalability": "",
  // Known performance characteristics, horizontal/vertical scaling notes.
  // Leave empty if scalability was not a design consideration.

  "known_limitations": "No production deployment. Log format is specific to the synthetic dataset used — would require a normalization layer to generalize to real infrastructure logs. LLM API costs would be non-trivial at scale.",

  "future_improvements": "Add a feedback loop where engineers can mark RCA reports as accurate/inaccurate to fine-tune the anomaly threshold. Add support for structured log formats (JSON logs from ECS/Kubernetes).",

  // ============================================================
  // EVIDENCE SOURCES (all sources that support the bullets above)
  // ============================================================

  "evidence_sources": {
    "github_link": "https://github.com/username/ai-rca-analyzer",
    "design_doc": "",        // Figma, Confluence, Notion, Google Docs link
    "architecture_diagram": "", // draw.io, Miro, Lucidchart link or file path
    "prd_link": "",          // Product requirement document
    "screenshot": "",        // Demo screenshot path or URL
    "api_spec": "",          // Swagger/OpenAPI URL or Postman collection
    "issue_tracker": "",     // JIRA board, GitHub Issues, Linear project URL
    "internship_doc": ""     // Manager brief, project summary, feedback doc
  },

  // ============================================================
  // AUTO-GENERATED (Claude fills these last, after all fields above are complete)
  // ============================================================

  "interview_questions": [
    {
      "q": "Why did you choose Isolation Forest over DBSCAN?",
      "a": "The log data was entirely unlabeled. DBSCAN requires density-based assumptions that don't generalize well to varying log volumes, whereas Isolation Forest works well on high-dimensional unlabeled data and is more robust to sparse distributions."
    },
    {
      "q": "How did you tune the contamination parameter?",
      "a": "I ran a grid search from 0.05 to 0.2 on a held-out synthetic test set of 15 incidents and selected the value that kept recall above 80% while minimizing false positives."
    },
    {
      "q": "Why LangGraph instead of a single LLM call?",
      "a": "A single prompt produces one unreviewed output. LangGraph lets me separate the analysis and review stages — the Reviewer agent can catch hallucinations or gaps in the Analyzer's reasoning before the final report is written."
    },
    {
      "q": "How did you handle the token limit problem?",
      "a": "Pre-filtered to the top 20 most anomalous logs (by Isolation Forest score) before passing to the LLM context window. This kept the prompt under 4K tokens for GPT-4-turbo while preserving the most relevant signal."
    }
  ],

  "resume_bullets": []
  // Filled last by the Bullet Generator using PACTI formula.
  // Every bullet here must be traceable to at least one field above.
}
```

---

## Impact Classification Rules

The `impact_type` field controls how metrics are phrased in bullets.

| Type | When to Use | Metric Phrasing Rule |
|---|---|---|
| `production` | System is live, serving real users | Exact numbers allowed: "Reduced P95 latency by 40% in production" |
| `research` | Academic project, paper, or benchmark on a dataset | Benchmark numbers: "Achieved 89% F1 on the test split of [Dataset]" |
| `development` | Personal/internship project, not in production | Must qualify: "Reduced local inference time by ~60% during development testing" |
| `learning` | Course project, tutorial follow-along | No hard metrics; describe application: "Applied transformer-based tokenization concepts to build a custom tokenizer for Hinglish text" |

**Key rule:** If a project is `development` or `learning`, never write a bullet that implies production usage. Metrics must be qualified.

---

## Evidence Engine: Non-GitHub Sources

This skill is not limited to GitHub repositories. Any of these sources can populate the schema:

### Internship Projects
Use `internship_doc` to capture:
- Manager-provided project brief
- PRD or scope document
- Any performance review language about the project

### Architecture Diagrams
Use `architecture_diagram` to attach a link to any Figma, draw.io, Miro, or Lucidchart diagram. Claude can reference the diagram description in bullets even without reading the image.

### API Specifications
Use `api_spec` to link to a Swagger/OpenAPI definition or Postman collection. This provides verifiable evidence of endpoints, request/response shapes, and API design decisions.

### Issue Trackers
Use `issue_tracker` to link to a GitHub Issues list or JIRA board. Closed issues are excellent evidence of bugs fixed, features shipped, and technical decisions made.

---

## Traceability Rule

Before the Resume Critic runs, verify: **every bullet in `resume_bullets` must cite at least one field from this schema as its source.**

| Bullet | Evidence Field | Confidence |
|---|---|---|
| "Designed anomaly detection using Isolation Forest..." | `key_decisions` + `tradeoffs` | 95% (github_link) |
| "Reduced investigation time from 20 to 3 minutes" | `metrics` + `impact_type: development` | 60% (needs qualification: "during testing") |
| "Built FastAPI async REST API" | `architecture` | 100% (github_link → main.py) |

---

## Template: Blank Schema for New Projects

```json
{
  "project_name": "",
  "problem": "",
  "metrics": "",
  "impact_type": "development",
  "key_decisions": "",
  "tradeoffs": "",
  "constraints": "",
  "validation_method": "",
  "challenges": "",
  "data_flow": "",
  "database": "",
  "repo_structure": "",
  "deployment": "",
  "scalability": "",
  "known_limitations": "",
  "future_improvements": "",
  "evidence_sources": {
    "github_link": "",
    "design_doc": "",
    "architecture_diagram": "",
    "prd_link": "",
    "screenshot": "",
    "api_spec": "",
    "issue_tracker": "",
    "internship_doc": ""
  },
  "interview_questions": [],
  "resume_bullets": []
}
```
