# Context Handoff: Arjun Manoj B.Tech Seminar Presentation (CSQ413)

> **File:** `context.md`  
> **Last Updated:** September 10, 2026  
> **Workspace Directory:** `C:\Users\aravindanirudh\Downloads\Arjun Manoj Seminar Related`  
> **Primary File Under Maintenance:** `Arjun_Seminar_Presentation/main.tex`

---

## 1. Project & Presentation Metadata

- **Student:** ARJUN MANOJ (CEC23CS043)
- **Course:** CSQ413 Seminar Presentation (B.Tech Computer Science and Engineering)
- **Institution:** Department of Computer Science and Engineering, College of Engineering, Cherthala
- **Seminar Guide:** Mrs. NANDANA RAJ R (Assistant Professor)
- **Topic:** Real-Time Detection Method for Cracked Eggs Based on Improved YOLOv8 and Dual Verification With Triple Classification Granularity
- **Base Paper Reference:**  
  D. Sun, H. Wei, Y. Luo, W. Li and Y. Yu, *"Real-Time Detection Method for Cracked Eggs Based on Improved YOLOv8 and Dual Verification With Triple Classification Granularity,"* **IEEE Access**, vol. 14, pp. 62322-62333, 2026.
- **Base Paper PDF Location:**  
  `Seminar Abstract/Real-Time_Detection_Method_for_Cracked_Eggs_Based_on_Improved_YOLOv8_and_Dual_Verification_With_Triple_Classification_Granularity.pdf`

---

## 2. Strict Rules & Conventions Established with the User

Any future assistant or turn **MUST** adhere to these strict constraints:

1. **Always Edit `Arjun_Seminar_Presentation/main.tex` Directly on Disk:**
   - Always read from disk using file viewing tools before making modifications.
   - Do NOT rely on cached or in-memory copies. The user occasionally edits the file directly on disk.

2. **No Unauthorized Changes:**
   - Do **NOT** perform any changes or refactors not explicitly requested by the user.
   - Do not add arbitrary text, dates, extra slides, or change slide themes without permission.

3. **Strict Punctuation & Oxford Comma Rules:**
   - **NO Oxford commas:** The user intentionally and systematically removed Oxford punctuation across the entire document (e.g., changed `, and` to ` and` in author lists, series of items, etc.). **NEVER** re-introduce Oxford commas.
   - **NO Em dashes (`-`) or En dashes (`-`):** Use standard single ASCII hyphens (`-`) only throughout the LaTeX document.

4. **Terminology Consistency:**
   - Use **"300 epochs"** consistently. Never use "iterations" for training duration.

5. **PowerShell Variable Expansion Warning:**
   - When running scripts or commands in Windows PowerShell via terminal, LaTeX math strings containing `$` (e.g. `$2.66`, `$10.17`, `$P_{real}$`) will be silently expanded/erased by PowerShell as environment variables. Always wrap commands in PowerShell verbatim here-strings (`@' ... '@`) or edit files directly via tool calls.

---

## 3. Current Slide Deck Architecture (`main.tex`)

The presentation contains **34 slides (frames)** using LaTeX Beamer (`\documentclass{beamer}`, `\usetheme{Madrid}`, default colortheme):

