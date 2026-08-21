---
name: Recruiter Rejection Simulator
description: Simulates why a recruiter would reject this resume in 6 seconds. Runs 3 rejection personas, generates explicit rejection reasons with fixes, and provides a more actionable signal than abstract ATS scores. Use after the Resume Critic as the final human-reality check.
---

# Recruiter Rejection Simulator

## When to Use This Skill

Use this skill as **Phase 5.5** — after the Resume Critic (Phase 5) passes all 9/10 dimensions, but before final delivery. This is the human-reality check that abstract scoring cannot provide.

Trigger phrases: "would a recruiter reject this", "simulate rejection", "why am I not getting callbacks", "reality check my resume"

---

## Core Principle

> **Your resume doesn't need to be perfect. It needs to survive the "no" pile.**
>
> A recruiter reviewing 300+ fresher applications has one primary action: **reject**.
> They're not looking for reasons to say yes. They're looking for reasons to say no.
> Your resume must eliminate every obvious rejection trigger.
>
> An ATS score of 97% means nothing if the recruiter puts you in the "no" pile at second 4.

---

## Simulation 1: The 6-Second Scan

**Persona**: Technical Recruiter with 300 resumes to screen today.
**Time**: 6 seconds.
**Task**: Decide "Maybe" or "No" pile.

### What the recruiter scans in 6 seconds (in order):
1. **Name + contact** (0.5s) — Is this a real person with professional contact info?
2. **Current/most recent title** (1s) — Does it match the role I'm hiring for?
3. **Education** (1s) — Right degree? Decent institution/CGPA?
4. **Skills section** (1.5s) — Do I see the 3-4 technologies I'm looking for?
5. **First project title** (1s) — Does it sound relevant?
6. **Overall visual impression** (1s) — Clean? One page? Not a wall of text?

### 6-Second Rejection Triggers

Evaluate each trigger. If triggered, output the rejection reason and fix.

| # | Trigger | What Causes It | Fix |
|---|---|---|---|
| 1 | **No clear role identity** | Skills section lists 30+ technologies across 8 categories | Reduce to 12-15 technologies in 4-5 categories aligned to role |
| 2 | **Title mismatch** | Most recent experience title doesn't match target role | Reorder experience or adjust emphasis |
| 3 | **AI/buzzword overload** | First 3 project titles all contain "AI" for an SDE role | Reorder projects; lead with engineering projects for SDE roles |
| 4 | **Visual clutter** | Too dense, inconsistent spacing, overflows page | Fix LaTeX spacing, reduce bullet count |
| 5 | **No relevant keywords visible** | JD critical keywords not in the first thing scanned | Move critical tech to top of skills section |
| 6 | **Education red flag** | Low CGPA prominently displayed, or CGPA hidden when it's strong | Show CGPA ≥8.0; hide if <7.0 |

### 6-Second Scan Output

```markdown
### Simulation 1: 6-Second Scan

**Verdict:** [MAYBE / NO]

**What the recruiter saw:**
- Name: ✅
- Title relevance: [✅ / ⚠️ / ❌] — [reason]
- Education: [✅ / ⚠️ / ❌] — [reason]
- Skills scan: [✅ / ⚠️ / ❌] — [reason]
- First project: [✅ / ⚠️ / ❌] — [reason]
- Visual: [✅ / ⚠️ / ❌] — [reason]

**Rejection reason (if NO):** [specific reason]
**Fix:** [specific action]
```

---

## Simulation 2: The 30-Second Technical Review

**Persona**: Senior recruiter or junior engineering manager doing initial tech screen.
**Time**: 30 seconds.
**Task**: Decide "Interview" or "Reject" from the "Maybe" pile.

### What the reviewer reads in 30 seconds:
1. **All project titles + tech stacks** (5s) — Do these technologies match what we use?
2. **Experience bullets — first bullet per job** (10s) — What did this person actually do?
3. **Skills section — full scan** (5s) — Any missing critical technologies?
4. **Project bullets — skim** (10s) — Do these sound real or tutorial-level?

### 30-Second Rejection Triggers

| # | Trigger | What Causes It | Fix |
|---|---|---|---|
| 1 | **Projects look tutorial-level** | Generic descriptions like "Built a CRUD app", no architecture reasoning | Add specific technical decisions, not just "used X" |
| 2 | **No deployment evidence** | No live demo links, no Docker, no CI/CD mentioned | Add deployment context even if local |
| 3 | **Metrics look fabricated** | "Improved performance by 85%" with no context | Qualify metrics or remove undefendable ones |
| 4 | **Technology mismatch** | Resume emphasizes Python/ML but JD needs Java/Spring | Reorder skills + swap project emphasis |
| 5 | **Too many similar projects** | 4 AI projects for an SDE role | Select 2-3 diverse, role-relevant projects |
| 6 | **No DSA evidence (for SDE)** | SDE role, no competitive programming, no DSA mentions | Add DSA coursework or problem-solving evidence if available |
| 7 | **Weak experience section** | Internship bullets are vague ("collaborated with team") | Rewrite with specific technical contributions |
| 8 | **Certification padding** | 5+ certifications taking prime resume space | Keep 2-3 relevant certs, remove padding |

### 30-Second Review Output

