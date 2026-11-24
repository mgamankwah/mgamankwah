# Phase 3B refinement review — November 24, 2026

## Scope and status

Implemented the owner's Phase 3B brief locally on `feature/portfolio-modernization`, starting from `a78eb45f5743512b78706b81a5c3af09b1a5ae5e`. This candidate awaits owner review. No push, merge, deployment, workflow dispatch or Phase 4 work was performed. `main` remains at `711943ef6dc60d5125b148189b431caa1a151d8c`. The original palette, typography, portrait, six-item navigation, shared Jekyll architecture, base path and compatibility routes are retained.

## Page-by-page changes

| Route under `/mgamankwah/` | Refinement |
| --- | --- |
| `/` and `index.html` | Approved headline and introduction; four editorial expertise areas; concise employment summary; Alzheimer’s and MYOBOLICA figures; deeper scientific context; distinct leadership entries. |
| `experience.html` | Approved enterprise descriptions; prominent contract-to-full-time transition; four research appointments with source-supported titles and dates; separate leadership entries without unverified metrics. |
| `projects.html` | Five projects in the requested order, with problems, methods, individual contributions, team outcomes, limitations and evidence. Three authentic scientific figures link to original resolution. |
| `research.html` | Bayesian inverse problems, quantum algorithms and hybrid quantum-classical learning; scientific questions and cross-links; two attributed coverage entries, including a working institutional reference for the unavailable 2021 article. |
| `about.html` | Owner-supplied professional narrative, approach to work, education and development, community building and personal interests. Unconfirmed degree dates are omitted. |
| `contact.html` | Welcoming introduction and LinkedIn as primary contact. An optional email block renders only if an approved address is configured; none is configured. |
| `publications.html` | All six papers retained; two first-author articles highlighted; complete author lists and verified citation details; separate preprint and thesis sections. |
| `talks.html` | All 11 presentation records retained, grouped in reverse chronological order with distinct title, event, date and type. GRASAG-USA remains explicitly undated. |

Secondary headers are shorter. Desktop section and project columns use approximately 30:70 proportions. Role dates align with headings and stack on small screens. Mobile navigation has minimum 44 px height; figures have meaningful alternatives, captions and keyboard-accessible original-image links. No JavaScript or dependencies were added to the site.

## Evidence and attribution register

This supplement supersedes older inventory entries only where explicitly stated below. Employment wording and current dates are owner-approved claims, not independently audited employer records. No internal Dell systems, data, clients or metrics are disclosed.

