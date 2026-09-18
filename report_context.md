# Seminar Report Master Guidelines and Engineering Standards

> **Document:** `report_context.md`  
> **Purpose:** Reusable master template, structural guidelines and strict faculty formatting standards for engineering seminar reports (e.g., KTU CSQ413 Seminar Report and similar degree curricula).  
> **Applicability:** Generalized for any student, faculty panel, department or technical research paper.

---

## 1. Core Principles & Literature Grounding

### A. Majority of Content Grounded in the Base Paper
- The report must be fundamentally rooted in a single high-quality, peer-reviewed primary research paper (the "Base Paper").
- At least 70% to 80% of technical descriptions, diagrams, system architectures, mathematical formulations, experimental tables, ablation findings and discussion points must originate directly from the base paper.
- Extraneous filler text, generic textbook definitions and off-topic discussions must be avoided.

### B. Standard Five-Chapter Architecture Matching the Base Paper
All technical seminar reports must adopt the five numbered major chapters that directly reflect scientific paper divisions:
1. `\chapter{Introduction}`: Background, commercial significance, limitations of existing technologies, comprehensive literature review of related studies, comparative literature summary table, research gaps, problem statement, research objectives and document organization.
2. `\chapter{Materials and Methods}` (or `\chapter{Proposed Methodology}`): Experimental hardware, data acquisition and dataset characteristics, baseline architecture, proposed architectural/algorithmic modifications, mathematical formulations, dynamic loss functions, decision logic, training protocol and quantitative evaluation metrics.
3. `\chapter{Results and Analysis}`: Systematic ablation experiments, computational complexity analysis (parameters, FLOPs, model footprint), benchmark comparisons against baseline and mainstream competitive models, precision-recall/convergence curves, qualitative visual results and live/field testing.
4. `\chapter{Discussion}`: Speed versus accuracy trade-offs, environmental and operational robustness, domain adaptability, failure modes/edge cases, edge computing integration and industrial practicalities.
5. `\chapter{Conclusion}`: Strictly written in continuous prose paragraphs (no bullet points or numbered lists allowed) summarizing key findings and exact quantitative metrics; no practical limitations section; future scope section retaining only the explicit future research directions identified in the base paper.
- `\chapter*{References}`: Unnumbered chapter in the document and listed as an unnumbered entry in the Table of Contents.

---

## 2. Universal Formatting & Stylistic Rules

These stylistic constraints must be enforced across all generated reports:

### A. Zero Em Dashes
- **Rule:** Never use em dashes (`---`, `—`, or `\textemdash`) anywhere in the document.
- **Enforcement:** Use single standard ASCII hyphens (`-`) exclusively for parenthetical breaks, ranges and hyphenated terms.

### B. Zero Oxford Punctuation
- **Rule:** Never use Oxford commas or Oxford ampersands (`, and` or `, &`).
- **Enforcement:** Use ` and` without a preceding comma across all prose, author lists, committee acknowledgements, item enumerations and bibliography entries.

### C. Always Edit Files Directly on Disk
- **Rule:** Always inspect and edit files directly on disk.
- **Enforcement:** Never overwrite or revert independent modifications made by the user. Apply surgical, targeted edits.

### D. Target Length and Density
- **Rule:** The document must compile to strictly **30 to 35 pages**.
- **Source Target:** Approximately 1,150 to 1,250 LaTeX source lines (~72 KB to 78 KB single-file document).

---

## 3. Front Matter & Page Layout Standards

### 1. Title Pages (First Cover & Second Title Page)
- **Title Block Layout:** Break long titles into 3 or 4 balanced, semantically coherent lines with 1.5 line spacing (`\fontsize{14}{21}\selectfont\bfseries`):
  ```latex
  {\fontsize{14}{21}\selectfont\bfseries
  <MAIN TITLE LINE 1>\\
  <MAIN TITLE LINE 2>\\
  <MAIN TITLE LINE 3>\\
  <MAIN TITLE LINE 4>}\par
  ```
- **Line Balance:** Ensure words never wrap onto an isolated line. Symmetrically balance line widths.
- **Vertical Spacing:** Standardize vertical skips symmetrically between the outer cover page and inner title page.

