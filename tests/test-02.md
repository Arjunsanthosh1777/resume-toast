# Test Suite 02: Advanced Edge Cases & Parser Failures

This file contains three diagnostic evaluation scenarios designed to test the **RESUME ROAST** skill's ATS parser auditing, duty-vs-impact transformation, and keyword-stuffing detection.

---

## Scenario 3: The Fatal ATS Formatting & Parsing Trap

### Candidate Context:
- **Candidate**: Jordan Blake
- **Target Role**: Mid-Level Frontend Engineer
- **Format**: Created using a graphic Canva template with a 2-column sidebar, contact info in Word headers, circular skill bars, and creative section titles.

### Input Resume:

```markdown
[HEADER REGION - Dropped by many ATS parsers]
Jordan Blake • Phone: (555) 441-2093 • Email: jordan.blake.ux@email.com • SF, CA

[SIDEBAR COLUMN - Left 30%]
WHERE I EXCEL:
★ JavaScript [████████░░] 80%
★ React [█████████░] 90%
★ CSS3 / HTML5 [██████████] 100%
★ TypeScript [██████░░░░] 60%
★ Node.js [█████░░░░░] 50%

EDUCATION:
B.A. Graphic Design & Minor in CS, SF State, 2019

MY TOOLBOX:
Figma, Webpack, Babel, Redux, Sass, Git, Adobe XD

[MAIN BODY COLUMN - Right 70%]
MY PROFESSIONAL JOURNEY:

Product Frontend Specialist | PixelForge Studios
2021 – Present
- Transformed design mocks into pixel-perfect web interfaces using React and Sass.
- Collaborated with UI/UX designers to implement dynamic animations and transitions.
- Contributed to the internal component library used by 4 frontend developers.
- Participated in weekly design critiques and sprint grooming sessions.

Web Designer & Developer | Apex Creative Labs
2019 – 2021
- Created custom WordPress and Shopify themes for local retail clients.
- Implemented responsive mobile layouts and cross-browser testing.
- Handled client requests for website updates and content refreshes.
```

---

## Scenario 4: The Fluffy & Impactless Duty-List Resume

### Candidate Context:
- **Candidate**: David Kim
- **Target Role**: Backend Software Engineer
- **Challenge**: Every single bullet point begins with passive duty phrases ("Responsible for", "Worked on", "Helped with", "Participated in"). There are zero quantifiable metrics or architectural explanations.

### Input Resume:

```markdown
David Kim
Chicago, IL | (555) 912-3482 | david.kim.backend@email.com | github.com/dkim-backend

SUMMARY
Backend engineer with 3 years of experience specializing in Python and API development. Looking to contribute to a growing engineering team.

SKILLS
Python, Django, FastAPI, PostgreSQL, Docker, AWS, Git, REST APIs, Celery

WORK EXPERIENCE

Software Engineer | FinEdge Technologies | Chicago, IL
January 2022 – Present
- Responsible for maintaining the company's core payment processing microservices.
- Worked on optimizing backend database queries to make things faster.
- Helped the team migrate legacy code from Django to FastAPI.
- Participated in writing unit tests to improve code coverage.
- Assisted with deploying Docker containers to AWS ECS.
- Attended daily scrum meetings, reviewed peer pull requests, and resolved Jira tickets.

Associate Developer | NorthBridge Solutions | Chicago, IL
May 2020 – December 2021
- Responsible for writing REST API endpoints using Python and Flask.
- Worked with the database administrator to update SQL tables.
- Helped fix bugs reported by the QA testing team prior to releases.
- Participated in team code reviews and updated API documentation.

EDUCATION
B.S. in Information Technology | University of Illinois at Chicago (2020)
```

---

## Scenario 5: The Keyword-Stuffed Mismatch

### Candidate Context:
- **Candidate**: Priya Patel
- **Target Role**: Senior Systems & Database Infrastructure Engineer (High-throughput C++, Rust, PostgreSQL internal storage engines)
- **Challenge**: The candidate dumped every trending tech buzzword (LLMs, GenAI, LangChain, PyTorch, Kubernetes) into the resume, but the target role requires low-level systems programming, lock contention optimization, and memory management.

### Input Resume:

```markdown
Priya Patel
New York, NY | priya.patel.tech@email.com | (555) 678-9012 | github.com/priyapatel-eng

PROFESSIONAL SUMMARY
Senior Distributed Systems Engineer with expertise in AI/ML, LLMs, GenAI, LangChain, Kubernetes, Rust, C++, Python, PostgreSQL, Kafka, and Deep Learning. Passionate about leveraging cutting-edge Generative AI and neural networks to transform database systems and enterprise infrastructure.

SKILLS
Languages: C++, Rust, Python, Go, SQL, Solidity
Cloud & DevOps: Docker, Kubernetes, Terraform, AWS, Helm, CI/CD
AI & Data: PyTorch, TensorFlow, LangChain, LlamaIndex, OpenAI API, HuggingFace, Vector DBs, Pinecone, Milvus, ChromaDB, Kafka, PostgreSQL, Redis, Cassandra

EXPERIENCE

Software Engineer | DataSynth AI | New York, NY
March 2022 – Present
- Implemented generative AI pipelines using LangChain and OpenAI APIs to automate document indexing.
- Experimented with fine-tuning open-source LLMs using PyTorch and HuggingFace.
- Built a vector search prototype using Pinecone and FastAPI.
- Maintained PostgreSQL database tables for storing user prompt history.
- Wrote Dockerfiles and deployed services using Kubernetes manifests.

Application Developer | Quantex Systems | New York, NY
June 2020 – February 2022
- Developed Python backend endpoints for internal analytics tools.
- Wrote SQL scripts to generate monthly business intelligence reports.
- Participated in testing and deploying software updates to AWS EC2.

EDUCATION
B.S. in Computer Science | Columbia University (2020)
```
