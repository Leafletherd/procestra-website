---
id: WEB-1
target: Website
status: shipped
date_drafted: 2026-05-15
date_shipped: 2026-05-15
depends_on: []
supersedes: []
summary: Procestra.app copy refresh — new tagline candidates, per-app blurbs (short + medium), updated privacy page (paste tracking, hash chain, local-first), pricing page draft, footer copy, Stories/Tutorials section concepts.
---

# WEB-1 — Procestra.app copy refresh

**Read first:** `/Users/zacharycoak/Documents/AppDev/Procestra/Assets/Brand/BRAND_VOICE.md` is the canonical voice spec. Every piece of copy in this prompt is informed by it. When in doubt about phrasing, check that document — it specifies what we say, what we don't, and what tone we hold.

This is a copy brief, not a structural redesign. The website's existing one-page layout stays for now. The job is to make every piece of text on it actually represent the brand.

---

## (1) Tagline / lead pitch

The site needs a strong line at the top. Below are five candidates. Pick one, or use them to inform a new direction. **Do not commit to one without confirming with the user.** Surface the choices and the trade-offs.

### Candidates

**A. "Quiet tools for thoughtful makers."**
- Distills the brand in five words
- "Quiet" carries calm/anti-hustle
- "Thoughtful" defines the audience
- "Makers" is the canonical word (not "creators")
- Risk: maybe too sparse, doesn't say what the tools ARE

