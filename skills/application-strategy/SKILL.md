---
name: Application Strategy
description: Decides whether to apply to a specific role, with what level of effort, and with which resume variant. Prevents wasted applications on roles with fundamentally poor fit and prioritizes high-probability opportunities.
---

# Application Strategy

## When to Use This Skill

Use this skill AFTER the JD Intelligence Analyzer has produced a keyword importance graph and AFTER the Candidate Position Brief exists. This skill answers:

> **"Should I actually apply to this job? And if yes, how?"**

Trigger phrases: "should I apply", "is this a good fit", "application strategy", "prioritize my applications", "which jobs should I target"

---

## Core Principle

> **Applying to 50 poorly-matched jobs is worse than applying to 10 well-matched jobs with tailored resumes.**
>
> Every application you send to a role where you have <40% fit wastes time that could be spent on:
> - Tailoring a resume for a role where you're a strong fit
> - Improving your DSA or projects
> - Getting referrals
> - Preparing for interviews
>
> This skill exists to prevent application spray-and-pray.

---

## Step 1: Fit Assessment

Using the JD keyword importance graph and the Candidate Position Brief, calculate fit across 4 dimensions.

### Dimension 1: Technical Skill Match

| Level | Criteria |
|---|---|
| Strong (8-10) | ≥80% of Critical keywords matched + ≥60% of Major keywords |
| Moderate (5-7) | 50-79% of Critical keywords matched |
| Weak (2-4) | 25-49% of Critical keywords matched |
| No Fit (0-1) | <25% of Critical keywords matched |

### Dimension 2: Experience Level Match

| Level | Criteria |
|---|---|
| Strong | JD says "0-2 years" or "fresher" or "new grad" or "entry level" |
| Moderate | JD says "1-3 years" or doesn't specify, but responsibilities are entry-level |
| Stretch | JD says "2-4 years" — possible but competitive |
| No Fit | JD says "3+ years" or "5+ years" or "Senior" or "Staff" or "Lead" |

### Dimension 3: Role Family Alignment

| Level | Criteria |
|---|---|
| Strong | JD role family matches candidate's PRIMARY role family |
| Moderate | JD role family matches candidate's SECONDARY role family |
| Weak | JD role family is adjacent (e.g., candidate is AI/ML, role is Data Engineer) |
| No Fit | JD role family is unrelated (e.g., candidate is backend, role is iOS Developer) |

### Dimension 4: Missing Critical Skills

Count the number of Critical keywords that:
- The candidate does NOT have
- Cannot be truthfully added (not even as "exposure to")
- Are hard requirements (not "nice to have")

| Level | Criteria |
|---|---|
| Strong | 0 missing critical skills |
| Moderate | 1 missing critical skill that is learnable |
| Weak | 2 missing critical skills |
| No Fit | 3+ missing critical skills |

---

## Step 2: Application Decision

Combine the 4 dimensions into a decision.

### Decision Matrix

| Decision | Criteria | Action |
|---|---|---|
| ✅ **Strong Apply** | ALL dimensions are Strong or Moderate, with at least 2 Strong | Generate fully tailored resume using the complete pipeline. High priority. |
| ⚠️ **Standard Apply** | Most dimensions are Moderate, no dimension is No Fit | Use the role-family master variant with light JD tailoring. Medium priority. |
| 🟡 **Stretch Apply** | 1 dimension is Weak but the rest are Strong/Moderate | Apply only if you have a referral or the company is a high-priority target. Include a cover letter addressing the gap. |
| ❌ **Low Probability** | 2+ dimensions are Weak, or 1 dimension is No Fit | Do not apply unless you have a strong referral. Your time is better spent elsewhere. |
| 🚫 **Do Not Apply** | Any dimension is a clear No Fit (e.g., requires 5+ YoE) | This role is not appropriate for your current profile. Move on. |

---

## Step 3: Application Plan

For ✅ and ⚠️ decisions, output a concrete application plan.

