---
name: Resume Bullet Writer
description: Transform weak resume bullets into evidence-grounded, engineering-precise statements using the PACTI formula (Problem → Action → Core Technical Decision → Implementation → Impact). Every bullet must be traceable to evidence and defensible in an interview.
---

# Resume Bullet Writer

## When to Use This Skill

Use this skill when the user wants to:
- Write or improve resume bullet points
- Transform weak descriptions into strong achievements
- Add metrics and quantifiable results
- Make their experience more compelling
- Mentions: "improve my bullets", "make my resume stronger", "quantify my achievements", "results-driven"

Also use when you see weak bullets that need improvement (passive language, no metrics, vague descriptions).

## Core Capabilities

- Transform weak bullet points into achievement-focused statements
- Apply STAR method and X-Y-Z formula
- Add quantifiable metrics and results
- Use strong action verbs
- Tailor bullets to specific roles/industries
- Ensure every bullet shows impact, not just duties

## The Bullet Point Problem

Most resumes have weak bullets that list job duties instead of achievements:

❌ **Weak Bullets (What NOT to do):**
- "Responsible for managing team"
- "Helped with customer service"
- "Worked on improving processes"
- "Assisted with projects"

These are passive, vague, and don't show impact or results.

✅ **Strong Bullets (What TO do):**
- "Led cross-functional team of 12 to deliver $2M product, increasing revenue by 35%"
- "Resolved 50+ customer issues daily, improving satisfaction scores from 3.2 to 4.8/5"
- "Streamlined approval process, reducing cycle time by 40% (from 10 to 6 days)"
- "Managed portfolio of 8 concurrent projects with 100% on-time delivery rate"

These are active, specific, and quantify the impact.

## Core Frameworks

### 0. PACTI Formula — Primary Framework for Technical Bullets

> **Use PACTI for all technical bullets.** X-Y-Z and CAR are secondary options for non-technical or business impact bullets.

**Structure:**
```
P — Problem:                What infrastructure/user/business problem existed?
A — Action:                 What did you specifically do?
C — Core Technical Decision: Why X over Y? (the reasoning behind your choice)
T — Implementation:         What did you build/use to execute?
I — Impact:                 What measurably changed? (qualify by impact_type)
```

**The "Core Technical Decision" is the most important and most commonly missing element.** It shows engineering thinking, not just task completion.

**PACTI Examples:**

```
❌ WEAK:  "Implemented Isolation Forest for anomaly detection"

✅ PACTI: "Chose Isolation Forest over DBSCAN for log anomaly detection because
           the system had no labeled data — IF's unsupervised nature made it
           robust to varying log densities; reduced false alerts by ~27% during
           development testing on 15 simulated incidents"
```

```
❌ WEAK:  "Built backend API with FastAPI"

✅ PACTI: "Chose FastAPI over Flask for the log ingestion API because native async
           support was critical for concurrent log processing; built 5 REST
           endpoints with automatic OpenAPI docs, handling ~500 log entries
           per batch during local testing"
```

**Impact Classification** — controls how metrics are phrased:
| impact_type | When to Use | Metric Phrasing Rule |
|---|---|---|
| `production` | System is live, serving real users | Exact numbers: "Reduced P95 latency by 40%" |
| `research` | Academic or benchmark project | "Achieved 89% F1 on held-out test set" |
| `development` | Personal/internship, not in production | Must qualify: "Reduced local inference time by ~60% during testing" |
| `learning` | Course project, tutorial extended | No hard metrics; describe knowledge applied |

---

**Structure:** "Accomplished [X] as measured by [Y] by doing [Z]"

- X = What you achieved
- Y = How you measured it
- Z = What actions you took

**Examples:**

```
❌ BEFORE: "Managed social media accounts"

✅ AFTER: "Grew Instagram following by 250% (5K to 17.5K) by implementing daily content calendar and influencer partnerships"

X = Grew Instagram following by 250%
Y = 5K to 17.5K followers
Z = Daily content calendar + influencer partnerships
```

```
❌ BEFORE: "Improved customer service"

✅ AFTER: "Increased customer satisfaction scores by 40% (3.2 to 4.5/5) by redesigning support ticketing system and training 15 agents"

X = Increased customer satisfaction by 40%
Y = 3.2 to 4.5 out of 5
Z = Redesigned ticketing system + trained agents
```

### 2. STAR Method

