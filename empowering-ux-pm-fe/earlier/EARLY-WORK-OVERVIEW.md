# Early work, 4 to 25 August 2026: before the data modelling

**Andrew Thompson, UX / Product Design, GoodLeap. Written 9 Oct 2026 by Cowork from the session
transcripts.**

This covers one long Cowork conversation from its start on 4 Aug up to 25 Aug, when it turned to
modelling customers, opportunities and jobs for Pros Web. Everything after that point is covered by
the project's own overview and by `pros-web-model-c/OVERVIEW.md` at the enclosing level.

**How to use this.** Read it for background and for what has already been found, so you do not redo
it. It is a record, not a specification. Where it says something was found in code, it was found in
code in August; re-check before relying on it. Where it says something was left open, nobody has
closed it in this record.

**Not covered here.** The Atlas files at the enclosing level (`atlas-*.md`,
`project-atlas-design-summary.md`, `claude-design-chart-fidelity-note.md`) came from a different
session that is not in the transcripts. Atlas only appears here as a Claude Design fidelity problem.

---

## The short version

Seven threads, all serving one question: how GoodLeap's contractor tooling moves from payments only
into selling and operations without the three platforms drifting further apart.

1. **A strategy read of both Pros repositories**, which produced a one-pager and the requests that
   became the four investigations.
2. **The FigJam PRD Diagrams board**, where the improve-the-UI-stage framing, the two-axis routing
   model and the bulk lead upload case live.
3. **Why Claude Design approximates**, which turned up a real defect in the shared token package.
4. **Four investigations** handed to the frontend leads.
5. **Origin payments, information architecture and site maps**, including a site-map tool built in
   Claude Design.
6. **Understanding Origin payments as a product**: roles, personas, invoices versus transactions.
   Two Confluence pages came out of it.
7. **A Claude Design brief for migrating Origin payments views into Pros Web.**

The thread that leads into the modelling: on 25 Aug it was established that in Merlin **a lead is an
address**, `{id, location, propertyId}`, with contacts, notes and proposals hanging off it. That
finding is where the customer model work starts.

---

## 1. The opening strategy read (4 to 6 Aug)

**Goal.** Four problems: designing Pros Web and Pros App in parallel without redoing translation
each time; converging on one design system while letting some things stay platform specific;
migrating Origin features into Pros without importing Origin's visual debt; and why Claude Design
will not reach parity with the Merlin repository. Andrew asked for the repositories to be read
directly rather than his framing taken at face value, and for tradeoffs before deliverables.

**Platforms.** Pros Web is Merlin (React, TypeScript, Vite, Tailwind, shadcn). Pros App is
`gl-pros-flutter` (Flutter, Riverpod, Widgetbook).

**Found.**

- The local Flutter checkout was one commit behind `origin/master`. The missing commit `09eac672`
  added the shared theme and the `crm`, `lead_details`, `price_book`, `proposal_options` and
  `app_shell` features.
- Colour naming is fragmented. Web uses `sol-*` roles from `@loanpal/design-tokens@0.5.5`. Flutter
  has a legacy palette, a Material 3 colour scheme and 41 orphan tokens. Only 3 hex values matched
  between the repositories.
- A translation layer exists in engineering's Gap Analysis (Confluence 4968087594), but it is
  feature level and one way.
- No Sol scope document, and competing convergence stories in Confluence (4479221774, 5076287497).
- The old `merlin-design-system` Claude skill was stale: wrong font, type names that do not exist,
  wrong primary colour. The real type variants are d1 to d3, h1 to h6, l1 to l4, p1 to p4.
- Four AI guidance files in the Merlin repo contradict each other.
- The shadcn registry (`@merlin` namespace, 55 metadata files) is readable at `/dev/sink`, which is
  not behind auth.

**Decided.**

- Build a **visual catalog first**, then work backward to a mapping file. Each Web/App pair carries a
  stable name, a relationship type and a one-line reason from day one.
- Medium: a live page with real components, a `/dev/parity` sibling route driven by the registry
  metadata. **Pilot flow: lead detail**, with the proposal page as a second option.
- Two requests for the Merlin frontend team and a third for the mobile team, sent to both frontend
  leads to delegate.

**Produced.** `pros-design-convergence-onepager.md`, now in this folder. The three requests became
investigations 01 to 03.

**Left open.** The `/dev/parity` catalog was never built. Sol's owner is still unknown.

---

## 2. The FigJam PRD Diagrams board (7 to 17 Aug)

