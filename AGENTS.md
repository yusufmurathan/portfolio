# AGENTS.md

Guidance for AI agents working in this repository.

## What this is

A single-page personal portfolio ("Achromatic Precision" design system) for Yusuf Murathan USTA. Pure static site: one `index.html`, one custom stylesheet, one small JS file. There is no build system, no package manager, no bundler, no tests, no CI, and no linting. All page copy is Turkish (`<html lang="tr">`); keep new content in Turkish. MIT-licensed; remote is `github.com/yusufmurathan/portfolio`.

## Commands

Nothing to build or test. To preview, serve the repo root with any static server:

```bash
python3 -m http.server 8000   # then open http://localhost:8000
```

Opening `index.html` via `file://` also works (no fetch/XHR), but Bootstrap, Bootstrap Icons, and the Inter font all load from jsDelivr/Google Fonts CDNs, so styling requires network access. Verify changes in a browser at desktop width and below 768px (the only screen breakpoint in `css/style.css`), and check print preview (see "Print mode" below).

Git gotcha: the owner frequently commits through GitHub's web interface ("Add files via upload" commits), so local clones can be behind `origin`. Run `git pull` before starting work.

## Architecture

- `index.html` — the entire site: fixed navbar, hero, then sections `#experience`, `#education`, `#skills`, `#projects`, `#contact`, footer. All content lives in markup, not JS.
- `css/style.css` (~400 lines) — overrides Bootstrap via `:root` custom properties (`--bs-body-bg`, `--bs-body-color`, `--bs-primary`, `--border-color`, `--heading-color`, `--card-bg`, `--accent-blue`) plus bespoke component classes (`.card-project`, `.timeline-item`, `.skill-badge`, `.border-precision`, `.btn-outline-precision`, `.section-title`, `.social-link`, `#backToTop`) and utilities (`.bg-amoled`, `.text-premium`, `.uppercase`, `.tracking-widest`).
- `js/main.js` (~90 lines) — a single `DOMContentLoaded` handler with four behaviors: smooth-scroll for nav links with a 100px fixed-navbar offset, closing the mobile navbar collapse, IntersectionObserver scroll-reveal, and the back-to-top button.
- `img/` — project screenshots. CSS renders them grayscale at 60% opacity; they gain color and a 1.05 scale on `.card-project:hover`. One project card (KeepSoundbarAndroidTV) uses an icon placeholder instead of an image.
- `DESIGN.md` — design spec; see next section. `Yusuf_Murathan_USTA_CV.pdf` is a root asset linked from the navbar ("CV İNDİR").

### Script order matters

`main.js` calls the global `bootstrap` object (`bootstrap.Collapse.getInstance`), which comes from the CDN bundle. `bootstrap.bundle.min.js` must load before `js/main.js` — both sit at the end of `<body>`. Preserve that order when adding scripts.

### Scroll reveal is progressive enhancement

The hidden state (opacity 0, `translateY(20px)`) for `.section-title`, `.card-project`, and `.timeline-item` is applied from JS, not CSS, so the page is still fully readable if JS fails to load. Do not move that initial hidden state into the stylesheet.

## Design system: DESIGN.md vs style.css

`DESIGN.md` (a design.md-format file: YAML front matter tokens + markdown prose) is the design source of truth in prose: AMOLED pure-black background, zero border radius everywhere, 1px `#1A1A1A` borders instead of shadows, white headings / `#A1A1AA` body text, a slate-blue accent used sparingly.

**Gotcha:** the YAML front matter and the prose disagree (e.g. front matter `surface: '#131313'` vs prose "background is #000000 (Pure Black)"). `css/style.css` implements the prose values, not the front matter: `--bs-body-bg: #000000`, `--bs-body-color: #A1A1AA`, `--border-color: #1A1A1A`, `--heading-color: #FFFFFF`. When changing design values, treat the prose as the reference for what is implemented, and update the DESIGN.md prose and the `:root` block together.

Design rules enforced in CSS that you must not break:

- **Zero radius:** `.btn, .card, .form-control, .nav-link, .dropdown-menu, .modal-content, .badge` get `border-radius: 0 !important`. Any new component must be square.
- **Depth is tonal layering, never shadows:** borders and slightly lighter fills only (`#0A0A0A` image container, `#333333` hover border). The navbar uses a frosted-glass backdrop blur instead of shadow.
- **The accent is currently unused:** `--accent-blue: #3B82F6` is defined in `:root` but referenced nowhere else. Per DESIGN.md it is reserved for critical interactions only; don't sprinkle it.
- Everything else is monochrome. Hover states brighten text/border color; primary buttons are solid white with black text.

## Print mode doubles as a CV

The `@media print` block in `style.css` flips the site to an ink-friendly white CV layout: hides the navbar and buttons, turns headings black, lightens borders, and removes hero padding. When changing markup or styles, check print preview so the CV mode keeps working.

## Known stale/quirky bits

- The CV download handler in `main.js` is a placeholder that only logs to the console; the download actually works via the anchor's `href="Yusuf_Murathan_USTA_CV.pdf"`. The code comment referencing a `CV.pdf` in the root is stale — the real PDF has a different filename.
- The smooth-scroll `offset = 100` in `main.js` is coupled to the fixed navbar's height; if you change navbar padding, adjust the offset too.
- `#contact` is a full section but has no navbar entry (nav links cover only `#experience`, `#education`, `#skills`, `#projects`).
- Global `*:focus { outline: none !important; }` strips all focus rings; focus feedback is per-component (e.g. `.nav-link:focus` color change). Give any new interactive element its own visible focus treatment.
- `html { scroll-behavior: smooth; }` in CSS coexists with the JS smooth-scroll handler; the JS exists to add the navbar offset on top of the native behavior.
