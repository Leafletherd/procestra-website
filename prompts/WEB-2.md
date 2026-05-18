---
id: WEB-2
target: Website
status: drafted
date_drafted: 2026-05-17
date_shipped: null
depends_on: ["WEB-1"]
supersedes: []
summary: Homepage pitch overhaul — screenshot in hero, audience eyebrow, trust strip, per-app detail sections, pipeline diagram concept.
---

# WEB-2 — Homepage pitch overhaul

**Read first:**
- `/Users/zacharycoak/Documents/AppDev/Procestra/Assets/Brand/BRAND_VOICE.md`
- `/Users/zacharycoak/Documents/AppDev/Procestra/Assets/Brand/COPYWRITING_STANDARD.md`
- `/Users/zacharycoak/Documents/AppDev/Procestra/Assets/Brand/SUITE_PHILOSOPHY.md`

This prompt is a structural redesign of the homepage, not just a copy pass. WEB-1 got the words right. WEB-2 gets the pitch right: what the page shows, in what order, with what hierarchy. The goal is a landing page that communicates the suite's value in a 10-second scroll.

**Reference:** Repertoire HQ (repertoirehq.com) was cited as a good example of this kind of pitch. Study what it does well:
- Product screenshot in the hero answers "what is this?" before any headline
- Eyebrow label "For singers & musicians" qualifies the audience instantly
- Feature cards are scannable: icon, title, one-sentence description
- Trust strip at the bottom of the hero provides fast factual orientation

Do NOT copy Repertoire's visual language. Procestra has its own — ochre palette, Fraunces headings, ink-on-parchment feel. The lesson is structural, not aesthetic.

---

## Prerequisites (blocking)

This prompt cannot ship without at least one app screenshot. Do not build the hero image slot and leave it empty. Either:
- **Option A:** A real screenshot of Provenance's ledger view, or Seed's garden view, cropped cleanly and sized at 2× for retina. This is the preferred path.
- **Option B:** A composed mockup showing the 4-circle mark at a larger size, styled to suggest the product without faking it.

Before implementation, confirm with the user which option to use and get the image file. The rest of the prompt describes the full design so the implementation session can work with full context, but the image slot is required before anything ships.

---

## 1. Hero section

### Current state
The hero is all text. Tagline, two sentences, email form. No image. No audience qualification.

### Target state

```
[Eyebrow label — small pill or text, ochre-600]
For writers, filmmakers, and makers.

[H1 — Fraunces, large, ink]
Quiet tools for thoughtful makers.

[Sub — DM Sans, ink-60]
Four native Mac apps. They carry a project from first idea to
finished portfolio. Your files stay on your machine throughout.

[App screenshot — right side, or centered below on mobile]
[One real screenshot: Provenance ledger, or Seed garden]

[Beta form — unchanged from current]
```

### Layout
On desktop: two-column split. Left: text + form. Right: screenshot.
On mobile: stacked — text → screenshot → form.

The screenshot should float slightly, with a light drop shadow and perhaps a subtle border matching `--border`. No device frame (phone mockup frame) unless the app is iOS-only; these are Mac apps.

### What changes from current
- Add the eyebrow label. "For writers, filmmakers, and makers." Keep it honest and specific without being exhaustive. Update the list when the audience understanding sharpens.
- Add the image column.
- The form and beta copy stay as-is — WEB-1 copy is correct.

---

## 2. Trust strip

Below the hero (full width, between hero and rule), a horizontal band of four short factual bullets separated by dots or light dividers:

```
Local-first  ·  No accounts  ·  Native Mac  ·  Four apps, one pipeline
```

Style: very small (10–11px), `--ochre-600` text, `--ochre-50` or `--border` background, generous padding. Think of the ticker bar at the bottom of the Repertoire page, but more restrained.

This should feel like a factual orientation, not a marketing claim. Every item here should be something you can verify in five minutes of using the app.

Don't add social proof ("trusted by X makers"). Per BRAND_VOICE.md §9, we don't use user counts as signals.

---

## 3. "What is Procestra" section

Current content is a good starting point — keep it mostly as-is. This section is working. One structural improvement: add a visual representation of the pipeline (Seed → Scene Board → Provenance → Works) before or inside the section.

### Pipeline diagram concept

