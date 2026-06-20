# Procestra website

Marketing site for the Procestra suite. **This `Website/` folder is its own git repo**, separate from the app code in the rest of `2026_Procestra/`. Commit web changes here, not in the parent.

## Deploy
- Host: **Netlify**, auto-deploys on **push to `main`** (remote: `Leafletherd/procestra-website`). `git push` is the deploy; there's no build step.
- `netlify.toml` sets `publish = "."`, security headers, and `application/xml` + 5-min cache headers for the appcast feeds.
- After favicon/icon changes, hard-refresh (⌘⇧R) — browsers cache favicons hard.
- Preview locally with headless Chrome: `"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" --headless --screenshot=/tmp/x.png --window-size=1280,2000 "file://$PWD/index.html"`. Use relative asset paths (`img/…`, not `/img/…`) so `file://` previews work.

## Structure
- Pages: `index.html` (home), `seed.html`, `espalier.html`, `provenance.html`, `privacy.html`, `contact.html`, `pricing.html`, plus internal `process_suite_brand_guidelines.html`.
- `img/` screenshots + app icons · `icons/` SVG marks for home cards · favicons/manifest at root · `sample/` a real exported Process Record (HTML + PDF) linked from the Provenance page.
- Each page carries its **own inline `<style>`** (no shared stylesheet) — when editing one app page, mirror the change across the others.

## The apps
Three local-first macOS apps. (Rebrand history: "Scene Board" → **Espalier**, "Works" → **Manifest**; Manifest isn't built.)

| App | Accent | Status | Buy URL (Lemon Squeezy) |
|---|---|---|---|
| Seed | clay `#C87B5A` | $19, live | `…/checkout/buy/9a4a27f5-c1a5-455c-a281-5d5f599131b7` |
| Provenance | teal `#1D9E75` | $29, live | `…/checkout/buy/96974ca5-ca9d-49e8-94a3-bb36257f5799` |
| Espalier | mauve `#A06878` | **not built** — notify form, no buy | `…/checkout/buy/0eb01a41-4ac9-420b-a8ea-c677c22bd297` (future) |

Suite logo circles (TL→clockwise): Seed clay, Espalier mauve, Provenance teal, Manifest slate `#5A6480`. Buy URLs change when LS products are recreated — use the latest the user gives.

## Design + copy conventions
- Palette: ochre-tan surface (`#F0E5CC`). Each app page sets a generic `--accent` to its app color. Fonts: Fraunces (headings) + DM Sans (UI).
- App pages use 1080px max-width (nav/hero/sections/footer aligned); home uses 860px. Reusable: `.feature-grid`/`.feature-card`, `.shot-frame`, `.trust-chip`.
- **No full-width dividers** except the one header rule under the nav. Section padding 3rem.
- **No em dashes anywhere** (hard user rule — use `.`, `,`, `:`, or `·`). Warm, unhurried tone; brief and visual over paragraph-heavy; don't invent facts (use `[CONFIRM …]` placeholders and flag).
- SEO on the four main pages: titles, meta descriptions/keywords, OG/Twitter tags, JSON-LD, `sitemap.xml`.

## Netlify notify forms
Pattern: a hidden detection `<form name="notify-*" data-netlify="true" netlify-honeypot="bot-field" hidden>` near `<body>`, visible `.notify-form` forms, and a small JS handler. Currently only **Espalier** (and home `notify-suite`) use forms; Seed/Provenance use buy buttons.

## Sparkle auto-update (appcasts)
- Feeds served from here: `appcast-provenance.xml`, `appcast-seed.xml`, `appcast-espalier.xml` → live at `procestra.app/appcast-*.xml`. **The appcast is the source of truth, not the bucket.**
- DMGs on Cloudflare R2: `https://pub-df65c2e764ca4985aed9f3e6d775dcf1.r2.dev/<app>-downloads/<App>-<ver>.dmg` (this `*.r2.dev` URL is used as production by choice).
- **Shared EdDSA key across all apps (intentional):** `SUPublicEDKey = mo0o7kL086SRjjyTW1HabtgP0ep5ECR7biu30ZmTwEQ=`. Don't generate new keys.
- **Ship a version:** in the `<item>`, bump `sparkle:version` (integer build — this triggers the update), `shortVersionString`, `pubDate`, the enclosure `url`, and `edSignature` + `length` (from `sign_update` on the new DMG; byte-specific). Then deploy. Before deploying, verify: `curl -sI <dmg-url>` is `200` and `content-length` equals the appcast `length`.
- Current: Provenance + Seed at **1.0.1 (build 2)**, live. Espalier appcast is a not-live placeholder. App-side runbooks: `../Provenance/RELEASE.md`, `../Provenance/UPDATES.md`.

## Open items
- Appcast 1.0.1 release notes are a generic placeholder — swap in a real changelog when available.
- Espalier: when built, capture real screenshots (currently a CSS "bench" mock), switch notify→buy, fill its appcast.
- Some unused/dead CSS remains on a few pages (harmless).
