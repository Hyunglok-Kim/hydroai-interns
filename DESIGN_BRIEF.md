# Design brief — v0.dev prompt pack

Use this to redesign the HydroAI Lab Summer 2026 intern hub on
[v0.dev](https://v0.dev). Each section below is a **drop-in prompt** for v0.
Generate one page at a time — v0 produces React + Tailwind + shadcn/ui — then
either (a) keep it as a Next.js site, or (b) export the static HTML and replace
the mkdocs site (see "Integration" at the bottom).

---

## :material-palette: Brand / mood (paste as the first prompt to v0)

```
I'm designing a static research hub for the HydroAI Lab's Summer 2026 intern
cohort. The lab combines deep learning with satellite remote sensing of the
global water cycle — soil moisture, precipitation, land-atmosphere coupling.

DESIGN DIRECTION
- Modern, slightly futuristic "AI x satellite Earth observation" feel.
  Think: Stripe meets NASA JPL meets a quiet science journal.
- Dark-mode-first (deep navy / near-black background, ~#0a1014).
  Light mode is a bonus, not required.
- Primary accent: cyan / teal (#22d3ee or similar). Use sparingly — gradients
  on hero, hover states, key numbers. The rest of the page is neutral.
- Subtle Earth-observation cues — faint grid overlays (lat-lon-style),
  thin radial gradients suggesting a globe or radar sweep, monospace numerics.
  NEVER cartoonish space art, no astronauts, no clip art.
- Typography: Inter for UI text, JetBrains Mono for code/numbers.
  Generous letter-spacing on small caps labels.
- Layouts breathe. Lots of whitespace. Single-column on mobile, generous
  multi-column on desktop (max-width ~1200px).

DO NOT
- No emoji decorations
- No cliché "AI brain" or "circuit board" illustrations
- No oversaturated rainbow gradients
- No marketing-y phrases like "Unleash the power of..."

CONTENT TONE
Direct, factual, a touch warm. The audience is undergraduates and early
graduate students — confident but not jargon-heavy. Read like a senior
researcher writing to junior collaborators.

LOGO
A PNG logo file is provided as `hydroai.png` (square, transparent
background). Place it top-left in the navbar, ~32px tall.
```

---

## :material-home: Page 1 — Home / Hero

```
Build the homepage of an internal research hub called
"HydroAI Lab — Summer 2026 Internship".

LAYOUT (top to bottom)

1. STICKY NAVBAR
   - Left: hydroai.png logo + text "HydroAI Lab" (small caps, tracking-wide)
   - Center/Right: nav links — Home · Schedule · Students · PI Dashboard · Resources
   - Far right: a small "Lab network only" badge with a lock icon

2. HERO SECTION (full-bleed, ~500px tall)
   - Background: dark navy (#0a1014) with a subtle radial gradient (cyan glow
     bottom-left, teal glow top-right, both at low opacity)
   - Faint lat-lon grid overlay (rgba(34, 211, 238, 0.06)), masked to fade
     toward the edges
   - Eyebrow text (small caps, cyan): "HYDROAI LAB · SUMMER 2026"
   - Headline (huge, 56px, gradient white-to-cyan):
     "AI meets satellite remote sensing for the global water cycle."
   - Subhead (max-width 640px, muted text):
     "Shared research hub for our summer cohort — weekly logs, datasets,
     figures, and discussions, all in one place."
   - Pill row of tags (chips with cyan border, transparent bg):
     · Deep learning  · SMAP · SMOS · GPM  · Land–atmosphere coupling
     · Reanalysis × in-situ  · Open science

3. STAT STRIP (4 cards in a row, full width)
   - "9 weeks" / "2 active projects" / "4 seats open" / "15 min final talk"
   - Each: large cyan number, small uppercase label below
   - Card style: thin cyan border at low opacity, gradient background

4. SECTION "What you'll do this summer"
   - One short paragraph
   - Below it: 3 project cards in a horizontal grid
     · Card 1: "Brown Ocean Effect" — Changik Park — Jun 22 – Aug 21
     · Card 2: "Soil Moisture Data Intercomparison" — Dowon Lee — Jun 22 – Aug 21
     · Card 3 (dashed border, lower opacity): "TBD — 4 seats opening later this summer"
   - Each card: small uppercase topic tag at top (cyan), bold title, 2-line
     description, metadata row (icon + intern name + date)
   - On hover: card lifts 3px, border glows cyan, subtle shadow

5. SECTION "Start here" — 4 navigation cards (Schedule, Students, PI Dashboard, Resources)
   Each with a small lucide icon, title, 1-line description.

6. FOOTER
   - Small. "HydroAI Lab — University of South Carolina · Summer 2026 cohort"
   - Built quietly, no big logos.

COMPONENTS TO USE
- shadcn/ui: Card, Badge, Button
- lucide-react icons (Satellite, Brain, Droplet, Globe, ArrowUpRight, Lock)
```

---

## :material-calendar: Page 2 — Schedule

```
Build the "Schedule" page for the HydroAI intern hub. Same brand/mood as the
homepage (dark, cyan accents, faint grid background).

CONTENT

Top of page:
- H1: "Schedule"
- Subhead: "The 9-week arc for the Jun 22 – Aug 21, 2026 cohort
  (Changik Park · Dowon Lee). Other interns plug in on their own dates."

SECTION 1 — "At a glance" timeline
Render as a horizontal stepper (or vertical on mobile). 9 nodes.

Week | Dates              | Theme                   | Friday deliverable
1    | Jun 22 – Jun 26    | Literature scoping      | Topic kickoff talk (10 min)
2    | Jun 29 – Jul 03    | Data acquisition        | Data inventory + plots
3    | Jul 06 – Jul 10    | Pipeline v1             | Reproducible notebook
4    | Jul 13 – Jul 17    | Mid-summer checkpoint   | Mid-checkpoint (10 min)
5    | Jul 20 – Jul 24    | Iterate                 | Updated figures
6    | Jul 27 – Jul 31    | Validation & robustness | Sensitivity tests
7    | Aug 03 – Aug 07    | Story & figures         | Talk outline + figures
8    | Aug 10 – Aug 14    | Dress rehearsal         | Rehearsal feedback
9    | Aug 17 – Aug 21    | FINAL TALKS             | 15-min final talk (Fri Aug 21)

Highlight weeks 1, 4, 8, 9 (talk weeks) with a cyan ring on the node.

SECTION 2 — "What 'done' looks like each week"
A tabbed component with 5 tabs: "Week 1", "Weeks 2–3", "Week 4", "Weeks 5–7",
"Weeks 8–9". Each tab shows a clean checklist of expectations for that phase.

SECTION 3 — "Weekly cadence" callout
A single info card:
  Mon — stand-up (15 min): what's the plan this week?
  Wed — async check-in: drop a screenshot or note in your weekly Google Doc.
  Fri — finish that week's section in your Google Doc. PI reviews over
       the weekend; comments land in the Doc by Monday.

SECTION 4 — "Standing events" table
A small table with: When / What / Where
  Mon 10:00 | Cohort stand-up | Lab
  Fri 14:00 | Weekly demo     | Lab
  Aug 21 (Fri) 14:00 | Final symposium | TBD

SECTION 5 — Holidays/no-meeting warning
A warning-style callout:
  "Fri Jul 03 — Independence Day observed (no formal demo, log still due)"
```

---

## :material-account-group: Page 3 — Students directory

```
Build the "Students" directory page. Same brand/mood.

LAYOUT
- H1: "Students"
- Subhead: "Two intern projects are active for the Jun 22 – Aug 21 window.
  Four more cohort members join on rolling start dates later this summer."

- A responsive grid (3 columns desktop, 2 tablet, 1 mobile) of intern cards.

ACTIVE CARDS (2)

Card A — links to /students/changik-park
  · Top tag: "LAND–ATMOSPHERE COUPLING" (small caps, cyan)
  · Avatar: simple monogram "CP" in a cyan-edged circle
  · Name: Changik Park
  · Project title: Brown Ocean Effect
  · Description (2 lines): How wet soils sustain tropical cyclones after
    landfall. Built on SMAP soil moisture, IBTrACS storm tracks, and ERA5
    reanalysis.
  · Footer row: calendar icon + "Jun 22 – Aug 21, 2026"
  · A small "Open Google Doc" button (ghost style, opens in new tab)

Card B — links to /students/dowon-lee
  · Top tag: "SATELLITE VALIDATION"
  · Avatar: monogram "DL"
  · Name: Dowon Lee
  · Project title: Soil Moisture Data Intercomparison
  · Description: Benchmarking SMAP, SMOS, ASCAT, ESA CCI, and reanalysis
    against ISMN in-situ.
  · Footer row: Jun 22 – Aug 21, 2026
  · "Open Google Doc" button

PLACEHOLDER CARDS (4)
  · Dashed border, lower opacity (60%)
  · Tag: "OPEN SEAT"
  · Name: "TBD Intern 3" (4, 5, 6)
  · Body: "Topic to be scoped together in week 1"
  · Footer: "Rolling start"
```

---

## :material-account-circle: Page 4 — Student profile (Changik Park)

```
Build a student profile page. This pattern will be reused for each intern.

LAYOUT

1. HEADER STRIP
   - Avatar (large monogram "CP")
   - Name: Changik Park
   - Subtitle: Brown Ocean Effect · Jun 22 – Aug 21, 2026 · Mentor: Hyunglok Kim
   - Right side: a large primary CTA button "Open my weekly log →"
     (cyan filled, lucide ExternalLink icon, opens Google Doc in new tab)

2. SECTION "Research question"
   Boxed quote-style component with the refined research question.
   Placeholder text:
     "Under what land-surface and atmospheric conditions does the brown ocean
     effect occur over the continental US, and can we predict its likelihood
     from pre-landfall soil moisture state?"

3. SECTION "Plan"
   Numbered list, 6 items (weeks W1, W2-3, W3-4, W5-6, W6-7, W8-9 themes).

4. SECTION "Data"
   Table with columns: Dataset / What / Used for
   Rows: SMAP L3/L4, IBTrACS, ERA5, MERIT/SoilGrids

5. SECTION "Weekly progress"
   A 9-row table with: # / Dates / Theme / Status pill
   Status pill colors:
     · "not started" — gray
     · "in progress" — cyan
     · "done"        — green
     · "blocked"     — amber
   All weeks start as "not started".

6. SECTION "Recent figures"
   A 3-column gallery placeholder (gray boxes labeled "Figure pending").
   When the student adds figures, this populates from a `figures/` folder.

7. FOOTER NOTE
   Small italic: "Pipeline scoping notes from the PI live at
   brown_ocean_effect/brown_ocean_pipeline.md (lab storage)."
```

(Repeat this prompt for Dowon Lee — substitute name "Dowon Lee", monogram
"DL", topic "Soil Moisture Data Intercomparison", and the appropriate plan
and data rows.)

---

## :material-view-dashboard: Page 5 — PI Dashboard

```
Build the "PI Dashboard" page. The PI checks this Monday morning before
stand-up. Same brand/mood.

LAYOUT

1. H1: "PI Dashboard"
   Subhead: "A single view to skim the cohort before Monday stand-up."

2. KPI ROW (4 stat cards)
   · Active interns: 2 (of 6)
   · Current week: 1
   · Logs updated this week: 0 / 2
   · Final talks scheduled: Aug 21

3. COHORT TABLE
   Columns: Intern / Project / Week / Weekly Log / Progress / Status

   Row 1: Changik Park · Brown Ocean Effect · 1 ·
          [Open Doc button, ghost cyan] ·
          [Progress bar, 5% filled, cyan-teal gradient] ·
          [Status pill "not started"]

   Row 2: Dowon Lee · Soil Moisture Data Intercomparison · 1 ·
          [Open Doc] · [5% bar] · [not started]

   Rows 3-6: TBD intern 3-6, faded, "not yet onboarded"

   Make the progress bar smooth and animated on initial render.

4. SECTION "Upcoming deliverables"
   A timeline-style list with date chips:
     · Fri Jun 26 — Topic kickoff talks (Changik, Dowon) · 10 min each
     · Fri Jul 17 — Mid-summer checkpoint talks
     · Fri Aug 14 — Dress rehearsals
     · Fri Aug 21 — Final symposium · 15 min talks

5. SECTION "Open questions"
   A collapsible/accordion list, one item per question, each tagged with the
   intern's name. Empty state: "No open questions yet — first kickoff is Jun 26."

6. SECTION "Quick links"
   3 link cards: Schedule, Resources, Weekly log template
```

---

## :material-book-open: Page 6 — Resources index

```
Build the "Resources" page. Same brand/mood.

LAYOUT
- H1: "Resources"
- Subhead: "Everything you need to run your project smoothly. Read these on day one."

- A 3-card grid:

  Card 1: Google Docs workflow
    Icon: Google Drive (or FileText)
    Body: "How to use your weekly log doc, how PI feedback works, sharing rules."
    Footer: "Read →"

  Card 2: Weekly log template
    Icon: ClipboardList
    Body: "Copy this into your Google Doc every Friday."

  Card 3: Data & compute policy
    Icon: Database
    Body: "Where to put big files, what NOT to share, how to cite datasets."

- Below: "Useful external links" list with small icons:
    · NASA SMAP — https://smap.jpl.nasa.gov/
    · ESA CCI Soil Moisture — https://www.esa-soilmoisture-cci.org/
    · ISMN — https://ismn.earth/
    · Copernicus CDS (ERA5) — https://cds.climate.copernicus.eu/
    · IBTrACS — https://www.ncei.noaa.gov/products/international-best-track-archive
    · Google Scholar — https://scholar.google.com/
```

---

## :material-application-cog: Integration — getting v0 output back into mkdocs

v0 emits React (Next.js) components. You have two paths:

### Option A — Keep it as a Next.js site (cleaner, recommended if you like v0)

1. In v0, click **"Add to codebase"** → it gives you a Next.js project.
2. `npm run build && npm run export` (or use Next.js static export).
3. Copy the exported `out/` directory to your nginx server (replace mkdocs's
   `site/site/`). The `DEPLOY.md` guide still applies — just point nginx
   `root` at the new directory.
4. Content lives in `app/page.tsx`, `app/students/changik-park/page.tsx`, etc.
   Editing markdown becomes editing JSX strings, which is more friction.
   Mitigate by putting copy into a single `content.ts` file.

### Option B — Steal the look, keep mkdocs (most pragmatic)

1. Generate the homepage and one student page in v0.
2. Open the v0 preview, **right-click → Inspect** → copy the rendered HTML.
3. From the v0 React code, extract the Tailwind classes used on key
   components (hero, cards, stat strip, progress bar).
4. Translate to your existing `site/docs/stylesheets/extra.css`:
   - The hero gradient + grid overlay → already in `.hydroai-hero`
   - The stat cards → `.hydroai-stat`
   - The project cards → `.hydroai-card`
5. Update the markdown to use any new component classes you added.

This keeps the static, markdown-driven simplicity of mkdocs while adopting
the visual polish from v0.

### Option C — Hybrid

Use a **third tool** that's already markdown-native and v0-compatible:
- **Astro** + `@astrojs/mdx` + shadcn — paste v0 components in, write
  content in MDX. Builds to static HTML. Good middle ground.

---

## :material-image: Assets to provide v0

When you start a v0 chat, upload:
- `hydroai.png` (the lab logo)
- A screenshot of the current site (so v0 sees what you're replacing) —
  optional but helpful

## :material-check-circle: Done checklist before re-deploying

- [ ] All 6 pages designed in v0 and exported
- [ ] hydroai.png used as navbar logo
- [ ] Dark mode is default; light mode optional
- [ ] Google Docs URLs filled in (Changik, Dowon) — search for
      `REPLACE_WITH_CHANGIK_DOC_ID` and `REPLACE_WITH_DOWON_DOC_ID`
- [ ] Lab-subnet allowlist in nginx (see `DEPLOY.md`)
- [ ] `mkdocs build` (or Next.js export) succeeds with no warnings
- [ ] Page tested on lab Wi-Fi from a student's laptop
