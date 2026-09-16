# Web design & conversion playbook

Distilled 2026-09-16 from a set of Claude Code skills (`high-converting-hero`,
`conversion-page-structure`, `conversion-copywriting`, `believable-social-proof`,
`cognitive-ease`, `premium-design-polish`, `cro-audit-and-testing`, `web-perf`,
`building-gohighlevel-websites`, `site-teardown`, `funnel-spy`) so a tool that can't read Claude
skill files — Codex, or any other coding agent — still gets the operative rules.

**How to use this file:** drop it into a project's own `AGENTS.md` (append it, or paste its
content in), or point any agent's global instructions file at it. It applies to any task that
builds, redesigns, audits, or writes copy for a website, landing page, or funnel page. It's also
kept live at `~/.codex/AGENTS.md` on the machine it was written on, appended into that machine's
existing global Codex instructions — if the source Claude skills change, that copy (and this one)
can go stale, so re-derive from `~/.claude/skills/{high-converting-hero,
conversion-page-structure,conversion-copywriting,believable-social-proof,cognitive-ease,
premium-design-polish,cro-audit-and-testing,web-perf,building-gohighlevel-websites,site-teardown,
funnel-spy}/SKILL.md` rather than trusting either copy is current.

## Priority: the fold is the project

Roughly 60% of visitors never scroll past the first screen, and visitors form an opinion in
about 50ms (the halo effect — a clean first screen makes everything below it more believable; a
cluttered one poisons it). Spend 80-90% of design and copy effort above the fold before touching
anything else.

**The five hero elements, and little else:**
1. **Headline** — the dream outcome, not the company name or category. Find it with the "so
   that" ladder: keep asking "so that..." until reaching what the buyer actually wants (exterior
   cleaning → so panels produce more energy → so the bill drops → so the owner trusts the
   investment worked — headline the end of that chain). Never open with vague positioning, the
   company name, or a category label.