**Structure:**
- **S**ituation: What was the context?
- **T**ask: What needed to be done?
- **A**ction: What did YOU specifically do?
- **R**esult: What was the measurable outcome?

**Example:**

Full STAR story:
"Inherited underperforming sales team (S) with 65% quota attainment. Tasked with improving performance within Q1 (T). Implemented new training program and revised commission structure (A). Achieved 92% quota attainment by Q2, generating $1.8M additional revenue (R)."

For resume bullet (condensed STAR):
"Revitalized underperforming sales team through training program and commission restructure, improving quota attainment from 65% to 92% and generating $1.8M additional revenue"

### 3. CAR Method (Alternative to STAR)

**Structure:**
- **C**hallenge: What problem existed?
- **A**ction: What did you do about it?
- **R**esult: What happened?

**Example:**

"Reduced customer churn (C) by implementing proactive outreach program (A), retaining 85% of at-risk accounts worth $500K ARR (R)"

## Power Verbs by Category

> **Engineering prose first.** Use these verbs. Avoid overuse of: Spearheaded, Orchestrated, Championed, Pioneered (flag if used >1×).

### Technical Execution
- Built, Designed, Implemented, Created, Developed, Wrote
- Deployed, Configured, Integrated, Extended, Refactored, Migrated
- Measured, Tested, Benchmarked, Validated, Debugged, Profiled

### Optimization & Impact
- Reduced, Automated, Improved, Optimized, Streamlined, Simplified
- Increased, Accelerated, Eliminated, Cut, Scaled, Expanded

### Leadership & Collaboration
- Led, Coordinated, Contributed, Mentored, Reviewed, Facilitated
- Presented, Documented, Trained, Onboarded

### Analysis & Research
- Analyzed, Identified, Evaluated, Researched, Investigated, Diagnosed
- Modeled, Forecasted, Audited, Assessed

### Achievement
- Achieved, Delivered, Secured, Exceeded, Completed, Shipped

## Quantification Strategies

Every bullet should have at least ONE number. Here's how to find metrics:

### Types of Metrics to Include

**1. Money**
- Revenue generated: "$2M in new revenue"
- Money saved: "Reduced costs by $50K annually"
- Budget managed: "Managed $5M project budget"
- Deal size: "Closed 3 enterprise deals worth $500K"

**2. Percentages**
- Growth: "Increased conversion rate by 45%"
- Improvement: "Reduced error rate by 60%"
- Efficiency: "Decreased processing time by 30%"
- Quality: "Improved accuracy from 85% to 98%"

**3. Time**
- Speed: "Reduced load time from 8s to 2s"
- Frequency: "Delivered weekly reports to 50+ stakeholders"
- Duration: "Completed 6-month project in 4 months"
- Saved time: "Automated process, saving team 10 hours/week"

**4. Scale/Volume**
- People: "Led team of 15", "Trained 50+ employees"
- Projects: "Managed 8 concurrent initiatives"
- Customers: "Served 500+ enterprise clients"
- Users: "Built product used by 100K+ daily active users"

**5. Comparison/Before-After**
- "Increased from X to Y"
- "Reduced from X to Y"
- "Grew from X to Y"

### When You Don't Have Exact Numbers

Use estimation strategies:

**Approximate with ~**
"Improved performance by ~40%"

**Use ranges**
"Managed team of 8-12 people"
"Generated $50K-$75K in monthly revenue"

**Use conservative estimates**
If you think it was 60%, say 50%
If you saved 100 hours, say 75 hours

**Quantify inputs if outputs unknown**
Can't measure revenue? Quantify activities:
- "Conducted 30+ customer interviews"
- "Analyzed 500+ data points"
- "Created 20+ marketing campaigns"

**Find related metrics**
Can't measure conversion? Measure traffic, engagement, or other funnel metrics

## Industry-Specific Bullet Examples

### Software Engineering

❌ WEAK:
- Wrote code for new features
- Fixed bugs in production
- Worked with product team

✅ STRONG:
- Architected authentication microservice serving 500K+ daily active users, reducing login latency by 60% (from 5s to 2s)
- Resolved 50+ critical production bugs over 6 months, improving system uptime from 97.2% to 99.8%
- Collaborated with product team to deliver 12 features ahead of schedule, resulting in 25% increase in user engagement

### Product Management

❌ WEAK:
- Managed product roadmap
- Worked with stakeholders
- Launched new features

