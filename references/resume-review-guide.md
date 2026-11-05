# Resume Review Guide & Evaluation Framework

This guide provides the diagnostic methodology, scoring rubrics, and bullet-point rewriting formulas used by the **RESUME ROAST** agent skill.

---

## 1. The 6-Second Screen Test

Eye-tracking studies by talent research firms show that technical and executive recruiters spend an average of **6 to 7.4 seconds** on an initial resume screen.

### Recruiter Eye Path & Visual Hierarchy
1. **Name & Current Title / Professional Identity** (Top center or top left).
2. **Current / Most Recent Company & Dates** (Title progression, employment longevity).
3. **Previous Company & Dates** (Career arc, upward trajectory).
4. **First 2 Bullet Points of Most Recent Role** (Scale, scope, high-impact metrics).
5. **Core Technical Stack / Skills Summary** (Baseline stack alignment).
6. **Education & Certifications** (Checkboxes for degree requirements).

### 6-Second Failures
- **The Visual Maze**: Multi-column layouts that force horizontal zig-zag reading.
- **The Wall of Text**: Paragraph blocks longer than 3 lines without bolding or bullet points.
- **Hidden Punchlines**: Burying the outcome at the end of a 4-line bullet point.
- **Missing Tech Context**: Stating "Built microservices" without mentioning language, framework, database, or cloud infrastructure.

---

## 2. Bullet-Point Construction Frameworks

Every resume bullet must answer three fundamental questions:
1. *What did you build or improve?*
2. *How did you do it (tools, architecture, methodology)?*
3. *What was the quantifiable business or engineering impact?*

---

### Formula A: The Google XYZ Formula
Developed by Laszlo Bock (Former SVP of People Operations at Google):

$$\text{Accomplished [X]}, \text{ as measured by [Y]}, \text{ by doing [Z]}$$

- **X (The Accomplishment)**: The tangible deliverable, feature, or outcome.
- **Y (The Measurable Metric)**: Percentage, time, currency, throughput, or error reduction.
- **Z (The Methodology/Action)**: The specific technologies, algorithms, architectural patterns, or processes utilized.

#### Examples:
- ❌ *Weak*: "Responsible for making database queries faster."
- ✅ *Google XYZ Rewrite*: "Optimized PostgreSQL customer order query performance, **reducing p99 API latency by 42% (from 850ms to 490ms)**, by redesigning composite indexes and implementing Redis query-level caching."
- ❌ *Weak*: "Helped onboard junior engineers."
- ✅ *Google XYZ Rewrite*: "Accelerated engineering team velocity by **slashing new hire onboarding ramp time from 4 weeks to 9 days**, through the creation of an automated Docker development environment and end-to-end documentation."

---

### Formula B: The Compressed STAR Method
Adapted from behavioral interviews for high-density resume bullets:

$$\text{[Strong Action Verb]} + \text{[Context / Problem]} + \text{[Technical Solution]} + \text{[Business Impact]}$$

- **Verb**: *Architected, Spearheaded, Refactored, Accelerated, Decoupled, Orchestrated*.
- **Problem**: Legacy monolith bottleneck, manual deployment failure rate, customer churn.
- **Solution**: Event-driven architecture, CI/CD pipeline, automated testing suite.
- **Impact**: Dollar savings, operational time reclaimed, uptime SLA achievement.

---

## 3. The Action Verb Taxonomy

Replace passive, duty-focused verbs with high-agency verbs categorized by outcome:

| Category | Forbidden Verbs (Passive) | Power Verbs (High Agency) |
|---|---|---|
| **Architecture & Creation** | *Worked on, helped build, participated in, made* | Architected, Engineered, Designed, Fabricated, Prototyped, Deployed |
| **Optimization & Speed** | *Tried to improve, sped up, cleaned up* | Accelerated, Optimized, Streamlined, Truncated, Refactored, Scaled |
| **Leadership & Direction** | *Managed meetings, was responsible for team* | Spearheaded, Chaired, Mentored, Orchestrated, Mobilized, Standardized |
| **Cost & Efficiency** | *Saved money, cut budget* | Slashed, Eliminated, Consolidated, Reclaimed, Monetized |
| **Quality & Reliability** | *Tested stuff, fixed bugs* | Fortified, Mitigated, Audited, Automated, Stabilized, Resolved |

---

## 4. Metric Identification Matrix

When candidates say *"My work wasn't tied to numbers,"* probe them across these 6 engineering and business metric categories:

```
┌────────────────────────────────────────────────────────┐
│             SIX UNIVERSAL METRIC CATEGORIES            │
├────────────────────┬───────────────────────────────────┤
│ 1. Latency & Time  │ p95/p99 latency, build time, TTFB │
│ 2. Cost & Capital  │ AWS/GCP bill reduction, tooling $ │
│ 3. Throughput      │ RPS, TPS, concurrent users, DAU  │
│ 4. Reliability     │ Uptime SLA (99.99%), MTTR, bugs   │
│ 5. Scale & Size    │ Data volume (TB/PB), cluster size │
│ 6. People & Ramp   │ Engineers hired, ramp days, hours │
└────────────────────┴───────────────────────────────────┘
```

---

## 5. Professional Summary Refactoring (The 3-Sentence Rule)

Avoid generic objectives like: *"Ambitious software engineer looking to leverage my skills at an innovative company."*

Use the **3-Sentence Value Proposition Formula**:
- **Sentence 1 (Identity & Scale)**: Current title, years of experience, core technical stack, and scale handled.
- **Sentence 2 (Signature Achievement)**: The single most impressive career accomplishment with verified metric.
- **Sentence 3 (Target Value)**: The exact engineering domain you specialize in delivering for the prospective employer.

#### Example:
> *"Staff Distributed Systems Engineer with 8+ years architecting high-throughput Go and Kubernetes microservices handling 250M+ daily events. Spearheaded a global data migration that cut cloud infrastructure costs by \$1.4M annually while maintaining 99.995% uptime. Specializes in asynchronous event pipelines, distributed database replication, and zero-downtime reliability engineering."*

---

## 6. Red Flags and Anti-Patterns

1. **The Keyword Soup**:
   - Dumping 40 technologies into a "Skills" section (e.g., *C++, Java, Rust, Swift, PHP, Kubernetes, PyTorch, Hadoop*) when only 3 are mentioned in work experience bullets.
   - *Fix*: Group skills by proficiency (`Core / Production`, `Working Knowledge`, `Familiar / Academic`).

2. **The "Promoted to Customer" Gap**:
   - Listing jobs with overlapping dates or vague month-less years (`2021 - 2022`) that raise employment verification questions.
   - *Fix*: Always format dates consistently: `Month Year – Month Year` (e.g., `Mar 2022 – Present`).

3. **Self-Rating Charts**:
   - Progress bars or star ratings (e.g., *JavaScript: 4/5 stars* or *Python: 85%*).
   - *Reason for rejection*: Completely subjective, uninformative to hiring managers, and causes severe parsing errors in modern ATS software.
