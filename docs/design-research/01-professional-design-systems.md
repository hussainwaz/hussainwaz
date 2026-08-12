# Design Language Research: Professional-Grade Design Systems

**Purpose:** Reference for migrating a personal brand (GitHub README + portfolio) from neon/cyberpunk (#7C3AED / #00D9FF / #FF6B9D, glow, particles) to a senior, restrained aesthetic.

**Method note:** Several official sites (vercel.com, radix-ui.com, ui.shadcn.com, linear.app, apple.com docs) were unreachable through the network proxy, so token-level specifics come from search results summarizing official docs plus community token-extraction projects (notably [VoltAgent/awesome-design-md](https://github.com/voltagent/awesome-design-md), which reverse-engineers live sites into DESIGN.md specs). Values marked "≈" are extracted/approximate rather than officially published. They are accurate enough to build from.

---

## 1. Linear (linear.app)

**One-line identity:** Near-black canvas, one desaturated indigo accent, hairline borders instead of shadows, aggressively tight display type. "Dense, technical, and quietly luxurious."

### Color
- **Canvas (dark):** ≈ `#010102`–`#08090A` — near-black with a faint blue tint, deliberately **not** pure `#000000`
- **Surface ladder (4 steps):** `#0F1011` → `#141516` → `#18191A` → `#191A1B` — hierarchy comes from this ladder, not shadows
- **Borders:** hairline `#23252A`, strong `#34343A`, tertiary `#3E3E44` (also cited: `#2A2E33`). Containers are separated by **1px borders, not drop shadows**
- **Text:** primary `#F7F8F8` (paper-white, not pure white), muted `#D0D6E0`, subtle `#8A8F98`, tertiary `#62666D` — a 4-step text ladder
- **Accent:** one lavender-indigo `#5E6AD2` (hover `#828FFF`) reserved for brand mark, focus rings, and primary CTAs only. Stated rule: "never decoratively"; no second accent, no atmospheric gradients
- Success `#27A644`; that's roughly the entire chromatic budget

### Typography
- **Face:** Inter Variable (marketing now uses "Linear Display/Text," an SF Pro-adjacent custom face; fallback SF Pro Display → system-ui). OpenType features `cv01`, `ss03` enabled globally for a more geometric look
- **Weights:** unusual variable-font values — 300 (light body), **510** ("signature" emphasis weight, just above regular — emphasis that doesn't shout), 590/600 (semibold display)
- **Tracking:** aggressive negative letter-spacing at display sizes: −3.0px @ 80px, −1.8px @ 56px, −1.0px @ 40px, −0.6px @ 28px, tapering to ~0 at 14px. Body 16px/1.5
- **Mono:** Berkeley Mono (or Linear Mono) at ~13px, code/technical contexts only

### Spacing / layout
- 4px base scale: 4, 8, 12, 16, 24, 32, 48; **96px between page sections**
- Radii: exactly three in practice — **6px controls, 12px containers, 9999px pills**
- Depth: surface-color ladder + 1px hairlines; effectively zero decorative shadow

### Motion
- Not published as tokens; observed behavior matches the "Emil Kowalski school" (see §7): fast fades/translates under ~200ms, ease-out, nothing ambient or looping

### Core principles
1. **Restraint as brand** — one accent, used functionally, never decoratively
2. **Hierarchy without decoration** — 4 background steps + 4 text steps + hairlines do all the work
3. **Engineered typography** — tight negative tracking and odd precise weights (510) make headlines feel machined, not styled

Sources: [Linear DESIGN.md (VoltAgent)](https://github.com/voltagent/awesome-design-md/blob/main/design-md/linear.app/DESIGN.md), [How we redesigned the Linear UI](https://linear.app/now/how-we-redesigned-the-linear-ui), [linear-ui-skills breakdown](https://lobehub.com/skills/ihlamury-design-skills-linear), [getdesign.md Linear analysis](https://getdesign.md/linear.app/design-md)

---

## 2. Vercel — Geist (vercel.com/geist)

**One-line identity:** True monochrome — pure grays with no warm/cool tint — one blue for interaction, custom Swiss-inspired typeface pair. Stated principles: **simplicity, minimalism, speed**.

### Color
- **Structure:** 10 scales — Backgrounds, Gray, Gray-alpha, Blue, Red, Amber, Green, Teal, Purple, Pink. Each functional (semantic states), only Blue is "brand"
- **Two background tokens per mode:** Background 1 (default) and Background 2 (used "sparingly when subtle differentiation is needed")
- **Light mode:** page `#FAFAFA`, cards/modals pure `#FFFFFF`, inset/hover `#F5F5F5`, hairline `#EBEBEB`, strong divider `#A1A1A1`
- **Text (light):** ink `#171717` (near-black, not #000), secondary `#4D4D4D` (docs also cite `#666666`), muted `#888888`
- **Dark mode:** background ≈ `#0A0A0A`, surfaces ≈ `#111`–`#1A1A1A` band, same gray-scale logic inverted
- **Accent:** Blue `#0070F3`/`#0072F5` is the **sole interactive accent** — links, focus rings, info. Red `#EE0000` error, Amber `#F5A623` warning (each with soft + deep variants)
- Famous rainbow gradients (`#007CF0→#00DFD8`, `#7928CA→#FF0080`, `#FF4D4D→#F9CB28`) exist but are **quarantined to hero-scale brand moments only** — never UI, never miniaturized. Stated don't: "don't introduce new accent colours beyond ink + gray + the gradient pairs"
- Key insight from analyses: "the premium quality comes from consistency applied to an absurdly narrow palette"

### Typography
- **Geist Sans** (open source): weights **400 / 500 / 600 only — 600 is the display ceiling**, nothing bolder
- **Geist Mono:** weight 400 at 12–13px — reserved for code, technical eyebrows/labels, terminal chrome; never body text
- **Scale (marketing):** 48px/600/−2.4px → 32px/600/−1.28px → 24px/600/−0.96px → 20px/600/−0.6px; body 16px/400/24px; small 14px/−0.28px; caption 12px
- "Negative tracking is part of the voice." Headlines are **sentence-case, period-terminated. All-caps headlines are explicitly prohibited**

### Spacing / layout
- 4px base unit: 4→8→12→16→24→32→40→48→64→96→128; hero bands up to 192px. Max width ~1400px, 24px desktop gutters
- **Radii:** 6px inputs/nav buttons, 8px cards, 12px pricing cards, 100px marketing CTA pills — and a rule to never mix the pill and 6px radius idioms in one screen
- **Shadows:** stacked, very-low-alpha multi-offset shadows plus a 1px inset hairline ring (`0 0 0 1px #00000014`), e.g. Level 3 = `0 2px 2px #0000000a, 0 8px 8px -8px #0000000a`. "Never single heavy drops"

### Motion
- No large published motion spec; practice follows §7 (Vercel design engineering): ≤300ms, ease-out, transform/opacity only

### Core principles
1. **True neutral grays** — zero tint = "developer tool" objectivity
2. **One interactive color** — blue means clickable; everything else is grayscale
3. **Type does branding** — a custom sans/mono pair plus tight tracking replaces decoration entirely

Sources: [Geist introduction](https://vercel.com/geist/introduction), [Geist colors](https://vercel.com/geist/colors), [Vercel DESIGN.md (VoltAgent)](https://github.com/voltagent/awesome-design-md/blob/main/design-md/vercel/DESIGN.md), [SeedFlip Vercel breakdown](https://seedflip.co/blog/vercel-design-system), [DesignSystems.one Geist](https://www.designsystems.one/design-systems/vercel-geist), [Geist Font](https://vercel.com/font)

---

## 3. Stripe (stripe.com)

**One-line identity:** The proof that gradients can read as senior: one atmospheric gradient mesh, strictly quarantined to hero backgrounds, over an otherwise ruthlessly disciplined near-monochrome system with ultra-light editorial type.

### Color
- **Primary:** one "blurple" — brand `#635BFF`, current marketing CTA indigo `#533AFD` (deep `#4434D4`, pressed `#2E2B8C`)
- **Text is never pure black:** ink is deep navy `#0D253D`, secondary `#273951`, muted `#64748D`
- **Surfaces:** white `#FFFFFF`, cool off-white `#F6F9FC` for alternating bands, warm cream `#F5E9D4` for occasional "interlude" sections; hairline `#E3E8EE`
- **Shadows are tinted navy, not black:** base `#003770` at 4–8% alpha (e.g. `rgba(0,55,112,0.08) 0 8px 24px`) — this is why Stripe's depth looks expensive
- **The gradient (the tasteful way):** cream → sherbet orange `#FF6118` → lavender → indigo `#533AFD` → ruby `#EA2261` → magenta `#F96BEE`, as an organic **mesh occupying only the upper third of marketing pages**. Rules extracted: gradient colors never become button/text colors ("Ruby: never used as a button color"); **"one filled pill per band"** — a single indigo CTA per section; no accent colors outside the documented gradient stops

### Typography
- **Söhne** (Klim Type Foundry) as variable `sohne-var`; open substitute: Inter at 300 with `ss01`
- **Signature move: weight 300 at display sizes** — 56px/300/−1.4px, 48px/300/−0.96px, 32px/300/−0.64px. Extracted rule: "bumping to 400+ removes the brand's editorial air"
- **Tabular figures (`font-feature-settings: "tnum"`) on every money/numeric cell** — micro-detail that signals financial infrastructure
- Buttons step up to 400; body 15–16px/300–400/1.4

### Spacing / layout
- 8px base; card padding 32px; marketing section padding 64–96px
- Radii: 6px inputs, 12px cards, **9999px pill buttons (signature — "no rounded rectangles" for CTAs)**
- **Docs design** (most-copied dev docs in the industry): three-column layout — nav left, prose center, **synchronized scrolling code column right**; code blocks, parameter tables, and status badges are first-class authoring primitives; single typeface across prose and UI

### Motion
- No published tokens; marketing motion is essentially the slow ambient drift of the hero mesh (WebGL) plus standard fast UI transitions — content itself is not animated

### Core principles
1. **Expression is quarantined** — 100% of the color exuberance lives in one background element; everything it sits on is disciplined near-monochrome
2. **Editorial typography** — light weights + negative tracking + tabular figures = "whispered authority" instead of bold shouting
3. **Precision as trust signal** — tinted shadows, tnum, hairline tables: financial-grade micro-detail

Sources: [Behind the Gradient — Design at Stripe (Medium)](https://uwux.medium.com/behind-the-gradient-design-at-stripe-476dcf61a51a), [Stripe DESIGN.md (VoltAgent)](https://github.com/voltagent/awesome-design-md/blob/main/design-md/stripe/DESIGN.md), [DesignMD Stripe token breakdown](https://www.designmd.run/blog/stripe-design-system-breakdown), [Moesif Stripe docs teardown](https://www.moesif.com/blog/best-practices/api-product-management/the-stripe-developer-experience-and-docs-teardown/), [WriteChoice Stripe docs teardown](https://writechoice.io/blog/best-api-documentation-stripe-teardown), [stripe.design](https://stripe.design/)

---

## 4. Apple Human Interface Guidelines / apple.com

**One-line identity:** Hierarchy through size/weight jumps and surface alternation; depth through translucent materials, not drop shadows; one system blue.

### Color
- **Accent:** one Action Blue `#0066CC` (focus ring `#0071E3`; links on dark tiles `#2997FF`) — "no secondary brand color"
- **Surfaces (light):** white `#FFFFFF`, signature off-white `#F5F5F7`, near-white `#FAFAFC`
- **Surfaces (dark):** tile grays `#272729` / `#2A2A2C` / `#252527`, nav pure `#000000`
- **Text:** near-black `#1D1D1F` (never `#000` for body), muted `#333333` / `#7A7A7A`
- **Dark-mode depth model (HIG):** two sets of background colors, **base** (recedes) and **elevated** (advances) — layering is communicated by lightening the surface, not by shadows
- Edge-to-edge **light↔dark band alternation replaces borders** as the primary divider

### Typography
- **SF Pro Display ≥ ~20pt, SF Pro Text below** — an explicit optical-size split
- iOS text styles: Large Title 34/Regular, Title 1 28, Title 2 22, Title 3 20, Headline 17 Semibold, Body 17 Regular, Callout 16, Subhead 15, Footnote 13, Caption 12/11
- **Weight discipline:** 300 rare/atmospheric, 400 body, 600 headlines — **weight 500 and 700 deliberately absent**; emphasis jumps 400→600
- marketing body locked at 17px; negative tracking at display sizes (−0.28…−0.37px); dynamic tracking tables built into SF

### Spacing / layout / depth
- 8px base; tile vertical padding 64–80px of air around product imagery
- Radii: 8px utility buttons, 11px capsules, 18px cards, 9999px primary CTA pills, **0px for full-bleed tiles**
- **Materials:** five translucent thicknesses (`ultraThin → thin → regular → thick → ultraThick`) that blur content behind them; thicker = better text contrast. **Vibrancy** (tinted-transparent label colors) keeps text legible on any material. Production frosted-bar recipe: `rgba(245,245,247,0.8)` + `backdrop-filter: saturate(180%) blur(20px)`
- Exactly **one** drop shadow on the marketing site — `rgba(0,0,0,0.22) 3px 5px 30px` — used only under product renders, never on cards/buttons/text

### Motion
- One systemic micro-interaction: `transform: scale(0.95)` on button press. Otherwise scroll-triggered product reveals; chrome itself does not dance

### Core principles
1. **Deference** — UI recedes so content (product) speaks; "no decorative gradients, no shadows on chrome"
2. **Depth via light, not shadow** — materials/blur and base-vs-elevated surface lightness communicate layering
3. **Big weight-jumps, few weights** — hierarchy from 400↔600 contrast and large size steps, not from color

Sources: [HIG Materials](https://developers.apple.com/design/human-interface-guidelines/foundations/materials/), [HIG Dark Mode](https://developers.apple.com/design/human-interface-guidelines/foundations/dark-mode/), [Apple DESIGN.md (VoltAgent)](https://github.com/voltagent/awesome-design-md/blob/main/design-md/apple/DESIGN.md), [Median HIG dark-mode summary](https://median.co/blog/what-are-apples-human-interface-guidelines-for-dark-mode)

---

## 5. Radix Colors & shadcn/ui — how professionals construct palettes

**One-line identity:** The industry-standard recipe: a 12-step functional gray scale + one accent scale, wired through semantic background/foreground token pairs.

### Radix: the 12-step scale (each step has a defined job)
| Steps | Role |
|---|---|
| 1–2 | App background / subtle (card, sidebar) background |
| 3–5 | UI component backgrounds: 3 normal, 4 hover, 5 pressed/selected |
| 6–8 | Borders: 6 subtle/non-interactive, 7 interactive component borders, 8 strong borders & focus |
| 9–10 | Solid fills (buttons, badges): 9 normal (the "purest" chroma step), 10 hover |
| 11–12 | Text: 11 low-contrast/secondary, 12 high-contrast/primary (both WCAG-checked) |

- **Tinted grays for harmony:** pure `gray`, plus grays micro-tinted toward an accent hue — **mauve** (purple-tinted), **slate** (blue-tinted), **sage** (green), **olive** (lime), **sand** (yellow). Rule: pick the gray whose tint matches your accent's hue (violet accent → mauve gray; blue accent → slate) or pure gray for maximal neutrality
- Typical anchor values (Radix defaults): light `gray1 ≈ #FCFCFC`, `gray12 ≈ #202020`; dark `gray1 ≈ #111111`, slate-dark-1 ≈ `#111113` — dark modes start near-black-but-not-black
- Every scale ships light, dark, and alpha (transparent) variants so the same step works over any background

### shadcn/ui: the token convention
- Everything is a **semantic `background`/`foreground` pair**: `--background/--foreground`, `--card/--card-foreground`, `--primary/--primary-foreground`, `--secondary`, `--muted/--muted-foreground`, `--accent`, `--destructive`, `--border`, `--input`, `--ring` — components never reference raw colors
- **Five base neutral choices:** neutral, gray, **zinc (default)**, slate, stone (warm) — you pick ONE gray family and it generates the whole theme
- Canonical default values: light `--background: 0 0% 100%` with `--foreground: 222.2 84% 4.9%` (≈ `#020817`, a very dark desaturated blue — again, not #000); dark mode inverts to background ≈ `oklch(0.145 0 0)` ≈ `#0A0A0A`. Newer versions use OKLCH
- Dark mode = swap the variable set under `.dark` — and set **every** variable, not just background/foreground
- **One global `--radius`** (default 0.5–0.625rem ≈ 8–10px) drives all corner rounding — a single decision, applied everywhere
- Net effect: an entire professional UI from ~2 decisions (one gray family + one accent) executed through ~20 semantic tokens

Sources: [Radix — Understanding the scale](https://www.radix-ui.com/colors/docs/palette-composition/understanding-the-scale), [Radix — Composing a palette](https://www.radix-ui.com/colors/docs/palette-composition/composing-a-palette), [Radix — Scales](https://www.radix-ui.com/colors/docs/palette-composition/scales), [shadcn/ui Theming](https://ui.shadcn.com/docs/theming), [SeedFlip shadcn dark-mode guide](https://seedflip.co/blog/shadcn-dark-mode-theming)

---

## 6. Warm minimal / editorial: Anthropic (Claude), Notion, Arc

### Anthropic / Claude — the "warm minimal" benchmark
- **Canvas is cream, not white:** `#FAF9F5`; surface ladder `#F5F0E8` → `#EFE9DE` → `#E8E0D2`; dark band `#181715` (warm near-black, elevated `#252320`). Extracted principle: *"Pure white reads as 'any other AI tool'; the warm tint is the brand differentiator"*
- **Warm text ladder:** ink `#141413`, body `#3D3D3A`, muted `#6C6A64`, faint `#8E8B82` — grays are warm-tinted to match the cream
- **One accent: coral `#CC785C`** (pressed `#A9583E`), reserved for primary CTAs and occasional full-bleed callouts; explicit don'ts: no cool blue/cyan accent, don't scatter coral on small elements
- **Serif + sans pairing:** display in **Copernicus/Tiempos-style serif at weight 400 — never bold** — with −0.3…−1.5px tracking; body/UI in Styrene B (substitute: Inter) 400/500; code JetBrains Mono 14/1.6. This serif-display-at-regular-weight is the core "editorial" move
- Hairlines `#E6DFD8`; radii 8px buttons/12px cards; 96px section rhythm; philosophy: **"color-block first, shadow rare"** — depth from cream-vs-dark band alternation, shadows only `0 1px 3px rgba(20,20,19,0.08)` on hover
- Shows **real product/code chrome instead of illustrations of code**

### Notion
- White `#FFFFFF` / soft `#F6F5F4` canvas; warm charcoal text `#37352F` (their famous not-quite-black); ink `#1A1A1A`; one purple CTA `#5645D4`; link blue kept distinct (`#0075DE`)
- Pastel feature tints (peach `#FFE8D4`, mint `#D9F3E1`, lavender `#E6E0F5`…) only as large card backgrounds — never as text color
- Inter-based "Notion Sans"; hero 80px/600/−2px; body 16px/400/**1.55 leading** ("generous body leading for documentation readability")
- **Rectangular 8px-radius buttons, deliberately not pills** — "sober-editorial" geometry as differentiation; 12px cards; 8px spacing base

### Arc (The Browser Company)
- Warm paper canvas `#FFFCEC` ("reads as paper rather than screen"); one voltage blue `#2702C2`/`#3139FB` used **rarely on purpose** — "never appears as a button fill on the core chrome and never repeats inside the same section"
- Soft geometric proprietary face (Marlin Soft) + serif (Times) accents + InterVariable for UI — playful, but still one accent + cream neutral underneath

**Shared "warm minimal" formula:** warm off-white canvas → warm-tinted gray text ladder → exactly one mid-saturation accent → editorial type move (serif display, regular weight, tight tracking) → depth via surface color, not shadows.

Sources: [Claude DESIGN.md (VoltAgent)](https://github.com/voltagent/awesome-design-md/blob/main/design-md/claude/DESIGN.md), [Notion DESIGN.md (VoltAgent)](https://github.com/voltagent/awesome-design-md/blob/main/design-md/notion/DESIGN.md), [Arc brand analysis (shadcn.io/design/arc)](https://www.shadcn.io/design/arc), [designlang arc.net](https://www.designlang.app/gallery/arc-net)

---

## 7. Motion standards (the Linear/Vercel school — Emil Kowalski)

Concrete, citable rules from the Vercel design engineer whose standards this whole cohort follows:

- **Durations:** button feedback 100–160ms · tooltips 125–200ms · dropdowns 150–250ms · modals/drawers 200–500ms · **everything UI ≤ 300ms**
- **Easing:** entering/exiting → `cubic-bezier(0.23, 1, 0.32, 1)` (strong ease-out) · on-screen movement → `cubic-bezier(0.77, 0, 0.175, 1)` · drawers → `cubic-bezier(0.32, 0.72, 0, 1)` · hover/color → plain `ease` · **never `ease-in` on UI** ("it delays the exact moment the user is watching") · linear only for constant motion (spinners, marquees)
- **What NOT to animate:** keyboard-initiated actions; anything used tens/hundreds of times a day; layout properties (`height/width/top/left/margin/padding`) — **animate only `transform` and `opacity`**
- **Scale conventions:** enter from `scale(0.95–0.97) + opacity 0` (never `scale(0)`); button press `scale(0.97)` on `:active`; popovers scale from their trigger via `transform-origin`
- **Springs:** `{ duration: 0.5, bounce: 0.1–0.2 }`; bounce almost never
- **Accessibility:** honor `prefers-reduced-motion` (keep fades, drop movement); gate hover effects behind `@media (hover: hover) and (pointer: fine)`
- What none of these brands ever ship: infinite looping gradients, particle fields, glow pulses, typing/marquee text, animated rainbow borders — **ambient animation is the single clearest amateur tell**

Sources: [emilkowalski/skills STANDARDS.md](https://github.com/emilkowalski/skills/blob/main/skills/review-animations/STANDARDS.md), [emilkowal.ski — 7 practical animation tips](https://emilkowal.ski/ui/7-practical-animation-tips), [vercel-labs web-animation-design skill](https://github.com/vercel-labs/open-agents/blob/main/.agents/skills/web-animation-design/SKILL.md)

---

## 8. Synthesis: what separates professional from amateur

Every system above, despite very different personalities (cold Vercel ↔ warm Anthropic), converges on the same structural decisions:

### The common denominators

1. **Neutrals do ~95% of the work; there is exactly ONE accent.** Linear `#5E6AD2`, Vercel `#0070F3`, Stripe `#533AFD`, Apple `#0066CC`, Claude `#CC785C`, Notion `#5645D4`, Arc `#3139FB`. Always mid-saturation (no neon), always functional (CTAs, links, focus — never decoration). Amateur = 3 competing saturated hues doing decoration.
2. **Never pure black, never pure white, never pure gray-on-a-whim.** Dark canvases: `#010102`, `#0A0A0A`, `#181715` — near-black with a deliberate tint. Text on light: `#171717`, `#1D1D1F`, `#0D253D`, `#37352F`. Grays are tinted to harmonize with the accent (Radix mauve/slate/sage logic).
3. **Hierarchy is a ladder of neutrals, not a rainbow.** ~4 background steps + ~3–4 text-gray steps + 2–3 border grays (the Radix 12-step formalizes this). Meaning is conveyed by lightness, weight, and size — color changes are reserved for interactivity and semantic states.
4. **Borders over shadows; hairlines over glow.** 1px borders at `#23252A` (dark) / `#EBEBEB`–`#E6DFD8` (light). When shadows exist they are multi-layer, 4–8% alpha, often color-tinted (Stripe's navy `rgba(0,55,112,0.08)`). Glow filters appear in none of these systems.
5. **Typography carries the brand: one sans + one mono (max +1 serif for editorial).** Inter/Geist/Söhne/SF/Styrene — 2–3 weights only (400/500/600; Stripe goes light with 300, Apple skips 500 and 700 entirely). **Negative letter-spacing on headings** (−1 to −3px at display sizes, roughly −0.02…−0.04em) is universal. Body 15–17px at 1.5–1.55 leading. Mono is quarantined to code/labels/data — never body copy.
6. **Headings differ by size + weight, not color.** Sentence case (Vercel bans all-caps headlines). Tiny uppercase is allowed only for 11–13px eyebrows/labels with +0.4…+1.5px tracking.
7. **Expressive color, if any, is quarantined to ONE background moment.** Stripe's mesh (upper third of hero only, never buttons/text), Vercel's gradient pairs (hero-scale only), Notion's pastels (card backgrounds only). It never touches text, borders, or icons.
8. **Consistent geometric system:** 4px or 8px spacing base; generous section rhythm (64–96px+); ~2–3 radii total (≈6–8px controls, 12px cards, pill for CTAs — pick one CTA idiom and keep it); max content width 1200–1440px.
9. **Motion is feedback, not decoration:** ≤300ms, ease-out, transform/opacity only, nothing ambient, nothing on keyboard actions, `prefers-reduced-motion` respected.
10. **Whitespace is the luxury signal.** Apple's 80px of air, Linear's 96px sections, Stripe's band rhythm — density of decoration is inversely correlated with perceived seniority.

### The distilled checklist (apply directly)

- [ ] **One accent color, mid-saturation** (e.g. keep a single desaturated violet like `#5E6AD2` if violet must survive from `#7C3AED`; drop `#00D9FF` and `#FF6B9D` entirely). Use it only for links, CTAs, focus.
- [ ] **Kill gradients on text and borders forever.** If a gradient survives, it's one static, blurred, low-key background wash in one hero — nowhere else.
- [ ] **Build a neutral ladder before choosing any color:** dark mode `#0A0A0A` canvas / `#111`–`#1A1A1A` surfaces / `#26–2A` borders / text `#EDEDED` → `#A1A1A1` → `#6B6B6B`; light mode `#FAFAFA` / `#FFFFFF` / `#EBEBEB` borders / text `#171717` → `#666` → `#999`. (Or take Radix slate/mauve wholesale.)
- [ ] **No pure #000 or #FFF for large areas or body text.**
- [ ] **One sans (Inter/Geist, weights 400/500/600 only) + one mono (Geist Mono/JetBrains Mono, code and small labels only).** Optional serif display at weight 400 if going the warm/editorial route.
- [ ] **Negative tracking on headings** (−0.02 to −0.04em), sentence case, no colored headings.
- [ ] **Emphasis = weight/size jumps** (400→600), never a color change.
- [ ] **1px hairline borders instead of shadows/glows;** if shadow, ≤8% alpha and layered.
- [ ] **4px/8px spacing grid; 2 radii (8px controls, 12px cards); 96px between sections.**
- [ ] **Motion ≤ 200–300ms, ease-out, transform/opacity only; zero looping/ambient animation; zero particles.**
- [ ] **Copy discipline:** no emoji walls, no exclamation marks doing the enthusiasm; specifics ("built X, used by Y") over vibes — the visual equivalent of Stripe's `tnum`: precision reads as seniority.
- [ ] **Show real work** (real code, real screenshots, real numbers) rather than decorative representations of work — Apple's "photography first," Claude's "show real code."

**The one-sentence rule:** amateur design adds (colors, glow, motion, emoji) to create interest; professional design subtracts until only one deliberate accent, one type voice, and a disciplined neutral ladder remain — and lets precision, spacing, and restraint signal seniority.
