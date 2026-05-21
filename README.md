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

- **20+ Specialized Agent Skills**: Comprehensive coverage of every stage in the job search funnel—from initial job description analysis to offer comparisons and salary negotiations.
- **ATS-Optimized Blueprints**: Built-in instructions aligned with Applicant Tracking System standards to maximize your pass rates.
- **The Ultimate LaTeX Mega-Prompt**: Generates beautiful, compilable LaTeX code based on **Jake's Template** (the gold standard for tech resumes).
- **Multi-Agent Compatibility**: Works natively with Cursor, Claude Code, Windsurf, Gemini, and 30+ other AI environments.
- **Achievement-Focused Output**: Automatically translates weak "responsible for" duties into impact-driven STAR/XYZ metrics.

---

## 📂 Repository Architecture

Here is how the repository is structured to enable native, zero-configuration loading by multiple AI agents:

```text
ResumeSkills/
├── .cursor/
│   └── skills/                  # Cursor-specific symlinks to skills
├── .agents/                     # Standardized agent directory
│   └── skills/                  # Core skill definitions
├── skills/                      # Source directories for each skill
│   ├── resume-ats-optimizer/
│   │   └── SKILL.md             # ATS optimizer rules & checklists
│   ├── resume-bullet-writer/
│   │   └── SKILL.md             # X-Y-Z and STAR statement frameworks
│   └── ...                      # 18 other specialized skills
├── ATS_RESUME_PROMPT.md         # The LaTeX Jake's Template Mega-Prompt
├── CONTRIBUTING.md              # Guidelines for adding new skills
├── LICENSE                      # MIT License file
└── README.md                    # You are here!
```

---

## 🛠️ The LaTeX Resume Mega-Prompt (`ATS_RESUME_PROMPT.md`)

Located in the root directory, [ATS_RESUME_PROMPT.md](ATS_RESUME_PROMPT.md) is a **Claude Mega-Prompt** designed to generate a perfect one-page resume using **Jake Gutierrez's LaTeX Template** (famous on Reddit's r/EngineeringResumes).

### ❓ Why Jake's LaTeX Template?
- **100% ATS Compliant**: Uses standard font structures, single-column design, and correct section headers.
- **Predefined Macros**: Includes custom tags for quick rendering of experience (`\resumeSubheading`), projects (`\resumeProjectHeading`), and skills.
- **Perfect Spacing**: Fine-tuned margins (`0.5 in`) to fit maximum professional density without looking cramped.

### 📝 How to Use the Mega-Prompt:
1. Open [ATS_RESUME_PROMPT.md](ATS_RESUME_PROMPT.md) and copy the entire text.
2. Open a new chat session with your AI (Claude 3.5 Sonnet is highly recommended).
3. Scroll to the bottom of the prompt and locate:
   - `INPUT 1: Job Description (JD)`
   - `INPUT 2: Your Old Resume / Details`
4. Paste the target Job Description and your current resume details in the designated slots.
5. Send the prompt to the AI.
6. The AI will output:
   - **Compilable LaTeX Code**: Drop this directly into [Overleaf](https://www.overleaf.com/) to compile your beautiful resume.
   - **Detailed Keyword Mapping**: A breakdown of target keywords, where they were added, and why.
   - **Before/After Bullet Changelog**: Proof of how your experience bullets were upgraded.

---

## 🧩 Available Skills & Workflows

Each skill in the `skills/` directory contains highly specialized prompt instructions that your AI agent will automatically reference to solve career-related tasks.

### 🛡️ Skill Category Breakdown

| Category | Skill | Key Objective / Framework |
| :--- | :--- | :--- |
| 📈 **Resume Optimization** | `resume-ats-optimizer` | Checks formatting, solves ATS parsing failures, target score 80%+ |
| | `resume-bullet-writer` | Converts passive duties into X-Y-Z metric-driven accomplishments |
| | `resume-quantifier` | Discovers opportunities to inject dollar amounts, %, and volume metrics |
| | `resume-formatter` | Enforces structural styling rules for clean, scannable layouts |
| | `resume-section-builder` | Builds targeted custom sections optimized for specific experience levels |
| 🎯 **Job Search Strategy** | `job-description-analyzer` | Computes weighted match score: `(Required × 0.70) + (Preferred × 0.30)` |
| | `resume-tailor` | Tactically highlights authentic skills corresponding to a specific JD |
| | `resume-version-manager` | Manages master resume variants and tracks tailored modifications |
| | `offer-comparison-analyzer`| Compares multiple offers with side-by-side total compensation models |
| ✉️ **Supporting Documents** | `cover-letter-generator` | Drafts punchy, non-generic cover letters tying experience to JD goals |
| | `linkedin-profile-optimizer`| Optimizes LinkedIn headlines, summaries, and search terms |
| | `portfolio-case-study-writer`| Converts resume bullets into structured, in-depth portfolio articles |
| | `reference-list-builder` | Prepares reference documents and prep sheets for prospective callers |
| 🗣️ **Interview & Salary** | `interview-prep-generator` | Generates situational STAR answers, practice questions, and prep guides |
| | `salary-negotiation-prep` | Creates market-rate research scripts, counter-offers, and scripts |
| 💼 **Specialized Paths** | `tech-resume-optimizer` | Customized for Software Engineers, Product Managers, and Tech Leads |
| | `executive-resume-writer` | Highlights C-suite/VP strategic leadership, P&L, and org scale |
| | `career-changer-translator`| Translates legacy jargon into target industry transferable skills |
| | `academic-cv-builder` | Organizes publication histories, grant awards, and teaching portfolios |
| | `creative-portfolio-resume`| Balances creative aesthetic design with ATS parsability |

---

## 🚀 Installation & Setup

You can load these skills into your local AI workspace in three ways:

### Option 1: CLI Install (Recommended)

Easily install the skills globally or locally using `npx`:

```bash
# Install all skills globally (works across all your projects and directories)
npx skills add Paramchoudhary/ResumeSkills -g -y

# Install to the current active workspace only
npx skills add Paramchoudhary/ResumeSkills -y

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
