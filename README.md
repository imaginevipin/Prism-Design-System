# imagine.io — Prism Design System

## Company & Product Context

**imagine.io** is a B2B SaaS company operating across two platform areas:

1. **3D Content Creation Platform** — Enables furniture, home furnishing, textile manufacturers and more to produce photorealistic 3D product imagery without engineering or 3D design expertise. Targets creative ops teams, brand managers, and product marketers at mid-to-large manufacturers and retailers.

2. **Physical AI / Robotics Simulation** — A physics-accurate 3D simulation environment and asset library for training robotics AI (supporting NVIDIA Isaac Sim). Targets robotics engineers, AI researchers, and enterprise infrastructure buyers.

The design system is named **Prism**.

---

## Sources Provided

| Source | Details |
|---|---|
| Figma file | `Design System 2025.fig` (mounted as VFS at `/`) — 5 pages, 45 frames. Key pages: `/In-Progress/` |
| Logo files | `uploads/Horizontal Dark.png`, `Horizontal Light.png`, `Vertical Dark.png`, `Vertical Light.png`, `Logo Mark.png` |
| Font files | `uploads/PPNeueMontreal-{Light,Book,Regular,Medium,SemiBold,Bold}.otf` |

---

## CONTENT FUNDAMENTALS

### Voice & Tone
- **Professional but accessible.** Copy avoids heavy jargon even in a technical B2B context. Speaks to capability and outcome ("create stunning photorealistic 3D content") not process.
- **Empowerment framing.** "Without any engineering or 3D design background" — the brand consistently emphasises removing barriers.
- **First-person "you" POV.** UI copy addresses the user directly ("Your plan", "Invite teammates"). No brand self-references like "we enable…".
- **Sentence case throughout.** Navigation items, buttons, and section headers use sentence case, not Title Case. Exception: proper nouns and product names.
- **No emoji.** The design system uses no emoji anywhere — iconography is handled exclusively via the custom SVG icon set.
- **Short, decisive copy.** Button labels are 1–3 words ("CTA Text", "Invite teammates", "Create team"). No padded copy.
- **Numeric specificity over vague claims.** Product copy favours concrete outcomes.
- **Calls-to-action** are papaya-orange — both visually and in linked text copy colour (`rgb(236,78,11)`).

### Examples from the Design System
- Nav item: "My plan", "Settings", "Logout"
- Contextual action: "Invite teammates", "Create team"
- Menu label: "Account menu items", "Org menu items"
- Section separator: uses a thin `1px solid #f7f7f7` divider, no label

---

## VISUAL FOUNDATIONS

### Colors
Primary brand colour is **Papaya** — a warm, vivid orange (`#ec4e0b`). It is used for primary CTA buttons, active states, highlighted text links, and brand accents. The design has a deliberate warm–neutral palette with no cool blues in the primary hierarchy.

| Role | Token | Value |
|---|---|---|
| Primary | `--papaya-500` | `#ec4e0b` |
| Primary hover | `--papaya-600` | `#d7470a` |
| Section bg / dark text | `--dark-500` | `#363636` |
| Body text | `--dark-900` | `#171717` |
| Secondary text | `--light-900` | `#686868` |
| Disabled / muted | `--light-700` | `#787878` |
| Border | `--light-400` | `#e1e1e1` |
| Surface | `--light-300` | `#f7f7f7` |
| Design/spec accent | `--color-purple` | `#9747ff` |

Neutral backgrounds are near-white (`#fbfbfb`, `#f9f9f9`, `#f7f7f7`). The app never uses dark mode.

### Typography
Single typeface: **PP Neue Montreal** (Pangram Pangram). All weights from Light (300) to Bold (700) are available locally in `fonts/`.

| Style | Size | Weight |
|---|---|---|
| H1 | 45px | SemiBold (600) |
| H2 | 37px | SemiBold (600) |
| H3 | 31px | SemiBold (600) |
| H4 | 26px | SemiBold (600) |
| Title 1 | 22px | Medium (500) |
| Title 2 | 18px | Medium (500) |
| Body | 15px | Regular (400) / Medium (500) |
| Caption | 12px | Regular or SemiBold |
| Label | 10px | Medium (500), uppercase, +8% tracking |

Line height is consistently **140%** across all sizes. Body and title copy uses `letter-spacing: 0.01em`.

### Spacing
Base unit is **4px**. Named scale (`--space-0` through `--space-16`): 0, 8, 12, 16, 20, 24, 32, 40, 48, 64, 80, 120, 160, 240, 400, 480px. Section padding is typically 64px. Component internal gaps are 4, 8, or 12px.

