# Figure rules for this site

One system, so a project page reads as one page rather than a scrapbook.

## Sizes

| | value |
|---|---|
| aspect | **16:9**, every figure in a section, no exceptions |
| served width | **1400 px** (2× the display width, for retina) |
| display width | `max-width: var(--col)` = **52rem** — the same cap as the prose, so text and images share one column edge |
| layout | **one figure per row** (`<div class="figs figs1">`) |
| format | photographs and image panels → JPEG q90 · charts and diagrams → PNG |
| card image | **1600×853** with `class="tall"` (the `.rcard img.tall` box) |

`--col` is declared once on `.proj`. Change it there and prose, figures and the
link row all follow.

## Figures you generate

Plot them at **7.2 in × 4.05 in** (183 mm, double-column journal width) at 300 dpi
→ 2160×1215, then downscale to 1400. Never `bbox_inches="tight"`: it gives every
figure different margins. Full rules: `FM_filament/docs/FIGURE_STANDARD.md`.

## Figures you cannot re-plot

Screenshots, drone frames, diagrams from elsewhere: **pad** to 16:9 on the
image's **own** background colour (sample the corners), then resize to 1400 wide.
**Never crop** — cropping deletes content the figure was chosen for. Padding on
the page ground instead of the image's own leaves visible bands whenever the
figure has a dark background.

## Captions

- Carry only what the image cannot show: the control, and the conclusion.
  Anything the figure already prints — bar values, axis titles, totals — is
  redundant.
- No protocol detail (seeds, folds, splits). If the error bars need defining,
  define them **inside** the figure.
- `0.92rem` in the body face, not monospace.
- Captions that sit side by side get one template and matching length.

## Checklist

1. Every image in the section reports the same aspect (script it, don't eyeball).
2. Text and figures end at the same right edge.
3. Card is 1600×853 and the `<img>` carries `class="tall"`.
4. Caption says nothing the figure already says.