✅ STRONG:
- Defined and executed product roadmap for $10M ARR product, prioritizing 50+ feature requests from 200+ customers
- Facilitated weekly stakeholder meetings with engineering, design, and executive teams to align on strategic priorities
- Launched 8 major features in 12 months, driving 40% increase in customer retention and $2M additional revenue

### Sales

❌ WEAK:
- Met with clients
- Closed deals
- Exceeded quota

✅ STRONG:
- Generated $3.2M in new business revenue by closing 15 enterprise deals, achieving 142% of annual quota
- Managed sales cycle for 50+ prospects simultaneously, maintaining 35% close rate (company average: 22%)
- Exceeded quarterly quota 8 consecutive quarters, ranking #2 out of 45 sales reps nationwide

### Marketing

❌ WEAK:
- Created marketing campaigns
- Managed social media
- Analyzed campaign performance

✅ STRONG:
- Launched 12 multi-channel campaigns generating $500K in attributed revenue and 2,500+ qualified leads
- Grew LinkedIn audience by 400% (3K to 15K followers) through thought leadership content strategy, resulting in 200+ inbound demo requests
- Analyzed campaign performance across 8 channels using Google Analytics, identifying 3 top-performing channels responsible for 75% of conversions

### Customer Success

❌ WEAK:
- Helped customers with problems
- Managed customer accounts
- Conducted onboarding sessions

✅ STRONG:
- Maintained 95% customer retention rate across portfolio of 50 enterprise accounts representing $4M ARR
- Resolved 40+ customer issues weekly with average response time of 2 hours, achieving 4.9/5 CSAT score
- Delivered 25+ onboarding sessions for new customers, achieving 90% product adoption rate within first 30 days

### Data Analysis

❌ WEAK:
- Analyzed data
- Created reports
- Made recommendations

✅ STRONG:
- Analyzed 500K+ transaction records to identify $2M revenue opportunity, presented findings to C-suite resulting in new product line
- Built automated reporting dashboard in Tableau reducing manual reporting time by 15 hours/week for team of 8
- Developed predictive model with 85% accuracy for customer churn, enabling proactive retention campaigns that saved $500K ARR

### Operations/Project Management

❌ WEAK:
- Managed projects
- Coordinated with teams
- Tracked progress

✅ STRONG:
- Led 8 cross-functional projects simultaneously with 100% on-time delivery rate and zero budget overruns across $5M portfolio
- Coordinated efforts across engineering, design, and marketing teams (30+ people) to launch product ahead of schedule
- Implemented project tracking system reducing status meeting time by 50% and improving visibility for 15+ stakeholders

## Common Bullet Writing Mistakes

### Mistake 1: Passive Language
❌ "Was responsible for..."
❌ "Helped with..."
❌ "Assisted in..."
❌ "Participated in..."

✅ Use active verbs: Led, Created, Delivered, Achieved

### Mistake 2: No Metrics
❌ "Improved website performance"
✅ "Improved website load time by 60% (8s to 3.2s)"

❌ "Managed large team"
✅ "Led cross-functional team of 25 across 4 departments"

### Mistake 3: Job Duties Instead of Achievements
❌ "Responsible for customer support"
✅ "Resolved 50+ tickets daily with 98% customer satisfaction score"

❌ "Managed social media accounts"
✅ "Grew social media following by 300% (10K to 40K) in 8 months"

### Mistake 4: Too Vague
❌ "Worked with stakeholders"
✅ "Facilitated weekly meetings with 15+ stakeholders across engineering, product, and executive teams"

❌ "Improved processes"
✅ "Streamlined approval workflow, reducing cycle time from 10 to 4 days (60% improvement)"

### Mistake 5: Too Long
❌ "Was responsible for managing and overseeing all aspects of the customer success function including onboarding, training, support, and retention for a portfolio of enterprise clients..."

✅ "Led customer success for 50 enterprise clients ($3M ARR), achieving 95% retention rate"

**Rule: Keep bullets to 1-2 lines maximum**

## Bullet Writing Process

### Step 1: Start with the Weak Bullet
```
Original: "Managed social media"
```

### Step 2: Ask Clarifying Questions
- What platforms?
- How many followers?
- What growth did you achieve?
- What specific actions did you take?
- What business impact resulted?

### Step 3: Gather Information
- Platforms: Instagram, LinkedIn
- Started: 5K followers
- Ended: 18K followers  
- Actions: Daily content calendar, influencer partnerships
- Impact: 200 leads generated