A simple horizontal flow: four circles (reusing the brand mark's four colors) connected by thin arrows, each labeled with the app name and a four-word role below it.

```
● Seed          →    ● Scene Board    →    ● Provenance     →    ● Works
  Ideas start here     Structure follows     The work records      Show the result
```

This communicates the pipeline metaphor without prose. It also ties each circle to the brand mark.

Implementation: SVG or pure CSS. Don't use an image. Should be responsive — on narrow viewports, stack vertically.

---

## 4. The apps section (expanded)

Currently: a 4-column grid with icon, name, tagline, one-sentence description. This is good for scanning but thin on persuasion. The next step is per-app sections with richer descriptions.

### Two options — pick with the user before implementing

**Option A — Expanded cards (lower effort)**
The 4-column grid grows to 2-column at ~860px or wider, with each card getting the medium blurb from WEB-1 §(2) instead of the short one. The grid structure stays; the content gets richer. This is the minimal version.

**Option B — Per-app sections (higher effort, stronger pitch)**
Four full-width sections below the grid, one per app. Each section has:
- The app's accent color as a left border or top border accent
- The app's medium blurb (from WEB-1 §(2))
- An optional screenshot or interface detail
- A callout of 1–2 specific features (written concretely, per COPYWRITING_STANDARD §4.2)

Example Provenance callout:
```
The paste tagger
When you paste into a tracked file, Provenance records the source
URL, the source app, and a 64-character preview. The actual content
never hits disk. You get a receipt. Nobody else does.
```

Option B is the right target when the apps have screenshots worth showing. Option A is the right move now if WEB-2 ships before the apps are polished enough for screenshots.

**Recommendation:** Ship Option A first. Queue Option B as WEB-3 once per-app screenshots exist.

---

## 5. Navigation improvements

Current nav: wordmark + Privacy + Contact. This is correct for an early beta page with limited pages.

When WEB-2 ships, consider whether any of these make sense to add:
- A "Download" or "Get early access" CTA link in the nav (once there's something to download or a TestFlight link)
- Nothing else — the nav is deliberately minimal per BRAND_VOICE.md

Do not add: a "Blog" nav link (until Stories posts exist), a "Docs" link (until documentation exists), social media icons (per SUITE_PHILOSOPHY.md), or a Pricing link (it's a placeholder page).

---

## 6. What stays the same

- The ochre palette, Fraunces headings, DM Sans body — unchanged.
- The beta signup form — unchanged. WEB-1 copy is correct.
- Footer: `© 2026 Procestra` | `Privacy · Contact` — unchanged.
- Max content width: 860px for the main landing, 680px for inner pages — unchanged.
- Privacy, Contact, Pricing pages — unchanged.
- No analytics, no tracking, no third-party scripts — unchanged.

---

## 7. What to avoid (from Repertoire reference)

Repertoire does some things Procestra explicitly should not do:
- Bold colored CTA buttons with App Store / Google Play — we're Mac-only, no mobile apps.
- Multi-column nav with Features / How it works / Pricing / Sign in / Download — too SaaS-y for this brand. Keep the nav minimal.
- Any "Social proof" section ("X thousand musicians trust Repertoire") — explicitly off-brand per BRAND_VOICE.md §9.
- Any "testimonials with photos" block — off-brand.
- Heavy use of the accent color (their magenta/pink) as a background color — Procestra's accent is more restrained; backgrounds stay ochre.

The Repertoire influence should stop at the structural lesson: show the product, qualify the audience, make features scannable. The visual and tonal execution is entirely Procestra's own.

---

## 8. Acceptance checklist

Before marking shipped, verify:

- [ ] Hero has an image (screenshot or approved mockup — not a placeholder)
- [ ] Eyebrow label identifies the audience
- [ ] Trust strip is present and contains only verifiable facts
- [ ] Pipeline diagram renders correctly at desktop and mobile widths
- [ ] App section uses either Option A or Option B (confirm with user before implementing)
- [ ] No em dashes anywhere in copy
- [ ] No words from COPYWRITING_STANDARD §1.2 banned list
- [ ] No "not X but Y" constructions
- [ ] The page reads aloud in under 90 seconds for the above-the-fold content
- [ ] Netlify form still works after structural changes (test a submission)
- [ ] No regressions on Privacy, Contact, or Pricing pages

---

## Notes for the implementation session

- The image for the hero must come from the user before you begin layout work. Do not improvise a placeholder.
- The pipeline diagram should be built in HTML/SVG, not as an image — it needs to be responsive.
- If the user chooses Option B (per-app sections), source the medium blurbs from `WEB-1.md §(2)` — they are already copywriting-standard-compliant.
- Keep the beta form's Netlify attributes exactly as-is (`name="beta-signup"`, `data-netlify="true"`, honeypot). Moving it in the layout should not break form detection.

When shipped: update this file's frontmatter (`status: shipped`, `date_shipped`), and add a row to `Procestra/Assets/Brand/PROMPT_LOG.md`.
