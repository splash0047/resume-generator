---
name: Candidate Positioning
description: Determines the candidate's primary role identity before any JD analysis. Classifies into role families, selects core tech identity, ranks projects by role relevance, and outputs a Candidate Position Brief consumed by all downstream stages. This is Phase -1 of the pipeline.
---

# Candidate Positioning

## When to Use This Skill

Use this skill as **Phase -1** — the very first step — before JD analysis, before bullet generation, before anything. This skill answers the most important question:

> **"What kind of candidate are you?"**

Trigger phrases: "position me for", "what role should I target", "generate resume", "create resume variant", any resume generation request

**This skill runs once per candidate profile, then the output is reused across all JD-specific tailoring.**

---

## Core Principle

> **A recruiter must identify your role identity within 6 seconds.**
> A resume that says "I know 30 technologies" communicates nothing.
> A resume that says "I'm an AI/ML engineer who builds production ML systems with Python and FastAPI" communicates everything.
>
> Positioning happens BEFORE keyword optimization. You cannot optimize what you haven't positioned.

---

## Step 1: Profile Analysis

Analyze the candidate's full profile (INPUT 2) across these dimensions:

### Experience Signals
| Signal | Weight | What to Extract |
|---|---|---|
| Job titles | High | Direct role identity (e.g., "AI Intern" → AI/ML signal) |
| Technologies used at work | High | Production-level tech stack |
| Project domains | Medium | What problems they solve (ML, web apps, CLI tools, infra) |
| Certifications | Medium | Industry validation direction (Azure AI, AWS, etc.) |
| Education focus | Low | Coursework alignment |

### Project Technology Distribution
Count how many projects use each technology category:
- **AI/ML**: ML models, LLMs, RAG, agents, vector databases, anomaly detection
- **Backend**: REST APIs, FastAPI, Express, databases, authentication
- **Frontend**: React, Next.js, UI components, responsive design
- **DevOps/Cloud**: Docker, CI/CD, cloud deployment, infrastructure
- **Data Engineering**: Pipelines, ETL, data processing, streaming
- **CLI/Tooling**: Command-line tools, developer experience, automation

---

## Step 2: Role Family Classification

Based on the profile analysis, classify into ONE primary and ONE secondary role family.

### Available Role Families

| Role Family | Key Signals |
|---|---|
| **SDE / Software Engineer** | Strong DSA, multiple languages, backend/API work, system design, production software |
| **AI/ML Engineer** | ML models, LLMs, RAG, AI agents, data pipelines, Python-heavy, research papers |
| **Full Stack Developer** | React/frontend + Node/backend, MERN/MEAN, responsive UI, authentication, RBAC |
| **DevOps / Cloud Engineer** | Docker, Kubernetes, CI/CD, cloud certifications, infrastructure, monitoring |
| **Data Engineer** | ETL pipelines, Spark, Kafka, data warehouses, SQL-heavy, streaming |

### Classification Rules

1. **Primary role** = the role family with the most evidence (projects + experience + certifications combined)
2. **Secondary role** = the next strongest, used for variant generation
3. **If tied**: Prefer the role family that matches the candidate's most recent experience
4. **Never classify as 3+ role families** — that's the "I know everything" anti-pattern

### Classification Output

```markdown
## Role Family Classification

**Primary:** AI/ML Engineer
**Evidence:** 3/6 projects are ML/AI, AI internship, Azure AI + Oracle AI certifications, LangGraph/CrewAI/RAG experience
**Secondary:** Software Engineer (Backend)
**Evidence:** FastAPI, REST APIs, Docker, Node.js/Express, database design
```

---

## Step 3: Core Technical Identity

Select **8-12 core technologies** that define this candidate for the primary role family. These are the technologies that MUST appear prominently in the resume.

### Selection Rules

1. **Include**: Technologies the candidate has used in ≥2 projects or ≥1 work experience
2. **Include**: Technologies that appear in >50% of JDs for the primary role family
3. **Exclude**: Technologies used in only 1 tutorial-level project
4. **Exclude**: Technologies that dilute the role identity (e.g., CrewAI for SDE roles)
5. **Maximum 12** — fewer is stronger

### Core Identity by Role Family (Examples)

**For SDE:**
```
Core: Python, C++, JavaScript, TypeScript, SQL, FastAPI, Node.js, Express, React, Docker, Git
Remove/Minimize: CrewAI, LangGraph, RAG, Neo4j, Azure OpenAI, FAISS, LangChain
```