| Claim | Evidence checked and disposition |
| --- | --- |
| Alzheimer’s competition F1 | [Repository README](https://github.com/mgamankwah/alzheimers_risk_prediction) reports tuned AdaBoost **93.28% F1 on the Kaggle competition test set**. Displayed as a team result on synthetic data, with no clinical validation claim. Individual EDA and feature-importance contributions remain as recorded in the Phase 2 attribution register. |
| Alzheimer’s 97% accuracy | Original `1_Model_Tuning_Entire_Set_Seyed.ipynb` output gives accuracy `0.970930` and F1 `0.958333` on the labelled-data validation holdout. This is distinct from the Kaggle test score. Verified but not added to the public summary; never characterize it as clinical accuracy. |
| MYOBOLICA | [Doctoral dissertation](http://rave.ohiolink.edu/etdc/view?acc_num=case1711387309757226), [first-author Bayesian paper](https://doi.org/10.1016/j.chaos.2024.115082) and [MYOBOLICA paper](https://doi.org/10.1109/TNSRE.2024.3447791) support the Bayesian, MCMC and uncertainty description. Doctoral contributions are separated from collaborative publication outcomes. |
| QPIXL reduction | [Original publication](https://doi.org/10.1038/s41598-022-11024-y) supports reductions up to 90% in gate counts for compression experiments on example scientific images using FRQI while retaining prominent features. Qualified accordingly; not a storage saving, general guarantee or end-to-end quantum speedup. [QPIXL++](https://github.com/QuantumComputingLab/qpixlpp) is the verified software repository. |
| ChloroFish MSE | [Model comparison notebook](https://github.com/mgamankwah/ChloroFish/blob/main/models/Model_comparison.ipynb) uses `TOTAL_SHRIMP_WEIGHT` from `SHRIMP_constant_gear.csv`. A 20% random test split is followed by a 20% validation split of the remaining training data (64/16/20 overall; random state 216). Validation MSE: training-mean baseline `2.4884055228466515`; histogram gradient boosting without imputation `1.3901438241851727`. Displayed rounded with evaluation context. The separate quantile notebook uses a transformed target; its scale is not conflated with these MSEs. Dataset preparation is the supported individual contribution. |
| Food Environment Atlas | [Team repository](https://github.com/db4014/food-atlas-2024) and [presentation](https://github.com/db4014/food-atlas-2024/blob/main/docs/Food_Envirionment_Atlas_Presentation.pdf) support USDA county data, 2013 diabetes prevalence and model comparison. Individual attribution remains presentation contribution and notebook edits, not unverified model authorship. |
| Five journal articles | Crossref DOI records checked for author order, titles, journals, volumes and article/page identifiers. All five canonical DOI links resolve. The two IEEE destinations return HTTP 202 access-check pages in the automated check; metadata was independently checked through Crossref. |
| EHands | [arXiv record](https://arxiv.org/abs/2502.15928) lists version 3, December 19, 2025, with **C. Pestano added as second author**. Current author order is reflected. No journal reference was present; a Crossref title check did not establish publication. Retained as a preprint. |
| 2024 research coverage | [Berkeley Lab feature](https://cs.lbl.gov/news-and-events/news/2024/quantum-insights-innovating-data-representation-analysis-and-visualization/) explicitly identifies Mercy and the quantum collaboration. Restored with concise attribution. |
| 2021 research coverage | The old Berkeley Lab URL now reaches a migration/not-found page. [CWRU's announcement](https://mathstats.case.edu/2022/06/applied-math-phd-student-mercy-amankwah-published-a-first-author-paper-on-quantum-pixel-representations-in-scientific-reports/) attributes the summer work and references the original feature. Public entry links to this working corroboration; the unavailable article's full text was not independently recovered. |
| Research appointments | Historical CVs support CWRU Instructor & Graduate Research Assistant, August 2019–May 2024; IonQ Quantum Applications Scientist Intern, June–August 2023; NERSC Quantum Algorithms Intern, June–August 2022; Berkeley Lab Research Intern, June–August 2021. Dissertation completion supports closing CWRU's older “Present” date. |
| Leadership | Historical CVs support SIAM Founding President, January 2022–May 2023, and Graduate Council Vice President, August 2022–May 2023. Descriptions use recorded activities without the four held numerical claims. |
| Education | OhioLINK and CWRU commencement records support the PhD, May 2024. [NIMS record](https://web.nims.edu.gh/about-nims/graduate-students) supports the MPhil program and NIMS/KNUST affiliation. Formal diploma-awarding wording and earlier graduation dates still need owner documentation. Public wording retains the established institutional affiliation without adding dates. Earlier thesis titles are supported by historical CVs; no fabricated thesis links were added. |
| Erdős development | [Official programs](https://www.erdosinstitute.org/programs) establish the titles **Data Science Boot Camp** and **Deep Learning Boot Camp**. Historical CV/project records support participation. Entries appear as professional development, without a verified certificate badge or date. The personal certificate endpoint could not be verified. |

### Figure provenance

- `assets/images/projects/alzheimers-feature-importance.jpg`: original project `images/feature_importance_v1.jpg`, 3730 × 1200, copied without resizing or modification. Git blob `0f8aa32ece4efd81d13b3731c365d7affced25a7` matches the source repository. Attribution is to the project team, not individual chart authorship.
- `Projects_files/myobolica_img.JPG`: existing approved visualization, 1483 × 675; retained unchanged and described as collaborative MYOBOLICA research.
- `Projects_files/qpixl_summary.JPG`: existing approved QPIXL visualization, 1304 × 559; retained unchanged and captioned with the paper citation.
- ChloroFish and Food Environment Atlas link to authentic notebooks/presentation evidence instead of fabricated figures.

## Outstanding owner decisions and privacy audit

Keep unresolved: Montana State MSc; formal MPhil awarding institution and early degree dates; personal Erdős certificate verification; 68 members, $5,358, 17 alumni and 14 mentorship participants; approved public email and general professional résumé; Scholar identity; GRASAG-USA date. No new claims or links for these holds were published.

All four historical CV/resume files were text-extracted and reviewed locally. Each contains personal email and telephone contact information. PDF metadata also contains author/creator/timestamp information, and older versions contain superseded career details and claims that should not automatically become current portfolio content.

| Preserved direct path under `/mgamankwah/` | Current decision |
| --- | --- |
| `Mercy_Amankwah_CV0.pdf` | Unchanged; still directly accessible; no new résumé CTA. |
| `Mercy-Amankwah_resume_2.pdf` | Unchanged; still directly accessible; no new résumé CTA. |
| `MercyAmankwah_Resume_master.pdf` | Unchanged; still directly accessible; no new résumé CTA. |
| `MercyAmankwah_resume.pdf` | Unchanged; still directly accessible; no new résumé CTA. |

**Proposed action for separate owner approval:** exclude these four PDFs from future rendered builds and replace the download with one approved, redacted, general professional résumé when supplied. This would retire direct website downloads, so it was not done under this refinement. Originals remain in Git; excluding website files would not remove public Git history. No history rewrite is part of Phase 3B. Private extraction files and audit images live outside the repository and served directory.

## Validation and local review

- Native Windows Ruby 3.3.14 / Jekyll 3.10.0 safe production build passes with the existing configuration. No global tool settings or production configuration changes are part of this commit.
- All 13 rendered HTML routes, referenced local assets and fragments, four retained PDFs, and excluded third-party legacy material checked. Baseline comparison preserves 97 route/fragment checks; no unresolved Liquid remains.
- All eight main/academic pages checked in Chromium at 1440, 768, 390 and 320 CSS px: no horizontal overflow; one main heading; images have alternatives; navigation targets meet 44 px minimum height. Full-page desktop and mobile screenshots cover all eight pages. Lazy figures were brought into view and decoded before recapturing affected mobile pages.
- Keyboard: visible skip-link focus, Enter transfers focus to `main`; header Tab order and Enter navigation work; focus outline is visible. A figure link opens the original 3730 × 1200 image by keyboard.
- Browser console returned no warning/error entries. Pages contain no JavaScript. Local HTML/assets/download HTTP checks passed; no third-party page assets were introduced.
- 21 unique external links checked: 18 HTTP 200, two IEEE HTTP 202 access checks, LinkedIn HTTP 999 automated-access block. The latter is a verification limit, not proof of a broken profile.
- Production workflow and all four historical PDF bytes are unchanged from the starting commit. No production operation was run.
- **Limits:** Native Chrome automation stopped because its current address could not be verified by the browser safety check. Actual browser zoom remains untested; narrow viewport reflow was tested but is not represented as native 200% zoom. No full screen-reader audit, physical mobile device, Safari or Firefox testing. This Windows Jekyll build is not a rerun of the exact GitHub Actions container.

Local preview: `http://127.0.0.1:8765/mgamankwah/`.
Accessible screenshot gallery: `http://127.0.0.1:8765/review/phase3b/`.

Build, start and stop scripts, screenshots and detailed check output live in sibling `.preview-review`, outside this repository. Final commit identity is available with `git log -1` and in the gallery. Review this candidate before any further phase or publication.

## Changed files

Eight page templates (`index`, `experience`, `projects`, `research`, `about`, `contact`, `publications`, `talks`); shared stylesheet; new figure include; one original project image; this review document and links from the inventory and Phase 3 notes. No changes to configuration, navigation data, compatibility pages, workflows, historical downloads or dependency manifests.
