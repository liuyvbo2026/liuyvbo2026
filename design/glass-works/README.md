# GitHub profile project gallery

This gallery follows the glass panels, typography, project order, and real product screenshots on https://liuyvbo2026.github.io/#works.

The original airy-studio portfolio entry is preserved. The gallery displays Shangtu AI, DocAI, Zhiying, and the repository index as separate accessible links. GitHub READMEs do not run custom CSS or JavaScript, so the visual cards are pre-rendered images.

## Source and rendering

Open `render.html` through a local HTTP server. Product screenshots and the background come from the personal site's assets; the remote references are included in the renderer. No generated product interface is used.

Query parameters:

- `kind=heading|shangtu|docai|zhiying|repositories`
- `size=desktop|mobile`
- `theme=light|dark`

Wait for `window.renderReady === true` before export. Desktop artboards are 840 CSS pixels wide; mobile artboards are 368 CSS pixels wide. Heights are 104/96 for the heading, 348/466 for project cards, and 128/137 for the repository link, respectively.

Export at twice the CSS dimensions with document zoom set to 2, then save WebP at quality 92. Keep the filename pattern `{kind}-{size}-{theme}.webp` under `assets/glass-works/`.

The README chooses the mobile composition at viewport widths up to 1011 pixels, accounting for GitHub's profile sidebar, and follows the browser's `prefers-color-scheme` setting. Every linked image has descriptive alternative text. The original portfolio entry keeps its reduced-motion fallback.

## Verification

Checked desktop and narrow layouts, light/dark image selection, image loading, absence of horizontal overflow, and all project destinations. Product copy retains the information already published in the profile and personal site.
