# Portfolio modernization · Phase 1

## Checkout and release workflow

The cloud checkout started on `work` at commit `711943ef6dc60d5125b148189b431caa1a151d8c` with a clean working tree. A read-only lookup of `origin/main` returned the same commit. The local `feature/portfolio-modernization` branch was created from that base. The remote had no branch by that name at inspection time. When a pull request is authorized, use the feature branch as its head and `main` as its base.

The existing workflow in [jekyll-gh-pages.yml](workflows/jekyll-gh-pages.yml) builds the repository with `actions/jekyll-build-pages@v1`, uploads the site and deploys to the `github-pages` environment. It runs on pushes to `main` and allows manual dispatch. Keep review activities outside that workflow. This phase makes no remote writes.

## Repository assessment

The site consists of nine root-level HTML files with duplicated header, navigation, and footer markup. The maintained navigation connects the homepage, publications, projects, and presentations. A second set of menus also exposes awards, media, and speaking. The checkout includes CSS and JavaScript from a portfolio template, local fonts and images, five PDFs, and saved-page asset directories. There is no site-specific package manifest or Jekyll configuration. The deployment action currently packages the authored HTML and assets.

| Area | Finding |
| --- | --- |
| Positioning | [The homepage](../index.html#L119) still rotates through “On the job market for Research Roles” and [describes the PhD as in progress](../index.html#L178). Use the owner's May 2024 completion date and supplied career timeline. Keep the doctoral work, prior scientific training, research organizations, and academic leadership discoverable. |
| Attribution | [Awards](../awards.html#L7), [media](../media.html#L7), and [speaking](../speaking.html#L7) include Bashir Mohammed branding or profile references. [The publication source](../publications.html#L200) also contains a commented-out bibliography tied to that name. [The alternate projects page](../projects_1.html#L120) contains a different body of work. Confirm ownership entry by entry before reusing anything from those pages. |
| Links and navigation | The homepage links to [two different Google Scholar profiles](../index.html#L133). Legacy footers contain placeholder social links, and [media source markup](../media.html#L381) contains a malformed `ttps:` URL. A browser reproduced two image 404s from `/img/%20media/` on Media and 11 from missing `Projects_files/` images on `projects_1.html`. Navigation labels and destinations vary across pages. |
| Accessibility | All nine pages request disabled zoom through viewport metadata. The mobile toggle is an anchor without an `href`. In Chromium at 390 px the mouse could open the menu, but the toggle could not take focus and Enter did not open it. The toggle also lacks `aria-expanded`. All four images on the active [Projects page](../projects.html#L143) lack `alt` attributes. Some pages use a generic `div` as the navigation container. |
| Dependencies | Active pages load jQuery 2.1.3, Bootstrap 4.4.1, Modernizr, Owl Carousel, Magnific Popup, Masonry, imagesLoaded, Shuffle, and a validator. [The site script](../js/main.js) calls a Google Maps plugin that active pages do not load, producing a runtime error on the homepage and Projects. It also references a PHP form endpoint absent from this static checkout. The current template pulls fonts or icons from third-party hosts. |
| Assets and metadata | `img/` occupies about 69 MB, including a roughly 50 MB `img/media/scholar.png`. The homepage portrait is about 1.7 MB and is rendered as a CSS background. There are several résumé filenames and generic template metadata. Confirm the approved résumé and profile links, retain existing download URLs, and use optimized derivatives for display where helpful. |

The active publications page displays Mercy Amankwah's journal bibliography. The active Projects page includes quantum image representation, QCrank, Bayesian muscle recruitment, and a data science boot camp project. The Talks page contains conference presentations. Treat those active pages as starting points for the preservation inventory and reconcile them with the owner's approved bibliography and résumé.

## Proposed architecture

Keep GitHub Pages and its existing Jekyll build. Adopt a single native Jekyll layout in `_layouts/` and small shared includes in `_includes/` for navigation and footer. Add front matter to pages as they migrate and keep their existing output paths. Use readable HTML or Markdown and a small shared stylesheet with responsive layout and visible focus states. Use a small script only where a native control cannot meet the interaction requirements. Add a minimal `_config.yml` for site metadata and explicit exclusions for repository-only material such as `AGENTS.md`. Use Jekyll's relative URL handling for generated links and test them under the project path.

- Lead with applied AI, enterprise modernization, intelligent automation, decision science, and strategic business problem-solving. Use the supplied professional timeline with Dell Technologies, Advantage xPO on contract at Dell, and Outlier clearly distinguished. Keep forward-looking positioning separate from documented accomplishments.
- Give research a dedicated entry point to the existing publications, projects, and talks URLs. Preserve support for the Bayesian, inverse problems, uncertainty quantification, scientific computing, and quantum work. Give the SIAM chapter and Graduate Council roles space alongside professional experience.
- Establish a public URL inventory for existing pages, known deep links, and downloads before editing content. Retain the original sources in Git and keep established public paths working. For legacy pages with mixed attribution, use owner-approved replacements or a relevant migration page at the existing path. Preserve confirmed work and asset URLs, including case-sensitive filenames.

## Implementation phases and acceptance criteria

| Phase | Scope | Acceptance criteria |
| --- | --- | --- |
| 2. Content and route inventory | Verify the experience timeline, leadership, publications, research, résumé, and legacy attribution. Inventory paths, anchors, and downloads. | Every existing page and confirmed academic item has a recorded destination. The owner has reviewed attribution decisions and approved the résumé and profile links. Professional copy has a source and excludes internal Dell material. |
| 3. Portfolio foundation and homepage | Add the shared layout, responsive styles, navigation, and professional homepage. Add an Experience page if the approved content warrants one. | Title, headline, and timeline reflect verified facts. Visitors can reach experience and research from the homepage. Navigation works with keyboard, touch, and JavaScript disabled. Layout works at narrow widths and browser zoom. |
| 4. Research and legacy pages | Migrate the research pages, reconcile legacy routes, prioritize approved awards and media, and replace template dependencies after checking consumers. | Existing agreed URLs and downloads resolve under `/mgamankwah/`. Verified records remain accessible. Local asset 404s and template runtime errors are resolved. Images carry appropriate text alternatives and original assets are preserved. |
| 5. Review and release preparation | Validate the built output, documentation, and PR changes. | Pages build passes. Route and fragment checks pass. Desktop, mobile, keyboard, zoom, contrast, reduced motion, and representative screen reader checks are complete. The owner reviews the preview and separately authorizes any merge or production deployment. |

## Preview and testing

Docker and Python are available in this cloud environment. The following local preview runs the same Jekyll image version used by the Pages action when inspected. The build mounts the checkout read-only. It serves the built output at the production project path and uses an otherwise empty directory outside the checkout.

```bash
set -euo pipefail
cd /workspace/mgamankwah
preview_root=$(mktemp -d)
mkdir "$preview_root/mgamankwah"
docker run --rm --network none \
  --mount "type=bind,source=$PWD,target=/site,readonly" \
  -e GITHUB_WORKSPACE=/site -e INPUT_SOURCE=. -e INPUT_DESTINATION=../tmp/pages-site \
  -e GITHUB_REPOSITORY=mgamankwah/mgamankwah -e GITHUB_API_URL=https://api.github.com \
  -e INPUT_BUILD_REVISION="$(git rev-parse HEAD)" \
  --entrypoint /bin/bash ghcr.io/actions/jekyll-build-pages:v1.0.13 -euc '
    /entrypoint.sh >&2
    tar -C /tmp/pages-site -cf - .
  ' | tar --no-same-owner -xf - -C "$preview_root/mgamankwah"
python3 -m http.server 8000 --bind 127.0.0.1 --directory "$preview_root"
```

Open `http://127.0.0.1:8000/mgamankwah/` from a browser in the same environment. Stop the server when the review is complete. For remote asynchronous review, consider a separate PR-only workflow with read permissions that uploads the built site as a downloadable artifact for local viewing. Keep the production workflow out of preview and omit any deployment step from PR checks.

The documented preview also passed with the Phase 1 documents present. All nine HTML files and five PDFs matched their sources byte for byte. The build excluded both development documents.

On the Phase 1 baseline, the Jekyll build passed. The local server returned the homepage, all nine HTML files, representative CSS, JavaScript and a photograph, and all five PDFs. In Chromium the Projects link worked at 1280 px and after clicking the mobile menu at 390 px. The browser also reproduced the JavaScript error, keyboard menu failure, and legacy image 404s documented above. External browser requests were excluded from these smoke checks. The live GitHub Pages URL could not be fetched because the cloud egress proxy returned HTTP 403 for the tunnel. Live content parity, external URLs, third-party font behavior, contrast, screen reader behavior, and cross-browser coverage remain unverified.

## Files proposed for later changes

| Files | Expected work |
| --- | --- |
| `index.html`, possible `experience.html` | Professional landing page and, if warranted, an experience page. |
| `projects.html`, `publications.html`, `talks.html` | Preserve active research URLs and migrate the confirmed content to shared layouts. |
| `awards.html`, `media.html`, `speaking.html`, `index1.html`, `projects_1.html` | Reconcile attribution and preserve public entry points with reviewed content or destinations. |
| `_config.yml`, `_layouts/default.html`, `_includes/`, new shared stylesheet under `css/` | Add site metadata, shared markup, and maintainable styling. |
| `js/main.js`, vendored `js/` and `css/`, `img/`, `Projects_files/`, root PDFs | Replace obsolete code after checking references. Preserve original assets and linked PDF names, and add display derivatives where useful. |
| Optional `.github/workflows/portfolio-preview.yml` | Build and upload a PR artifact if remote review is needed. |

## Owner decisions and open questions

- Confirm the public résumé PDF, primary Google Scholar profile, preferred contact destination, and which awards, media, and speaking entries belong in the portfolio.
- Confirm which professional examples, if any, can be described publicly. The supplied role titles and dates are sufficient for the first draft of the timeline. Project details, results, and metrics require evidence and approval for publication.
- Reconcile the URL inventory against the live site when access is available. The repository paths and project-prefix build provide the current baseline.
- If owners want remote previews, confirm the artifact review workflow and repository permissions before adding CI. GitHub environment protection settings were outside this inspection.