### Shadows
Four named shadow levels using `rgba(0,0,0,α)`:
- **Shadow-100** (Menus): `0px 0px 10px rgba(0,0,0,0.15)`
- **Shadow-200** (Standard cards): `0px 0px 40px rgba(0,0,0,0.20)`
- **Shadow-300** (Dragging items): `0px 0px 20px rgba(0,0,0,0.25)`
- **Shadow-400** (Overlays/modals): `0px 0px 40px rgba(0,0,0,0.25)`

### Border Radius
- `4px` — colour swatches, small chips
- `5px` — **primary radius**: buttons, menus, cards, panels, nav items (everything)
- `8px` — desktop app window outer shell

### Backgrounds & Surfaces
Backgrounds are always white or very light grays — no dark mode, no heavy gradients. Design system section headers use `rgb(54,54,54)` or `rgb(215,71,10)` (papaya-600) as background blocks for visual rhythm.

### Borders
Borders are thin (`1px`) and light: `rgb(225,225,225)` for structural borders and `rgb(247,247,247)` for dividers. Dashed purple (`rgb(151,71,255)`) is used only in design spec callouts (not in product).

### Hover / Press States
- Buttons: hover = `papaya-600`, pressed = `papaya-700`
- Nav items: hover shows a light `rgba` background tint
- Menus: hover state shows `background: var(--light-300)` on the row
- No scale/shrink animation on buttons; opacity shifts are subtle

### Animation
Not explicitly defined in the design system. UI is generally static / transition-free at the component level. Where transitions exist, they would follow standard 150–200ms ease-in-out patterns for menu open/close.

### Iconography (see ICONOGRAPHY below)
All icons 24×24px. Custom SVG set, mostly Material Design–derived with custom additions (Sparkle, Magic Brush, 3D, AR, Curator, etc.).

### Cards
Cards use `borderRadius: 5px`, `backgroundColor: #fff`, and `boxShadow: var(--shadow-200)`. No border in shadow state. Internal padding is `12px`.

### Layout
The app shell is a fixed two-column layout:
- **Left nav panel**: `236px` wide, white background, `1px solid #f7f7f7` right border
- **Top bar**: `64px` tall, spanning full width right of nav
- Content area fills the remainder

---

## ICONOGRAPHY

### Approach
All icons are custom 24×24px SVGs. The style is **Material Design–derived**: filled shapes, clean geometry, monochrome. Icons render at `rgb(54,54,54)` (dark-500) on light backgrounds and white on dark/papaya backgrounds.

No external icon CDN is used. Icons are embedded inline or referenced as SVG files.

### Icon categories (from Figma)
| Category | Examples |
|---|---|
| **Main** | 3D, Tick, Edit, Favourite, Generate, List, Grid, Present, Share, Settings, Close, Send, Attach, Drag, Code, Request, Terms of Use, Magic Brush, Draw, Download, Undo, Redo, Open In New, Sparkle, Sparkle Bold |
| **Display page** | 3D Product, AR, Configurator, Products, Camera, Lighting, Images, Templates, Settings, Themes, Hierarchy, Metadata, Automation, Exclusives, More |
| **Arrows** | Arrow Left Alt, Arrow Right Alt, Arrow Up Alt, Arrow Down Alt, Keyboard Arrow Up/Down/Left/Right, Up, Down, Left, Right |
| **Socials** | Discord, Instagram, LinkedIn, Twitter/X, Facebook, Reddit |

### Copied icon SVGs
Located in `assets/icons/`: edit, favourite, generate, list, present, attach, drag, request, magic-brush, sparkle, sparkle-bold, discord, instagram, linkedin, settings, draw.

---

## TEXT COLOR CORRECTION (verified)
- **Main / primary text**: `#363636` (`--dark-500`) — used for headings, nav items, UI labels
- **Subtext / captions / body copy**: `#787878` (`--light-700`) — secondary info, metadata, timestamps
- `#686868` (`--light-900`) exists in the scale but `#787878` is the canonical secondary text value

---

## FILE INDEX

```
/README.md                      ← this file
/SKILL.md                       ← agent skill definition
/colors_and_type.css            ← CSS custom properties: colors, type scale, spacing, shadows
/fonts/                         ← PP Neue Montreal .otf files (all 6 weights)
/assets/
  logo-horizontal-dark.png      ← horizontal wordmark, dark version
  logo-horizontal-light.png     ← horizontal wordmark, light version
  logo-vertical-dark.png        ← stacked wordmark, dark
  logo-vertical-light.png       ← stacked wordmark, light
  logo-mark.png                 ← logomark only
  icons/                        ← copied SVG icon set
/preview/                       ← Design System tab HTML cards
/ui_kits/
  app/                          ← imagine.io web app UI kit
    index.html                  ← interactive app prototype
    components/                 ← JSX component files
```