### Step 4: Apply Formula
Using X-Y-Z:
"Grew Instagram and LinkedIn following by 260% (5K to 18K) by implementing daily content calendar and 15 influencer partnerships, generating 200+ qualified leads"

### Step 5: Optimize Length
If too long, prioritize most impressive metrics:
"Grew social media audience by 260% (5K to 18K followers) through content strategy and influencer partnerships, generating 200+ leads"

## Bullet Strength Checklist

Every bullet should have:
- ✅ Strong action verb (avoid "responsible for", "helped")
- ✅ At least one number/metric
- ✅ Specific outcome or result
- ✅ Context of scale (team size, budget, users, etc.)
- ✅ 1-2 lines maximum
- ✅ Reads as an achievement, not a duty
- ✅ Relevant to target role

## Output Format

When rewriting bullets, provide:

```markdown
## BULLET IMPROVEMENTS

### Original Bullet #1:
"Managed customer accounts"

### Issues:
- Passive language ("managed")
- No metrics
- Vague (what does "managed" mean?)
- No results shown

### Improved Version:
"Grew portfolio of 40 enterprise accounts from $2M to $3.5M ARR (75% growth) through quarterly business reviews and proactive upselling strategy"

### What Changed:
- Added scale (40 accounts)
- Added growth metric (75%, $2M to $3.5M)
- Specified actions (QBRs, upselling)
- Shows business impact (revenue growth)

---

### Original Bullet #2:
[Continue for each bullet...]
```

## Special Situations

### For Entry-Level/Recent Graduates
Focus on:
- Academic projects with real impact
- Internship achievements
- Relevant coursework projects
- Volunteer work with quantifiable results
- Club leadership with metrics

Example:
"Led university marketing club of 50 members, organizing 8 events attended by 300+ students and securing $10K in corporate sponsorships"

### For Career Changers
Focus on:
- Transferable skills
- Reframe old experience for new industry
- Highlight relevant projects/side work
- Emphasize learning and adaptation

Example:
"Managed cross-functional teams of 15 (traditional retail) → can become:
"Led cross-functional teams of 15 across operations, merchandising, and customer experience, coordinating workflows and achieving 100% project completion rate"

### For Gaps in Employment
Focus on:
- Freelance/consulting work
- Volunteer achievements
- Side projects
- Professional development

Don't draw attention to gaps, just fill space with relevant achievements.

## Interview Defensibility Rule

> **If you cannot answer the questions your bullet implies, the bullet should not exist.**

Every bullet must pass a 30-second defensibility test before it appears on the resume:

| Bullet Type | Implied Interview Question |
|---|---|
| Technology choice | "Why did you choose X over Y?" |
| Architecture claim | "Walk me through the system design." |
| Metric claim | "How did you measure this?" |
| Scale claim | "What was the traffic pattern / dataset size?" |
| Leadership claim | "Who was on the team, what was your specific role?" |

**Workflow:**
1. Write the bullet using PACTI
2. Generate the 2–3 most likely interview questions it implies
3. Can you answer them clearly? → Keep the bullet
4. Cannot answer one or more? → Either rewrite the bullet to reflect what you CAN defend, or remove it

**Examples:**

```
Bullet: "Reduced debugging time by 70% using AI-powered log analysis"
Q: "How was the 70% reduction measured?"
→ Cannot answer (no measurement was done) → REWRITE

Rewrite: "Automated log pre-filtering using Isolation Forest scores, reducing
 the manual log review set from ~500 to ~50 entries per incident during
 development testing"
→ Defensible ✅
```

---

## Implementation Checklist

For each resume bullet:
1. ✅ Apply PACTI: Problem → Action → Core Technical Decision → Implementation → Impact
2. ✅ Classify impact_type: production / research / development / learning
3. ✅ Check evidence: traceable to a source file, README, or document
4. ✅ Check truthfulness: wording accurately reflects evidence (not overstated)
5. ✅ Generate 2 interview questions: can you answer them? Keep if yes.
6. ✅ Check metrics: qualified by impact_type (no bare numbers for development projects)
7. ✅ Check specificity: ≥1 technology/algorithm/system named
8. ✅ Check length: ≤2 rendered lines
9. ✅ Check verbs: no cliché overuse (flag if Spearheaded/Orchestrated/Pioneered used >1×)
10. ✅ Read aloud: sounds like an engineer, not a marketer

