# Developer Portfolio Design: State of the Art 2025–2026

## 0. Executive summary — the meta-shift

The center of gravity in respected developer portfolios has moved decisively from "look what I can make the browser do" to **quiet, typography-led, content-first sites with obsessive micro-detail**. The people whose portfolios engineers actually admire (Rauno Freiberg, Paco Coursey, Emil Kowalski, Lee Robinson, Anthony Fu) all converge on the same formula: near-monochrome palette, one typeface family used extremely well, short concrete copy, real shipped work as proof, and restrained motion that rewards attention rather than demanding it. Awwwards jurors say the same from the other direction: "generic creative dev tropes are now so common that jurors discount them," and what scores is "originality with intent — an idea that couldn't be swapped onto any other brand" ([Hon Tran, Awwwards jury 2026](https://www.hontran.dev/blog/best-award-winning-websites-2026)).

For someone leaving a neon-cyberpunk aesthetic behind: the neon/rainbow/particle look is a circa-2019–2021 trend (it spiked with the Cyberpunk 2077 marketing cycle) that now reads as niche and template-derived; guidance explicitly flags it as "alienating to general audiences" and appropriate only where deliberate kitsch is the point ([stellae.design](https://www.stellae.design/en/learn/cyberpunk-ui-design), [TemplateMonster](https://community.templatemonster.com/design-trend-high-tech-inspired-cyberpunk-color-schemes/)). In the AI era, surface flash has additionally lost signaling value entirely: "AI has collapsed the cost of producing surface-level artifacts, making portfolios without a work trace indistinguishable from generated noise" ([earezki.com](https://earezki.com/ai-news/2026-07-24-the-new-developer-portfolio-is-not-a-screenshot-it-is-the-work-trace/)).

---

## 1. Named exemplar portfolios and what makes them read senior

### The "design engineer" canon (the most-admired tier)

**Rauno Freiberg — [rauno.me](https://rauno.me)** (Staff Design Engineer, Vercel; ex-Browser Company/Arc; creator of cmdk; author of "Invisible Details of Interaction Design" and [Devouring Details](https://devouringdetails.com/))
- One-line self-description: *"design engineer creating software that makes people feel something."*
- Aesthetic: extreme minimalism organized around an operating-system concept — a familiar dock, interface sounds, a side-scrolling feed of projects/experiments/photography. Big type, lots of empty space, "a well-executed dark mode with carefully chosen tones that complement the imagery" ([foleo.design](https://www.foleo.design/Blog/rauno-freiberg), [pafolios.com](https://pafolios.com/rauno-freiberg), [killerportfolio.com](https://www.killerportfolio.com/by/rauno-freiberg)). Earned an Awwwards Honorable Mention ([awwwards.com/sites/portfolio-2025](https://www.awwwards.com/sites/portfolio-2025)).
- Why it reads senior: the concept is personal and unswappable; the flourishes are micro (cursor behavior, sound, physics on small elements) rather than macro (no page-wide gradients or particles); the work itself — shipped software downloaded millions of times weekly — is the content.

**Paco Coursey — [paco.me](https://paco.me)** (Design Engineer at Linear, ex-Vercel design system/dashboard)
- Self-description: *"frontend developer and designer... practicing minimalist."* The site is essentially a text page: name, one-line role, short prose, lists of projects and writing. Focused on "minimalism, UI interactions, and typography," covering "typography, motion design, copywriting, and performance" ([roster.so](https://roster.so/designer/paco-coursey), [designengineer.fyi](https://designengineer.fyi/paco-coursey), [ui.land interview](https://ui.land/interviews/paco-coursey)). Repo is public: [github.com/pacocoursey/paco](https://github.com/pacocoursey/paco).
- Why it reads senior: near-zero decoration; the confidence is in what's *absent*. Grayscale, system-adjacent sans, generous whitespace, hover states as the only ornament.

**Emil Kowalski — [emilkowal.ski](https://emilkowal.ski)** (Design Engineer at Linear, ex-Vercel; creator of Sonner + Vaul — ~70M weekly npm downloads combined; teaches [animations.dev](https://animations.dev))
- Minimal light page: name, one paragraph, writing list, projects. His stated philosophy is the industry reference point for tasteful motion: "motion is communication, not decoration… **the best animation is the one you remove**."
- Why it reads senior: the animation expert's own site is almost still. Authority is signaled by download counts and essays, not effects.

**Lee Robinson — [leerob.com](https://leerob.com)** (ex-VP of DX at Vercel, now Cursor)
- His 2024–2025 redesign was an explicit *removal* exercise: "simplicity and removing clutter that had accumulated over the years… simple design, clean typography, refreshed content," using the View Transitions API for smooth page transitions; he describes the result as "minimal" ([leerob.substack.com](https://leerob.substack.com/p/summer-2024)). The site is mostly a writing index plus short pages like [/beliefs](https://leerob.com/beliefs).
- Why it reads senior: black-on-white, one column, content-forward. The single animation (view transitions between pages) is structural, not decorative.

**Anthony Fu — [antfu.me](https://antfu.me)** (Vercel; creator of Vitest, Slidev, VueUse, UnoCSS)
- Self-description: *"fanatical open sourceror."* Clean white/dark-auto minimal blog-portfolio so admired it spawned entire theme ecosystems (Astro "AntfuStyle" theme, Valaxy themes) ([github.com/antfu/antfu.me](https://github.com/antfu/antfu.me), [astro-antfustyle-theme.vercel.app](https://astro-antfustyle-theme.vercel.app/)). Signature touch: subtle SVG line-drawing background animations and hand-drawn feel on an otherwise austere page; respects system color scheme.
- Why it reads senior: massive open-source output presented in a plain chronological list — inversion of flash-to-substance ratio.

**Josh W. Comeau — [joshwcomeau.com](https://www.joshwcomeau.com)** (educator; ex-Gatsby, Khan Academy, DigitalOcean)
- The canonical example of *playfulness done professionally*. "Whimsical lil' details": icon micro-interactions, easter eggs, an interactive rainbow, 3D shapes he modeled himself in Blender ([whimsy.joshwcomeau.com](https://whimsy.joshwcomeau.com/), [A Million Little Secrets](https://www.joshwcomeau.com/blog/whimsical-animations/)). Palette is rich (dark navy + pink/yellow accents) but the whimsy is opt-in and micro — the reading experience stays clean.
- Key distinction vs childish: his delight moments are *crafted and hidden*, not blasted at the visitor on load. He also wrote the standard free reference on portfolio strategy: [Building an Effective Dev Portfolio](https://www.joshwcomeau.com/effective-portfolio/) (free ebook: three sections — About, Projects, Contact; act as a "tour guide" to your work; keep About personal, not formal, because "overly formal makes you forgettable").

**Brittany Chiang — [brittanychiang.com](https://brittanychiang.com)** (senior front-end engineer)
- The most-forked developer portfolio on the internet (v4 repo ~8k+ stars). Dark slate/navy scheme with a single mint/teal accent, "slick, dark-schemed design with attention-to-detail throughout, including subtle hover effects… and a consistent color scheme with green accent" ([adminlte.io](https://adminlte.io/blog/react-portfolio-templates/), [onepagelove.com](https://onepagelove.com/brittany-chiang)). Known hexes from her public repos: v4 navy `#0a192f` with green `#64ffda`; the current version uses Tailwind slate (`#0f172a` family) with teal accent. Current site is a single page: sticky left column (name, role, one-liner, nav), scrolling right column of experience/projects with hover-lit cards.
- Caveat worth knowing: because it's been forked thousands of times, *copying* it now reads as template; the lesson to extract is the discipline (one accent color, typographic hierarchy, hover restraint), not the layout.

### The Awwwards / creative-dev tier (aesthetically maximal but controlled)

- **Dennis Snellenberg — [dennissnellenberg.com](https://dennissnellenberg.com)**: Awwwards Site of the Day + Honorable Mention; freelance designer/dev in Rotterdam; "minimalist and highly interactive… micro-animations, parallax scrolling, and transitions using GSAP, Barba.js, and Locomotive Scroll"; dark charcoal + off-white, huge name typography, magnetic buttons, playful cursor-following elements ([awwwards.com/sites/dennis-snellenberg](https://www.awwwards.com/sites/dennis-snellenberg)). The most-cloned "creative dev" portfolio on YouTube — again, now a known template look.
- **Hon Tran — [hontran.dev](https://www.hontran.dev)**: creative WebGL/GSAP developer, 11 international awards, Awwwards jury 2026. His published analyses of [what actually wins awards in 2026](https://www.hontran.dev/blog/best-award-winning-websites-2026) and the [Awwwards judging rubric](https://www.hontran.dev/blog/awwwards-judging-criteria) (Design / Usability / Creativity / Content weighted) are the best current insider source: one strong concept executed further than expected beats trope stacking.
- **Recent Awwwards portfolio winners** for reference-browsing: Olha Lazarieva (SOTD Oct 2025 — "elegant, minimal system"), Elliott Mangham (SOTD Dec 2025 — creative developer, 10× SOTD), Artiom Yakushev (Site of the Month Jan 2026), Bruno's Portfolio (SOTD + Developer Award Mar 2026) — all at [awwwards.com/websites/winner_category_portfolio](https://www.awwwards.com/websites/winner_category_portfolio/). By-Kin studio won SOTD + Developer Award with "confident editorial typography and smooth scroll" on Next.js + GSAP ([case study](https://www.hontran.dev/blog/by-kin-case-study-award-winning-website)).
- Curation galleries to mine: [godly.website](https://godly.website/?preset=Portfolios) (hand-picked, ~1,000+ sites, portfolio preset), [Muzli's 100 best portfolios](https://muz.li/blog/top-100-most-creative-and-unique-portfolio-websites-of-2025/), [bentogrids.com](https://bentogrids.com/), [wallofportfolios.in](https://www.wallofportfolios.in/bento-grids).

### Game-dev-relevant exemplars

From [Sitebuilder Report's game developer portfolio roundup](https://www.sitebuilderreport.com/inspiration/game-developer-portfolios) and [gamedesigning.org](https://gamedesigning.org/career/game-design-portfolio/):
- **Jenova Chen** (thatgamecompany, *Journey*): minimalist site, simple timeline, elegant typography — the games carry the color.
- **Brenda Romero**: black-and-white palette, minimal, straightforward navigation.
- **Josh Caratelli** (engineering director): full-screen imagery, side menu, professional layout.
- **Shawn Beck**: dark theme + bright accent, clean navigation, clear project highlights.
- Craft advice specific to game portfolios: lead with a positioning headline ("combat designer," "gameplay programmer"), use **GIF/video thumbnails** so work is felt instantly, and pair every piece with written context on intent and outcome — "communicating your thinking, not just what you made" ([Alexia Mandeville](https://alexiamandeville.medium.com/how-to-make-a-great-game-design-portfolio-14169d6838fb)).
- One honorable niche: **nostalgic OS-simulation portfolios** (e.g. Mitch Ivin's Windows XP recreation, featured by [WeAreDevelopers](https://www.wearedevelopers.com/en/magazine/644/five-nostalgic-developer-portfolios-for-inspiration-644)). These succeed on *execution fidelity* — they're effectively a shipped product demo. High risk, high effort; only worth it if flawless.

---

## 2. Trend-by-trend status report (what's current vs "2022 template")

Compiled primarily from [studiomeyer.io's 2026 six-month reality check](https://studiomeyer.io/en/blog/webdesign-trends-2026-reality-check), [Fireart's 2026 trends](https://fireart.studio/blog/the-best-web-design-trends/), [DesignRush 2026](https://www.designrush.com/agency/website-design-development/trends/web-design-trends), [Creative Boom's "trends creatives are so over"](https://www.creativeboom.com/insight/10-trends-creatives-are-so-over-in-2026/), and [Ioana Teleanu's "Aesthetics in the AI era" 2026 forecast](https://medium.com/design-bootcamp/aesthetics-in-the-ai-era-visual-web-design-trends-for-2026-5a0f75a10e98):

| Trend | 2025–26 status | Verdict for a portfolio |
|---|---|---|
| **Editorial / typography-driven** | The dominant premium direction. "Text as the primary interface architecture"; viewport-scaled (vw) headlines; type as focal point instead of stock imagery | **Safest strong choice.** This is what reads senior right now. |
| **Dark monochrome + single accent** | Standard for developer-facing work; mirrors Vercel/Linear/GitHub-dark tooling aesthetics ([webportfolios.dev](https://www.webportfolios.dev/blog/best-color-palettes-for-developer-portfolio)) | **Current and professional.** The default senior developer look. |
| **Warm minimalism / off-whites** | Rising as the light-mode counterpart; "calm linen whites and warm greige" for editorial portfolios; pure `#FFFFFF` considered harsh ([bscwebdesign.at](https://bscwebdesign.at/en/blog/5-modern-alternatives-to-pure-white-ffffff-2025/)) | **Current.** Distinctive because most devs default to dark. |
| **Grain/noise texture** | In. Subtle CSS/SVG grain "breaks up digital perfection," adds tactility, counters AI-slick sameness ([Fireart](https://fireart.studio/blog/the-best-web-design-trends/), [followupmedia](https://followupmedia.com/textured-grains-design-trend-2025/)) | **Current** — at 2–5% opacity. Heavy grain is Dribbble-poster territory. |
| **Serif comeback** | Strong and sustained: serifs have moved into "digital interfaces, tech branding" ([Alberto Gombáu](https://medium.com/@gombau/typographic-trends-2025-the-thousand-forms-of-the-contradictory-208c8e61cd5b), [Creative Boom](https://www.creativeboom.com/insight/font-trends-2025/)) | **Current.** A serif display over a sans body is a fast "designer taste" signal. |
| **Monospace/terminal ("Technical Mono")** | Named 2026 trend: "monospaced typography, command-line simplicity, high-contrast layouts… instantly signaling craft, precision, and technical authority," popularized by Vercel/Linear/Cursor/Raycast/Resend/PostHog marketing ([Teleanu](https://medium.com/design-bootcamp/aesthetics-in-the-ai-era-visual-web-design-trends-for-2026-5a0f75a10e98)) | **Current when restrained**: mono for labels, metadata, nav, code — not body text. Full fake-terminal UIs are a gimmick. |
| **Bento grids** | Held up as a *layout tool*, but "most designers overuse them, forcing them into contexts where they don't belong"; templates are everywhere (Framer/Figma/Astro/Envato) ([SaaSFrame](https://www.saasframe.io/blog/designing-bento-grids-that-actually-work-a-2026-practical-guide), [studiomeyer](https://studiomeyer.io/en/blog/webdesign-trends-2026-reality-check)) | **Borderline.** A whole-page bento personal site now reads "Framer template." One bento section (e.g. a now/stack/links block) is fine. |
| **Glassmorphism** | Demoted to a component technique: "used conservatively on navigation and modals only" ([studiomeyer](https://studiomeyer.io/en/blog/webdesign-trends-2026-reality-check)) | **Dated as a theme**, fine as a blurred sticky-nav detail. |
| **Neobrutalism** | Split: "avoid for corporate/mainstream"; alive only as deliberate anti-grid statement for creative studios ([studiomeyer](https://studiomeyer.io/en/blog/webdesign-trends-2026-reality-check), [Brandemic](https://brandemic.in/blog/must-know-ui-design-trends)) | **Mostly dated** (the pastel-cards-hard-shadow version = 2022 Dribbble). |
| **Gradient mesh / aurora** | Still alive in SaaS, but with explicit overuse warnings: "if the gradient doesn't serve hierarchy or mood, it's decoration… one aurora moment per viewport" ([designmd.app](https://designmd.app/library/gradient-mesh-aurora-evolved/), [colorshunter](https://colorshunter.com/blog/gradient-design-trends)) | **Risky on a portfolio** — reads "AI-startup landing page," not "person." |
| **Animated rainbow gradients, particles, glow text** | The core of the 2019–2021 cyberpunk wave; explicitly "niche and can feel alienating"; tied to the Cyberpunk 2077 moment ([stellae.design](https://www.stellae.design/en/learn/cyberpunk-ui-design)) | **Dated / reads junior.** This is precisely the look to leave. |
| **Kinetic/scroll-driven typography** | "More polish than substance" per the reality check; impressive in awards contexts, heavy elsewhere ([studiomeyer](https://studiomeyer.io/en/blog/webdesign-trends-2026-reality-check)) | Optional garnish; never load-bearing. |
| **Default-shadcn/Tailwind look** | Named sameness problem: "Most Tailwind + shadcn apps look like they were built by the same person, or worse, the same AI model" ([Design Systems Collective](https://www.designsystemscollective.com/is-anyone-else-tired-of-every-tailwind-shadcn-app-looking-the-same-69c545e73114)); fixes = commit to a radius identity (0px sharp / 1rem soft), replace default grays, one owned accent ([freedesignmd](https://freedesignmd.com/blog/shadcn-looks-generic)) | Use the tools, override the defaults. Default `rounded-lg shadow-md text-gray-600` = instantly generic. |
| **Tactile brutalism / engineered precision** | Rising: "sharp geometry, 1px solid borders, stark typography to project engineered precision, moving away from blurred drop shadows" ([Fireart](https://fireart.studio/blog/the-best-web-design-trends/)) | **Current** — and a natural fit for a developer identity. |

---

## 3. What reads CHILDISH vs what reads SENIOR

### Childish/amateur signals (with sources)

- **Skill progress bars / percentage meters** ("JavaScript 85%") — universally mocked; a percentage of an unbounded skill is meaningless and is the canonical junior-portfolio tell (recurring theme across [UX Playbook's 11 portfolio red flags](https://uxplaybook.org/articles/11-common-ux-portfolio-mistakes-and-solutions), [Pesto's recruiter red flags](https://pesto.tech/resources/what-are-the-biggest-red-flags-recruiters-spot-on-developer-portfolios)).
- **Badge walls and stat-widget stacks** on GitHub profiles: "animated badge carousels should be skipped; three different stat widgets stacked vertically signal that you optimized your README instead of building things" ([devbio.me GitHub README guide](https://devbio.me/blogs/github-profile-readme-guide)). Recruiters view GitHub profiles at high rates (est. 78–87%) but for **under 2 minutes** — noise gets scanned past.
- **Emoji-heavy presentation**: 39% of senior managers consider workplace emoji unprofessional; consistent guidance is icons over emojis, and even in creative tech, restraint ([myresumee.com](https://www.myresumee.com/blog/bdg-what-recruiters-say-about-emoji-in-resumes-yes-people-are-trying-it), [tealhq.com](https://www.tealhq.com/post/resume-icons)). A wall of 🚀✨💻 in a README/hero is a junior signal.
- **Too many colors / dopamine palettes**: "dopamine palettes" are on the 2026 avoid list for professional contexts ([studiomeyer](https://studiomeyer.io/en/blog/webdesign-trends-2026-reality-check)); professional palettes run 1 background family + 1 text family + **one** accent.
- **Over-animation**: "A page with 3–5 purposeful micro animations feels premium, while a page with 20 competing animations feels chaotic" ([sohelmalek.com](https://sohelmalek.com/blog/ui-micro-animations-high-converting-websites-2026/)); "most animations hurt UX more than they help" ([R.H Rizvi](https://medium.com/@R.H_Rizvi/why-your-beautiful-web-animations-are-killing-conversions-and-motion-isnt-the-problem-46f1a791c629)).
- **Over-engineered toy projects**: "almost three-quarters of rejected tech-lead candidates had some version of an absurdly over-engineered todo list" and 68% of rejected candidates highlighted projects hiring teams actually viewed negatively ([Sohail Saifi's 100-portfolio analysis](https://medium.com/@sohail_saifi/i-analyzed-100-tech-lead-portfolios-these-5-projects-are-red-flags-to-recruiters-04d03303d445)).
- **Broken responsive behavior under the polish**: overlapping text, stray scrollbars, fixed-width containers — "visual polish can hide performance issues, broken layouts, or outdated practices" ([Contra](https://contra.com/p/kXU7WbZb-hire-web-developers-portfolio-red-flags-you-cant-ignore)).
- **Vague, undocumented projects**: "unclear descriptions, missing context, vague timelines… mirrors how they'll communicate during a project" ([Pesto](https://pesto.tech/resources/what-are-the-biggest-red-flags-recruiters-spot-on-developer-portfolios)).
- Grandiose framing ("WELCOME TO MY UNIVERSE"-style hero copy) belongs to the same family as the above: it centers spectacle instead of work.

### Senior signals

- **Restraint as confidence**: "The sophistication isn't in the animation — it's in the restraint" ([School of Motion](https://schoolofmotion.com/blog/websites-with-great-animation-2026)). Every canon example in §1 is quieter than its author's ability.
- **2–4 deep case studies over 8–10 shallow cards**: "depth of reasoning is the differentiator, not project count" ([GreatFrontEnd](https://www.greatfrontend.com/blog/frontend-developer-portfolio)). Structure: problem + constraints → your role and decisions → measurable outcome. "Recruiters scan for logic and ownership, not archives of artifacts" ([uxfol.io](https://blog.uxfol.io/ux-case-study-structure/), [scale.jobs](https://scale.jobs/blog/top-5-case-study-formats-for-job-portfolios)). Metrics matter: conversion, load time, revenue, downloads. A closing "what I'd do differently" line is "the clearest evidence of judgment" ([earezki.com](https://earezki.com/ai-news/2026-07-24-the-new-developer-portfolio-is-not-a-screenshot-it-is-the-work-trace/)).
- **A work trace, not just screenshots** (AI-era shift): commits, PRs, design decisions, written reasoning — things AI can't fake retroactively ([earezki.com](https://earezki.com/ai-news/2026-07-24-the-new-developer-portfolio-is-not-a-screenshot-it-is-the-work-trace/)).
- **Typography carrying the design** (see §2 and §6).
- **Personal voice**: Comeau's advice — the About section should be personal because "overly formal makes you forgettable" ([effective-portfolio](https://www.joshwcomeau.com/effective-portfolio/)). Personality lives in *content and micro-details*, not in color count.
- **Performance and accessibility as aesthetics**: fast load, `prefers-reduced-motion` respected, WCAG contrast, 200% text zoom.
- **GitHub profile parity**: the profile should match the portfolio's restraint — a 2–3 line intro, pinned repos with real descriptions, at most one dark-themed stat card that matches the profile, never badge walls ([devbio.me](https://devbio.me/blogs/github-profile-readme-guide), [awesome-github-profile-readme](https://github.com/abhisheknaiidu/awesome-github-profile-readme)).

---

## 4. Copywriting tone

### How respected engineers actually write about themselves (confirmed examples)

- Rauno Freiberg: "design engineer creating software that makes people feel something" — role + effect, seven words.
- Paco Coursey: "frontend developer and designer… practicing minimalist" — plain nouns, no adjectival inflation.
- Emil Kowalski: builds "for designers and developers, thinking deeply about the user interface — how it looks, feels, and behaves."
- Anthony Fu: "fanatical open sourceror" — three words, then lets a project list (Vitest, Slidev, VueUse, UnoCSS) do the arguing.
- Lee Robinson: describes his own site simply as "minimal… simple design, clean typography, refreshed content."

The shared pattern: **role + specific domain + proof**, in under ~15 words, first person, lowercase-temperature prose. Authority comes from named shipped artifacts (cmdk, Sonner, Vitest), not from adjectives.

### The formula (from bio-writing guidance)

Lead with the role and specialty, add one sharp line about what you've done, skip status-seeking language: "No one needs to hear you're 'results-oriented' or 'passionate about innovation.' Those phrases are empty. Swap them for specific accomplishments" ([Huntr](https://huntr.co/blog/short-professional-bio-examples), [resumeoptimizerpro](https://resumeoptimizerpro.com/blog/professional-bio-examples)). Hero-copy guidance: 8–10 words max, concrete over hedging — "headlines that hedge say nothing" ([InBuild hero guide](https://www.inbuild.io/blog/hero-section-design-guide)).

### Banned-phrase list (amateur tells)

- "Crafting digital experiences" / "crafting seamless user experiences"
- "Passionate about…" (the single most-cited empty phrase — [copywriting.org](https://copywriting.org/a-good-copywriter-portfolio-should-have/), [Huntr](https://huntr.co/blog/short-professional-bio-examples))
- "Code wizard / ninja / rockstar / guru"
- "Turning coffee into code," "I debug with coffee" and all caffeine jokes
- "Welcome to my universe/world/digital playground"
- "Results-oriented," "detail-oriented," "innovative solutions"
- Listing AI tools as badges without shown usage — "reads as unverified and can work against you" ([Code Labs Academy](https://codelabsacademy.com/en/blog/build-future-proof-portfolio-2026-with-and-without-ai/))

### Rewrite pattern for this user (full-stack + game dev + UI/UX)

Amateur: "🚀 WELCOME TO MY UNIVERSE — passionate full-stack wizard crafting immersive digital experiences ✨"
Senior shape: "Full-stack developer and game developer. I build web products and games end-to-end — most recently [named thing]." Then let 2–4 case studies with numbers carry the rest.

---

## 5. Motion design: premium vs cheap

**What premium motion looks like** ([School of Motion](https://schoolofmotion.com/blog/websites-with-great-animation-2026), [stan.vision](https://www.stan.vision/journal/micro-interactions-2025-in-web-design), [Webflow](https://webflow.com/blog/microinteractions), Kowalski's published principles):

- **Micro over macro**: hover states, focus rings, button presses, link underline transitions, cursor-adjacent details — not full-viewport spectacles. Dan Saffer: "Microinteractions are an exercise in restraint, in doing as much as possible with as little as possible" ([IxDF](https://ixdf.org/literature/article/micro-interactions-ux)).
- **Concrete numbers**: hover scale ~1.02 ("2% is subtle; going bigger makes it feel like a toy"); ~50ms delay on active states "feels snappy" ([Roberto Moreno Celta](https://robertcelt95.medium.com/micro-interactions-that-dont-annoy-the-3-second-rule-for-ui-animation-9881300cd187)); micro-interactions in the 150–300ms band; 3–5 purposeful animations per page, not 20 ([sohelmalek](https://sohelmalek.com/blog/ui-micro-animations-high-converting-websites-2026/)).
- **Kowalski's rules** (the current community reference): animation must communicate, not decorate; prefer ease-out for entrances; animate opacity/transform only (compositor-friendly); "the best animation is the one you remove."
- **Structural motion > decorative motion**: leerob's use of the **View Transitions API** for page-to-page continuity is the model — one system-level idea instead of many scattered effects ([leerob.substack.com](https://leerob.substack.com/p/summer-2024)).
- **Scroll restraint**: subtle fade/rise reveals (single use per element, short distance) are fine; scroll-jacking, long pinned sequences, and parallax-everything belong to the awards-circuit genre and annoy in a portfolio meant for hiring. Even in that genre, winners use "one strong concept executed further than anyone expects," not effect stacks ([hontran.dev](https://www.hontran.dev/blog/best-award-winning-websites-2026)).
- **Respect `prefers-reduced-motion`** — itself a senior signal.
- **What reads cheap**: on-load animation of everything, typewriter hero text, bouncing scroll-down arrows, spinning skill icons, particle backgrounds, tilt-on-hover cards everywhere, AOS-library default fade-up on every section ("designers assuming sophistication equals effectiveness" — [R.H Rizvi](https://medium.com/@R.H_Rizvi/why-your-beautiful-web-animations-are-killing-conversions-and-motion-isnt-the-problem-46f1a791c629)).
- Tooling associated with the premium tier: GSAP + Lenis/Locomotive smooth scroll (creative tier), Motion/Framer Motion (product tier), CSS view transitions (content tier).

---

## 6. Concrete design tokens: palettes, type, spacing

### Palettes (hex, sourced)

**A. Dark monochrome + single accent** (the senior developer default — [webportfolios.dev](https://www.webportfolios.dev/blog/best-color-palettes-for-developer-portfolio), [SeedFlip](https://seedflip.co/blog/accent-colors-dark-mode), [sixtythirtyten](https://www.sixtythirtyten.co/blog/developer-portfolio-color-palette)):
- Background `#0a0a0a` (near-black; softer than pure black), body text `#e5e5e5`, muted text ~`#a3a3a3`, accent `#22d3ee` (cyan) — explicitly matching "tools developers actually use (Vercel, Supabase, GitHub dark)."
- Accent alternatives that pass AA on near-black: cyan `#06B6D4` (Tailwind), lime (Ghost's single accent on an otherwise monochrome palette), or a restrained red/orange for CTAs.
- Brittany Chiang's documented v4 tokens (public repo): navy `#0a192f` + mint `#64ffda`; current site: Tailwind slate `#0f172a` + teal. Proven, but now widely recognized.

**B. Warm light minimalism** (distinctive light-mode option — [bscwebdesign.at](https://bscwebdesign.at/en/blog/5-modern-alternatives-to-pure-white-ffffff-2025/), [designyourway](https://www.designyourway.net/blog/portfolio-color-palettes/)):
- Never pure `#FFFFFF`: use `#FAFAFA` (tech-neutral), `#FDFDFD` (premium), or warm `#FFFDF7`; warm beiges `#EDE7DC` / `#F1EADF` for section contrast.
- Documented ratio for a warm-neutral portfolio: 40% charcoal, 30% mid-gray, 25% off-white, 5% single hot accent (orange-red).
- Ink text on warm ground: near-black `#1a1a1a`–`#222` rather than `#000`.

**C. Universal rule**: one background family, one ink family, **one** accent used only for interactive/emphasis moments. Grain overlay at very low opacity is the current way to keep large flat fields from feeling sterile ([Fireart](https://fireart.studio/blog/the-best-web-design-trends/)).

### Font pairings (all free/open-source, sourced from [The Crit](https://thecrit.co/resources/best-font-pairings-portfolio), [Mantlr cheat sheet](https://mantlr.com/blog/google-fonts-pairing-cheat-sheet), [Stylokit](https://stylokit.com/blog/top-20-fonts-for-modern-web-design-2025), [Matt Medley](https://medium.com/design-bootcamp/best-google-font-pairings-for-ui-design-in-2025-ba8d006aa03d)):

| Direction | Heading | Body | Mono (labels/code) | Read |
|---|---|---|---|---|
| Vercel-school engineer | **Geist** (open source, Vercel) | Geist | **Geist Mono** | The current design-engineer default |
| Editorial + technical | **Instrument Serif** (Google Fonts) | **Instrument Sans** (Google Fonts) | JetBrains Mono | "Elegant and intentional… great for design portfolios" |
| Techy character | **Space Grotesk** (Google Fonts — "techy, distinctive personality… for developer tools") | DM Sans or Inter | IBM Plex Mono | Modern, slightly warm |
| Neutral-premium | **Satoshi** (free via Fontshare — "clean yet characterful") | Satoshi or General Sans (Fontshare) | JetBrains Mono | Startup-grade polish |
| Workhorse | **Inter** (variable) | Inter | JetBrains Mono | Safe; slightly commodity now — needs strong layout to not read default |

Notes: Neue Montreal is the paid startup favorite; Inter/Roboto Flex variable fonts remain the performance-safe baseline ([hueandeye](https://www.hueandeye.org/typography-trends-2025/)); Berkeley Mono (paid) and Departure Mono (free, "the 2025–26 indie standout, evoking 1980s computing") are the fashionable mono flexes ([madegooddesigns](https://madegooddesigns.com/best-monospace-fonts-2026/)). Monospace for nav/metadata/section labels is the tasteful dose of "terminal" — a full terminal cosplay is not.

### Layout & spacing habits (sourced numbers)

- Body 16px minimum; body line-height 1.5–1.6; headline line-height 1.1–1.2 ([adoc-studio typography guide](https://www.adoc-studio.app/blog/typography-guide), [greadme](https://www.greadme.com/blog/seo/best-font-sizes-for-readability-complete-guide)).
- Line length 50–75 characters, 66 the sweet spot → text max-width ≈ `38em` / `65ch` ([UXPin](https://www.uxpin.com/studio/blog/optimal-line-length-for-readability/)).
- Type scale ratio 1.250 (major third) or 1.333 (perfect fourth) for portfolios ([The Crit](https://thecrit.co/resources/typography-for-portfolios)); headings 1.3–1.6× body for subheads.
- Whitespace is load-bearing: it "reduces eye strain, defines content blocks per Gestalt principles, supports F/Z scanning" ([Locally Lost](https://locallylost.com/guides/typography-and-readability/)). The canon sites all use a narrow single column (~640–720px) with very generous vertical rhythm.
- Current border/surface language: 1px solid borders and sharp or single-radius geometry over blurred drop shadows ([Fireart](https://fireart.studio/blog/the-best-web-design-trends/)); commit to one radius identity site-wide (0px sharp / 1rem soft) rather than mixed defaults ([freedesignmd](https://freedesignmd.com/blog/shadcn-looks-generic)).
- Relative units (rem/em) for WCAG 200% zoom compliance.
- Page skeleton that recurs across the senior canon: name + one-line role → 2–3 sentence intro → selected work (2–4 items, each linking to a case study or live artifact) → writing (optional but high-signal) → now/about → contact. One column, no sidebar circus, footer with plain-text links.

---

## 7. Practical synthesis for this specific user

1. **Kill entirely**: animated rainbow gradients, glow text, particles, emoji in headings, "WELCOME TO MY UNIVERSE," skill bars, badge walls, typewriter effects. Every one of these appears on the documented amateur-tell lists above.
2. **Choose one of two proven directions**: (a) dark `#0a0a0a` monochrome + one accent, Geist/Inter + mono labels — the design-engineer look; or (b) warm off-white editorial with a serif display (Instrument Serif) — rarer among devs, strong taste signal. Game work (trailers, GIFs) supplies the color in both; the chrome stays neutral.
3. **Spend the personality budget on micro-craft, not macro-flash**: one signature interaction (à la Rauno's dock or Comeau's hidden details), hover states at 1.02 scale, view transitions — and stillness everywhere else.
4. **Rebuild content as 2–4 case studies** with problem/role/decisions/metrics and a "what I'd change" line; for games, GIF thumbnails + design-intent writeups.
5. **Match the GitHub profile**: short intro, pinned repos with real one-line descriptions, at most one theme-matched stat card, zero animated badges.
6. **Copy**: first person, ≤15-word identity line naming real domains and a real shipped thing; no "passionate," no "crafting," no coffee.

---

*Method note: direct fetching of the portfolio sites themselves was blocked by this environment's network egress proxy, so per-site descriptions are synthesized from multiple third-party design-curation and review sources (Awwwards, killerportfolio, pafolios, foleo, One Page Love, designengineer.fyi, ui.land, public GitHub repos) rather than first-hand page inspection; hex values are quoted only where documented in public repos or cited articles.*
