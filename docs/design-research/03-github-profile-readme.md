# Research Findings: Redesigning a GitHub Profile README for a Senior/Professional Look

## 1. Technical Constraints (confirmed current as of 2025–2026)

GitHub renders the profile README (the `username/username` repo's `README.md`) with GitHub Flavored Markdown plus a strict HTML sanitizer. Everything a designer does must fit inside this allowlist.

**What is ALLOWED:**

- **HTML tags:** `h1–h6`, `p`, `div`, `br`, `b`, `i`, `strong`, `em`, `a`, `pre`, `code`, `img`, `picture`, `source`, `blockquote`, `details`/`summary` (with `open` attribute — collapsible sections), `table`/`thead`/`tbody`/`tfoot`/`tr`/`th`/`td`/`caption`, `dl`/`dt`/`dd`, `kbd`, `samp`, `var`, `q`, `sup`, `sub`, `ins`, `del`, `hr`, `ruby`/`rt`/`rp`, `ol`/`ul`/`li`. Reference: [seanh's "HTML Tags You Can Use on GitHub" gist](https://gist.github.com/seanh/13a93686bf4c2cb16e658b3cf96807f2) and [github/markup #245](https://github.com/github/markup/issues/245) / [#246](https://github.com/github/markup/issues/246) (GitHub has never fully documented the allowlist; the community gist is the de facto reference; see also [community discussion #144854](https://github.com/orgs/community/discussions/144854)).
- **Attributes:** `align` (the deprecated-HTML-but-works `align="center"`/`"right"` on `p`, `div`, `img`, `td` — this is the only layout control), `width`/`height` on `img`, `href`/`src`, `alt`, `open`, `cite`, `id` (limited). Side-by-side layout is faked with tables or `align="left/right"` floated images (see jessfraz's profile, below).
- **Images:** PNG/JPG/GIF/SVG, local paths or URLs. All external images are rewritten through GitHub's **Camo proxy** (`camo.githubusercontent.com`), which caches aggressively — relevant for dynamic images (see §4).
- **Animation:** Animated GIFs play; **SVGs animate via SMIL or CSS embedded inside the SVG file** — this works because the SVG is loaded as an image, and inline `<style>` *inside the SVG file* survives (the sanitizer only strips HTML in the markdown itself). This is how readme-typing-svg, capsule-render, snake SVGs, and custom animated headers all work. Even `foreignObject` HTML/CSS inside an SVG renders. Sources: [egghead lesson on SVG+inline CSS profiles](https://egghead.io/lessons/css-use-svg-with-inline-css-animations-to-personalize-your-github-profile), [theopinionateddev.com](https://www.theopinionateddev.com/blog/customize-your-github-profile-with-css-and-svg-animations).
- **Theme awareness:** `<picture>` + `<source media="(prefers-color-scheme: dark)">` (see §5).
- **Misc:** emoji shortcodes, HTML entities, footnotes `[^1]`, Mermaid/GeoJSON/LaTeX math blocks (LaTeX `\color{}` is a known hack for colored text).

**What is STRIPPED / IMPOSSIBLE:**

- No `<style>` blocks, no `style` attributes surviving reliably, no `class`, no external stylesheets — **no CSS in the markdown, period** ([happycoding.io tutorial](https://happycoding.io/tutorials/html/github-profile-readme): "You can't use CSS at all!").
- No `<script>`, `<iframe>`, `<input>`, `<button>`, `<form>`, event handlers — nothing interactive beyond links and `<details>`.
- No custom fonts, no font-size/color control in text — typography beyond h1–h6/bold/italic/`code` must be baked into an image/SVG.
- No web requests at view time except images — every "dynamic" element is an image URL pointing at a service or an Actions-regenerated file.

**Design implication:** the entire craft is (a) restrained use of native markdown typography, (b) at most one or two well-made SVG/PNG images, (c) `align` + tables for layout, (d) `<picture>` for theming. Everything else is decoration smuggled in through images.

---

## 2. What Respected Engineers Actually Do (primary-source survey, fetched August 2026)

The raw profile READMEs of ~30 well-known engineers were fetched. The single strongest finding: **the most respected names have either no profile README at all, or a few lines of plain prose.** The credibility flows from pinned repos and the work itself, not the README.

**No profile README at all (404 on `username/username`):** Linus Torvalds (`torvalds`), Dan Abramov (`gaearon`), Mitchell Hashimoto (`mitchellh`), Evan You (`yyx990803`), Evan Wallace (`evanw`), TJ Holowaychuk (`tj`), Guillermo Rauch (`rauchg`), DHH (`dhh`), Kelsey Hightower, Brad Fitzpatrick (`bradfitz`), Jake Wharton, George Hotz (`geohot`), Fabien Potencier (`fabpot`), Pieter Levels (`levelsio`), Mitsuhiko (Armin Ronacher), BurntSushi (ripgrep), matklad (rust-analyzer), Steve Klabnik, Wes Bos. An empty profile is a completely acceptable senior signal — "the work speaks."

**One-liner / near-empty:**
- **Andrej Karpathy** ([karpathy/karpathy](https://github.com/karpathy/karpathy)): the entire README is `I like deep neural nets.` Nothing else.
- **Rich Harris** (Svelte): a single link to `rich-harris.co.uk`.

**Short prose bio, links, zero widgets:**
- **Jon Gjengset** ([jonhoo](https://github.com/jonhoo/jonhoo)): two paragraphs of plain prose — current role, book, YouTube, podcast, sponsorship link — and explicitly delegates to "see pinned repos." No images at all.
- **fasterthanlime** (Amos Wenger): prose intro plus a hand-curated bullet list of current projects, each with a one-line *substantive* description ("pure Rust, sans-io ZIP reading. Handles zip64, trailing zips, the weird stuff"). Reads like an engineer's changelog, not a brochure.
- **cassidoo**: conversational prose + plain link list of things she made. No badges/stats.
- **ThePrimeagen**: plain markdown headings and joke bullets — zero images.
- **Max Howell** ([mxcl](https://github.com/mxcl/mxcl), Homebrew): a deadpan Wikipedia-style biography written in prose. Personality via *writing*, not graphics.
- **Addy Osmani**: literally the default GitHub template bullets, template comment still in the file. Even at his level of visibility, plain text.

**Minimal with one tasteful visual element:**
- **Anthony Fu** ([antfu/antfu](https://github.com/antfu/antfu)): a single centered `<samp>` row of dot-separated plain-text links (me · blog · projects · talks · sponsor). Famous, widely imitated, ~600 bytes total. The `<samp>` monospace styling is the entire "design."
- **Kent C. Dodds**: one custom banner image + a single "Learn more about me" link. Two elements total.
- **Gift Egwuenu** ([lauragift21](https://github.com/lauragift21/lauragift21)): centered name, a `Website • X • LinkedIn • YouTube` plain-link row, `---` rules, two short prose paragraphs.

**Custom/self-updating done well (the "engineered" tier):**
- **Simon Willison** ([simonw/simonw](https://github.com/simonw/simonw)): one prose sentence, then a three-column table (Recent releases / Blog posts / TILs) auto-updated by a GitHub Action writing between HTML comment markers. This is the canonical "self-updating README" ([his approach on HN](https://news.ycombinator.com/item?id=23807881)). No stats cards, no icons — the dynamic content is *his actual output*, not vanity metrics.
- **Jess Frazelle** ([jessfraz/jessfraz](https://github.com/jessfraz/jessfraz)): a grid of **custom-generated local SVG panels** (`header.svg`, `repositories.svg`, etc.) committed to the repo by an Action — one consistent visual system, no third-party card services.
- **Platane** (author of the snake): ironically one of the most restrained — just the snake `<picture>` block with proper dark/light sources and a one-line credit.
- **muesli** (charmbracelet): short prose, one right-aligned logo image, auto-generated "recently working on" lists via his own [readme-scribe](https://github.com/muesli/readme-scribe).

**The kitsch-as-irony data point:** **Sindre Sorhus** (most-starred individual on GitHub) has a deliberate 90s-GeoCities parody profile — under-construction GIFs, hit counter, party furby. The joke lands *because* the audience understands decorated profiles read as kitsch.

**Counter-example:** **Anurag Hazra** — author of github-readme-stats itself — uses a custom header PNG, small inline tech icons, and his own stats cards. Notably, even he keeps it to a curated few, and his credibility line is prose: "Built github-readme-stats… 50m+ hits, 50K stars."

---

## 3. Reputation of Common Widgets Among Senior Engineers

Direct "this is cringe" threads are scarce in indexable form (much of it lives in Reddit/HN comments), but the pattern across [GitHub community discussion #28686](https://github.com/orgs/community/discussions/28686) ("Profile badges are patronising, ugly and might be used as a signal of superiority" — quotes: badges "look like they were drawn in crayon by a young child", "unprofessional kiddie stuff"), best-practice writeups, hiring-side articles, and the behavior of senior engineers themselves (§2) gives a clear consensus:

| Element | Consensus / evidence |
|---|---|
| **shields.io badge walls** | "Badges are trivial to fake and easy to overdo. A row of twelve colorful shields that link nowhere reads as decoration, and **experienced reviewers discount it on sight**" ([slategit.com badge guide](https://slategit.com/blog/ci-cd-badges-on-github-readme-guide)). [daily.dev best practices](https://daily.dev/blog/readme-badges-github-best-practices/): 3–5 *meaningful* badges beat a dozen decorative ones. On *project* repos, functional badges (build/coverage) carry weight; on *profile* pages, "Skills: JavaScript / HTML / CSS" shields are pure decoration. |
| **Skill icon walls (skillicons.dev)** | Listing "HTML, CSS, Git, VS Code" as icons is a bootcamp-template marker. Zero senior profiles surveyed use them (Anurag Hazra uses five 20px icons — the restrained ceiling). A tech list carries no evidence; pinned repos do. Roundup sites now say it explicitly: "It does not need to be loud, animated, or packed with every badge you can find" ([githubcard.com](https://githubcard.com/blog/github-profile-readme-ideas?lang=en)). |
| **github-readme-stats cards** | Two problems. (a) *Signal*: hiring-side sources say reviewers "don't count green squares — they look at 2–4 pinned repositories with clean READMEs" ([Instahyre checklist](https://resources.instahyre.com/blog/github-profile-checklist/), [readmedesign.com recruiter piece](https://readmedesign.com/blog/what-recruiters-look-for)). (b) *Reliability*: the shared Vercel instance is chronically rate-limited — "Maximum retries exceeded" / 503 errors leave **broken-image icons on your profile** ([issue #1471](https://github.com/anuraghazra/github-readme-stats/issues/1471), [#2415](https://github.com/anuraghazra/github-readme-stats/issues/2415), [#4431](https://github.com/anuraghazra/github-readme-stats/issues/4431)); the fix is self-hosting with PATs ([dev.to guide](https://dev.to/uya0526design/self-host-your-github-stats-badge-on-vercel-fixing-the-broken-image-on-your-profile-readme-la0)). A neon-themed stats card that intermittently 503s is the opposite of professional. |
| **Streak stats** | Reads as gamified grind culture ([DenverCoder1/github-readme-streak-stats](https://github.com/DenverCoder1/github-readme-streak-stats) — "Stay motivated and show off your streak 🔥"). HN discussion of [gamification's effects on GitHub developers](https://news.ycombinator.com/item?id=33309969) is broadly skeptical of streak mechanics. Streaks also advertise *quantity over quality* — the exact wrong signal for a senior. |
| **Contribution snake** | Every search result is a how-to; it ships in every "make a killer profile" YouTube tutorial, which is precisely the problem: it is the single most template-identifying element. Fun engineering credit goes to [Platane/snk](https://github.com/Platane/snk); on a profile in 2026 it signals "followed a tutorial." |
| **Typing SVG headers** | Same category — an animated gimmick from the template ecosystem (readme-typing-svg); adds motion and zero information. Animated images on GitHub cannot be paused (accessibility negative). |
| **Profile view counters** | Vanity metric, trivially inflatable, and historically unreliable (services died when Heroku ended free tiers — [dev.to](https://dev.to/groverception/add-visitor-count-to-git-hub-readme-md-profile-readme-md-4o9b)). Low numbers actively hurt; high numbers prove nothing. |
| **capsule-render waving headers / rainbow gradients** | The visual signature of the profile-generator ecosystem ([topics/beautiful-profile-readme](https://github.com/topics/beautiful-profile-readme)). The [awesome-github-profile-readme list](https://github.com/abhisheknaiidu/awesome-github-profile-readme) itself segregates these into "Fancy/Retro/GIFS" categories, distinct from "Minimalistic." |

**Meta-signal:** GitHub's whole ecosystem tagged itself here — sindresorhus parodies it; the snake's own author doesn't decorate; roundups aimed at *getting hired* now uniformly preach restraint: "Clarity, Cohesion, Call to action, Accuracy… under 5 seconds to identify what the developer specializes in" ([readmedesign.com examples](https://readmedesign.com/blog/best-github-profile-readme-examples)).

---

## 4. The Restrained Professional Design Pattern

Synthesized from §2's best examples, a senior-reading profile has **at most 4 elements**:

1. **Optional: one custom typographic header** — a hand-made SVG/PNG (name + one-line positioning), committed to the repo, with dark/light variants via `<picture>`. No animation, or a single subtle SMIL fade at most. This is the *only* place for visual identity. (Kent C. Dodds, jessfraz, Caneco are reference points; antfu proves even this is optional — a `<samp>` link line suffices.)
2. **2–4 sentences of prose** — who you are, what you build, where you work; written like jonhoo/fasterthanlime: concrete, specific, no adjectives about yourself, no emoji-bullet template ("🔭 I'm currently working on…" is instantly recognizable as the default template).
3. **A curated project list or nothing** — either rely on pinned repos entirely (the real content; reviewers open 2–4 pinned repos with good READMEs — [Instahyre](https://resources.instahyre.com/blog/github-profile-checklist/), [SOLTECH](https://soltech.net/what-do-hiring-managers-actually-look-for-in-a-github-portfolio/)), or a short hand-written list with one substantive line each (fasterthanlime pattern).
4. **Plain-text links** — `site • blog • twitter/x • linkedin • email` as a `<p align="center">` row (antfu/lauragift21 pattern). No social shields.

**Tooling for the "engineered" tier (if any dynamic element is wanted):**

- **[lowlighter/metrics](https://github.com/lowlighter/metrics)** (~17k stars, maintained; shared instance at metrics.lecoq.io) — GitHub Action rendering one consolidated SVG; 4 templates (**classic, terminal, markdown, repository**), 47+ plugins, 335+ options. Professional usage: **one** image, `classic` or `terminal` template, 2–3 plugins max (e.g. languages + recent activity), default muted palette, `config_timezone` set, committed to the repo (no third-party runtime dependency, so it can't 503 like the stats-card services).
- **Self-updating content via Actions** — the Simon Willison pattern: a scheduled Action rewrites sections between `<!-- marker -->` comments with *real output* (releases, posts). Generalized by [muesli/readme-scribe](https://github.com/muesli/readme-scribe) and simonw's Python approach ([HN thread](https://news.ycombinator.com/item?id=23807881), [mokkapps writeup](https://mokkapps.de/blog/how-i-built-a-self-updating-readme-on-my-git-hub-profile)).
- **Custom SVG generation in Actions** — the jessfraz pattern: generate your own SVG panels on a schedule, commit them locally, full typographic control, one coherent design system.
- **Camo caveat for anything dynamic:** GitHub proxies and caches all external images via Camo ([community #141814](https://github.com/orgs/community/discussions/141814)); dynamic endpoints must send `Cache-Control: no-cache`, or you purge with `curl -X PURGE https://camo.githubusercontent.com/<id>` ([github-badge-cache-buster](https://github.com/sbts/github-badge-cache-buster)). **Committing generated SVGs to the repo itself sidesteps most staleness/failure modes** — another argument for the Actions-commit approach over live third-party card URLs.

---

## 5. Dark/Light Mode Best Practices

- **Canonical method — `<picture>` element** (supported since GitHub's [Nov 2021 changelog](https://github.blog/changelog/2021-11-24-specify-theme-context-for-images-in-markdown/), detailed in the [GitHub blog how-to](https://github.blog/developer-skills/github/how-to-make-your-images-in-markdown-on-github-adjust-for-dark-mode-and-light-mode/)):
  ```html
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="header-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="header-light.svg">
    <img alt="Descriptive alt text" src="header-light.svg">
  </picture>
  ```
  Always include the fallback `<img>` (it also carries the alt text) — Platane's profile is a live reference implementation.
- **Legacy method — `#gh-dark-mode-only` / `#gh-light-mode-only` URL fragments**: still functions in 2025–2026 (orhun's profile uses it today) but **officially deprecated** in favor of `<picture>` and removed from current docs ([stefanjudis.com](https://www.stefanjudis.com/notes/how-to-define-dark-light-mode-images-in-github-markdown/), [tenthirtyam.org, Apr 2026](https://tenthirtyam.org/dispatches/2026/04/05/light-and-dark-mode-images-in-github-markdown/)). Don't build new work on it; it's also GitHub-only (breaks on GitLab/other renderers).
- **Do dark/light at the markdown level, not inside the SVG.** Media queries embedded inside an SVG served through `<img>`/Camo are not reliably evaluated across browsers; `<picture>` is guaranteed.
- **Design both variants deliberately**: transparent backgrounds + colors legible on both `#ffffff` and `#0d1117`; test both themes plus the "system" setting; never ship a dark-only image (white-on-transparent turns invisible in light mode — the most common profile bug).
- Dynamic-image caveat: github-readme-stats' `theme=` parameter cannot follow the viewer's theme by itself ([issue #1645](https://github.com/anuraghazra/github-readme-stats/issues/1645)) — another reason a wrapped `<picture>` with two pre-rendered local SVGs is superior.

---

## 6. Do / Don't Summary

**DO**
- Treat pinned repos as the real content; make *their* READMEs excellent (purpose in 20 seconds, live demo, clean structure).
- Write 2–4 sentences of specific, concrete prose; let personality come through writing, not graphics.
- Use a plain-text link row (`site • blog • x • email`), optionally in `<samp>`, centered with `align="center"`.
- If using any visual: one custom SVG header, dark/light via `<picture>`, committed to the repo, real alt text.
- If dynamic: one lowlighter/metrics SVG (classic/terminal, ≤3 plugins) or an Actions-driven "recent releases/posts" section between comment markers — content that is *your actual output*.
- Commit generated images to the repo (immune to third-party 503s and Camo staleness).
- Consider that an empty profile is a valid, senior choice.

**DON'T**
- Skill-icon walls, shields.io "skills" badges, or any badge that isn't a live, meaningful signal.
- github-readme-stats / streak cards on the shared instance (rate-limited, breaks visibly), and neon themes anywhere.
- Contribution snake, typing SVG, capsule-render waves, particles, rainbow gradients, glow filters — the template-tutorial signature set.
- Profile view counters (vanity, unreliable, low numbers hurt).
- The default template's emoji bullets ("🔭 I'm currently working on…") — instantly recognizable boilerplate.
- Emoji as structure (a few in prose are fine; emoji-prefixed section headers read as template).
- `#gh-dark-mode-only` fragments in new work (deprecated); dark-only images; relying on CSS/media queries inside SVGs for theming.
- More than one animated element; ideally zero (can't be paused; accessibility and tone both suffer).

**Key sources:** [seanh HTML-tags gist](https://gist.github.com/seanh/13a93686bf4c2cb16e658b3cf96807f2) · [github/markup #245](https://github.com/github/markup/issues/245) · [GitHub blog: dark/light images](https://github.blog/developer-skills/github/how-to-make-your-images-in-markdown-on-github-adjust-for-dark-mode-and-light-mode/) · [2021 theme-context changelog](https://github.blog/changelog/2021-11-24-specify-theme-context-for-images-in-markdown/) · [lowlighter/metrics](https://github.com/lowlighter/metrics) · [muesli/readme-scribe](https://github.com/muesli/readme-scribe) · [simonw self-updating README (HN)](https://news.ycombinator.com/item?id=23807881) · [stats-card outage issues #1471](https://github.com/anuraghazra/github-readme-stats/issues/1471)/[#4431](https://github.com/anuraghazra/github-readme-stats/issues/4431) · [badge-restraint guidance (slategit)](https://slategit.com/blog/ci-cd-badges-on-github-readme-guide) · [daily.dev badge best practices](https://daily.dev/blog/readme-badges-github-best-practices/) · [community #28686 badge criticism](https://github.com/orgs/community/discussions/28686) · [awesome-github-profile-readme](https://github.com/abhisheknaiidu/awesome-github-profile-readme) · [recruiter-perspective checklist (Instahyre)](https://resources.instahyre.com/blog/github-profile-checklist/) · [readmedesign.com recruiter piece](https://readmedesign.com/blog/what-recruiters-look-for) · [Camo cache discussion #141814](https://github.com/orgs/community/discussions/141814)