```markdown
### Simulation 2: 30-Second Technical Review

**Verdict:** [INTERVIEW / REJECT]

**Technology Match:** [Strong / Moderate / Weak]
- Matched: [list]
- Missing: [list]
- Irrelevant (taking space): [list]

**Project Credibility:** [High / Medium / Low]
- [Project 1]: [Assessment]
- [Project 2]: [Assessment]

**Experience Quality:** [Strong / Adequate / Weak]
- [Role 1]: [Assessment]

**Rejection reason (if REJECT):** [specific reason]
**Fix:** [specific action]
```

---

## Simulation 3: Engineering Manager Deep Read

**Persona**: Engineering Manager who will work with this hire.
**Time**: 2 minutes.
**Task**: "Would I be comfortable asking this person to whiteboard what's on their resume?"

### What the EM evaluates:
1. **Technical depth** — Does this person understand WHY, not just WHAT?
2. **Architecture credibility** — Do the described systems make technical sense?
3. **Growth trajectory** — Is there evidence of learning and increasing complexity?
4. **Red flags** — Anything that would make me uncomfortable in a technical interview?

### EM Rejection Triggers

| # | Trigger | What Causes It | Fix |
|---|---|---|---|
| 1 | **Scope overstatement** | "Production-ready ML system" for a student project | Use accurate scope language: "developed and deployed locally" |
| 2 | **Architecture nonsense** | Technologies combined in ways that don't make sense | Verify architecture claims are technically coherent |
| 3 | **No "why" in bullets** | Every bullet is "Built X using Y" — no reasoning | Add selective technical reasoning (don't force PACTI on every bullet) |
| 4 | **Buzzword salad** | "Leveraged RAG with LangGraph agents for AI-powered orchestration" | Replace with concrete: "Built 3-agent pipeline using LangGraph for log analysis with RAG retrieval" |
| 5 | **Can't whiteboard this** | Describes complex system but evidence suggests it's a tutorial follow-along | Scale claims to match actual contribution |
| 6 | **Impact without evidence** | "Reduced X by Y%" with no measurement methodology visible | Add qualifier or remove metric |

### EM Deep Read Output

```markdown
### Simulation 3: Engineering Manager Deep Read

**Verdict:** [PROCEED TO INTERVIEW / CONCERN / REJECT]

**Technical Depth Assessment:**
- Bullet N: [Strong — explains reasoning]
- Bullet N: [Weak — no "why", just "what"]

**Architecture Credibility:**
- [Project]: [Credible / Questionable / Overblown]

**Whiteboard Confidence:**
- "I would be comfortable asking about: [list]"
- "I would NOT ask about (seems fragile): [list]"

**Red Flags:** [list or "None"]
**Growth Evidence:** [assessment]
```

---

## Combined Rejection Report

After all 3 simulations, produce a combined report.

```markdown
## Recruiter Rejection Simulator Report

**Candidate:** [Name]
**Target Role:** [Title]
**Date:** [Date]

### Summary

| Simulation | Verdict | Key Issue |
|---|---|---|
| 6-Second Scan | [MAYBE/NO] | [Primary issue or "None"] |
| 30-Second Review | [INTERVIEW/REJECT] | [Primary issue or "None"] |
| EM Deep Read | [PROCEED/CONCERN/REJECT] | [Primary issue or "None"] |

### All Rejection Reasons (Prioritized)

1. **[CRITICAL]** [Reason] — Fix: [Action]
2. **[HIGH]** [Reason] — Fix: [Action]
3. **[MEDIUM]** [Reason] — Fix: [Action]

### Fixes Required Before Submission
- [ ] [Fix 1]
- [ ] [Fix 2]
- [ ] [Fix 3]

### Post-Fix Recommendation
After implementing fixes: [SUBMIT / SUBMIT WITH COVER LETTER / RECONSIDER APPLICATION]
```

---

## Fresher-Specific Calibration

When the candidate is a fresher (≤1 year experience), calibrate ALL personas accordingly:

1. **Don't expect production-scale metrics** — Evaluate project complexity, not production impact
2. **Value CGPA and certifications more** — These are primary signals for new grads
3. **DSA evidence matters for SDE roles** — Its absence is a legitimate rejection trigger for mass SDE hiring
4. **GitHub quality is a strong signal** — A well-documented repo compensates for lack of production experience
5. **Internship quality > quantity** — One meaningful internship with technical depth beats three "collaborative" internships
6. **Tutorial-detection is critical** — A fresher resume with 6 projects that all look like tutorial follow-alongs is worse than 2 projects with genuine engineering

---

## Rules

1. **This skill is NOT a score. It's a rejection test.** The output is "reasons you'd be rejected" — not "your resume is 85% good."
2. **Every rejection reason must have a fix.** Never flag a problem without a solution.
3. **Personas are independent.** A resume can pass the 6-second scan but fail the EM deep read. That's normal — they test different things.
4. **Be brutally honest.** The candidate is better served by a harsh simulator than a polite one. Saying "your resume is fine" when it's not costs them interviews.
5. **Run AFTER the Critic.** The Critic checks objective dimensions (evidence, truthfulness, ATS). This skill checks subjective human reactions. Both must pass.
6. **Fixes from this skill loop back to the Humanizer** for rewriting, then through the Critic again before final delivery.