| Slide # | Section / Title | Key Contents / Visual Assets |
|---|---|---|
| **1** | Title Slide | Reduced title font (`\large`), presenter: `ARJUN MANOJ (CEC23CS043)`, guide: `Mrs. NANDANA RAJ R`, empty `\date{}`. |
| **2** | Outline | Beamer `\tableofcontents`. |
| **3** | Introduction | Industry breakage rate (3%), manual inspection bottlenecks, commercial risks. |
| **4** | Limitations of Existing Methods | Acoustic resonance, traditional computer vision (Otsu), existing deep learning limitations. |
| **5** | Research Objectives and Key Contributions | Primary objective + 3 core contributions (granularity, YOLOv8 structural enhancements, live deployment). |
| **6** | Literature Survey: Part 1 | 5-column table (`Paper, Author, Year`, `Methodology`, `Dataset`, `Result`, `Limitations`) covering Liang (2020), Datta (2019), Turkoglu (2021). |
| **7** | Literature Survey: Part 2 | 5-column table covering Botta (2022), Yin (2024), Huang (2023). |
| **8** | System Hardware and Conveying Mechanism | 6 parallel channels, 360 eggs/min throughput, 360-degree roller rotation, parallel CCD camera alignment. |
| **9** | Physical Conveying System | Full-slide Figure 1 (`figure1_egg_conveying_device.jpg`). |
| **10** | Machine Vision Setup | Full-slide Figure 2 (`figure2_machine_vision_system.jpg`). |
| **11** | Triple Classification Granularity | Diagram (`classificationCategories.png`): Class 1 (Intact), Class 2 (Cracked Egg), Class 3 (Damaged Area). |
| **12** | Improved YOLOv8 Pipeline Architecture | Enlarged Figure 3 left module (`figure3_improved_yolov8_architecture_1.jpg`). |
| **13** | Detailed Backbone and Neck Modules | Enlarged Figure 3 right module (`figure3_improved_yolov8_architecture_2.jpg`). |
| **14** | Deformable Convolution v2 (DCNv2) Module | Mathematical formulation ($y(p_0)$), modulation scalars ($\Delta m_k$), symbol definitions with spacing. |
| **15** | DCNv2 Sampling Comparison | Full-slide Figure 4 (`figure4_dcnv2_sampling_comparison.jpg`). |
| **16** | BiFPN Feature Fusion & Small Target Head | Multi-scale fusion ($P_2$ to $P_5$), weighted connections, Figure 5 (`figure5_fpn_panet_bifpn_structure.jpg`). |
| **17** | Wise-IoU v2 (WIoUv2) Dynamic Bounding Box Loss | Outlier degree $\beta$, non-monotonic focusing coefficient $r$, symbol definitions with spacing. |
| **18** | Dual Verification Mechanism | Joint decision rules: cracked if Class 2 OR Class 3 detected; intact only if Class 1 AND neither Class 2 nor 3. Formulas and symbol definitions. |
| **19** | Online Deployment Pipeline & Video Inference | Figure 6 (`figure6_training_schematic.jpg`). |
| **20** | Industrial Online Deployment and Testing | Figure 7 (`figure7_online_deployment_testing_1.jpg` and `figure7_online_deployment_testing_2.jpg`). |
| **21** | Evaluation Metrics | Formulations for Precision, Recall, mAP:0.5, FPS, FNR, and FPR with full symbol definitions. |
| **22** | Ablation Study: Impact of Proposed Components | Table 1 (ablation across 8 variants) + Table 2 (Model complexity: $2.66 \times 10^7$ params, 86.5 G FLOPs, 51.1 MB). |
| **23** | Comparative Experiments with Mainstream Detectors | Table 3 benchmark against Faster R-CNN, YOLOv5, YOLOv8 baseline, YOLOv11. |
| **24** | Model Precision-Recall Dynamics | Full-slide Figure 8 (`figure8_pr_curves_comparison.jpg`). |
| **25** | Static Detection Results | Full-slide Figure 9 (`figure9_detection_effects_comparison.jpg`). |
| **26** | Production Line Online Sorting Protocol | 60 frames/egg, multi-frame accumulation, continuous roller translation. |
| **27** | Factory Online Inspection Accuracy (FNR and FPR) | Tables 5 & 6: Baseline vs Proposed model across Class 1, 2, 3, plus Compound Dual Verification FNR ($5.52\% \times 19.19\% = 1.06\%$). |
| **28** | Production Line: Visual Detection Results | Full-slide Figure 10 (`figure10_production_line_detection.jpg`). |
| **29** | Production Line: Detection Speed Stability | Full-slide Figure 11 (`figure11_online_detection_speed.jpg`). |
| **30** | Discussion: Operational Findings and Edge Cases | Speed vs accuracy trade-off (45 FPS vs 52 FPS), surface adaptability, duck eggs vs quail eggs, reticular micro-cracks. |
| **31** | Conclusion and Future Scope | 92.9% mAP, 45 FPS, 1.06% compound miss rate, dark-box lighting, super-resolution. |
| **32** | References: Part 1 | References [1]-[5] (Base paper + Liang, Datta, Turkoglu, Botta). |
| **33** | References: Part 2 | References [6]-[10] (Yin, Huang, Zhu [DCNv2], Tan [BiFPN], Tong [WIoU]). |
| **34** | Final Slide | "Thank You! Questions and Discussion". |

---

## 4. Key Decisions, Fixes Applied & Technical Rationale

### A. Literature Survey Table Horizontal Rules Fix (Slides 6 & 7)
- **Symptom:** Horizontal rules were not rendering in compiled PDF viewers (Overleaf PDF.js, Chrome).
- **Cause:** Previous code used `booktabs` (`\toprule`, `\midrule`, `\bottomrule`). In `booktabs`, `\midrule` defaults to `0.05em` ($\approx 0.4\,\text{pt}$). Inside `\resizebox{\textwidth}{!}{...}`, the entire table was scaled down by $\approx 0.68\times$, shrinking the rule to $\approx 0.27\,\text{pt}$. This fell below browser rasterizer 1-pixel thresholds and vanished.
- **Solution Applied:** Replaced `booktabs` rules with standard LaTeX `\hline` and set `\setlength{\arrayrulewidth}{0.8pt}` inside each table. Scaled thickness is now $\approx 0.54\,\text{pt}$ to $0.68\,\text{pt}$, guaranteeing crisp, visible rendering.

### B. References Breakdown (10 Entries vs 7 Papers)
- **Base Paper (1):** [1] Sun et al. (2026) - Base paper.
- **Survey Papers (6):** [2] Liang (2020), [3] Datta (2019), [4] Turkoglu (2021), [5] Botta (2022), [6] Yin (2024), [7] Huang (2023).
- **Architectural Method Citations (3):** 
  - [8] Zhu et al. (2019) - Inventor of DCNv2 (Slide 14).
  - [9] Tan et al. (2020) - Inventor of BiFPN / EfficientDet (Slide 16).
  - [10] Tong et al. (2023) - Inventor of WIoU dynamic loss (Slide 17).