```markdown
## Application Strategy

**Role:** [Title] at [Company]
**Decision:** [✅ Strong Apply / ⚠️ Standard Apply / 🟡 Stretch Apply / ❌ Low Probability / 🚫 Do Not Apply]

### Fit Assessment

| Dimension | Score | Assessment |
|---|---|---|
| Technical Skill Match | X/10 | [Assessment] |
| Experience Level Match | [Strong/Moderate/Stretch/No Fit] | [Assessment] |
| Role Family Alignment | [Strong/Moderate/Weak/No Fit] | [Assessment] |
| Missing Critical Skills | [N missing] | [List of missing skills] |

### Resume Variant
**Use:** [Primary role family variant / Custom tailored]
**Project Order:** [Project 1, Project 2, Project 3]
**Skills Emphasis:** [Top 5 skills to lead with]
**Certifications:** [Which to include]

### Missing Requirements
| Missing Skill | Learnable? | How to Address on Resume |
|---|---|---|
| [Skill] | [Yes/No] | [Strategy: "Exposure to X in Project Y" or omit] |

### Application Effort
**Estimated time:** [15 min / 30 min / 1 hour / 2 hours]
**Effort breakdown:**
- Resume tailoring: [X min]
- Cover letter: [X min, if needed]
- Application form: [X min]

### Additional Recommendations
- **Referral:** [Recommended / Not necessary / Critical for this stretch role]
- **Cover Letter:** [Not needed / Recommended / Essential to address gaps]
- **Follow-up:** [Standard / Worth a LinkedIn connection request]
- **Portfolio link:** [Include / Not necessary]
```

---

## Step 4: Batch Application Prioritization

When the candidate has multiple jobs to apply to, rank them.

```markdown
## Application Priority Queue

| Priority | Role | Company | Decision | Key Strength | Key Risk |
|---|---|---|---|---|---|
| 1 | [Title] | [Company] | ✅ Strong | [Strength] | [Risk or "None"] |
| 2 | [Title] | [Company] | ✅ Strong | [Strength] | [Risk] |
| 3 | [Title] | [Company] | ⚠️ Standard | [Strength] | [Risk] |
| 4 | [Title] | [Company] | 🟡 Stretch | [Strength] | [Risk] |
| -- | [Title] | [Company] | ❌ Skip | -- | [Why] |

### Recommended Weekly Application Budget
- **Fully tailored (✅):** 3-4 per week
- **Standard variant (⚠️):** 5-7 per week
- **Stretch with referral (🟡):** 1-2 per week
- **Total applications:** 10-12 per week maximum

> [!TIP]
> Quality beats quantity. 10 well-targeted applications per week with tailored resumes
> will outperform 50 spray-and-pray applications with a generic resume.
```

---

## Fresher-Specific Adjustments

### For Indian Fresher Market

1. **Mass recruiter roles (TCS, Infosys, Wipro, etc.)**: Experience level is always "Strong" for freshers. Focus on CGPA and DSA. These roles have automated screening — ATS optimization matters more here.

2. **Startup roles**: Experience level is often unlisted. If responsibilities seem entry-level, treat as "Moderate" fit. Startups value project quality over pedigree.

3. **Product company roles (Google, Microsoft, Amazon, etc.)**: Experience level requirements are strict. "SDE-1" or "New Grad" are the only appropriate levels. DSA is the primary filter.

4. **Remote/international roles**: Additional screening for communication skills. If the JD mentions "async communication" or "distributed team", note this.

### Application Volume Guidelines for Freshers

| Phase | Duration | Volume | Focus |
|---|---|---|---|
| Week 1-2 | Warmup | 5-8 applications | Best-fit roles only, perfect your resume variants |
| Week 3-6 | Active | 10-15 per week | Mix of strong and standard apply |
| Week 7+ | Broadening | 12-20 per week | Expand to stretch roles, include cover letters |

---

## Red Flags in Job Postings (Flag to Candidate)

| Red Flag | Signal | Recommendation |
|---|---|---|
| "Rockstar" / "Ninja" / "10x" | Unrealistic expectations | Apply cautiously, expect vague responsibilities |
| Very wide salary range (₹4L-₹25L) | Role is poorly defined | Confirm actual level before investing time |
| "Must have 0-10 years experience" | Copy-paste JD, no serious screening | Low-quality application, don't over-invest |
| No specific technologies listed | Vague role or non-technical screener | Proceed but expect generic interview process |
| "Work-life balance" not mentioned + "fast-paced" × 3 | Potential burnout culture | Personal decision, but be aware |
| Unpaid internship for technical role | Exploitative | Generally avoid unless there's a very specific learning opportunity |

---

## Rules

1. **Be honest about fit.** It's better to tell the candidate "don't apply" than to help them waste 2 hours on a perfectly tailored resume for a role they'll never get.
2. **Referrals change everything.** A 🟡 Stretch role becomes a ⚠️ Standard Apply with a warm referral. Always factor this in.
3. **This skill saves time, not effort.** The time saved by NOT applying to poor-fit roles should be redirected to tailoring applications for strong-fit roles.
4. **Re-evaluate periodically.** As the candidate improves their profile (more DSA, better projects, new certifications), roles that were previously ❌ may become 🟡 or ⚠️.
5. **Never discourage unnecessarily.** If the candidate is passionate about a specific company/role and it's a 🟡 Stretch, help them with their best application — just be transparent about the odds.