### 2. Certificate Page
- **Vertical Clearance before Signatures:** Insert generous vertical spacing (`\vspace{2.0cm}`) between the university certification paragraph and the `Guide Co-ordinator HoD` table header.
- **Signature Clearance:** Allocate `1.6cm` of blank vertical space (`\\[1.6cm]`) between the `Guide` / `Co-ordinator` / `HoD` headers and the faculty names for physical signatures.
- **Symmetric Spacing:** Balance the vertical distance between names and designations (`\\[0.15cm]`) to match the distance between designations and department (`\\[0.15cm]`).
- **Department Naming:** Format department text consistently across all three columns:
  ```latex
  \parbox[t]{4.4cm}{\centering Dept. of <Department Name>\\\& Engineering}
  ```
- **Template Layout:**
  ```latex
  \vspace{2.0cm}
  \begin{center}
  \begin{tabular}{@{}c@{\hspace{0.4cm}}c@{\hspace{0.4cm}}c@{}}
  \textbf{Guide} & \textbf{Co-ordinator} & \textbf{HoD}\\[1.6cm]

  <Guide Name> & <Coordinator Name> & <HoD Name>\\[0.15cm]

  <Guide Designation> & <Coordinator Designation> & <HoD Designation>\\[0.15cm]

  \parbox[t]{4.4cm}{\centering Dept. of <Department Name>\\\& Engineering} &
  \parbox[t]{4.4cm}{\centering Dept. of <Department Name>\\\& Engineering} &
  \parbox[t]{4.4cm}{\centering Dept. of <Department Name>\\\& Engineering}
  \end{tabular}
  \end{center}
  ```

### 3. Acknowledgement Page
- **Coordinator Format:** List all seminar coordinators with designations and departments with strictly NO Oxford comma:
  > `...<Coordinator 1>, <Designation>, <Department>, <Coordinator 2>, <Designation>, <Department> and <Coordinator 3>, <Designation>, <Department> for their valuable coordination and guidance...`

### 4. Page Numbering Protocol
- **Cover Pages and Certificate:** Unnumbered (`\thispagestyle{empty}`).
- **Front Matter (Roman Numerals):** Roman numeral numbering begins at Acknowledgement:
  ```latex
  \pagenumbering{roman}
  \setcounter{page}{1}
  ```
  Sequence:
  - Page `i`: Acknowledgement
  - Page `ii`: Abstract
  - Page `iii` (and `iv` if multi-page): Contents
  - Next Page: List of Figures
  - Next Page: List of Tables
- **Main Body (Arabic Numerals):** Arabic numbering starts at Chapter 1:
  ```latex
  \pagenumbering{arabic}
  \setcounter{page}{1}
  ```

### 5. Table of Contents (TOC) Standards
- **Prominent Title:** Enlarge the Contents title to 24pt bold using `\cfttoctitlefont` in `tocloft`.
- **CRITICAL Header Bleed Prevention:** Never redefine `\contentsname` with font sizing commands (such as `\fontsize{24}{28}`). LaTeX's `\tableofcontents` automatically injects `\contentsname` into the running header (`\leftmark`). Adding font sizes to `\contentsname` causes the header on subsequent pages to blow up into a giant 24pt header. Instead, keep `\contentsname` as plain text and style the title via `tocloft`:
  ```latex
  \setlength{\cftbeforetoctitleskip}{-0.5cm}
  \setlength{\cftaftertoctitleskip}{0.8cm}

  \renewcommand{\cfttoctitlefont}{\hfill\fontsize{24}{28}\selectfont\bfseries}
  \renewcommand{\cftaftertoctitle}{\hfill}
  ```
- **TOC Exclusions:** Exclude Abstract, List of Figures and List of Tables from the Table of Contents using `\usepackage[nottoc,notlof,notlot]{tocbibind}` without calling `\addcontentsline`.
- **References in TOC and Running Header:** References must be an unnumbered chapter and an unnumbered entry in the TOC. Crucially, explicitly call `\markboth{References}{}` immediately after `\chapter*{References}` so that the running header (`\leftmark`) updates to `References` instead of carrying over the previous chapter's title (such as `Conclusion`):
  ```latex
  \chapter*{References}
  \markboth{References}{}
  \addcontentsline{toc}{chapter}{References}
  ```