**B. "A suite for the process of making."**
- Process-forward (the suite's defining angle)
- "Suite" makes the four-app nature visible
- Slightly more functional
- Risk: less evocative

**C. "Honor your process."**
- Two words, direct
- Verb-driven (active)
- Resonates with Provenance specifically
- Risk: imperative voice could feel preachy

**D. "Four tools for the work behind the work."**
- Names the quantity (four = scale of the offering)
- "Work behind the work" is the process angle, said differently
- Slightly poetic without being precious
- Risk: a bit longer

**E. "Local-first tools for the long work of making."**
- Names a technical differentiator (local-first)
- "Long work" carries the slow/considered ethos
- Risk: "local-first" is jargon for non-developers

**My honest pick:** **A or D**, leaning A for headline use and D for an immediate subhead.

### Suggested treatment

If headline + subhead:
```
[A. as headline, ~48pt Playfair Display]
Quiet tools for thoughtful makers.

[Subhead, ~16pt System]
Four native Mac apps for the long, careful kind of creative work —
making ideas, structuring stories, tracking your process, and
sharing the finished thing.
```

If single line: A alone, with the per-app row directly below.

---

## (2) Per-app blurbs

Each app needs three lengths of copy ready for different surfaces.

### Short (the one-liner, for the homepage grid)

**Seed** — *A garden for ideas. Plant them. Let them grow. Transplant the ones that take.*

**Scene Board** — *Where stories find their shape. Beats, scenes, structure — flexible, visual, yours.*

**Provenance** — *The quiet ledger of how a project gets made. Every save, every source, every paste — recorded.*

**Works** — *Your portfolio, on your terms. Local-first. Polished without polish you didn't ask for.*

### Medium (1–2 paragraphs, for app detail sections)

**Seed**
> Seed is a local-first home for ideas before they become projects. Plant short notes whenever a thought lands. Refine them on the bench, a working surface for comparing and arranging. When an idea takes root, transplant it into Scene Board to give it structure — and Provenance will remember the seed's whole life: when you planted it, the edits, the merges, the moment it became part of a project.
>
> Markdown bodies, full git history, no accounts, no cloud. Just you, your ideas, and a tool that keeps up.

**Scene Board**
> Scene Board is a kanban-meets-storyboard for writers, filmmakers, and any maker whose work has shape. Start with a structural template — Save the Cat 40-beat, Hero's Journey, Story Circle, Three-Act — or work free-form on a 2D canvas with optional grid snap. Group beats into containers. Color-code cards. Link related cards across the board.
>
> Whether you're outlining a screenplay or planning a multi-month project, Scene Board gives you the structure you need without forcing the structure you don't want.

**Provenance**
> Provenance watches a project quietly while you work. It snapshots your files, records the sources you cite, logs the pastes you make (including pastes from AI sites, transparently), and lets you check in with yourself about how the work is going. The result is a complete record of how something got made — the kind of receipts that prove the work behind the work was actually yours.
>
> Local-first by design. Nothing leaves your machine unless you tell it to. No accounts, no telemetry, no surveillance. Just a careful record of your own process.

**Works**
> Works is the curation surface for things you've finished. Add a folder, point Works at the work inside it, and let it generate a portfolio site — Editorial, Gallery, or Cinema templates, with optional behind-the-scenes pages drawn from the project's Provenance ledger.
>
> The output is a portable static site you can host anywhere, share by zip, or open from your USB drive. No accounts, no platforms, no analytics. Just your work, presented well.

### Long (for individual app pages or marketing posts — write these later, not in this prompt)

Each app gets its own page in v2 of the site. Out of scope for this prompt; queued for after launch.

---

## (3) Privacy policy page

This is the most important page to update. Procestra's brand is local-first, transparent, no surveillance — the privacy page is where that promise is concrete.

**Replace whatever is currently on the privacy page** with the copy below. Adjust wording for grammar/flow but preserve the *substance* and the *plainness*.

### Suggested page structure

```
Privacy

We built Procestra to respect the way you work. This page tells you
exactly what each app does with your data — in plain English, not
legalese.

What stays on your machine
─────────────────────────

Everything. All four Procestra apps are local-first. We do not have
servers that store your work. There is no Procestra account. There
is no syncing through us. There is no analytics service we send
information to.

When you write a seed in Seed, edit a board in Scene Board, save a
file inside a Provenance-tracked project, or add a work to a Works
library — those actions touch files on your Mac and nothing else.

Cloud-synced files
──────────────────

If you keep your project folders in iCloud Drive, Google Drive
(Desktop), Dropbox, or another file-syncing service, Procestra
treats them like any other local file. The cloud service does its
own syncing; we don't know about it.

If a document lives only in a browser (a Google Doc you only edit on
the web, for instance), Procestra cannot track it. There is no local
file for us to watch.

What Provenance specifically records
───────────────────────────────────

Provenance is the most data-rich app in the suite. Here's exactly
what it logs, in your project's local .ledger folder:

  · File saves — when a tracked file changes, we record a timestamp
    and a git snapshot.
  · Check-ins — short reflections you type into the app yourself.
  · Sources — URLs, files, or passages you choose to log as references.
  · Artifacts — supporting material (scanned notes, images) you
    explicitly add.
  · Paste sources — when you paste into a tracked file, we record:
      - a SHA-256 hash of the pasted content,
      - the first 64 characters as a preview,
      - the source URL (if pasted from a webpage or app that
        provides one),
      - the source app (if known).
    Full pasted content is never written to disk. The 64-character
    preview helps you remember what was pasted; the hash lets us
    verify provenance later.

You can turn off paste tracking at any time in Settings.

What we don't record
────────────────────

  · Keystrokes — Provenance does not record what you type or how
    fast. There is no keystroke log anywhere.
  · Screen activity — no screenshots, no screen recording, no
    window-focus tracking.
  · Webcam or microphone — never accessed.
  · Browsing history — Provenance does not look at your browser.
    The paste tracker only records information from clipboard events
    that originated from a paste action you performed in a tracked file.

The hash-chained ledger
──────────────────────

Provenance's event log is hash-chained — each event includes a
SHA-256 hash derived from the previous event. If anyone modifies the
log retroactively (including you), the chain breaks visibly. This
is a feature for the user: it lets you prove your own process
honestly. It is not a system Procestra monitors or sees.

You can verify the chain yourself. The documentation explains how.

Your data, your machine, your choice
───────────────────────────────────

Procestra has no ability to access your data because there is no
Procestra server holding it. You can:

  · Delete a .ledger folder at any time — Provenance forgets.
  · Disconnect a project — the data stays on disk; we stop watching.
  · Move your files anywhere — Procestra uses macOS bookmarks to
    follow them.
  · Export everything — Provenance exports as Markdown, PDF, or a
    structured .provenance.bundle/ for portability.

What our website does
─────────────────────

This website (procestra.app):

  · Doesn't use analytics services like Google Analytics or
    Plausible. We don't track visits.
  · Doesn't set cookies for tracking.
  · Doesn't include third-party ad or marketing scripts.
  · The beta signup form stores email addresses in a flat list we
    use to email you about Procestra updates. We will not share or
    sell that list. You can ask us to remove your address at any
    time.

If anything here changes
────────────────────────

We'll update this page and date it. We won't change the substance
of the privacy promise without a clear note explaining what changed.

Last updated: [today's date when published]
```

The page should be plain, scannable, free of legalese. The tone is "an honest person explaining how the thing works," not "a lawyer covering the company."

---

## (4) Pricing page

The pricing structure (decided in earlier conversations) — verify with the user before publishing actual numbers, but draft the page with this content:

```
Pricing

Procestra is paid software. We chose pricing that reflects the kind
of tool this is: bought, owned, used carefully, kept for a long time.

The Suite
─────────

  $40 / year         All four apps, all updates that year
  $99 lifetime       All four apps, all current and future updates
  $5 / month         All four apps, monthly billing

The annual purchase is the most popular path. The lifetime option
is the most honest one — you buy it, you own it, you keep it.

Individual apps
───────────────

If you only want one:

  Seed only          $20 lifetime
  Scene Board only   $25 lifetime
  Provenance only    $35 lifetime
  Works only         $25 lifetime

Why a subscription option?

Because some people prefer it, and we like to give the choice.
Most makers will be better served by the lifetime purchase.
The monthly is for trying things out and for people whose
relationship with software is short-term.

How licenses work
─────────────────

Your license is per-person. Use Procestra on your own Macs (all of
them). When the apps check whether your license is valid, they ask
our license server once, then save the answer locally. After the
first check, the apps work offline forever.

We don't lock features behind tiers. Whatever apps your license
covers, you get the full app.

What about updates after the year ends (annual plan)?

Your apps keep working. You stop getting new versions. Renew if
you want updates; don't if the version you have is enough. Either
way, no app you've used stops functioning.
```

**Note:** the license-server line is forward-looking. If the licensing system isn't built yet, soften to "We're building licensing now; before launch this page will describe how it works." Don't promise something not yet implemented.

---

## (5) Footer copy

The current footer (if any) should be replaced with:

```
Made by Zachary Coak in [city — if you want to name one; otherwise omit].
Procestra is a small, independent project.

procestra.app
```

No social media icons. No "© 2026 Procestra LLC. All rights reserved." (boilerplate). No "Powered by [framework]" credits.

If you want a copyright line for legal safety, the smallest possible:
```
© 2026 Procestra
```

That's enough.

---

## (6) Stories / Blog section (concept — not built yet)

Add a placeholder section on the homepage between the apps and pricing:

```
Stories

We'll publish occasional notes here — on how the apps were built,
on creative process in general, and on what people are making with
Procestra. Coming soon.
```

Or just a "Subscribe for posts" form that goes to the same email
list as the beta signup, marked "blog posts" so we can segment
later.

Don't build the actual blog yet. Just hold the space.

---

## (7) Tutorials / Walkthroughs section (concept — not built yet)

Same treatment as Stories:

```
Tutorials

A library of short, focused tutorials is on the way. Until then,
each app's README in the project root walks through the basics.
```

Or link to a Notion / GitHub page if you've started drafting walkthroughs there. Don't build the tutorial page if there's nothing yet — empty pages read worse than no page.

---

## (8) Beta signup copy

If the beta signup form is still on the site, update its copy:

```
Be a Procestra Beta tester

We're sending early builds to a small group of makers. If that's
you, drop your email and we'll be in touch when we have something
worth showing.

[email field] [Join the beta]
```

Same form as today (just a list-add). No marketing-y "join the
revolution" copy. Just plain.

---

## (9) "What is Procestra?" section

If the homepage has an above-the-fold explainer (it should), it
should be 1–2 paragraphs:

```
Procestra is a suite of four native Mac apps built around how
creative work actually gets made: Seed for ideas, Scene Board for
structure, Provenance for process, Works for the finished result.

Local-first. No accounts. No subscriptions you can't escape from.
No surveillance. Built for makers who care about the long, careful
kind of work — and want their tools to reflect that.
```

If the site already has this section, replace it with the above. If
not, add it directly under the tagline.

---

## What NOT to include on the site

Per BRAND_VOICE.md §9, these are not part of how we talk about
Procestra:

  · User counts ("trusted by 10,000 writers")
  · Press logos or "as seen in" rows (we don't have any yet, and we
    don't want to be that)
  · Testimonials with photos (corporate-feeling)
  · Founder photos / mission-statement-y blocks (it's a small
    project; don't inflate)
  · A "vision" page
  · A roadmap page (we have plans, but they're not public-facing)
  · Comparison tables with competitors (Notion, Things, etc. — not
    our story to tell)
  · "AI-powered" anywhere, ever
  · A FAQ that goes on for 30 questions — keep it to 5 or fewer
    actual questions if you have one

---

## Verification

After applying these edits, verify:

  · The site reads as one person made it (it did)
  · Every word checks out against BRAND_VOICE.md
  · The privacy page is the most-careful page on the site
  · The footer doesn't include analytics, social, or boilerplate
  · The tagline (whichever was picked) appears prominently
  · No hype words snuck in (revolutionary, disrupt, AI-powered,
    seamless, empower, game-changing, next-generation)

If anything in the brief above contradicts BRAND_VOICE.md, the
voice doc wins — flag the conflict and we'll resolve it.

When shipped, update this file's frontmatter `status: shipped` +
`date_shipped`, and update `Procestra/Assets/Brand/PROMPT_LOG.md`.
