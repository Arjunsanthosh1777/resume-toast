# RESUME ROAST – AI Agent Skill

**RESUME ROAST** is a production-grade, reusable AI agent skill engineered to conduct rigorous, uncompromisingly honest, and actionable resume evaluations.

Unlike generic chatbots or visual template mockups, RESUME ROAST functions as an **Executive Talent Evaluator and Senior Technical Hiring Manager**. It diagnoses structural flaws, performs ATS parser readability audits, calculates candidate-to-job-description alignment, refactors passive bullet points into high-impact **Google XYZ / STAR** achievements, and exposes interview vulnerabilities—all while strictly upholding factual integrity and refusing to hallucinate candidate qualifications.

---

## 📁 Repository Structure

```
RESUME-ROAST/
├── SKILL.md                          # Core AI agent instructions & execution rules
├── README.md                         # Installation, activation, and usage documentation
├── references/
│   ├── resume-review-guide.md        # 6-Second Screen, Google XYZ formulas, & metric rubrics
│   └── ats-checklist.md              # 10 ATS fatal traps & 12-point pre-flight checklist
├── examples/
│   ├── sample-resume.md              # Full-stack developer sample resume with common flaws
│   └── sample-job-description.md     # Senior Full-Stack Engineer target job description
└── tests/
    ├── test-01.md                    # Scenario 1 (Junior Career Pivot) & Scenario 2 (Senior Tech Lead)
    ├── test-02.md                    # Scenario 3 (ATS Layout Trap), Scenario 4 (Duty List), Scenario 5 (Keyword Stuffed)
    └── expected-results.md           # Test assertions, expected rubrics, and pass criteria
```

---

## ⚡ Core Capabilities

1. **The 6-Second Screen Audit**: Evaluates visual hierarchy, scan velocity, and immediate value delivery based on technical recruiter eye-tracking behavior.
2. **ATS-Style Readability Analysis**: Audits resumes against parsing engines (Greenhouse, Workday, Lever, iCIMS, Taleo) to flag multi-column traps, header/footer data loss, non-standard section titles, and graphical progress bar errors.
3. **Resume-to-Job-Description Gap Analysis**: Cross-examines candidate qualifications against target job requirements, mapping direct matches, transferable skills, and disqualifying gaps.
4. **Google XYZ & STAR Bullet Rewriter**: Transforms weak, passive duty statements (*"Responsible for writing unit tests"*) into measurable engineering achievements (*"Engineered automated test suite using Jest, boosting code coverage from 55% to 88% and cutting regression bugs by 30%"*).
5. **Interview Vulnerability Generator**: Pinpoints ambiguous claims, inflated buzzwords, and technical gaps, generating tough behavioral and architectural questions hiring managers will ask.
6. **Zero-Hallucination Guarantee**: Strictly forbids fabricating candidate metrics, years of experience, or titles. All rewritten bullets preserve verified facts and provide bracketed placeholders (`[X%, Y ms, Z scale]`) for user-verified numbers.

---

## 📋 Standard 9-Section Evaluation Output Schema

Every evaluation delivered by the RESUME ROAST skill strictly adheres to the following structured format:

```
1. Overall Assessment
   ├── Scorecard (Impact, ATS Readability, Role Match, Clarity)
   └── Executive Verdict (Brutally honest 2-3 paragraph summary)
2. Strong Points (3-5 verified competitive strengths)
3. Weak Points & Red Flags (4-6 categorized issues with recruiter perspectives)
4. ATS-Style Readability Observations (Structural & parsing risks)
5. Job Description Match Analysis (Must-Haves Table, Keywords, Seniority fit)
6. Missing or Weak Skills (Explicit gaps vs superficial mentions)
7. Improved Resume Bullet Suggestions (Original -> Critique -> XYZ Rewrite -> Strategy)
8. Interview Preparation Questions (5 high-conviction technical & trade-off probes)
9. Priority Action Plan (Phase 1: <1 hr triage, Phase 2: Overhaul, Phase 3: Defense)
```

