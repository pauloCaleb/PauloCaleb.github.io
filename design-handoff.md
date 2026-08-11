# Portfolio — Design Handoff Spec

## 1. Design tokens (`style.css :root`)

| Token | Value | Role |
|---|---|---|
| `--bg` | `#0e1512` | Page background (soldermask) |
| `--surface` | `#121b17` | Card background |
| `--surface-2` | `#17221c` | Footprint / image-slot background |
| `--copper` | `#c97a3d` | Primary accent — refdes labels, borders, hover |
| `--copper-soft` | `rgba(201,122,61,.35)` | Dashed borders, background glow |
| `--silk` | `#e7e2d3` | Primary text |
| `--signal` | `#5fb3ab` | Links, section comments |
| `--muted` | `#8a978c` | Secondary text |
| `--line` | `rgba(231,226,211,.12)` | Hairlines, dividers |

Type: `Space Grotesk` (display / h1 / h3) · `Inter` (body) · `IBM Plex Mono` (refdes, comments, contact links, mono labels).

**Gap found:** spacing is currently ad-hoc (20/22/24/28/40/60/64/80px). No formal scale defined. Suggested fix if the site grows: adopt a 4px base scale (4/8/12/16/24/32/48/64/96) and replace one-off values.

## 2. Components

**`.card`** — default (1 column) and `.wide` (spans full grid width). States: rest, `:hover` (border → copper-soft, translateY(-2px)), `:focus-visible` (copper outline, inherited from global rule).

**`.footprint`** — image slot, `aspect-ratio: 16/10` capped at `max-height: 360px` (`.small` variant: `4/3`, capped `220px`). Three states:
- populated → `<img>` fills via `object-fit: cover`
- `.missing` (set by JS on `<img>` error) → dashed inset border + centered mono caption `"NOT POPULATED — {expected filename}"`
- hover → inherited from parent `.card`, no independent state

**`.refdes`** — mono, copper, uppercase-style tag (`U01`…`U09`) prefixing every hero block and card.

**`.comment`** — mono, signal-teal, `// SECTION NAME` pattern marking each category.

**`.subgrid`** — auto-fit grid (`minmax(140px, 1fr)`) for secondary images inside a `.wide` card.

## 3. Responsive behavior

Single breakpoint at **780px**: `.grid` drops from `repeat(2, 1fr)` to `1fr` (cards stack). Hero and type sizes use `clamp()` instead of breakpoints, so they scale continuously down to small phones. No breakpoint currently adjusts `.subgrid` — it self-wraps via `auto-fit`.

## 4. UX copy audit

| Item | Current | Issue | Suggested fix |
|---|---|---|---|
| Contact links | Raw `mailto:` / `tel:` text only | No label before the value; screen-reader users hit the value with no context | Add a small mono eyebrow above each: `EMAIL` / `PHONE` |
| Section header | `// GENERAL CADs` | Breaks parallelism with `// PCB PROJECTS`, `// OTHER PROJECTS` (noun+noun vs acronym+lowercase-s) | `// CAD & MECHANICAL` or `// MECHANICAL CADs` |
| Placeholder state | `NOT POPULATED — {filename}` | ✅ No change — in-voice, uses real PCB terminology, tells the user exactly what to do |
| Repo CTA | `View source — github.com/…` | ✅ No change — active voice, plain, exact destination stated |

## 5. Open questions for next pass

- Confirm final copy for the two flagged items above before editing `index.html`.
- Once real images are in `assets/`, re-check `.footprint` crop points — `object-fit: cover` may cut off tall/portrait photos (e.g. the eAlive connector shot); may need `object-position` per image.
