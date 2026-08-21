---
name: Fresher Signal Analyzer
description: Evaluates fresher-specific hiring signals that generic resume tools ignore. Scores 9 dimensions critical for new-grad hiring (CGPA, DSA, project depth, GitHub quality, deployment evidence, etc.) and identifies the weakest signal with improvement recommendations.
---

# Fresher Signal Analyzer

## When to Use This Skill

Use this skill when the candidate has **≤2 years of professional experience** (internships count as 0.5 years each). Run it as part of **Phase 1** alongside evidence extraction.

Trigger phrases: "analyze my profile", "am I ready to apply", "what should I improve", "fresher resume check", "new grad profile review"

---

## Core Principle

> **Fresher hiring is signal-scarce. Every signal matters more.**
>
> When a candidate has 5+ years of experience, the resume writes itself from work history.
> When a candidate has 0-2 years, recruiters look for different signals:
> CGPA, DSA ability, project depth, GitHub quality, certifications, hackathons.
>
> Your resume pipeline must know which signals are strong, which are weak,
> and which are missing — before optimizing the resume.

---

## The 9 Fresher Signals

Score each dimension 1-10. Identify the weakest signal and recommend improvement.

### Signal 1: Academic Performance (CGPA/GPA)

| Score | Criteria |
|---|---|
| 9-10 | CGPA ≥ 9.0 / GPA ≥ 3.8 at a recognized institution |
| 7-8 | CGPA 8.0-8.9 / GPA 3.5-3.7 |
| 5-6 | CGPA 7.0-7.9 / GPA 3.0-3.4 |
| 3-4 | CGPA 6.0-6.9 / GPA 2.5-2.9 |
| 1-2 | CGPA < 6.0 or not reported |

**Resume impact**: Display CGPA prominently if ≥ 8.0. Hide if < 7.0. For 7.0-7.9, include only if the JD doesn't specify a minimum.

### Signal 2: Internship Quality

| Score | Criteria |
|---|---|
| 9-10 | 2+ internships at recognized companies, each 3+ months, with measurable technical output |
| 7-8 | 1-2 internships with clear technical contributions and specific technologies |
| 5-6 | 1 internship with basic technical exposure |
| 3-4 | 1 short internship (< 2 months) or non-technical internship |
| 1-2 | No internships |

**What to evaluate in each internship**:
- Duration (longer = more credible)
- Company recognition (known companies = stronger signal)
- Technical depth (specific technologies and implementations vs. "helped the team")
- Concrete deliverables (what did you actually build/ship?)

### Signal 3: DSA / Problem-Solving Evidence

| Score | Criteria |
|---|---|
| 9-10 | 500+ problems solved, active contest participation, strong rating (e.g., LeetCode top 10%) |
| 7-8 | 200-500 problems, occasional contests, DSA visible in projects |
| 5-6 | 100-200 problems, DSA in coursework, basic competitive programming |
| 3-4 | < 100 problems, DSA only in academic projects |
| 1-2 | No visible DSA evidence |

> [!WARNING]
> For Indian SDE fresher hiring, DSA is often the #1 technical screening criterion. A beautiful resume cannot compensate for DSA weakness when the recruiter's first filter is "can this person solve a medium-level coding problem?"

**Resume impact**: If DSA evidence exists, include it. If it doesn't, this is a profile improvement priority, not a resume improvement priority.

### Signal 4: Project Depth (not count)

| Score | Criteria |
|---|---|
| 9-10 | 2+ projects with clear architecture, multiple components, technical decisions documented, tests, deployed |
| 7-8 | 2-3 projects with genuine engineering (not tutorials), clear problem-solution structure |
| 5-6 | 3-4 projects but mostly CRUD/tutorial-level with minor customization |
| 3-4 | Projects exist but appear to be tutorial follow-alongs |
| 1-2 | No projects or only college assignments |

**What makes a project "deep" (not just present)**:
- Solves a real problem (even if the problem is small)
- Multiple components/services (not a single-file script)
- At least one non-trivial technical decision (algorithm choice, architecture choice, database choice)
- Can be whiteboarded in an interview
- Has a working demo or deployment

### Signal 5: GitHub Quality

Score EACH of the candidate's top 3 repositories, then average.

| Dimension | 1-3 (Weak) | 4-6 (Adequate) | 7-10 (Strong) |
|---|---|---|---|
| README | Missing/template | Basic setup instructions | Purpose, architecture, screenshots, setup, usage |
| Commit history | 1-3 bulk commits | Regular commits, no message quality | Descriptive commits, development progression visible |
| Code structure | Flat, all in root | Basic folders | Clear architecture, separation of concerns |
| Tests | None | Some test files | Test coverage for core functionality |
| Documentation | None | Inline comments | Docstrings + API docs |

**Resume impact**: If GitHub quality is ≤ 4, recommend the candidate improve their top 2 repos BEFORE applying. A recruiter who clicks a GitHub link and sees a bare repo with one commit loses confidence in the entire resume.

### Signal 6: Certification Relevance

| Score | Criteria |
|---|---|
| 9-10 | Industry-recognized certifications directly matching target role (e.g., Azure AI for AI roles, AWS SAA for cloud roles) |
| 7-8 | Relevant certifications from recognized issuers (Microsoft, AWS, Google, Oracle) |
| 5-6 | Certifications exist but are tangentially related to target role |
| 3-4 | Only MOOC completion certificates (Coursera, Udemy) |
| 1-2 | No certifications |

