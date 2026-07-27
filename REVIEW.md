# Altify moat — review guide

Three interwoven static pages that argue one thesis: Altify's data architecture
is AI-ready in a way generic sales AI is not, across three layers of use.

No build step. Plain HTML, inline SVG, one custom "DC" component framework loaded
by `support.js`. Hosted on GitHub Pages and Netlify from the same repo.

Live: https://putyourwifeouttawork.github.io/altify_moat_simple/

## The canonical pages (review these)

| File | Role | Live path |
| --- | --- | --- |
| `Altify 4D Moat.dc.html` | **The vision.** The moat argument (scale becoming clarity, the figure-8 loop, the coach, outcomes). Embeds the grounding explainer as an accordion. | `/Altify%204D%20Moat.dc.html` and `/` (redirect) |
| `architecture.html` | **The three layers.** A tab switcher over three panes: Execution (seller outcomes), Collaboration (Slack + Claude interfaces + the flag motion), Operating System (the data-structure deep dive). Opens on Operating System. | `/architecture.html` |
| `grounding.html` | **The grounding.** Standalone "how the structure captures context and guides AI" explainer. Four mechanism visuals + an animated traversal. | `/grounding.html` |
| `v2/index.html` | **Byte-identical copy of the vision page** for the `/v2/` path (asset links rewritten to `../`). Netlify/Pages path insurance. Edit in lockstep with the moat page. | `/v2/` |

## How they cross-link (the "interwoven" part)

- Vision → `The three layers` (top of page) and `The architecture` + `The grounding` (nav) → architecture.html, grounding.html
- Architecture → `The vision` (logo, topbar, footer) and `The grounding` (footer) → moat page, grounding.html
- Grounding → `The vision` and `The full architecture` (footer) → moat page, architecture.html
- All links are **relative**, so they resolve identically on Pages and Netlify.

## Shared conventions (worth checking a reviewer understands)

- **Layer colour code**, consistent across pages: Execution = blue `#53AFD4`,
  Collaboration = purple `#9A8BD4`, Operating System = red `#D5552E`. The
  architecture hero's figure-8 highlights the matching zone when a tab is selected.
- **The running deal**: one fictional deal (Meridian, Jane Okafor, the renewal,
  Jain Frit) recurs across every visual so the reader tracks one story.
- **Copy rules the pages hold to**: no em/en dashes anywhere; a running body-copy
  word budget on grounding.html (~425); the grounding "arrow law" (every drawn
  connection is directed, typed, named, non-crossing).
- **Vendor names**: deliberately sparing. Salesforce appears as the host platform;
  Slack and Claude appear in the collaboration layer *as their real interfaces* to
  make the "Altify is headless" point. No competitor is named or compared.

## Not canonical — ignore when reviewing

- `v3.html`, `v4.html` — superseded drafts of the moat page, kept for rollback.
- `index.html` — a redirect stub to the moat page.
- `uploads/` — original design scaffolds, pre-build.
- `_ds/`, `assets/`, `support.js` — design-system tokens, fonts, logo, and the
  component runtime. Boilerplate; the argument lives in the HTML above.
- `.nojekyll` — required so Pages serves the underscore-prefixed `_ds/` folder.
