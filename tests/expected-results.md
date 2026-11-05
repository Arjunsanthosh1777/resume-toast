# Test Suite Evaluation Rubric & Expected Results

This document establishes the validation benchmarks and testable assertions for the **RESUME ROAST** AI agent skill across all 5 evaluation scenarios.

---

## Universal Assertion Criteria (Must Pass for All Scenarios)

1. **Schema Compliance**: The response **MUST** contain all 9 numbered sections in exact sequence:
   1. Overall Assessment (Scorecard + Verdict)
   2. Strong Points
   3. Weak Points & Red Flags
   4. ATS-Style Readability Observations
   5. Job Description Match Analysis (or Seniority Calibration if no JD)
   6. Missing or Weak Skills
   7. Improved Resume Bullet Suggestions (with Google XYZ rewrites)
   8. Interview Preparation Questions
   9. Priority Action Plan
2. **Zero Hallucination Guarantee**: The agent **MUST NOT** fabricate metrics, company titles, or technologies. All rewrites requiring candidate numbers must use clear bracketed placeholders: `[e.g., cut latency by X%, from Y to Z]`.
3. **No False ATS Guarantees**: The agent **MUST NOT** make claims like *"This guarantees 100% ATS score."*
4. **Distinction Between Weakness vs Missing Data**: Missing GitHub, metrics, or team sizes must be categorized as *Missing Information*, while passive phrasing or typos must be categorized as *Actual Weaknesses*.

---

## Scenario 1 Benchmark: The Junior Career Changer (Maya Lin)

| Check | Metric / Target | Pass Condition |
|---|---|---|
| **Roast Scorecard** | Impact: 3-4/10, ATS: 7-8/10, Clarity: 5-6/10 | Accurately rates low impact due to unquantified bootcamp projects. |
| **Mandatory Red Flag Caught** | Objective Statement | Flags *"Seeking an entry-level developer role where I can learn from mentors..."* as candidate-centric rather than employer-centric. |
| **Transferable Skill Leverage** | Marketing Experience | Commends the 35% organic search increase in marketing, but advises reframing it around web analytics, conversion rates, and frontend technical SEO. |
| **Project Audit** | Generic Bootcamp Capstone | Flags `RecipeBox` and `BookTracker` as generic tutorial projects that signal bootcamp origin; advises adding real-world complexity (rate-limiting, testing, CI/CD). |
| **Bullet Rewrite Sample** | `RecipeBox` Authentication | Must transform *"Implemented user registration and login with passwords"* into a secure auth flow with bracketed placeholders: *"Architected secure user authentication system using JWT and bcrypt with salted password hashing, protecting [X] user accounts and establishing protected REST endpoints."* |
| **Interview Questions** | Security & State Management | Asks about token storage vulnerabilities (localStorage vs httpOnly cookies) and React re-render optimization in reading lists. |

---

## Scenario 2 Benchmark: The Senior Tech Lead (Marcus Vance)

| Check | Metric / Target | Pass Condition |
|---|---|---|
| **Roast Scorecard** | Impact: 3-5/10, ATS: 6-7/10, Seniority: 5/10 | Flags disparity between "12+ years Staff/Principal claim" and complete absence of architectural scale metrics. |
| **Mandatory Red Flag Caught** | Buzzword Inflation ("Synergy & Modernization") | Directly calls out *"Spearheaded the modernization of company's flagship platform..."* and *"Championed DevOps best practices"* as corporate fluff devoid of technical substance. |
| **Missing Architecture Depth** | Kafka / Microservices | Demands concrete numbers: How many messages/sec? How many microservices? What was the partition strategy? What was the p99 latency SLA? |
| **Date Ambiguity** | Year-only dates (`2019 – Present`) | Flags year-only formatting as ambiguous under employment verification audits. |
| **Bullet Rewrite Sample** | Kafka Architecture | Rewrites *"Architected cutting-edge event-driven streaming solutions using Apache Kafka and Spring Boot"* to: *"Architected distributed event-streaming pipeline utilizing Apache Kafka and Spring Boot, ingesting [X million] daily events across [Y] partitions with sub-[Z]ms latency and 99.99% uptime SLA."* |
| **Interview Questions** | Distributed Systems Trade-offs | Challenges candidate on Kafka consumer group rebalances, partition lag mitigation, and handling distributed transactions across microservices (Saga pattern vs 2PC). |

