# Sources, Upgrade to Pros

**Specific to this project. Design system, product repositories, people and tooling quirks are in the
global sources file at the root.**

> **Who may write to this file:** any surface that can write. One row per source. Update the
> **Checked** date when you use one. When something turns out to be unreachable or out of date,
> change its note rather than deleting the row.

---

## Team record

| Source | Kind | Where | Access | Good for | Checked |
|---|---|---|---|---|---|
| **u2p-project-planning** | Repository, `loanpal-engineering` | Cloned in the enclosing folder | Local, read and edit. **Cannot commit or push.** Contributions go as a branch and a pull request for Joel | The durable team record: entity model, scenario walkthroughs, a 26-scenario pressure-test campaign, open items, a decision log and meeting notes. Also a glossary and an onboarding document | 11 Sep 2026 |
| **Scenario beat scripts** | Confluence, ProsOperations space, page "Scenarios" | Atlassian | Connector | Seventeen scripts, S1 to S17, each naming the entities lit at every beat. S15 and S16 are the multi-trade cases, S8 and S17 the membership cases, S12 the declined-financing case | 10 Sep 2026 |

**How to read a scenario page.** Three columns, unequally reliable.

| Column | What it is | How much to trust it |
|---|---|---|
| **What happens** | The team's plain language account of the journey | **The important one.** This is what the scenario is for |
| **Notes** | The team's own questions: open points on the experience or the model, missing detail, future considerations, permutations not walked | Real signal about what is unresolved. Not decisions |
| **Entities** | Generated, not authored. An inference about where each beat touches DRAFT v3 | A reading, not a specification. Wrong in places, and it maps to DRAFT v3 rather than to our own model |

The consequence: **the scenarios are authoritative on the experience, not on the model.** Build from
What happens, mine Notes for what is unsettled, and treat Entities as orientation.

**Review status is on the page, as a title marker.** A tick means the team has reviewed it, a
construction marker means review is in progress, and no marker means it has not been reviewed. Not all
of them have been reviewed. Check the marker on the page rather than trusting any list of them,
because it moves.

**Vocabulary warning.** Only **S16 and S17** have been rewritten into the current vocabulary, where
the spine is the Project and the Job is the work entity. **S4, S5, S13, S14, S14B and S15** still call
the spine a Job and the work a Workstream. Joel deferred a coordinated rename on 5 September. Read a
page's header before trusting its nouns.

**Andrew's position in that repository.** Nothing he has authored is in it. The Thompson scenario was
adopted as S15 on 1 September and he is cited in its provenance file.

---

## Boards

The boards are the source of truth. Any local copy is a copy, and when they disagree the board wins
and the local file gets updated.

| Source | Kind | Where | Good for | Checked |
|---|---|---|---|---|
| **Pros Entities** | FigJam, the team's collaboration surface | File `pNgQNZTXaNC8CFK2yFTItu` | **DRAFT v3**, the current team model, at node `498:4910`. DRAFT v2 at `45:282`. **Andrew's Model v3** at `498:5293` | 10 Sep 2026 |
| **Upgrade to Pros** | FigJam, Andrew's | File `6MefcsO9RsEcIQzjCPBiiX` | Page "Object mapping, Model C" at `461:5406`. Model C v1, the project management diagram, the Thompson scenario told without the model, and the Model C v3 structure diagram. Daidipya's Base Entity Map at `591:2905` and his glossary at `642:4228` | 10 Sep 2026 |

**How to read them.** The Figma text extraction tool fails on large board nodes. Use a rendered
screenshot at high resolution instead, because the small annotation is usually where the argument is.

---

## The other models

| Whose | Where it is | Shape |
|---|---|---|
| **Andrew, Model C** | This folder, plus both boards | Project mandatory and existing before pricing. Lead per trade, surviving decline. Money at the container |
| **Team, DRAFT v3** | Pros Entities board | Project is the spine and models one customer journey. Job executes one committed scope component. Service Plan sits beside Project |
| **Daidipya, Base Entity Map** | Upgrade to Pros board, plus a glossary | No spine; the Lead is the deal. A sub-Job is the schedulable unit |
| **Joel, Full entity map** | Pros Entities board, DRAFT v2 | Project existed but was optional and grouped Jobs after the sale. Carried the service flywheel |

A full even-handed comparison of the first three is in the entity modelling thread. **It predates
DRAFT v3** and should be read as background rather than as current.

---

## Joel's UX factory

**Not Andrew's effort. He is not involved in it and it does not inform his work.** It is recorded here
because parts of it are worth raiding, and because knowing it exists stops it being rediscovered. See
`../standards/external-work.md` for how this material is handled: reference, never input, and nothing
crosses over until Andrew says so.

Added by Joel in pull request 18 on the team repository, 10 September 2026, plus four commits after
it. Built on DRAFT v3, not on the model in `../upgrade-to-pros/VOCABULARY.md`.