**Board.** Built in August on PRD Diagrams (`xnAm19usDkWqW5aKawYPrT`), Page 12. **It has since moved.**
Checked 9 Oct: Page 12 and its sections no longer exist on PRD Diagrams. The work now lives on the
**Upgrade to Pros** board (`6MefcsO9RsEcIQzjCPBiiX`), **Page 1**: Section 1 (50:3828), Guardrails -
two axes (50:3868), Use case - bulk lead upload (50:3882), IA - Payments across Origin / Pros App /
Pros Web (50:3903), and an unnamed section (226:4008). Andrew works in columns, topic on the top row,
read left to right.

**The main section: Section 1.**
https://www.figma.com/board/6MefcsO9RsEcIQzjCPBiiX/Upgrade-to-Pros?node-id=50-3828

This is the board's anchor. Read as columns, left to right:

- **Objectives.** Improve the software development lifecycle, particularly the stages that design and
  implement UI and UX, to enable:
  1. Use of AI platforms (Claude Design, Claude Code, Figma AI) in the UI and UX phases.
  2. PMs and frontend and backend engineers designing and shipping features.
  3. Pros Web and Pros App features designed in parallel, rather than App following.
  4. Preventing silent drift between Pros Web and App. Added after a critique.
  5. Faster, more intelligent migration of Origin functionality to Pros.
- **Mapping categories**, for how a component relates across platforms: same, different shape,
  deliberately different, missing on one side.
- **Statuses**, split by relationship:
  - Between Pros App and Web: parity is fine, parity is broken, parity needs tweaking.
  - Origin to Pros migration: not yet assessed, re-specified in Pros vocabulary, built in Pros,
    retired in Origin.
- **Initial end-to-end flows to map:** lead details, then the proposal page.
- **Sources:** Widgetbook for the Pros App, the shadcn registry for Pros Web, and Origin still needing
  a repository connection. The target is a unified component catalog.
- **Likely process:**
  - People without frontend skills get a UX lead to work with before, during and after, plus a
    purpose-built Claude Design project.
  - People with frontend skills get a UX lead and a CODEOWNERS file to guide the process.
- **Needs and next steps:**
  - Form a workgroup on the unified component catalog with PMs, designers and frontend engineers.
    The stakeholders still need identifying.
  - Give designers, and possibly PMs, capable local environments. Support today is haphazard and
    unfair to both sides.
  - Keep testing Claude Design, Figma AI and v0 as they evolve, with periodic assessments and case
    studies.
  - Implement the next phase of Sol components (tables, cards and so on), Pros Web first, then the App.
  - Add UX review paths to CODEOWNERS with branch protection, scoped so design is not pulled into
    every pull request.
- **The red sticky:** most of these items need focused frontend engineering help across all three
  platforms.
- **Annotations:** Widgetbook is at 63 components and the shadcn registry at 65, but about 10 web
  primitives have no mobile counterpart and about 8 more are structurally incompatible. Origin cannot
  render alongside Pros, because it runs on React 17 to 18 and an older Tailwind while Merlin is on
  React 19 and Tailwind 4.

**Other sections on the page.**

- Two-axis guardrails: https://www.figma.com/board/6MefcsO9RsEcIQzjCPBiiX/Upgrade-to-Pros?node-id=50-3868
- Bulk lead upload case: https://www.figma.com/board/6MefcsO9RsEcIQzjCPBiiX/Upgrade-to-Pros?node-id=50-3882
- Payments IA across Origin, Pros App and Pros Web: https://www.figma.com/board/6MefcsO9RsEcIQzjCPBiiX/Upgrade-to-Pros?node-id=50-3903

**What the other sections add.**

- **UX review on UI paths**, worded as "Require UX review on UI paths, via CODEOWNERS plus branch
  protection". CODEOWNERS holds paths, not phrases, and only gates anything with branch protection.
  Jira needs a separate rule.
- **Two axes.** Rows are frontend capability of the person building, which decides routing. Columns
  are novelty (Assemble, Compose, Extend), which decides gating. Novelty is judged against the
  catalog, not self declared; a new interaction pattern always counts as Extend.
- **The bulk lead upload case.** Sandhya Ganjikunta built it in a day as a proof of concept behind a
  feature flag: 8 files, 12 existing components, Sol tokens only, full translations. The board
  section records where Andrew was limited in tweaking the design inside the pull request, what the
  changes were, and what would unblock it. Main production gap: responsive behaviour, because the
  page renders inside the Flutter webview.
