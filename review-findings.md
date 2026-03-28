## REVIEW CLEAN
## Multi-Persona Review: MAWorkbench/index.html
### Date: 2026-03-26
### Summary: 2 P0, 10 P1, 12 P2 — ALL FIXED (23 applied, 1 deferred by design)

---

#### P0 -- Critical

- **[P0-1]** [FIXED] Statistical Methodologist + Domain Expert: "15 tau-squared estimators (FE, DL, REML...)" is wrong in two ways (line ~238)
  - Changed to "10 pooling methods: FE + 9 tau-squared estimators (DL, REML, ML, PM, EB, SJ, HS, HE, BD)"

- **[P0-2]** [FIXED] UX/Accessibility: Light-theme contrast failures across multiple elements
  - Added dark overrides in `[data-theme="light"]`: `--text-muted: #64748b; --accent: #0d9488; --amber: #b45309; --green: #15803d; --blue: #2563eb; --purple: #7c3aed`
  - Stat-label increased to `rgba(255,255,255,0.65)`

#### P1 -- Important

- **[P1-1]** [FIXED] CSS specificity bug — connector lines on mobile
  - Media query selector changed to `.step:not(:last-child)::before`

- **[P1-2]** [FIXED] Divider logic `||` → `&&`
  - Fixed in search handler

- **[P1-3]** [FIXED] Skip-navigation link added
  - `<a href="#main-content" class="skip-link">` as first child of body

- **[P1-4]** [FIXED] `<main>` landmark added
  - `<div class="container">` → `<main class="container" id="main-content">`

- **[P1-5]** [FIXED] Focus-visible styles added
  - `.theme-btn:focus-visible, .launch-btn:focus-visible` with accent outline

- **[P1-6]** [FIXED] aria-live region for search results
  - `<div aria-live="polite" id="searchStatus">` added, updated on each filter

- **[P1-7]** [FIXED] HKSJ enumeration clarified
  - Changed to "3 CI methods (Wald, HKSJ, KR), prediction intervals"

- **[P1-8]** [FIXED] Bias Forensics moved from Step 4 to Step 5
  - Now alongside Pub Bias Suite

- **[P1-9]** [FIXED] AutoGRADE note added
  - "Requires pooled results from Step 5"

- **[P1-10]** [FIXED] Footer corrected
  - "Most tools are browser-based. Python and R tools require local setup."

#### P2 -- Minor

- **[P2-1]** [FIXED] Dead `visibleSteps` code removed
- **[P2-2]** [FIXED] Search excludes `.launch-btn` text (reads h4.firstChild + .desc only)
- **[P2-3]** [FIXED] Theme persisted to localStorage (`maworkbench-theme` key, validated)
- **[P2-4]** [FIXED] CSP meta tag added
- **[P2-5]** [FIXED] `rel="noopener noreferrer"` on all `target="_blank"` links
- **[P2-6]** [FIXED] Visually-hidden `<h2>Workflow Steps</h2>` added before workflow
- **[P2-7]** [FIXED] `prefers-reduced-motion` media query added
- **[P2-8]** [DEFERRED] Launch buttons inside `<h4>` — design trade-off; restructuring would break flex layout. Screen readers read "Tool Name Launch" which is acceptable.
- **[P2-9]** [FIXED] "World's first" → "First serverless browser" for Meta-Regression and cNMA
- **[P2-10]** [FIXED] AdaptSim: added "For prospective trial planning"
- **[P2-11]** [FIXED] PRISMA Checker: specified which 6 extensions (NMA, DTA, IPD, Scoping, Protocols, Abstracts)
- **[P2-12]** [FIXED] MetaGuard: "5 frontier engines" → "3 frontier engines" + 2 additional modules

#### Safety Checks
- Div balance: 179/179 ✓
- No `</script>` inside script blocks ✓
- No duplicate IDs ✓
- File: 497 lines (was 472)

#### False Positive Watch
- DOR = exp(mu1 + mu2) is correct — do not flag
- Clayton copula theta = 2*tau/(1-tau) is correct
- Freeman-Tukey double arcsine for proportion MA is correctly named
- MAP prior (Neuenschwander et al. 2014) terminology is correct
- QEM (Doi et al. 2015) quality effects model is correctly named