### 6. List of Figures & List of Tables Uniform Spacing and Large Titles
- **The Problem:** Standard LaTeX `report.cls` and `titlesec` automatically inject `\addvspace{10\p@}` between chapters into `.lof` and `.lot`, creating awkward vertical gaps between figures/tables of different chapters (e.g. between Figure 2.X and 3.1, or between Table 1.1, 2.X and 3.1). Additionally, standard `\chapter*` titles render at only 16pt.
- **The Solution:**
  1. In the preamble, neutralize `\ttl@addvspace` and `\@chapter` spacing hooks:
     ```latex
     \makeatletter
     \def\ttl@addvspace#1#2{}
     \patchcmd{\@chapter}{\addtocontents{lof}{\protect\addvspace{10\p@}}}{}{}{}
     \patchcmd{\@chapter}{\addtocontents{lot}{\protect\addvspace{10\p@}}}{}{}{}
     \makeatother
     ```
  2. Manually format the List of Figures and List of Tables pages using `\l@figure` and `\l@table` with `\numberline` and `\pageref`, with prominent 24pt bold centered titles:
     ```latex
     %=========================================================
     % LIST OF FIGURES
     %=========================================================
     \clearpage
     \markboth{List of Figures}{}
     \thispagestyle{fancy}

     \vspace*{-0.5cm}
     {\centering\fontsize{24}{28}\selectfont\bfseries List of Figures\par}
     \vspace{0.8cm}

     \makeatletter
     \l@figure{\numberline{<Chapter>.<Index>}{<Figure Caption Text>}}{\pageref{<fig:label>}}
     ...
     \makeatother
     \clearpage
     ```
     ```latex
     %=========================================================
     % LIST OF TABLES
     %=========================================================
     \clearpage
     \markboth{List of Tables}{}
     \thispagestyle{fancy}

     \vspace*{-0.5cm}
     {\centering\fontsize{24}{28}\selectfont\bfseries List of Tables\par}
     \vspace{0.8cm}

     \makeatletter
     \l@table{\numberline{<Chapter>.<Index>}{<Table Caption Text>}}{\pageref{<tab:label>}}
     ...
     \makeatother
     \clearpage
     ```
  3. This eliminates auxiliary file caching lag and guarantees 100% uniform line spacing across the entire list.

---

## 4. Content Formatting Standards

### 1. Table Formatting
- **Vertical Rules Mandatory:** All data tables must include vertical borders on every column boundary and outer edges (`|c|c|...|` or `|p{...}|...|`).
- **Horizontal Rules:** Use standard horizontal `\hline` rules (top, bottom and separating header from data rows).
- **No Borderless Tables:** Borderless booktabs styles (`\toprule`, `\midrule`, `\bottomrule` without vertical lines) are strictly disallowed by faculty review panels.

### 2. Figure Sizing
- Key architectural diagrams, experimental setups, training pipelines and performance comparison graphs must be sized prominently to ensure legibility, typically `0.90\textwidth` to `0.95\textwidth`.
- Captions must be placed beneath figures with clean descriptive text.

### 3. Chapter 5: Conclusion & Future Scope
- **Chapter Title:** `\chapter{Conclusion}` (never use "Conclusion and Future Scope").
- **Conclusion Section:** Written strictly in continuous **prose paragraphs** without bullet points or numbered lists. Preserve all exact technical metrics and findings from the base paper.
- **Practical Limitations:** Do not include a practical limitations section.
- **Future Scope Section:** Retain only the specific future research directions explicitly stated in the base paper.

---

## 5. Automated Python Verification Test Suite

Before submitting or approving any seminar report LaTeX code, execute this automated Python verification script on the target `main.tex` to ensure full compliance:

