# ATS (Applicant Tracking System) Readability Checklist

Applicant Tracking Systems (such as **Greenhouse, Workday, Lever, iCIMS, Taleo, and Ashby**) are used by over 98% of Fortune 500 companies and mid-to-large tech employers to ingest, parse, index, and filter candidate resumes.

This checklist provides the architectural requirements for parser-safe resume formatting.

---

## 1. How Modern ATS Parsers Process Resumes

When a PDF or DOCX is uploaded:
1. **Text Extraction**: The ATS strips visual styling and flattens the document into raw, unformatted text strings.
2. **Entity Extraction (Chunking)**: Machine learning models or rule-based parsers scan for standard anchor headers (`Experience`, `Education`, `Skills`) to segment data.
3. **Field Normalization**:
   - Dates are mapped to chronological career timelines.
   - Company names and job titles are matched against standardized taxonomy databases (e.g., O*NET, LinkedIn data dictionaries).
4. **Keyword & Semantic Search**: Recruiters search by exact skill keywords, boolean strings (`"Kubernetes" AND ("Go" OR "Golang")`), or semantic vector similarity.

---

## 2. The 10 Fatal ATS Parsing Traps

### ❌ Trap 1: Two-Column / Multi-Column Layouts
- **The Failure**: Most parsers read left-to-right across the entire page geometry before moving down. In a two-column layout, the parser will read Line 1 of Column 1 followed immediately by Line 1 of Column 2, mangling dates, titles, and bullet points into nonsensical gibberish.
- **The Fix**: Use a clean, **single-column** layout. Keep visual hierarchy linear.

### ❌ Trap 2: Storing Contact Information in Headers or Footers
- **The Failure**: To conserve page margins, candidates frequently place their Name, Email, Phone, and LinkedIn inside Microsoft Word or Google Docs document headers/footers. Many ATS extraction engines ignore headers/footers entirely to omit repeating page numbers, resulting in an "Anonymous Candidate" profile with no contact details.
- **The Fix**: Place contact information within the body text at the very top of the page.

### ❌ Trap 3: Tables and Floating Text Boxes
- **The Failure**: Visual builders (Canva, Photoshop, Figma, complex Word templates) use invisible table cells or floating text frames to position elements. Parsers frequently drop floating text boxes or scramble table rows.
- **The Fix**: Format with standard paragraph text, tabs, bulleted lists, and standard margin indentation.

### ❌ Trap 4: Non-Standard Section Titles
- **The Failure**: Creative titles confuse parsing models:
  - ❌ *"Where I've Created Magic"* -> ATS treats as unmapped text.
  - ❌ *"Toolbox & Arsenal"* -> ATS misses technical skills.
  - ❌ *"Credentials"* -> Ambiguous between education and licenses.
- **The Fix**: Use industry-standard canonical headings:
  - `Work Experience` or `Professional Experience`
  - `Education`
  - `Technical Skills`
  - `Projects`
  - `Certifications`

### ❌ Trap 5: Graphic Elements, Icons & Skill Progress Bars
- **The Failure**: Inserting a phone icon next to your number, a GitHub logo, or visual bar charts (*Python: 80%*) yields unparseable binary data, garbage Unicode characters, or dropped lines.
- **The Fix**: Replace icons with clear text labels: `Phone:`, `Email:`, `GitHub:`, `LinkedIn:`. List skills as categorized text.

### ❌ Trap 6: Date Format Ambiguity
- **The Failure**: Using non-standard date formats causes errors in calculating "Total Years of Experience":
  - ❌ `'21 - '23` (Could be days, months, or years).
  - ❌ `Winter 2022 – Fall 2023` (Seasonal dates are not universal).
  - ❌ `2022` (Ambiguous: 1 month or 12 months?).
- **The Fix**: Standardize to `MM/YYYY – MM/YYYY` or `Month YYYY – Month YYYY` (e.g., `03/2021 – 08/2023` or `Mar 2021 – Aug 2023`). Always write `Present` for current roles.

### ❌ Trap 7: Unselectable / Scanned PDF Text
- **The Failure**: Exporting a resume as an image-flattened PDF (rasterized PNG/JPEG) prevents text selection. The ATS sees a blank page of 0 words.
- **The Fix**: Test your PDF: Open it in any PDF viewer and press `Ctrl+A` / `Cmd+A` to select all text. Copy and paste into Notepad. If text pastes cleanly, the ATS can read it.

### ❌ Trap 8: Keyword Stuffing & "Invisible White Text"
- **The Failure**: Pasting blocks of keywords in white text at the bottom of the page or repeating "Python" 30 times. Modern parsers strip font color styles and expose the raw text directly in the recruiter's preview pane. When discovered, candidates are immediately blacklisted.
- **The Fix**: Integrate keywords naturally in context within work experience bullets and project descriptions.

### ❌ Trap 9: Unclean Font Selection
- **The Failure**: Using decorative, non-standard, or custom web fonts (e.g., downloaded TTF/OTF fonts) that lack standard Unicode glyph mappings causes characters like `fi`, `fl`, or dashes to parse as `?` or missing symbols.
- **The Fix**: Stick to universally recognized system fonts:
  - **Sans-Serif**: Arial, Calibri, Helvetica, Roboto, Segoe UI.
  - **Serif**: Georgia, Garamond, Times New Roman.

### ❌ Trap 10: Broken or Obfuscated Hyperlinks
- **The Failure**: Relying solely on raw 100-character URLs (`https://linkedin.com/in/john-doe-123491823/`) or ambiguous anchor text ("link") that fails when printed.
- **The Fix**: Use clean, descriptive anchor text with the real destination embedded, or short customized URLs (e.g., `linkedin.com/in/johndoe`, `github.com/johndoe`).

---

## 3. The 12-Point Pre-Flight ATS Verification Checklist

Before sending any resume into an ATS, verify every item below:

- [ ] **1. Single-Column Architecture**: Entire document flows in a single top-to-bottom column.
- [ ] **2. Body Contact Placement**: Name, phone, email, and location are in standard body text (not in header/footer).
- [ ] **3. Text Selectability**: Able to select, copy, and paste all text into Notepad without mangled characters.
- [ ] **4. Standard Section Headings**: Uses `Professional Experience`, `Education`, `Technical Skills`, `Projects`.
- [ ] **5. Canonical Date Format**: Formatted as `Mon YYYY – Mon YYYY` or `MM/YYYY – MM/YYYY`.
- [ ] **6. Zero Graphic Skill Gauges**: No progress bars, star ratings, or percentage meters.
- [ ] **7. Standard Bullet Characters**: Uses standard solid round bullets (`•`) or simple dashes (`-`).
- [ ] **8. Job Title Syntax Consistency**: `Job Title | Company Name | City, State | Mon YYYY – Mon YYYY`.
- [ ] **9. Acronym & Expanded Term Pairs**: Uses both acronym and full name at least once (e.g., *"Amazon Web Services (AWS)"*, *"Continuous Integration / Continuous Deployment (CI/CD)"*).
- [ ] **10. Safe Typography**: Clean system font between 10pt and 11.5pt for body; 13pt to 16pt for headings.
- [ ] **11. No Hidden Text**: All text is visible, high-contrast, black-on-white.
- [ ] **12. Correct File Extension**: Saved as `.pdf` (text-based) or `.docx`.
