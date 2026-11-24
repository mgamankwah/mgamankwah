# Portfolio architecture and review plan

The approved brief keeps Jekyll and GitHub Pages. This plan defines the content and design for review before implementation. The [content inventory](portfolio-content-inventory.md) records sources, attribution, publication gates, and unresolved claims. The checkout remains on `feature/portfolio-modernization` with [Phase 1](portfolio-modernization.md) intact at commit `551db40`.

## Sitemap and page outlines

Use the primary navigation in this order: **Home · Experience · Projects · Research · About · Contact**. Paths in the table are relative to `/mgamankwah/`.

| Page and URL | Content outline |
| --- | --- |
| **Home** `/` and `/index.html` | Name, concise role headline, approved positioning summary, portrait, and paths to Experience and Projects. Follow with a short overview of three professional themes, selected project examples, and a research section linking to publications and presentations. |
| **Experience** `/experience.html` | Reverse-chronological Dell Technologies, Advantage xPO contract at Dell, and Outlier entries. Use the exact employer, title, dates and approved contribution language. Group IonQ, NERSC and Berkeley Lab research experience below. Put agentic AI exploration in the current role or interests. Cross-link to About for education and leadership. |
| **Projects** `/projects.html` | Lead with Alzheimer's Risk Prediction and ChloroFish. Include MYOBOLICA, Quantum Pixel Representation and Compression, and Food Environment Atlas. Each entry covers the question, methods, individual role where evidenced, team credit, results and limitations as applicable, and a source link. Retain a link to the related QCrank study on Research. Use anchor links for individual entries before adding standalone case study routes. |
| **Research** `/research.html` | Explain the PhD work, Bayesian inference and uncertainty quantification, and scientific and quantum computing in plain language. Link to selected studies, QCrank, the full bibliography and presentations. Add thesis links and media coverage once verified. |
| **Publications** `/publications.html` · under Research | Retain the six named records, distinguish peer-reviewed work from preprints where supported, preserve bylines, and use DOI or authoritative publication links. |
| **Presentations** `/talks.html` · under Research | Preserve all 11 relevant talk and poster records. Add program, slide, or recording links only after verifying the speaker and destination. |
| **About** `/about.html` | Use the full approved biography as the source for the personal narrative. Cover mathematical training, academic leadership, education, and the interest in connecting technical capabilities to business needs. Add confirmed recognitions only. |
| **Contact** `/contact.html` | Use a short invitation relevant to applied AI, modernization, and data science. Prefer owner-confirmed LinkedIn and GitHub links. Add a general professional résumé and a public email only when approved. |

### Compatibility routes and assets

| Existing route | Proposed treatment |
| --- | --- |
| `/index1.html` | Keep the URL as a short entry point into About. Carry forward corroborated biography facts and preserve the old source in Git. |
| `/projects_1.html` | Keep an accessible entry point into Projects. Exclude all 12 legacy project descriptions from public output. |
| `/speaking.html` | Keep an entry point into `/talks.html`. Exclude the five unverified video embeds. |
| `/awards.html` | Keep an entry point to the leadership and recognition section on About. Add an Awards listing only when there is verified material. |
| `/media.html` | Keep an entry point to Research. Add a coverage section on the established route if the two candidate features and display assets are confirmed. |
| Four Mercy PDFs at the site root | Preserve the existing case-sensitive paths pending an explicit privacy decision. Keep the new résumé slot separate at `/assets/docs/mercy-amankwah-resume.pdf`. |
| `/mphil-2-phd.pdf` and `/bradstack-presentation.pdf` | Retire the third-party Bradford PDF from public output and remove its incoming reference during migration. The BradStack PDF is already absent. Preserve the Bradford source file in Git history. |
| `img/`, `Projects_files/` and other asset paths | Keep verified and previously linked photos and figures at their established URLs. Add display derivatives separately. Review dependencies and exclude material attributable to other people from the build. |

Use small Jekyll pages with clear links for legacy entry points so visitors with JavaScript disabled can follow them. Set canonical URLs where the content is equivalent. Preserve existing valid fragments either at the original content or at a compatibility location with a path to the corresponding section. The checkout's nine HTML files use the same six structural IDs: `page_container`, `site_header`, `main`, `main-content`, `primary`, and `content`. Use the repo and built output as the current compatibility baseline. Live Pages access is still blocked from this cloud environment, so additional inbound paths and fragments remain unverified.

## Homepage and navigation proposal

1. **Header.** A type-led Mercy Amankwah wordmark with six navigation links and a visible active state. Use a semantic navigation landmark, a skip link, and `aria-current="page"` for the active primary link. Research leads to a hub with clear Publications and Presentations links.
2. **Hero.** Put the name and concise headline on the left and the approved portrait on the right at wider widths. Stack them on small screens with the headline and primary links before the photo. Proposed headline treatment:
   - **Mercy Amankwah, PhD**
   - **Data Scientist at Dell Technologies**
   - Applied AI · Enterprise Modernization · Intelligent Automation & Decision Science
   - Short support line: “I’m a data scientist and applied mathematician working at the intersection of AI, enterprise modernization, and business decision-making.”
   - Primary link **View experience** and secondary link **Explore projects**. Add the approved general résumé later.