```python
import re
import sys

def verify_seminar_report(tex_path):
    with open(tex_path, "r", encoding="utf-8") as f:
        text = f.read()

    errors = []

    # 1. Zero Em Dashes
    if text.count("---") > 0:
        errors.append("Found em dash '---'")
    if text.count("\u2014") > 0:
        errors.append("Found unicode em dash")
    if text.count(r"\textemdash") > 0:
        errors.append("Found \\textemdash")

    # 2. Zero Oxford Commas
    oxford = list(re.finditer(r",\s+(?:and|&)\b", text, re.IGNORECASE))
    if len(oxford) > 0:
        errors.append(f"Found {len(oxford)} Oxford comma(s): {[m.group(0) for m in oxford[:3]]}")

    # 3. Vertical Rules in All Data Tables
    tabulars = re.findall(r"\\begin\{tabular\}(.+)", text)
    for t in tabulars:
        if "@{" in t:
            continue  # layout/signature block table
        if "|" not in t:
            errors.append(f"Table missing vertical rule: {t.strip()}")

    # 4. Five Major Numbered Chapters
    chapters = re.findall(r"\\chapter\{([^}]+)\}", text)
    expected_chapters = [
        "Introduction",
        "Materials and Methods",
        "Results and Analysis",
        "Discussion",
        "Conclusion"
    ]
    # Allow alternative for Chapter 2
    if len(chapters) == 5:
        if chapters[0] != "Introduction":
            errors.append(f"Chapter 1 should be 'Introduction', got '{chapters[0]}'")
        if chapters[1] not in ["Materials and Methods", "Proposed Methodology"]:
            errors.append(f"Chapter 2 should be 'Materials and Methods' or 'Proposed Methodology', got '{chapters[1]}'")
        if chapters[2] != "Results and Analysis":
            errors.append(f"Chapter 3 should be 'Results and Analysis', got '{chapters[2]}'")
        if chapters[3] != "Discussion":
            errors.append(f"Chapter 4 should be 'Discussion', got '{chapters[3]}'")
        if chapters[4] != "Conclusion":
            errors.append(f"Chapter 5 should be 'Conclusion', got '{chapters[4]}'")
    else:
        errors.append(f"Expected exactly 5 chapters, found {len(chapters)}: {chapters}")

    # 5. Environment Balance
    envs = ["document", "titlepage", "center", "tabular", "figure", "table", "enumerate", "itemize"]
    for env in envs:
        b = len(re.findall(r"\\begin\{" + env + r"\}", text))
        e = len(re.findall(r"\\end\{" + env + r"\}", text))
        if b != e:
            errors.append(f"Mismatched environment '{env}': {b} begins vs {e} ends")

    # 6. Check for Header Font Bleed Prevention
    if "\\contentsname" in text:
        idx = text.find("\\contentsname")
        snippet = text[idx:idx+60]
        if "\\fontsize" in snippet:
            errors.append(f"Font size found in \\contentsname (will bleed into headers): {snippet}")

    # 7. Check for Enlarged Titles
    if "List of Figures" in text:
        if not re.search(r"\\fontsize\{2[0-9]\}\{[0-9]+\}\\selectfont\\bfseries\s+List of Figures", text):
            errors.append("List of Figures title not enlarged to 20pt+ bold")
    if "List of Tables" in text:
        if not re.search(r"\\fontsize\{2[0-9]\}\{[0-9]+\}\\selectfont\\bfseries\s+List of Tables", text):
            errors.append("List of Tables title not enlarged to 20pt+ bold")

    # 8. Check References Header Mark
    if "\\chapter*{References}" in text:
        ref_idx = text.find("\\chapter*{References}")
        ref_block = text[ref_idx:ref_idx+120]
        if "\\markboth{References}{}" not in ref_block:
            errors.append("References chapter missing \\markboth{References}{} (running header will display previous chapter name)")

    if errors:
        print(f"VERIFICATION FAILED WITH {len(errors)} ERROR(S):")
        for err in errors:
            print(f"  - {err}")
        return False
    else:
        print("ALL MASTER SEMINAR REPORT STANDARDS VALIDATED SUCCESSFULLY!")
        return True

if __name__ == "__main__":
    path = sys.argv[1] if len(sys.argv) > 1 else "main.tex"
    success = verify_seminar_report(path)
    sys.exit(0 if success else 1)
```