**Rule**: Certifications are supporting evidence, never the center of a fresher profile. 2 relevant > 5 irrelevant.

### Signal 7: Hackathon / Competition Evidence

| Score | Criteria |
|---|---|
| 9-10 | Won/finalist in recognized hackathon (SIH, HackMIT, etc.) or strong competitive programming rating |
| 7-8 | Selected for internal rounds of major hackathon, or regular contest participation |
| 5-6 | Participated in college-level hackathons |
| 3-4 | Participated but no notable outcome |
| 1-2 | No hackathon or competition experience |

### Signal 8: Deployment Evidence

| Score | Criteria |
|---|---|
| 9-10 | Multiple projects deployed and live with working demo links |
| 7-8 | At least 2 projects deployed (Netlify, Vercel, Streamlit Cloud, etc.) |
| 5-6 | 1 project deployed, others local only |
| 3-4 | Docker/containerization but no live deployment |
| 1-2 | All projects are local/README only |

**Resume impact**: Working demo links are extremely high-signal. A recruiter clicking a demo link and seeing a working application is worth more than 5 resume bullets.

### Signal 9: Technical Depth vs. Breadth Ratio

This is a meta-signal that evaluates whether the candidate has depth in a few areas or surface knowledge across many.

| Score | Criteria |
|---|---|
| 9-10 | Deep expertise in 2-3 technology areas, each supported by multiple projects + work experience |
| 7-8 | Clear primary technology area with supporting breadth |
| 5-6 | Moderate depth across 3-4 areas |
| 3-4 | Surface-level exposure to 5+ areas, no clear depth |
| 1-2 | Technology list looks like a keyword dump with no evidence of depth |

**How to measure depth in a technology**:
- Used in 2+ projects: +2
- Used in work experience: +2
- Has certification: +1
- Can explain architecture decisions: +2
- Has done something non-trivial with it: +3

---

## Signal Analysis Report

```markdown
## Fresher Signal Analysis Report

**Candidate:** [Name]
**Experience Level:** [0-2 years + internship count]
**Date:** [Date]

### Signal Scores

| # | Signal | Score | Assessment |
|---|---|---|---|
| 1 | Academic Performance | X/10 | [Brief assessment] |
| 2 | Internship Quality | X/10 | [Brief assessment] |
| 3 | DSA Evidence | X/10 | [Brief assessment] |
| 4 | Project Depth | X/10 | [Brief assessment] |
| 5 | GitHub Quality | X/10 | [Brief assessment] |
| 6 | Certification Relevance | X/10 | [Brief assessment] |
| 7 | Hackathon/Competition | X/10 | [Brief assessment] |
| 8 | Deployment Evidence | X/10 | [Brief assessment] |
| 9 | Depth vs. Breadth | X/10 | [Brief assessment] |

**Overall Signal Strength:** X/10 (average)

### Weakest Signal: [Signal Name] (X/10)

**Why this matters:** [Explanation of why this signal is important for the target role]

**Improvement Plan:**
1. [Specific action to improve this signal]
2. [Specific action]
3. [Timeline estimate]

### Strongest Signals (Lead with these)
1. [Signal] — [How to leverage this on the resume]
2. [Signal] — [How to leverage]

### Signal Gap by Role Family

| Signal | SDE Impact | AI/ML Impact | Full Stack Impact |
|---|---|---|---|
| DSA | CRITICAL | Medium | Medium |
| Project Depth | High | CRITICAL | High |
| Certifications | Low | High | Low |
| Deployment | Medium | Medium | CRITICAL |

### Resume Optimization Priority
Based on signal analysis, the resume should:
1. [Most important emphasis]
2. [Second priority]
3. [What to de-emphasize]

### Profile Improvement Priority (Outside the Resume)
These improvements would have MORE impact than resume optimization:
1. [Improvement 1 — e.g., "Solve 200+ DSA problems on LeetCode"]
2. [Improvement 2 — e.g., "Add README, screenshots, and tests to top 2 GitHub repos"]
3. [Improvement 3]
```

---

## The "Your Resume Is Not Your Bottleneck" Check

After scoring all 9 signals, apply this test:

> If ≥3 signals score ≤4/10, output this warning:

```markdown
> [!CAUTION]
> ### Your resume is NOT your primary bottleneck.
>
> With [N] weak signals, improving your resume from 70/100 to 90/100 will have
> minimal impact on your callback rate. Your effort should be split:
>
> - 30% Resume + application strategy
> - 30% [Weakest signal improvement]
> - 20% [Second weakest signal improvement]
> - 20% Interview preparation
>
> NOT:
> - 80% Resume optimization
> - 20% Everything else
>
> The resume can get you into the funnel. It cannot compensate for [weak signal].
```

---

## Rules

1. **Score based on evidence, not claims.** If the candidate says "I know DSA" but has no LeetCode profile, problem count, or DSA-heavy projects, DSA Evidence scores ≤3.
2. **Be honest, not cruel.** The purpose is actionable improvement, not discouragement. Every weak score must have a specific improvement path.
3. **Adjust weights by role family.** DSA matters much more for SDE than for Full Stack. Deployment matters more for Full Stack than for AI/ML Research.
4. **This analysis is private.** It informs the resume pipeline but is NOT shown on the resume itself. The resume shows the candidate's strengths. This report shows where to improve.
5. **Re-run when the profile changes.** New projects, new certifications, more DSA problems — these change the signal scores.
