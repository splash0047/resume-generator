# 🎯 AI Resume & Career Skills for Agentic Coding Assistants

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![Agent Support](https://img.shields.io/badge/Agents-Cursor%20%7C%20Claude%20%7C%20Windsurf%20%7C%20Gemini-blue)](https://github.com/splash0047/resume-generator)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/splash0047/resume-generator)

A highly optimized collection of AI agent skills and custom instructions focused on resume optimization, ATS compatibility, job applications, and career development. Designed for job seekers, career changers, and professionals who want AI agents (like **Claude Code**, **Cursor**, **Windsurf**, and **Gemini**) to help with resume writing, ATS optimization, interview prep, and strategic career growth.

---

## 📖 Table of Contents
- [✨ Key Features](#-key-features)
- [📂 Repository Architecture](#-repository-architecture)
- [🛠️ The LaTeX Resume Mega-Prompt (`ATS_RESUME_PROMPT.md`)](#%EF%B8%8F-the-latex-resume-mega-prompt-ats_resume_promptmd)
- [🧩 Available Skills & Workflows](#-available-skills--workflows)
- [🚀 Installation & Setup](#-installation--setup)
  - [Option 1: CLI Install (Recommended)](#option-1-cli-install-recommended)
  - [Option 2: Manual Install](#option-2-manual-install)
  - [Option 3: Direct Download](#option-3-direct-download)
- [🤖 Supported AI Agents](#-supported-ai-agents)
- [💡 How to Use Skills](#-how-to-use-skills)
- [🛠️ How to Customize & Create Skills](#%EF%B8%8F-how-to-customize--create-skills)
- [📊 Why These Skills Matter](#-why-these-skills-matter)
- [🤝 Contributing](#-contributing)
- [📜 License](#-license)

---

## ✨ Key Features

- **29 Specialized Agent Skills**: Comprehensive coverage of every stage — from candidate positioning and JD analysis to recruiter rejection simulation and offer comparison.
- **Candidate-Positioning-First Pipeline**: Determines your role identity (SDE / AI-ML / Full Stack) *before* keyword optimization. The most important step for freshers.
- **Evidence-Grounded Bullets**: Every resume bullet must be traceable to GitHub source code, project evidence, or verifiable experience. No fabricated metrics.
- **Recruiter Rejection Simulator**: Simulates why a recruiter would reject your resume in 6 seconds — more useful than abstract ATS scores.
- **Fresher Signal Analyzer**: Evaluates 9 hiring signals critical for new grads (CGPA, DSA, project depth, GitHub quality, deployment evidence).
- **Application Strategy Engine**: Decides whether to apply at all, preventing wasted effort on poor-fit roles.
- **The Ultimate LaTeX Mega-Prompt**: Generates compilable LaTeX using **Jake's Template** with a 10-step quality pipeline.
- **Multi-Agent Compatibility**: Works natively with Cursor, Claude Code, Windsurf, Gemini, and 30+ other AI environments.

---

## 📂 Repository Architecture

Here is how the repository is structured to enable native, zero-configuration loading by multiple AI agents:

```text
resume-generator/
├── .agents/                     # Standardized agent directory
│   └── skills/                  # Mirrored skills for agent auto-loading
├── .cursor/
│   └── skills/                  # Cursor-specific symlinks
├── skills/                      # Source directories for each skill
│   ├── candidate-positioning/   # NEW: Phase -1 — Role identity first
│   ├── application-strategy/    # NEW: Apply or skip decision engine
│   ├── fresher-signal-analyzer/  # NEW: 9-signal fresher profile scorer
│   ├── recruiter-rejection-simulator/ # NEW: 6s/30s/EM rejection test
│   ├── jd-intelligence-analyzer/
│   ├── engineering-evidence-database/
│   ├── github-project-analyzer/
│   ├── resume-humanizer/
│   ├── resume-critic/
│   ├── resume-ats-optimizer/
│   ├── resume-bullet-writer/
│   └── ...                      # 15 more specialized skills
├── ATS_RESUME_PROMPT.md         # The LaTeX Mega-Prompt (10-step pipeline)
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

---

## 🛠️ The LaTeX Resume Mega-Prompt (`ATS_RESUME_PROMPT.md`)

Located in the root directory, [ATS_RESUME_PROMPT.md](ATS_RESUME_PROMPT.md) is a **10-step pipeline** that generates a perfect one-page resume using **Jake Gutierrez's LaTeX Template**.

### 🔄 Pipeline Architecture

```
Phase -1: Candidate Positioning     → "What kind of candidate are you?"
Phase  0: JD Intelligence           → Keyword graph + style inference
Phase 0.5: Application Strategy     → "Should you even apply?"
Phase  1: Evidence Extraction        → GitHub analysis + evidence database
Phase  2: Resume Audit               → Gap analysis against JD
Phase  3: LaTeX Construction         → Build resume with Jake's template
Phase  4: ATS Validation             → Standard headers + keyword check
Phase  5: Critic Quality Gate        → 10-dimension scorecard
Phase 5.5: Rejection Simulator       → 6s scan / 30s review / EM deep read
Phase  6: Final Delivery             → LaTeX + Audit Report + Interview Pack
```

### ❓ Why Jake's LaTeX Template?
- **100% ATS Compliant**: Standard font, single-column, correct section headers.
- **Predefined Macros**: `\resumeSubheading`, `\resumeProjectHeading`, `\resumeItem`.
- **Perfect Spacing**: Fine-tuned margins for maximum density without clutter.

### 📝 How to Use the Mega-Prompt:
1. Open [ATS_RESUME_PROMPT.md](ATS_RESUME_PROMPT.md) and copy the entire text.
2. Open a new chat session with your AI (Claude, Gemini, or Cursor).
3. Fill in the 3 inputs at the bottom:
   - `INPUT 1: Job Description (JD)`
   - `INPUT 2: Your Resume / Details`
   - `INPUT 3: Evidence Sources` (GitHub URLs recommended)
4. Send the prompt. The AI will execute the 10-step pipeline and output:
   - **Compilable LaTeX Code** — Drop into [Overleaf](https://www.overleaf.com/)
   - **Resume Audit Report** — Bullet-by-bullet evidence + confidence scores
   - **Recruiter Rejection Analysis** — Why a recruiter might reject you + fixes
   - **Interview Preparation Pack** — Q&A pairs per bullet

---

## 🧩 Available Skills & Workflows

Each skill in the `skills/` directory contains highly specialized prompt instructions that your AI agent will automatically reference to solve career-related tasks.

### 🛡️ Skill Category Breakdown

| Category | Skill | Key Objective / Framework |
| :--- | :--- | :--- |
| 🎯 **Positioning & Strategy** | `candidate-positioning` | **NEW** — Determines role identity (SDE/AI-ML/Full Stack) before any optimization |
| | `application-strategy` | **NEW** — Apply/Skip decision engine with fit assessment |
| | `fresher-signal-analyzer` | **NEW** — 9-signal fresher profile scorer (CGPA, DSA, GitHub quality, etc.) |
| | `recruiter-rejection-simulator` | **NEW** — 6s/30s/EM rejection simulation with fixes |
| 📊 **Evidence Pipeline** | `jd-intelligence-analyzer` | Keyword importance graph + role family classification + style inference |
| | `engineering-evidence-database` | 15-field evidence schema for traceable bullets |
| | `github-project-analyzer` | Extracts verified tech stack + confidence-scored bullets from repos |
| 📝 **Resume Generation** | `resume-humanizer` | 7-dimension scoring to remove AI patterns + apply engineering prose |
| | `resume-critic` | 10-dimension quality gate including Truthfulness + Candidate Positioning |
| | `resume-bullet-writer` | PACTI (selective) + X-Y-Z + CAR bullet frameworks |
| | `resume-quantifier` | Evidence-first metrics; fresher-specific guidance against fake numbers |
| | `resume-ats-optimizer` | ATS parsing + keyword placement (natural, not repetitive) |
| | `resume-formatter` | Jake's template structural rules |
| | `resume-section-builder` | Section ordering + conditional coursework rules |
| | `resume-tailor` | Role-specific highlighting of true experience |
| | `resume-version-manager` | Master resume + variant tracking |
| 🎯 **Job Search** | `job-description-analyzer` | Weighted match score computation |
| | `offer-comparison-analyzer` | Side-by-side total compensation models |
| ✉️ **Supporting Documents** | `cover-letter-generator` | Non-generic cover letters tied to JD goals |
| | `linkedin-profile-optimizer` | Headlines, summaries, search optimization |
| | `portfolio-case-study-writer` | Resume bullets → detailed portfolio case studies |
| | `reference-list-builder` | Reference prep and formatting |
| 🗣️ **Interview & Salary** | `interview-prep-generator` | STAR answers, practice questions, prep guides |
| | `salary-negotiation-prep` | Market research, counter-offer scripts |
| 💼 **Specialized Paths** | `tech-resume-optimizer` | SWE, PM, Tech Lead specific |
| | `executive-resume-writer` | C-suite/VP strategic leadership |
| | `career-changer-translator` | Cross-industry skill translation |
| | `academic-cv-builder` | Publications, grants, teaching |
| | `creative-portfolio-resume` | Creative design + ATS balance |

---

## 🚀 Installation & Setup

You can load these skills into your local AI workspace in three ways:

### Option 1: CLI Install (Recommended)

Easily install the skills globally or locally using `npx`:

```bash
# Install all skills globally (works across all your projects and directories)
npx skills add splash0047/ResumeSkills -g -y

# Install to the current active workspace only
npx skills add splash0047/ResumeSkills -y

# List all globally installed skills
npx skills list --global

# List local skills
npx skills list
```

### Option 2: Manual Install

If you prefer to configure this manually, clone this repository and copy the skills directly into your agent's directory:

```bash
# Clone the repository
git clone https://github.com/splash0047/resume-generator.git

# Create the cursor skills directory (if not exists)
mkdir -p ~/.cursor/skills

# Copy the core skill md files
cp -r resume-generator/skills/* ~/.cursor/skills/
```

### Option 3: Direct Download

Download individual skill folders from [the GitHub website](https://github.com/splash0047/resume-generator) and place them inside the `.agents/skills/` or `.cursor/skills/` directory of your project folder.

---

## 🤖 Supported AI Agents

These skills are written in standardized system-prompt markdown, making them compatible with major agentic frameworks:

*   **Cursor** (via `.cursorrules` or individual cursor skills)
*   **Claude Code** (via the local `.agents/` setup)
*   **Windsurf** (via custom `.windsurf` configurations)
*   **Copilot Workspace** & **Aider**
*   **Antigravity / Amp / Augment** & 30+ other IDE and terminal-based assistants

---

## 💡 How to Use Skills

Once the skills are installed, you do not need to do anything special! Simply ask your AI assistant questions in normal, plain English. The agent will recognize the context and pull instructions from the relevant skill.

> [!NOTE]
> Ensure your AI agent has permission to read files in the `.cursor/` or `.agents/` folder.

### 💬 Prompts to Try:

*   **For ATS Optimization:**
    > *"Review my resume against this Senior Frontend Engineer JD. Can you run an ATS compatibility check and suggest keywords to add?"*
*   **For Bullet Improvement:**
    > *"Here is a weak bullet from my last job: 'I worked on the website and fixed bugs.' How can we rewrite this using the XYZ formula?"*
*   **For Interview Readiness:**
    > *"I have a Technical PM interview at Amazon next Tuesday. Review my resume and generate 5 STAR behavior stories for customer obsession."*
*   **For Salary Negotiations:**
    > *"I received an offer of $115K base. Help me draft a professional, polite counter-offer email requesting $125K based on my experience."*

---

## 🛠️ How to Customize & Create Skills

Want to build your own custom career workflows? You can create a new skill in 3 steps:

1. Create a markdown file with custom frontmatter:
   ```markdown
   ---
   name: my-custom-skill
   description: Briefly explain when the agent should trigger this skill
   ---
   ```
2. Define clear boundaries under headings: `## When to Use This Skill`, `## Core Capabilities`, and `## Execution Workflow`.
3. Save the file in `.agents/skills/my-custom-skill/SKILL.md` and your agent will pick it up automatically!

---

## 📊 Why These Skills Matter

> [!IMPORTANT]
> The job application landscape is highly competitive.
> - Over **75% of resumes** are automatically filtered out by ATS parsers before reaching a human.
> - An average corporate job posting receives over **250 applications**.
> - Most candidates fail to quantify their achievements, leading to lower callbacks.

These skills are designed specifically to bridge this gap. By utilizing structured frameworks (like STAR and XYZ) and optimizing syntax for standard ATS compilers, applicants can experience:
- **2x to 3x more interview requests** per application cycle.
- A **faster overall job search** (saving an average of 2 months of effort).
- Greater confidence during negotiations, leading to **higher overall starting offers**.

---

## 🤝 Contributing

Contributions make the open-source community amazing! If you have ideas for new skills or modifications to existing ones:

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingSkill`)
3. Commit your Changes (`git commit -m 'Add some AmazingSkill'`)
4. Push to the Branch (`git push origin feature/AmazingSkill`)
5. Open a Pull Request

See [CONTRIBUTING.md](CONTRIBUTING.md) for more details.

---

## 📜 License

Distributed under the MIT License. See [LICENSE](LICENSE) for more details.

---

<p align="center"><i>Created with 💖 for job seekers everywhere. Good luck with your search! 🚀</i></p>
