# Profile visuals

The profile entrance follows the typography, grayscale pixel backdrop, and rounded button on https://liuyvbo2026.github.io/. The gallery displays two independently linked project cards per row on wide screens. Cards wrap naturally on narrow screens so descriptions remain readable.

Each project has one flat outer card. The product screenshots inside retain their angled, overlapping composition. The gallery contains Shangtu AI, DocAI, Zhiying, and the repository index. The hero is now a static visual and links to the personal site.

GitHub READMEs do not run custom CSS or JavaScript, so the visuals are exported as images. Every image has descriptive alternative text and light/dark variants.

## Rendering

Serve `render.html` over HTTP. Product screenshots and the pixel backdrop are loaded from the personal site's assets.

Query parameters:

- `kind=hero|heading|shangtu|docai|zhiying|repositories`
- `size=desktop|mobile`
- `theme=light|dark`

Wait for `window.renderReady`. Export at twice the CSS dimensions by using a double-size viewport and document zoom 2. Save WebP at quality 94 to `assets/flat-works/{kind}-{size}-{theme}.webp`.

| Asset | Desktop CSS size | Mobile CSS size |
| --- | --- | --- |
| Hero | 840 × 360 | 368 × 382 |
| Heading | 840 × 104 | 368 × 96 |
| Project / repositories | 420 × 440 | 368 × 440 |

The README uses two linked 410-pixel-wide images within each gallery paragraph, with normal wrapping on smaller screens. Picture sources select the narrow composition up to 1011 viewport pixels and use `prefers-color-scheme` for theme selection.

## Checks

Verified two project cards on each desktop row, complete image loading, correct destinations, no horizontal overflow, and readable mobile/dark variants. The renderer checks that project copy remains inside the outer card and no outer stack elements are present.