---

## Scenario 3 Benchmark: The Fatal ATS Parsing Trap (Jordan Blake)

| Check | Metric / Target | Pass Condition |
|---|---|---|
| **Roast Scorecard** | ATS Readability: 1-2/10 (Severe Failure) | Immediately identifies this resume as unparseable by major ATS systems. |
| **Mandatory Red Flag 1** | Header Contact Info | Flags that putting Name, Phone, and Email in the document header causes 80%+ of ATS parsers to drop contact information entirely. |
| **Mandatory Red Flag 2** | Two-Column Layout | Warns that left-to-right parser geometry will interleave sidebar skills with work history into scrambled strings. |
| **Mandatory Red Flag 3** | Graphical Skill Progress Bars | Condemns `★ React [█████████░] 90%` as unparseable graphic clutter that communicates zero objective proficiency. |
| **Mandatory Red Flag 4** | Non-Standard Headings | Flags *"Where I Excel"*, *"My Toolbox"*, and *"My Professional Journey"* as unmapped headers that cause data loss. |
| **Remedy Provided** | Layout Reconstruction | Provides explicit single-column, standard-heading (`Work Experience`, `Technical Skills`) refactoring template. |

---

## Scenario 4 Benchmark: The Fluffy & Impactless Duty List (David Kim)

| Check | Metric / Target | Pass Condition |
|---|---|---|
| **Roast Scorecard** | Impact & Quantification: 2-3/10 | Strictly penalizes resume where 100% of bullets begin with passive duty phrases. |
| **Mandatory Red Flag Caught** | Duty-Based Mindset | Flags that "Responsible for" describes job expectations, not personal accomplishments or engineering achievements. |
| **Zero Metric Problem** | Vague Optimization | Calls out *"Worked on optimizing backend database queries to make things faster"* as meaningless without stating *which queries*, *what optimization technique*, and *how many milliseconds were saved*. |
| **Bullet Rewrite Sample** | Django to FastAPI Migration | Transforms *"Helped the team migrate legacy code from Django to FastAPI"* to: *"Co-led architectural migration of core microservices from Django to FastAPI, decreasing asynchronous request latency by [X]% and boosting throughput from [Y] to [Z] req/sec by leveraging Pydantic and asyncpg."* |
| **Interview Questions** | Concurrency & Async | Asks why FastAPI was chosen over Django Ninja/Go, and how async database connection pooling was tuned under high concurrency. |

---

## Scenario 5 Benchmark: The Keyword-Stuffed Mismatch (Priya Patel)

| Check | Metric / Target | Pass Condition |
|---|---|---|
| **Roast Scorecard** | JD Alignment: 2-3/10 (Severe Misalignment) | Catches that candidate's experience is GenAI/wrapper-focused while target role is core low-level database systems. |
| **Mandatory Red Flag Caught** | Keyword Stuffing Disconnect | Calls out the contradiction between claiming "Senior Distributed Systems & Rust/C++ Engineer" and having zero production Rust/C++ work bullets (only Python, LangChain, and wrapper scripts). |
| **Credibility Risk** | "Toy" Projects vs Production | Explains that senior hiring managers will instantly disqualify a candidate claiming deep C++/Rust expertise when their actual daily work is basic prompt engineering and vector DB calls. |
| **Interview Questions** | Deep Systems Interrogation | Generates brutal systems questions (e.g., LSM-tree vs B-tree write amplification, WAL crash recovery protocols, memory-mapped I/O in C++) to demonstrate the candidate's immediate vulnerability if they enter an interview with this resume. |
| **Strategic Remedy** | Career Positioning Pivot | Recommends either tailoring strictly for GenAI Application Engineering roles, or adding substantive open-source systems contributions in Rust/C++ before claiming seniority. |