- **The payments information architecture matrix** and **the three-platform site map** (thread 5).

**Framing for buy-in.** The pitch to frontend engineers is **"UI production got cheap. Coordination
did not."** Four buckets: make the system findable; get design in at the right moment; let designers
act on their own feedback; keep pace with the tools. Suggested closing ask: a named owner on each of
the three platforms.

---

## 3. Why Claude Design approximates, and the token defect (7 Aug)

**Three layers of failure.** Claude Design cannot see the token values, cannot see the components,
and the written guidance was wrong. Fixing the docs alone does not fix Claude Design.

**The defect.** In `@loanpal/design-tokens@0.5.5` the hex and HSL fields disagree for 309 of 403
entries, 95 of them visibly; worst is `color.blue.700`. **Web reads HSL, Flutter reads hex**, so the
platforms diverge silently. The stated hue is pinned per colour family while the hue derived from hex
drifts with lightness, so these are two independent ramps, not a conversion bug. This is
investigation 04.

**Also found.** Sol already ships a Flutter build (`SolMaterialTheme`, 108 semantic tokens) and a
`tokens.json`. Poppins is the brand display face; Inter is the product face.

**The Claude Design system project** had real component source mixed with hand-authored recreations
that were wrong: a second type scale, button heights that do not match production, singular token
names where components use plural, no Tailwind config, a radius conflict. Recommended deletions were
given. `claude-design-system-project-notes.md` sets the authority order and a version pin. Fix the
design system project, not the feature projects that reference it.

**Atlas, briefly.** Rebuilding the Atlas Financing page in Claude Design is not worth it: Recharts and
Radix cannot be reproduced, and responsiveness uses container queries plus a script-driven tier
system. Screenshot the real thing and work from the differences, or edit in the repository.

**Produced, at the enclosing level.** `merlin-sol-design-reference.md`,
`claude-design-project-prompt.md`, `claude-design-system-project-notes.md`, `sol-tailwind-theme.css`
and its inline variant. `reference/merlin-sol-tokens.css` in this repository appears to be a later
copy.

**Left open.** Whether the deletions were applied in Claude Design. Claude Design's vendored component
bundle was found broken standalone on 11 Aug; Andrew said to leave it for now.

---

## 4. The four investigations (6 to 13 Aug)

All at the enclosing level. Each states its finding in the title, and each says it needs frontend
expertise to confirm. Docs for engineers must not mention what Claude got wrong in earlier drafts,
and were renamed from "request" to "investigation" for that reason.

| File | Finding | For |
|---|---|---|
| `investigation-01-merlin-sol-token-values.md` | Sol's token values are not readable from the Merlin repo | Merlin frontend |
| `investigation-02-merlin-ai-guidance-cleanup.md` | The styling guidance files contradict each other and the code | Merlin frontend |
| `investigation-03-pros-app-catalog-and-theme.md` | The Pros App catalog has nothing keeping it current, and Sol already ships a Flutter build | Pros App / Flutter |
| `investigation-04-design-system-token-hex-hsl.md` | The token package ships two disagreeing colour palettes, and web and Flutter each read a different one. High severity | `goodleap/design-system` maintainers |

**Open.** No response from the frontend leads is recorded.

---

## 5. Origin payments, information architecture and site maps (7 to 25 Aug)

**Repositories.** Origin payments frontend is `loanpal-engineering/pay-mfe`; backends
`payment-party-service` and `payment-pos-service`. The shell is `origin-shell`. User management lives
in `origin-mfe`, which was not cloned. Zadok Kim was adding a pricebook transaction flow into Origin
from Merlin, which is the opposite direction to the migration.

**Payments IA.** The Pros App has a lot of payments (196 Dart files: reader, Tap to Pay, eCheck,
links, refunds, subscriptions). Pros Web had only an analytics tab, plus invoicing, which was missed
at first. Origin is back office; the Pros App is field. They overlap on about 4 of 25 jobs. No lift
and shift: Origin is React 18, Tailwind 3, single-spa. **The core conflict: invoices are organised by
lead in both Pros surfaces and globally in Origin.** Likely shape: per-lead views plus a new
organisation-level financial area.

**Site map.** Route tables were the wrong unit. Of 282 Pros App routes, most were overlays, debug
screens, training duplicates or steps of one wizard. **The unit became the nav spine**: Pros App tabs
and Pros Web sidebar sections, with flows collapsed. For Origin, only payments navigation. The App's
Leads tab and webviews that draw from Pros Web are ignored. Drafted in text first, then built.