**For AI/ML Engineer:**
```
Core: Python, ML, Scikit-learn, LLMs, RAG, LangGraph, FastAPI, FAISS, Elasticsearch, Docker, Git
Remove/Minimize: Next.js, Tailwind CSS, Bootstrap, Prisma ORM, GraphQL
```

**For Full Stack:**
```
Core: React, Next.js, Node.js, Express, TypeScript, MongoDB, MySQL, REST APIs, Docker, Git, Tailwind CSS
Remove/Minimize: CrewAI, LangGraph, FAISS, Elasticsearch, Neo4j, Isolation Forest
```

---

## Step 4: Project Priority Ranking

Rank ALL candidate projects by relevance to the primary role family. Output a priority list with selection recommendations.

### Ranking Criteria

| Factor | Weight |
|---|---|
| Technology overlap with core identity | 40% |
| Problem domain relevance | 25% |
| Architecture complexity | 20% |
| Deployment/demo evidence | 15% |

### Output Format

```markdown
## Project Priority for [Role Family]

### Include on Resume (Top 2-3)
1. **[Project Name]** — [Why it fits: covers X core technologies, demonstrates Y]
2. **[Project Name]** — [Why it fits]
3. **[Project Name]** — [Why it fits, if space permits]

### Keep in Portfolio Only
4. **[Project Name]** — [Good project but doesn't fit this role variant]
5. **[Project Name]** — [Domain mismatch for this role]

### Recommendation
Lead with [Project 1] — it covers [N] critical technologies and demonstrates [problem-solving type].
```

---

## Step 5: Skill Section Strategy

Determine the Technical Skills section layout for the resume.

### Rules

1. **Maximum 5 categories** in Technical Skills
2. **Maximum 15 total items** across all categories for fresher resumes
3. **Order categories** by JD relevance (most relevant first)
4. **Order items within categories** by proficiency and relevance
5. **Remove technologies** that:
   - Are not in the core identity AND not in the JD
   - Were used in only one tutorial-level project
   - Dilute the primary role signal

### Category Templates by Role

**SDE:**
```
Languages: Python, C++, JavaScript, TypeScript, SQL
Backend: FastAPI, Node.js, Express.js, REST APIs
Frontend: React.js, HTML5, CSS3
Tools: Docker, Git, GitHub, CI/CD
Databases: MongoDB, MySQL, PostgreSQL
```

**AI/ML:**
```
Languages: Python, SQL, JavaScript
AI/ML: Scikit-learn, LLMs, RAG, LangGraph, CrewAI, FAISS
Backend: FastAPI, REST APIs, Elasticsearch
Cloud: Azure AI, AWS, Docker, CI/CD
Databases: MongoDB, PostgreSQL, Neo4j
```

---

## Step 6: Certification Selection

Select 2-3 certifications most relevant to the primary role family.

### Rules
1. **Maximum 3 certifications** on a fresher resume
2. **Relevance > quantity** — 2 relevant certs beat 5 irrelevant ones
3. **Order by**: Role relevance → Issuer prestige → Recency
4. Certifications not selected still exist on LinkedIn — they're not deleted, just not on THIS resume

---

## Full Output: Candidate Position Brief

This brief is consumed by ALL downstream stages (JD Analyzer, Bullet Generator, Humanizer, Critic).

```markdown
## Candidate Position Brief

**Candidate:** [Name]
**Primary Role:** [Role Family]
**Secondary Role:** [Role Family]
**Generated:** [Date]

### Core Technical Identity (8-12 technologies)
[Ordered list]

### Project Priority
1. [Project] — Include
2. [Project] — Include
3. [Project] — Include if space
4. [Project] — Portfolio only
...

### Skill Section Layout
[Category: items] format

### Certifications to Include
1. [Cert]
2. [Cert]

### Technologies to Remove/Minimize
[List with reasons]

### Candidate Positioning Statement
(1-2 sentence identity used internally, NOT placed on resume)
"[Name] is an AI/ML-focused backend engineer with internship experience building
ML systems and multiple deployed AI projects. Strongest in Python, FastAPI,
and ML pipeline development."
```

---

## Rules

1. **This skill runs BEFORE the JD Intelligence Analyzer.** The JD Analyzer then uses this brief to refine (not override) the positioning.
2. **One primary role per resume.** If the JD clearly fits the secondary role, switch — but never try to be both simultaneously.
3. **The brief is a filter, not a fabrication.** It selects and orders true experience. It never adds skills or projects the candidate doesn't have.
4. **Update the brief when the candidate profile changes** (new project, new certification, new experience). Don't regenerate for every JD.
5. **For experienced candidates (3+ years)**: This skill is less critical because work experience naturally positions. For freshers, it's THE most important step.