| Piece | Where | What it is |
|---|---|---|
| **ux-factory skill** | `.claude/skills/ux-factory/` in the team repository | Takes one scenario's beat script and generates a clickable beat-by-beat walkthrough. One scenario per run, one commit each |
| **The generated walkthrough** | `ux/s1-full-loan/` | S1 only so far. A `flow.md` mapping beats to screens, and a `prototype.html` of about 1,700 lines |
| **The shared entity map** | `ux/entity-map.py`, output at `ux/kit/entity-map.svg` | **One** generated map of DRAFT v3: 7 lanes, 47 nodes, 59 edges. Lanes become rows so it sits wide and short under the screens. Lit per beat by matching each node against that beat's entity chips |
| **The page archetypes** | `ux/page-templates.md` | Nine page designs transcribed from a **UX DRAFT section on the Pros Entities board**, node `137:2376`, with their rationale |
| **The screen inventory** | `ux/screen-inventory.md` | Which scenario uses which archetype, plus a **Gaps** table of archetypes the board has not designed |
| **The design kit** | `ux/kit.css`, `ux/kit/tokens.css` | Explicitly a stopgap standing in for Andrew's component library, with a documented plan to adopt the real one component at a time |

### What is worth borrowing

- **The simplified entity map that lights per beat.** One generated SVG shared by all seventeen
  scenarios, with no scenario holding map data of its own, so the map and the beat's entity list
  cannot disagree. An edge lights only when both its endpoints are touched, which is the rule the
  board's own overlays use. That constraint is the good idea, not the drawing.
- **Three panes on one view:** the beat's own words verbatim, the screen, and the lit map underneath.
- **Dark entities as the upsell surface.** The board's wedge-first rule says an entity a scenario does
  not light should render as an empty panel that advertises the adjacent capability, rather than being
  absent. That ties the entity overlay and the UI together in a way neither does alone.
- **Naming gaps rather than improvising them.** A beat with no archetype gets rendered, banners itself
  as unmatched, and adds a row to the inventory.

### What does not transfer

- **It is built on DRAFT v3, not Andrew's model.** The entity map is generated from a serialised
  snapshot of the board, so it carries DRAFT v3's mint rule, its single lead with several interests,
  and Service Plan beside Project. None of the five differences in
  `CLAUDE-DESIGN-CONTEXT.md` are reflected.
- **The UI needs work, and partly by instruction.** The skill records wireframe fidelity as a
  deliberate choice attributed to Andrew on 8 September: grey boxes, one accent, real numbers, no
  brand gradients, on the grounds that a polished screen invites polish feedback and buries the
  structural finding. So some of what looks unfinished is on purpose. The parts that are not are the
  composition, which does not follow `../standards/ui-composition.md`.
- **Its kit is not the design system.** `ux/kit.css` is a stopgap with `k-*` classes. Andrew's
  extracted Sol tokens and the Pros Web utility classes are a different lineage.

### The nav contract they build to

A UX DRAFT section on the board states a navigation constraint, and Joel's skill treats it as binding
on itself. **It is not binding on us**, and nothing below has been adopted. Recorded so the position
is known, not so it is followed: **four lenses over one spine.** Home, Pipeline for work rows, Customers for the person anchor,
Properties for the property anchor, Money for receivable rows, then a secondary group. Three stated
consequences:

1. **Embed detail surfaces, never list surfaces.** Origin and GoodPay arrive as columns, filters and
   drill-ins, never as their own tabs with their own pipelines.
2. **One row per thing, everywhere.** Finance accounts, invoices and card transactions are columns
   and chips on a row, never sibling rows.
3. **Project is not a nav item.** You land on it from a row's umbrella chip.

**The third one is the interesting one**, because Andrew's five views treat the project workspace as a
first-class page. Arriving from a row is still arriving, so the two may be compatible. Either way it
is a question Andrew can take up when he wants to, or decline to take up. That another effort is
already building to it is not a reason to.

### Two boundaries worth knowing

- **The factory is read-only against Claude Design**, enforced by a pre-tool hook and an allow-list,
  not just by instruction. It can list and read projects and files and nothing else. The stated
  reason is that the design project is Andrew's working surface and generated wireframes must not end
  up where the canonical components live.
- **The Gaps table is a request queue aimed at Andrew.** Components the scenarios provably need and
  the kit does not have are reported rather than invented locally, on the grounds that a component
  invented there is a second design system starting.

S1 alone produced four gaps: every mobile surface, site assessment detail, work-lane setup, and job
close-out.

---

## Configuration reference

| Source | What it is |
|---|---|
| **Project management configuration** | Three boards, ten stages, five sub-statuses, five gates, with minimal and maximal examples. In the entity modelling thread. Written before Model C, and the stage and gate values in every mockup come from it. Note there are duplicate copies in the modelling thread and the design handoff folder |