**Settled about the Pros App.** CRM on and CRM off give mutually exclusive tab sets. **Andrew does not
want the legacy features**, so the map is CRM only. This project is about the migration, not a
unified catalog.

**Vocabularies used in the map.**

- Connector type: same, different-shape, deliberately-different.
- Connector status: not-assessed, re-specified, built, retired.
- Node migration: third-party, out-of-scope, later-wave, not-yet-real.

**The site-map tool.** Built in Claude Design from `site-map-data.json` and
`site-map-tool-build-brief.md`, with a focus view; adjacency matrix and cross-platform alignment are
listed as possible explorations. Structure is owned by the editor, content by Claude. Claude Design
cannot write back to project files and keeps state in browser storage, so the round trip is export,
replace the project file, then import. Checked against Pros Web's route tree on 12 Aug: 75 nodes.

**Screenshots.** Pros Web's route tree covers pages but not states. The Pros App already has 184
golden PNGs committed, heavy on payments and CRM.

**Left open.** The Target column of the IA matrix is empty. Whether Origin absorbs Pros or the reverse
was never resolved. "Import in patch mode" was never explained. The screenshot manifest, contact sheet
and audit script were never built. `pa-origin-webview` has no parent node. Payment schedules was
suggested as the most interesting design opportunity.

---

## 6. Origin payments as a product (12 to 24 Aug)

**Answered from `pay-mfe`.**

- **The Pros App transacts and consumes configuration. Origin configures and oversees.** So Pros Web
  becomes the configuration and oversight layer.
- Transactions and payments are the same thing under four names. There is a dead transactions page.
- Invoices answer "who owes me"; transactions answer "what money moved". Transactions is the superset
  and holds export.
- **Origin invoices have no upstream source of truth.** The contractor types the amount. The
  opportunity is to derive amounts from the proposal in Pros.
- Subscriptions are open ended. Payment schedules are mock-backed and gated to two test
  organisations behind a flag.

**Personas.** Andrew corrected the first answer: roles and responsibilities means **who uses payments,
how often and why**, not permission roles. Code cannot answer that. From Slack and Confluence: three
personas (field rep, owner, GoodLeap Payments Support, since onboarding is not self serve). RBA Esler
was up to 60% of year-to-date payments volume, and its reps cannot see Pricebook at checkout. Failures
are operational, not aesthetic.

**Confluence pages created** in the Merlin space:

- "Origin Payments: roles, responsibilities, and the stories behind today's product", 5564366852,
  uses a Verified / Inferred / Unknown key.
- "Cross-platform design system strategy: what we have across Pros Web, Pros App and Origin",
  5565153282. Origin uses Lumos 2; Sol ships targets for Tailwind 3 and 4, Flutter and Lumos, but
  only Pros Web consumes it.

**Open.** Three roles nobody seems to use. Pendo does not record role. The roles and permissions
spreadsheet on SharePoint was never obtained.

---

## 7. Claude Design brief for the Origin migration (25 Aug)

`claude-design-origin-migration-brief.md`, at the enclosing level. **One rule: Origin is read-only
reference; Merlin is the only build target.** Six traps: Stripe embeds, the four-name collision, the
dead file, the payouts page outside the route table, payment schedules not being real, and the
pricebook iframe. Token values come from the connected design system project, never from the Merlin
repo. The site-map data is safe to bring in: no secrets, though it describes unreleased work.

---

## Corrections Andrew made in this period

Each of these should already be reflected in `standards/`. If one is not, it is a gap.

- Plain language; he has little frontend experience.
- Old Confluence pages are a source of questions, not answers.
- Ignore the old `merlin-design-system` skill.
- Do not name individual engineers in documents sent to leads.
- Leave local environment detail out of shareable summaries.
- Documents for engineers do not mention Claude's earlier mistakes.
- "Investigation", not "request", for asks that need frontend expertise.
- Do not say "non-designers".
- Stop leading with colour drift; frame the larger problem.
- Draft in Claude first, then build in FigJam or Claude Design.

## Tooling quirks found

- FigJam reads failed until screenshots were requested as base64. Node 2002:4593 lives on Page 12,
  not the default page. Shape text clips because insets are larger than documented. His cards are
  square with 16pt body text.
- The Jira connector dropped out, so markdown was used instead of tickets.
- Claude Design cannot write back to files and keeps state in browser storage.
- Route-derived maps miss pages that are not conventionally routed.
- There were two diverged Merlin clones; the one in Documents was recommended as the only one.
