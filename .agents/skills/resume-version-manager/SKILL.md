---
name: Resume Version Manager
description: Track different resume versions, maintain master resume, manage tailored versions
---

# Resume Version Manager

## When to Use This Skill

Use this skill when the user:
- Has multiple resume versions to manage
- Needs to track tailored resumes
- Wants to maintain a master resume
- Is applying to many different roles
- Mentions: "resume versions", "master resume", "different versions", "track resumes", "which resume"

## Core Capabilities

- Create and maintain master resume document
- Track tailored resume versions
- Organize resume versions by role/industry
- Maintain consistent source of truth
- Streamline resume updates
- Prevent version confusion

## The Version Management Problem

**Common Pain Points:**
- "Which version did I send to Company X?"
- "Where's my most recent resume?"
- "I have 15 resume files and don't know which is best"
- "I forgot to update my resume after that project"
- "I keep tailoring from different base versions"

**The Solution:**
A systematic approach with:
1. One master resume (source of truth)
2. Organized tailored versions
3. Clear naming conventions
4. Update workflow

## Master Resume Concept

### What is a Master Resume?

A comprehensive document containing:
- ALL your experiences (not just recent)
- ALL bullet points you've ever written
- Every achievement, project, skill
- Full details (even if they won't fit on one page)

**Purpose:** Source of truth to pull from when tailoring

### Master Resume Structure

```markdown
# MASTER RESUME - [YOUR NAME]
Last Updated: [Date]

## CONTACT INFORMATION
[Full contact details]

## PROFESSIONAL SUMMARY VERSIONS
[Summary for Role Type A]
[Summary for Role Type B]
[Summary for Role Type C]

## ALL SKILLS
### Technical Skills
[Complete list by category]

### Soft Skills
[Complete list]

### Industry Knowledge
[All domains]

## PROFESSIONAL EXPERIENCE

### Company Name | Title | Dates

**All Bullets (choose best for each application):**
• Bullet 1 (leadership focused)
• Bullet 2 (technical focused)
• Bullet 3 (results focused)
• Bullet 4 (collaboration focused)
• Bullet 5 (additional achievement)
• Bullet 6 (additional achievement)

**Keywords this experience covers:**
[List of keywords this job demonstrates]

### Previous Company | Title | Dates
[Same format...]

## EDUCATION
[Complete education history]

## CERTIFICATIONS
[All certifications ever earned]

## PROJECTS
[All notable projects]

## VOLUNTEER / ADDITIONAL
[All other relevant experience]
```

## File Organization System

### Folder Structure

```
Resume/
├── Master/
│   └── LastName_Master_Resume.docx
├── Tailored/
│   ├── ProductManagement/
│   │   ├── LastName_PM_Google_Jan2024.pdf
│   │   └── LastName_PM_Meta_Jan2024.pdf
│   ├── Engineering/
│   │   ├── LastName_SWE_Startup_Feb2024.pdf
│   │   └── LastName_SWE_Enterprise_Feb2024.pdf
│   └── General/
│       └── LastName_General_Resume.pdf
├── CoverLetters/
│   ├── Google_PM_CoverLetter.docx
│   └── Meta_PM_CoverLetter.docx
└── Applications/
    └── ApplicationTracker.xlsx
```

### File Naming Convention

**Pattern:**
`[LastName]_[Role/Type]_[Company]_[Date].pdf`

**Examples:**
- `Smith_ProductManager_Google_Jan2024.pdf`
- `Smith_SWE_Stripe_Feb2024.pdf`
- `Smith_DataScience_General_2024.pdf`
- `Smith_Master_Resume_v3.docx`

## Version Categories

### By Target Role

**Product Management:**
- Emphasizes: Strategy, roadmap, metrics, stakeholders
- Skills highlight: Product tools, analytics, user research

**Software Engineering:**
- Emphasizes: Technical projects, systems, code
- Skills highlight: Languages, frameworks, tools

**Data Science:**
- Emphasizes: Analysis, ML, statistical methods
- Skills highlight: Python, SQL, ML libraries

### By Industry

**Tech/Startup:**
- Emphasizes: Innovation, growth, scrappiness
- Tone: Modern, direct, achievement-focused

**Enterprise/Corporate:**
- Emphasizes: Scale, process, collaboration
- Tone: Professional, structured, comprehensive

**Finance:**
- Emphasizes: Analysis, compliance, accuracy
- Tone: Conservative, precise, credentialed

### By Seniority Level

**Individual Contributor:**
- Focus on execution and technical skills
- Detailed project descriptions
- Technical accomplishments

**Manager:**
- Team leadership and development
- Cross-functional collaboration
- Business impact metrics

**Executive:**
- Strategic leadership
- P&L responsibility
- Organizational transformation

## Application Tracking

### Simple Tracker Spreadsheet

```
| Company | Role | Version Used | Date Applied | Status | Notes |
|---------|------|--------------|--------------|--------|-------|
| Google | PM | PM_Google_Jan | 1/15/24 | Interview | 2nd round 2/1 |
| Meta | PM | PM_Meta_Jan | 1/18/24 | Applied | Referral from John |
| Startup | PM | PM_General | 1/20/24 | Rejected | Too senior |
```

### Information to Track

- Company name
- Job title
- Resume version used
- Cover letter version used
- Application date
- Application method (portal, referral, direct)
- Current status
- Follow-up dates
- Notes and contacts

## Update Workflow

### When to Update Master Resume

**Immediately Update For:**
- New job or promotion
- Completed major project
- New skills or certifications
- Significant achievements
- Awards or recognition

**Quarterly Review:**
- Add recent accomplishments
- Update metrics with new data
- Refresh skills section
- Remove outdated information

### Master to Tailored Workflow

```
1. Start with Master Resume
   ↓
2. Copy to new file (don't edit master)
   ↓
3. Analyze job description
   ↓
4. Select relevant bullets from master
   ↓
5. Choose appropriate summary version
   ↓
6. Reorder skills for relevance
   ↓
7. Add job-specific keywords
   ↓
8. Trim to appropriate length
   ↓
9. Save with proper naming convention
   ↓
10. Update application tracker
```

## Common Scenarios

### Scenario 1: Applying to Similar Roles

**Strategy:**
- Create one well-tailored version for the role type
- Make minor adjustments for each company
- Track which slight variation went where

### Scenario 2: Applying to Different Role Types

**Strategy:**
- Create separate base versions for each role type
- Maintain clear folder organization
- Each version pulls from same master

### Scenario 3: Rapid Application Volume

**Strategy:**
- Create 2-3 strong category versions
- Use "general" versions for quick applications
- Reserve deep tailoring for top choices

### Scenario 4: Career Transition

**Strategy:**
- Create transition-focused version
- Emphasize transferable skills
- Maintain original industry version as backup

## Version Control Best Practices

### DO:
- ✅ Always work from master as source
- ✅ Use consistent naming conventions
- ✅ Track which version went where
- ✅ Keep master updated
- ✅ Date your files
- ✅ Backup to cloud storage

### DON'T:
- ❌ Edit master directly for applications
- ❌ Use vague names like "resume_final_v2"
- ❌ Forget which version you sent
- ❌ Let master get out of date
- ❌ Have multiple "master" files
- ❌ Delete old versions (archive instead)

## Output Format

When managing resume versions:

```markdown
# RESUME VERSION MANAGEMENT

## Master Resume Status
**Last Updated:** [Date]
**Location:** [File path]
**Total Experience Entries:** [X]
**Total Bullet Points Available:** [X]

## Active Versions

### Role Type: Product Management
**Base Version:** PM_General_2024.docx
**Tailored Versions:**
| Company | File Name | Date Created | Status |
|---------|-----------|--------------|--------|
| Google | PM_Google_Jan24 | 1/15/24 | Submitted |
| Meta | PM_Meta_Jan24 | 1/18/24 | Submitted |

### Role Type: Engineering
[Same structure]

## Update Queue
- [ ] Add Q4 project results to master
- [ ] Update skills with new certification
- [ ] Archive versions older than 6 months

## Recommended Actions
1. [Action 1]
2. [Action 2]
```

## Version Management Checklist

- ✅ Master resume exists and is current
- ✅ Folder structure is organized
- ✅ Naming convention is consistent
- ✅ Application tracker is maintained
- ✅ Know which version sent to each company
- ✅ All versions pull from same master
- ✅ Backup system in place
- ✅ Old versions archived (not deleted)
- ✅ Update workflow is established
- ✅ Regular master resume reviews scheduled

---

## Resume Version Learning (Outcome Tracker)

> **Turn your application history into a data-driven optimizer.**
> After 5+ applications, patterns emerge: which bullets get you interviews,
> which projects resonate at startups vs. enterprise, which JD match scores
> actually correlate with callbacks.

### Outcome Log Template

Track every application using this table:

```markdown
## Application Outcome Log

| Date | Company | Role | Resume Version | JD Match % | Outcome | Days to Response | Notes |
|---|---|---|---|---|---|---|---|
| 2026-08 | rtCamp | SWE | v3-rtcamp | 87% | Phone Screen | 5 | GitHub profile mentioned |
| 2026-08 | Darwinbox | SWE | v2-darwinbox | 74% | OA Invite | 3 | |
| 2026-08 | Amazon | SWE | v4-amazon | 91% | Rejected | 14 | No response to OA |
| 2026-08 | Atlassian | SWE | v3-atlassian | 82% | Interview | 7 | API design bullets noted |
| 2026-08 | PhonePe | SWE | v2-phonePe | 78% | No Response | 21 | |
```

**Outcome codes:**
- `Phone Screen` — recruiter reached out
- `OA Invite` — online assessment sent
- `Interview` — technical interview scheduled
- `Rejected` — explicit rejection received
- `No Response` — no contact after 3+ weeks (assume rejected)
- `Offer` — offer received

### Analysis Prompts (run after 5+ applications)

Ask Claude to analyze your outcome log with these prompts:

**1. Bullet Correlation**
> "Looking at my outcome log, which bullets appeared in resumes that got interviews vs. rejections? Which projects correlated with callbacks?"

**2. JD Match Threshold**
> "What's the minimum JD match % in my log that still resulted in an OA or interview? Is there a clear threshold?"

**3. Company Type Pattern**
> "Do my startup applications perform better or worse than enterprise applications? Which resume version sections seem to matter most for each?"

**4. Response Time Analysis**
> "Which applications got the fastest responses? What did those resume versions have in common?"

**5. Version Performance**
> "Which resume version (by version name) has the best interview-to-application ratio? What changed between the weaker and stronger versions?"

### Learning Loop

After every 5 applications:

```
Analyze outcome log
       │
       ▼
Identify lowest-performing bullets/projects
       │
       ▼
Check evidence database: are those bullets well-grounded?
       │
       ▼
Rewrite or replace weak evidence
       │
       ▼
Update master resume
       │
       ▼
Generate new tailored versions from updated master
```

### Version Naming Convention (Updated)

Include outcome in the version archive once known:

```
resumes/
├── master/
│   └── master-resume-2026-08.md
├── versions/
│   ├── v3-rtcamp-2026-08-[phone-screen].pdf   ← outcome appended
│   ├── v2-darwinbox-2026-08-[oa].pdf
│   ├── v4-amazon-2026-08-[rejected].pdf
│   └── v3-atlassian-2026-08-[interview].pdf
└── outcome-log.md
```

This naming convention makes pattern analysis trivial — you can grep for `[interview]` or `[rejected]` to compare versions instantly.

