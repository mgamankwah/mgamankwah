# Phase 3 portfolio review

The feature branch adds the professional homepage, Experience, Projects, Research, About, and Contact. It uses one Jekyll layout, shared navigation and footer, and a responsive stylesheet in `assets/styles/portfolio.css`. The portfolio loads zero JavaScript and makes no external font requests. The two WebP portrait sizes are derived from the existing `img/profile1.jpg`. The original remains in the checkout and at its direct built URL.

## Route and content decisions

- `/mgamankwah/` and `/mgamankwah/index.html` serve the homepage. The six primary destinations and all retained HTML routes use the project base path.
- `publications.html` and `talks.html` use the shared layout and retain the original six citation entries and publisher URLs and all 11 presentation records. The Research hub adds the owner-confirmed OhioLINK, ORCID, and DOI links. Confirming publication metadata and presentation sources remains Phase 4 work.
- `index1.html`, `projects_1.html`, `speaking.html`, `awards.html`, and `media.html` remain available as compatibility pages with links to the relevant current sections. The six historical structural fragment IDs remain available through the shared layout.
- Third-party legacy material stays in Git history. The Jekyll configuration excludes the Bradford PDF, unreviewed media assets, and unused template files. Production workflow files are untouched.
- The four existing Mercy PDF paths remain in the Jekyll build for compatibility. The current pages contain no résumé download link. The review ZIP omits these historical PDFs so it can be reviewed without redistributing them. The release decision about continued direct exposure remains open.
- The Alzheimer’s and ChloroFish entries distinguish documented individual contributions from team methods. Food Environment Atlas uses team attribution. Agentic AI appears as exploration in Experience. The site omits both Scholar candidates, the four leadership figures, and unapproved case studies.

## Reviewing on Windows

1. Extract the review ZIP with **Extract All**. Open the extracted folder that contains the `mgamankwah` directory.
2. In File Explorer, type `powershell` into the address bar and press Enter. With Python 3 installed, run `py -m http.server 8765 --bind 127.0.0.1`. If your installation provides `python` instead of `py`, run `python -m http.server 8765 --bind 127.0.0.1`.
3. Open `http://127.0.0.1:8765/mgamankwah/` in a browser. Start at Home and use the header to visit all six pages. Research links to Publications and Talks. Narrow the window to review the mobile layout. Press Ctrl+C in PowerShell to stop the local server.

For a fresh Jekyll build in the cloud, follow the [Phase 2 build procedure](portfolio-architecture-phase-2.md#rendered-review-workflow). For a shareable review package, use a ZIP containing only the rendered HTML, the site stylesheet, and the approved image and favicon files. Keep résumé archives, third-party assets, configuration, and repository files out of the review package.

## External link check

All three GitHub project repositories and the GitHub profile returned HTTP 200 when checked from the cloud. The environment proxy blocked the OhioLINK, ORCID, LinkedIn, DOI, arXiv, IEEE Xplore, Nature, and ScienceDirect destinations. Those HTTP results establish a verification limit in the cloud. The independently verified OhioLINK, ORCID, and DOI URLs were retained as supplied by the owner.

## Checks performed

- Built with the GitHub Pages action image `ghcr.io/actions/jekyll-build-pages:v1.0.13` and served a fresh ZIP extraction under `/mgamankwah/`.
- Checked all 13 HTML routes, every referenced local asset and fragment, all six navigation destinations, and the historical citation links and presentation text against commit `01d0860`.
- Rendered every route in Chromium at 1440, 768, 390, and 320 px and verified that each page reflowed without horizontal overflow and all images decoded. Checked image alternative text and representative 4.5:1 text contrast pairs.
- Walked the skip link, header focus order, keyboard activation, and research navigation with JavaScript disabled. Checked 200% CSS zoom reflow on the main and academic pages.
- Observed zero Chromium page errors, failed local requests, and external asset requests. Verified the ZIP inventory and byte-for-byte parity of its 21 site files with the build. Captured nine screenshots from the extracted archive.

The checks ran in cloud Chromium. The Windows instructions use the same Python server and extracted directory structure. Windows, Safari, Firefox, and a screen reader were outside this test run.

## Phase 4 scope

Review the visual and functional Phase 3 candidate before further changes. Then verify publisher and event records, reconcile awards and media where source records establish attribution, and confirm additional figure captions and academic assets. Resolve the résumé and Scholar decisions separately. Recheck public inbound links and run broader browser and screen-reader checks before release.