2. **Subheadline** — clarifies the headline and removes the sacrifice ("without X, Y, Z").
3. **One CTA, one action.** Lightweight verbs beat commitment verbs ("Start my free trial" beats
   "Subscribe"). First person ("my," not "your"). A number kills uncertainty ("Start in two
   taps"). Show the total beside the button for purchases.
4. **Hero image that proves the headline, not decorates it.** Show the outcome, not an abstract
   mood shot. Real product screens beat illustration. If using AI-generated imagery: prompt from
   the "so that" ladder's endpoint, match lighting/treatment to the rest of the page, and
   disclose it wherever the buyer's trust depends on authenticity (a specific client result, a
   real person's likeness) — never pass a generated "customer" off as a real testimonial subject.
   Optional scroll-effect polish (parallax, scroll-scrub): never animate the LCP image itself
   (ship it visible immediately), prefer CSS `scroll-timeline`/`transform` over heavy JS
   libraries, respect `prefers-reduced-motion`, and test on a throttled mid-range phone.
5. **Trust elements** — one strong proof element and a risk-reversal line (guarantee, free
   cancellation, "no card required") directly under the CTA.

Five-second test before shipping any hero: show it for 5 seconds, then ask — what does this do,
who is it for, what do I do next, why now? Any fuzzy answer fails; fix before touching anything
below the fold.

## Page structure: Problem → Promise → Proof → Action

Visitors move top to bottom and judge each section against the question in their head at that
moment. Default skeleton (cut what the offer doesn't need — every section must survive "is this
critical for conversion?"):
1. Above the fold (see hero elements above)
2. Proof strip — logos/review count/stat bar directly under the hero
3. Problem — name the pain or open question
4. Promise/solution — benefit-led, one idea per block
5. How it works — 3-4 steps max, never 5+ (each step raises perceived effort)
6. Proof wall — stacked social proof mapped to real objections, grid on desktop / stacked on
   mobile, **never a carousel** (low engagement, hidden proof doesn't exist to the visitor)
7. Objection handling — the specific fears that remain
8. Final CTA — restate outcome + risk reversal, one button

Section headers must carry the value proposition, not a label: "Testimonials" →
"312 gyms doubled their leads with this system." Strip navigation to logo + one CTA on any
dedicated landing page. One goal, one CTA, no competing destinations.

## Copywriting: turn hard questions into easy ones

Every element asks the visitor a question; hard questions ("is this worth $19/mo?") get
"I'll think about it later," which means never. The value equation: perceived value rises with
**dream outcome** and **likelihood of success**, falls with **time delay** and **effort** — every
line should push one of those four levers (compress time where truthful: "in 7 days"; reduce
effort: "without cold calling, we handle setup").

- Assume visitors read only headlines (roughly 90% of winning A/B tests are headline or image
  tests). Write at a 5th-8th grade reading level. Specific beats generic ("delivery in 23
  minutes" beats "fast delivery").
- Transparency as persuasion: proactively stating a downside raises trust ("Day 5: we remind you
  before your trial ends" outsells feature bullets, because it proves there's no trap).
- Never ask for commitment before value is demonstrated. Never use a claim with no number, no
  timeframe, no mechanism.

## Believable social proof

A text quote with no name is furniture. Each of these compounds believability: evidence of the
actual result (photo/video beats a sentence), full name + photo, a verifiable source (Google,
Trustpilot, a LinkedIn profile), specific numbers, a one-line story of context. Rank, most to
least believable: video testimonial of the result > photo evidence + named written review >
screenshot proof > written review with name/photo/source/numbers > name only > anonymous quote
(avoid — can lower trust).

Map proof to actual objections (will it work for my industry? for a business my size?) rather
than showing generic praise — generic proof impresses without persuading. Put risk reversal
(guarantee, free cancellation) directly under every CTA, at the moment of decision, never buried
on a policy page.

## Cognitive ease: reduce the mental cost of every screen

- One CTA per page. Every removed form field is a conversion gain (3-field forms convert roughly
  2x over 9-field forms) — ask only what the immediate next step needs.
- Prices: one number, not a range (ranges read as risk). Anchor with a crossed-out reference
  price. Show the full total at the decision point, beside the button.
- Visual hierarchy: if everything is emphasized, nothing is. Consistent imagery treatment and
  rhythm let the eye predict where the next piece of information lives.
- Check mobile first — it's the majority of landing-page traffic.

## Premium visual craft

Two typefaces max, one dominant brand color + one accent used sparingly. Stylistic unity across
imagery beats individually-beautiful mismatched stock. Motion signals craft but only when
purposeful (reveal in reading order, animate the product doing its job) — heavy/janky animation
costs more in conversions than it gains in polish; pages loading in ~1s convert roughly 3x better
than 5s pages.

## Core Web Vitals — hard targets, not vibes

Target the "good" threshold at the 75th percentile, mobile and desktop, for **LCP** (Largest
Contentful Paint), **INP** (Interaction to Next Paint), and **CLS** (Cumulative Layout Shift).
Current numeric thresholds move — check `https://web.dev/articles/vitals` rather than trusting a
stale number here. Rules that don't go stale:
- Never lazy-load the likely LCP element; resize/compress every image before upload; reserve
  intrinsic space (width/height or `aspect-ratio`) to prevent layout shift.
- Ship the LCP resource early and never animate it in.
- Limit font variants, defer non-critical scripts, remove unused CSS/JS.
- Measure the canonical public URL after deploy, not just a local/staged build — lab scores
  (Lighthouse) and field data (Search Console Core Web Vitals report) answer different questions.

## Technical SEO checklist (verify all, every indexable page)

Meta title (unique, descriptive) and meta description written for the result, not a character
quota · alt text on every image (empty `alt=""` for decorative ones, never keyword-stuffed) ·
exactly one `<h1>`, logical H2-H6 order · concise descriptive URL slugs · purposeful internal
links with useful anchor text · one absolute self-consistent canonical tag · enforce HTTPS site-
wide, no mixed content · `og:title`/`og:description`/`og:image` (absolute URL, real image, not a
placeholder) + Twitter Card equivalents, validated with each platform's inspection tool ·
schema/JSON-LD matching visible content exactly, one graph per page, no duplicate owners ·
`robots.txt` allowing intended crawling · `noindex` (not `robots.txt` alone) for anything that
must not appear in search · XML sitemap with only canonical, indexable URLs, submitted to Search
Console · verify a Search Console property · audit for broken links/404s and fix or redirect them
(no chains, no loops).

**Backlinks are a separate, off-page workstream** — a technically flawless page with no external
authority still under-ranks a weaker page with real backlinks behind it. Legitimate sources only:
earned press, relevant industry directories, partner cross-links, citation-worthy original
content. Never buy links or use link farms/automated submission — this risks a manual action.
Exhaust internal link equity first; it's free and fully controlled.

## Ongoing CRO program

Doubling conversions beats doubling traffic (every future visitor benefits, traffic gains don't
compound). Audit first for the obvious gaps above, establish baseline conversion rate and traffic
level, then: test one variable at a time, above the fold first, weekly cadence; roll winners into
the control and repeat.

## Competitive teardown workflow (reverse-engineering another site)

When asked to analyze how a competitor's site/page was built, or to reverse-engineer one, run
this directly with shell access — no special tool required:

1. **Fetch the real HTML.** `curl -sL --compressed --max-time 30 -A "Mozilla/5.0 ..." "<URL>" -o
   /tmp/teardown-page.html`. Read/grep it for section class names, image/video src paths, SVGs,
   meta tags, every `<script src>` and `<link rel=stylesheet href>`. Only fall back to an
   in-agent fetch tool if curl 403s or returns an empty SPA shell.
2. **Find the main JS/CSS files** (paths under `/dist/`, `/build/`, `/assets/`, named
   `main.js`/`app.js`/`bundle.js`) — skip GTM/analytics/consent/CDN-library/WordPress-core
   scripts, they're not the site's own code.
3. **Fetch and grep those files locally** (`curl` to disk, then grep for signal before reading):
   `grep -onE "gsap|ScrollTrigger|scrub|IntersectionObserver|Lenis|locomotive|barba|swup|
   quickSetter|--[a-z-]+|cubic-bezier|stagger|SplitText|marquee|parallax" app.js` for behavior;
   `grep -onE "--[a-z0-9-]+:|@font-face|@keyframes|@media|#[0-9a-fA-F]{3,8}|clamp\(|
   backdrop-filter|clip-path|cubic-bezier" style.css` for the design system.
4. **Assemble a teardown doc**: confirmed tech stack (with the evidence — a script tag, an actual
   code reference, not a guess), the full design system (colors, type, spacing, breakpoints),
   an effects table (implementation + how hard to clone), and a section-by-section build plan
   with a recommended stack and npm packages. Be specific ("GSAP ScrollTrigger, scrub:true,
   pinned to .hero, scaling 1→0.3"), not vague ("uses scroll animations"). Distinguish confirmed
   (found in source) from inferred (guessed from class names/patterns).
5. Common "impressive but simple" patterns to recognize: image sequences swapped on
   scroll/mouse (looks like video, it's just frames), SplitText character staggers, parallax as
   different transform multipliers per layer, a noise overlay as a fixed div with
   `mix-blend-mode: overlay`, magnetic buttons as mousemove + transform.

For a whole competitor **funnel** (not just one page's build) rather than its code: walk every
page a stranger sees to checkout, note the offer ladder and prices, check ad libraries (Meta Ad
Library, TikTok Creative Center) for whether they're running paid traffic, identify the tracking
pixels/software running the funnel from page source, and score it against real gates (clarity of
offer, friction in the path, proof present, urgency/scarcity legitimacy) rather than vibes.
Report gated/unknown numbers as estimates, never as confirmed facts.

**Ethical/legal line, both workflows:** studying structure, tech stack, and technique to build
your own version is normal competitive practice. Copying their actual code, copyrighted copy or
images verbatim, or accessing anything behind a login/paywall is not — treat a teardown as
research input, never as content to reproduce.