- **Pending Decision for User:** 
  - Keep all 10 references (academic integrity for algorithmic modules) across 2 slides.
  - OR trim to strictly the 7 seminar papers ([1]-[7]), which will condense references onto a single slide.

### C. Architecture Diagram Split (Slides 12 & 13)
- Base paper Figure 3 was originally a two-part image. It was cleanly split into `figure3_improved_yolov8_architecture_1.jpg` (main pipeline on Slide 12) and `figure3_improved_yolov8_architecture_2.jpg` (DCNv2/BiFPN sub-modules on Slide 13) with maximum visual enlargement.

### D. Math Symbol Definitions
- Every equation slide (Slides 14, 17, 18, 21) has an explicit `\textbf{Symbol Definitions:}` block with `\vspace{0.12cm}` above the list to prevent overlap.

### E. Madrid Footer Standardization
- **Symptom:** Footer was an overlapping, overflowing mess across slides.
- **Cause:** `\author` and `\institute` lacked optional short arguments `[...]`. Beamer consequently injected the entire multi-line author block (`Submitted by... Under the Guidance of...`) and two-line institute block with `\\` into the single-line Madrid footline box. The short title was also overly long (`Cracked Egg Detection via Improved YOLOv8`).
- **Solution Applied:** Set `\author[Arjun Manoj | CEC23CS043]{...}`, `\title[Cracked Egg Detection]{...}`, and `\institute[]{...}` in the preamble. Footline now cleanly presents `Arjun Manoj | CEC23CS043` in the left box, `Cracked Egg Detection` in the center box, and frame numbers in the right box without overlap.

### F. Font Size Reduction on Text-Only Slides
- **Context:** Faculty noted that purely text slides looked heavily descriptive / paragraph-dense.
- **Solution Applied:** Added `\small` directly after `\begin{frame}` on all 9 text-only slides (Slides 3, 4, 5, 8, 10, 16, 20, 31, 32). This reduces body font from 11pt to 10pt on these frames, improving whitespace, readability and presentation pacing while matching the `\small` text style of the table notes.

---

## 5. File & Directory Inventory

```
C:\Users\aravindanirudh\Downloads\Arjun Manoj Seminar Related\
├── .git\
├── context.md                                            <- THIS CONTEXT HANDOFF FILE
├── Arjun_Manoj_CEC23CS043_CSQ413_Seminar_Summary.pdf     <- Seminar summary document
├── CSQ413_Seminar_Syllabus.pdf                           <- KTU Seminar syllabus guidelines
├── Arjun_Seminar_Presentation\                           <- PRIMARY WORKING DIRECTORY
│   ├── main.tex                                          <- Active presentation source (34 slides)
│   ├── classificationCategories.png                      <- Generated diagram for Slide 11
│   ├── classificationCategories.excalidraw               <- Diagram source file
│   ├── figure1_egg_conveying_device.jpg                  <- Conveyor mechanical layout
│   ├── figure2_machine_vision_system.jpg                 <- Camera and roller vision rig
│   ├── figure3_improved_yolov8_architecture_1.jpg        <- YOLOv8 overall pipeline diagram
│   ├── figure3_improved_yolov8_architecture_2.jpg        <- DCNv2 & BiFPN internal sub-modules
│   ├── figure4_dcnv2_sampling_comparison.jpg             <- Standard vs deformable sampling
│   ├── figure5_fpn_panet_bifpn_structure.jpg             <- FPN vs PANet vs BiFPN comparison
│   ├── figure6_training_schematic.jpg                    <- Offline training + online deployment flow
│   ├── figure7_online_deployment_testing_1.jpg           <- Production line testing setup
│   ├── figure7_online_deployment_testing_2.jpg           <- Production line egg tracking stream
│   ├── figure8_pr_curves_comparison.jpg                  <- PR curves across defect categories
│   ├── figure9_detection_effects_comparison.jpg          <- Comparison of Faster R-CNN, YOLOv5, YOLOv8, Proposed
│   ├── figure10_production_line_detection.jpg            <- Live sorting detections on roller conveyor
│   └── figure11_online_detection_speed.jpg               <- Frame rate stability graph over 400 frames
├── Seminar Abstract\
│   ├── 22_ArjunManoj_Seminar_Abstract.docx
│   ├── 22_ArjunManoj_Seminar_Abstract.pdf
│   └── Real-Time_Detection_Method_for_Cracked_Eggs...pdf <- Full IEEE Access base paper
├── Sample_Seminar_Content\                               <- Reference presentation & report templates
│   ├── Sample_Seminar_Presentation.pdf
│   ├── Sample_Seminar_Report.pdf
│   └── main.tex
└── Backups\
    ├── PPT_First_Submission\
    └── PPT_Second_Submission\
```

---

## 6. How to Resume in a New Chat

When opening a new chat, paste or reference this file:
> *"I am continuing work on Arjun Manoj's seminar presentation. Read `@context.md` and check `Arjun_Seminar_Presentation/main.tex` on disk before making any changes."*