3. **Professional themes.** Three concise editorial sections show applied AI and enterprise adoption, modernization and intelligent automation, and data science for strategic business decisions. Tie each to an approved contribution or a source. Identify emerging interests in the fuller Experience or About copy.
4. **Selected work.** Feature Alzheimer's Risk Prediction and ChloroFish as team projects with clear dataset context. Include a link to the full project selection. Follow with a research section that highlights the mathematical foundation and makes the publication and presentation paths visible.
5. **Footer.** Name, confirmed contact or profiles, and essential navigation. Keep it concise.

Use deep navy `#14283B` for headlines and primary text, muted teal `#176D69` for links and accents, warm ivory `#FAF9F6` for the page surface, slate `#526579` for secondary text, and white `#FFFFFF` for raised surfaces or suitable inverse text. Choose a strong display face and a readable body face with local or system fallbacks. Use generous whitespace, a restrained grid and clear typographic hierarchy. Use source-owned photography and research imagery. Require keyboard focus visibility and WCAG 2.2 AA contrast in the final component states. At narrow widths, keep links reachable through wrapped navigation or a native disclosure. Use a disclosure only if it remains accessible without scripting. Omit rotating headlines, skill bars, generic illustrations and decorative animation.

## Implementation sequence and acceptance

| Phase | Files and implementation | Acceptance |
| --- | --- | --- |
| **3. Shared foundation and homepage** | Add a minimal `_config.yml`, `_layouts/default.html`, shared header and footer in `_includes/`, a shared stylesheet, and the Home, Experience, and Contact entry points. Set the project base URL and use Jekyll-relative URLs. | Approved headline and timeline are accurate. The three themes are discernible. Primary navigation reaches every destination included in the review build. No résumé link appears before approval. The local Pages build passes and its desktop and mobile views are reviewable. |
| **4. Projects, Research, About, and compatibility** | Implement `projects.html`, `research.html`, `publications.html`, `talks.html`, and `about.html`. Replace the five legacy entry points with the reviewed content or links. Add approved asset derivatives and exclude third-party content from the build. Remove obsolete dependencies after verifying remaining consumers. | Five selected projects and QCrank follow the inventory. Project contributions and results have appropriate scope and attribution. The six bibliography entries and 11 presentations remain accessible. Valid routes, fragments, approved PDFs, and verified images resolve under the project prefix. Confirmed third-party content is absent from the built artifact, including raw downloads. |
| **5. Review and release readiness** | Check the rendered build and compatibility inventory. Document any intentionally retired routes. Prepare a feature-branch PR when authorized. | Review desktop, mobile and narrow layouts, keyboard focus and navigation, 200% zoom, contrast, reduced motion and representative screen reader output. Verify downloads, external links where reachable, local asset responses, browser errors and content holds. Review the result with the owner. Any push, merge, workflow dispatch or production deployment requires explicit authorization. |

The production workflow currently builds and deploys on pushes to `main` and supports manual dispatch. Keep it outside the review path. The preview and release checks should inspect the same feature commit under review.

## Rendered review workflow

Build the current feature checkout with the GitHub Pages action image, stage the result under the actual project prefix, and package the built files. The command below creates a local artifact and serves it for browser checks. The checkout is mounted read-only and the build runs with its network disconnected. Its archive contains the rendered output, so a reviewer can view that same result without cloning the repository or running Docker.

```bash
set -euo pipefail
cd /workspace/mgamankwah
review_root=$(mktemp -d)
mkdir "$review_root/mgamankwah"
docker run --rm --network none \
  --mount "type=bind,source=$PWD,target=/site,readonly" \
  -e GITHUB_WORKSPACE=/site -e INPUT_SOURCE=. -e INPUT_DESTINATION=../tmp/pages-site \
  -e GITHUB_REPOSITORY=mgamankwah/mgamankwah -e GITHUB_API_URL=https://api.github.com \
  -e INPUT_BUILD_REVISION="$(git rev-parse HEAD)" \
  --entrypoint /bin/bash ghcr.io/actions/jekyll-build-pages:v1.0.13 -euc '
    /entrypoint.sh >&2
    tar -C /tmp/pages-site -cf - .
  ' | tar --no-same-owner -xf - -C "$review_root/mgamankwah"
tar -C "$review_root" -czf "$review_root/portfolio-preview.tar.gz" mgamankwah
printf 'Review archive: %s/portfolio-preview.tar.gz\n' "$review_root"
python3 -m http.server 8765 --bind 127.0.0.1 --directory "$review_root"
```

For a live private cloud preview, use a configured, authenticated HTTP preview and bind the same build to `0.0.0.0` on its configured port. At Phase 2 inspection no HTTP preview port was configured. The cloud reported SSH capability, and this chat did not offer a forwarding or shared-browser control tool. If the owner enables an HTTP preview port for this chat, start the release candidate there and verify its exact portal URL and project path. The desktop viewer can also open the internal server in a supported chat.

For an asynchronous review, supply the archive through the review chat once the redesign is authorized and built. Extract it, then run `python3 -m http.server 8765 --bind 127.0.0.1` from the extracted archive's parent folder containing `mgamankwah/`. Open `http://127.0.0.1:8765/mgamankwah/` in the browser on that same computer. Test this route with the approved review build, including a small-screen pass and the linked research and download paths. A separate, read-only PR artifact job is an option if later authorized.

Phase 2 verified the documented build and archive on the existing site. A fresh extraction served the homepage, Projects, Publications, Talks and an existing PDF under the project prefix. Chromium followed the Publications link at 1280 px and 390 px. The Phase 2 documents were excluded from the built output.
