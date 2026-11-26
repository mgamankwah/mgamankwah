# Phase 5 — Local release candidate validation

Validated November 26, 2026 on Windows. The owner-approved Phase 4 patch was applied to clean `feature/portfolio-modernization` at `129188b27aaee20da5b4f07469f229da7e9f6a1b`. `git apply --check` succeeded, and the ten resulting file hashes match the patch's intended Git blobs. The complete diff was reviewed. No replacement copy, redesign or additional public-content correction was necessary.

This is a local release candidate for final review, not production authorization. No push, merge, deployment, force-push or workflow dispatch was performed in this assignment. The remote feature baseline is `129188b2`; production remains `711943ef6dc60d5125b148189b431caa1a151d8c`.

## Scope and preserved decisions

The patch changes `about.html`, `awards.html`, `experience.html`, `index.html`, `projects.html`, `publications.html`, `research.html`, `talks.html`, the content inventory, and the new Phase 4 reconciliation document. This Phase 5 record is the only additional repository file. Contact and the approved design remain unchanged.

The owner has approved KNUST BSc 2016 and MPhil 2018 (through NIMS), CWRU PhD May 2024, the two selected recognitions, and ICM 2018 delivery. Leadership metrics are intentionally omitted. The four historical CV downloads are explicitly retained despite the recorded privacy concerns. This decision supersedes earlier proposed retirement and approval holds. New general résumé, public email, Scholar, GRASAG-USA award/date and personal training certificate verification remain deferred as described in Phase 4.

## Results

| Check | Result |
| --- | --- |
| Native production build | Passed with existing Ruby 3.3.14, Jekyll 3.10.0 and `JEKYLL_ENV=production`; safe build under `/mgamankwah/`. |
| Routes, assets and fragments | All 13 HTML routes passed; 202 local references resolved; 113 baseline route/fragment checks preserved. No duplicate IDs or unresolved Liquid. |
| Historical CVs | All four responses are valid PDFs. Source and built bytes match the Phase 3B baseline. Their direct full-preview URLs remain available; they are omitted only from the shareable review ZIP. |
| Content preservation | Six papers, eleven presentations and five projects retained. Author correction is a supporting link, not a seventh paper. |
| Metadata and semantics | Page descriptions, canonical URLs, `lang=en`, one H1 and zoom-permitting viewport metadata checked on all 13 pages. Image alternatives present. |
| Responsive layout | Eight main/academic pages checked at 1440, 768, 390 and 320 CSS px in Chromium; no horizontal overflow. All 16 desktop/mobile captures have decoded images. Mobile navigation targets are at least 44 px high. |
| Keyboard and focus | Visible skip-link outline; Enter focuses `main`; representative header Tab/Enter navigation works. A figure link opens the 3730 × 1200 original image by keyboard. |
| Text contrast | Computed foreground/background checks on 495 rendered text elements across all eight pages found no AA threshold failures; lowest measured ratio approximately 5.34:1. This does not assess text inside scientific raster figures or every interactive state. |
| Native zoom / additional browser | Microsoft Edge on Windows: Home checked at native 200%; Projects loaded at 200% and navigation, project index, heading and body visually inspected at native 400%. Content reflowed without an observed horizontal scrollbar. Zoom restored to 100%. |
| Console and requests | No warning/error entries observed in the Chromium console. Local HTTP page/asset/download checks passed. The site contains no script tags. |
| Privacy | No new private contact values, common credential patterns or confidential Dell details found in the approved change and rendered HTML review. No new email, résumé CTA or internal project data introduced. |
| Protected files | Stylesheet, navigation data, shared includes/layout, configuration, workflow, image assets and historical PDFs unchanged. |

## External link checks

28 unique external links were requested without changing their destinations: 23 returned HTTP 200. Five could not be fully validated:

- Two IEEE DOI destinations return HTTP 202 access-check responses.
- LinkedIn returns HTTP 999 to automated requests.
- The SIAM CSE21 archive returns HTTP 403.
- The IMU ICM Open Arms page fails local TLS issuer-certificate verification in Python.

These are access/verification limits, not proof of missing pages. Approved links and content were retained; no certificate or browser security control was bypassed. Research verification was not repeated or rewritten.

## Remaining test limits

- Native Chrome accessibility state was unavailable. Edge supplied the additional-browser and actual zoom checks; this is not a complete multi-engine browser matrix.
- Spoken screen-reader behavior was not audited. NVDA was not found at standard installation locations, and no speech-output capture was available. Accessibility-tree and keyboard checks do not replace a representative NVDA/JAWS/VoiceOver user review.
- Safari, Firefox, physical mobile devices, forced-colors/high-contrast modes, every hover/focus state and a full WCAG conformance audit remain outside this run.
- The native Jekyll build is not a rerun of the exact GitHub Pages action container. No production workflow was used for testing.

No confirmed implementation defect remains from the performed checks. The limitations above remain explicit review items before production approval, rather than silently being marked as passed.

## Review and handover artifacts

Live full-clone preview: `http://127.0.0.1:8765/mgamankwah/`.
Updated screenshot gallery: `http://127.0.0.1:8765/review/release-candidate/`.

The sibling `Portfolio_Final_Release_Review.zip` contains the required source, sanitized rendered site, 16 screenshots, original approved patch, validation records and Windows instructions. The four historical CV PDFs, private audit exports, credentials, Git history, dependencies and unrelated files are excluded. Omitting downloads from a shareable review ZIP does not retire them from the repository or full-clone build.

`DEVELOPMENT-HANDOVER.md` is updated outside the public checkout and included in the ZIP. Final local SHA, clean-state confirmation and package checksums are recorded in the handover artifacts. Existing Phase 3B package remains available as a historical review snapshot.

Build from the full clone with `& '..\.preview-review\Build-Preview.ps1'`. If needed, start the loopback preview with `& '..\.preview-review\Start-Preview.ps1'`. The package has independent relative-path build/serve helpers. Source edits require rebuilding; screenshots are fixed captures of this candidate. Continue only with the owner's next explicit scope; do not infer authorization to push or publish from this validation record.