---

## 🚀 Installation & Setup

### Option A: Google Antigravity & Agentic Coding Assistants
1. Copy or clone this directory into your agent skills path:
   ```bash
   # Custom skill directory
   cp -r resume-roast /path/to/antigravity/skills/resume-roast
   ```
2. The agent will automatically detect `SKILL.md` via its YAML frontmatter metadata.

### Option B: Claude Code / Anthropic Agent Ecosystem
1. Place the `resume-roast` folder in your project's `.claude/skills/` or active workspace.
2. In your prompt, invoke the skill:
   ```text
   Review this resume using the resume-roast skill.
   ```

### Option C: Standalone Agent / Custom LLM System Prompt
If using a custom script, OpenAI Assistant, or Cursor Rule:
1. Load `SKILL.md` as the core system prompt instructions.
2. Provide `references/resume-review-guide.md` and `references/ats-checklist.md` as context or tool resources.

---

## 💡 How to Use the Skill

### 1. General Resume Roast (Without a Job Description)
Provide the candidate's resume text:

```markdown
Please roast my resume:

[Paste Resume Text]
```
> **Agent Behavior**: The agent will conduct a full 9-section evaluation focusing on market competitiveness, ATS safety, impact quantification, and bullet rewrites. In Section 5, it will prompt you to provide a target Job Description for tailored matching.

### 2. Targeted Job Description Alignment Roast (Recommended)
Provide both the resume and the target job description:

```markdown
Please review my resume against this job posting:

--- RESUME ---
[Paste Resume Text]

--- JOB DESCRIPTION ---
[Paste Target Job Description]
```
> **Agent Behavior**: The agent will cross-examine every requirement, highlight exact keyword matches vs missing skills, calibrate your seniority, and rewrite bullets specifically targeting the employer's domain.

---

## 🧪 Testing & Validation Suite

The skill includes **5 comprehensive test scenarios** located in the `tests/` directory:

| Test File | Scenario | Archetype / Test Case | Primary Diagnostic Focus |
|---|---|---|---|
| `tests/test-01.md` | **Scenario 1** | Junior Career Changer (Maya Lin) | Transferable skill framing, unquantified bootcamp capstones |
| `tests/test-01.md` | **Scenario 2** | Senior Tech Lead (Marcus Vance) | Buzzword inflation, missing architectural scale & throughput metrics |
| `tests/test-02.md` | **Scenario 3** | Fatal ATS Parsing Trap (Jordan Blake) | 2-column layouts, header contact loss, skill progress bars |
| `tests/test-02.md` | **Scenario 4** | Fluffy Duty-List Resume (David Kim) | 100% passive "responsible for" bullets, zero business impact |
| `tests/test-02.md` | **Scenario 5** | Keyword-Stuffed Mismatch (Priya Patel) | GenAI keyword stuffing vs core systems database engineering |

### Validating Skill Outputs
Review the test assertions and evaluation rubrics in [`tests/expected-results.md`](file:///C:/Users/KGCAS/.gemini/antigravity/scratch/resume-roast/tests/expected-results.md) to benchmark agent responses against expected scorecards, red flags, and bullet rewrites.

---

## 🔒 Ethical Guidelines & Anti-Hallucination Policy

1. **No Fabricated Data**: RESUME ROAST will never generate synthetic numbers or fake metrics to make a bullet sound better. It provides the structured template with explicit placeholder brackets (`[X%]`, `[Y ms]`) that candidates must populate with real data.
2. **No Guaranteed ATS Scores**: RESUME ROAST explains how parsers operate and identifies structural risks, but explicitly refuses to guarantee arbitrary numerical ATS match scores or interview invitations.
3. **Preservation of Candidate Voice**: Recommendations respect the candidate's authentic career trajectory while systematically removing passive voice, jargon, and visual clutter.
