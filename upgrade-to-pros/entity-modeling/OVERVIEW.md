# Pros entity modelling — handoff

**Andrew Thompson, UX / Product Design · 10 September 2026**

Read this at the start of the next chat and nothing else is needed to keep going. It is weighted
towards the last few sessions, where the work stopped being one person's model and became four
people's argument. Earlier history is compressed to a paragraph at the end.

---

## The one-paragraph version

Pros Web needs entities Merlin does not have: something to represent work that might be sold, and
something to hold work sold together. **Model C** is the answer developed here: a mandatory
container under the customer, holding the sale and the work as peers, with opportunities living on
the customer and linking in. Three other people are modelling the same territory —
**Daidipya** (Base Entity Map), **Joel** (Full entity map), and **John Gaquin**, who spotted that
"Job" was being used for two different things. As of **DRAFT v3** on the shared board, the group has
resolved that collision in the direction Model C already pointed: **Project is the spine, Job is the
work entity.** The next job is to compare DRAFT v3 against Model C, settle on one model, and start
designing UI against it and against the scenario set.

---

## The state of play, as of DRAFT v3

The single most important recent development. On the Pros Entities board, the team's map has moved
from DRAFT v2 to **DRAFT v3**, worked on by Daidipya, Andrew, Joel and John together while walking
scenarios.

**What changed in DRAFT v3:**

- A new **Spine** lane has appeared at the top, containing **"Project — The Spine · Models one
  customer journey"** and **Service Plan**.
- **Job** has been narrowed. It now reads **"execution of one committed scope component"** and sits
  in the Work lane with its visits, material orders, permits, crew assignments and checklists.

That is John's collision resolved, and resolved the way Model C had it: the lifecycle container is
called Project, and Job is the work-domain entity beneath it. Two vocabularies converged; the level
disagreement is largely gone.

**Service Plan also appears in the Spine lane**, beside Project. Services and memberships are the
group's current frontier and are the subject of open question 7.

**What this does not settle.** Whether the container is thin or holds the financial roll-up.
Whether it is minted from a proposal or declared before pricing. Whether it is per-property or
per-customer. Where declined-but-still-wanted demand lives. Those are the four things to check DRAFT
v3 against, and they are listed as open questions below.

---

## Emerging: services and memberships

New territory as of 10 Sep, not yet modelled here. The group has started looking at **services and
memberships** — annual maintenance on an HVAC system being the example — and these express both
jobs and money differently inside the work stream. One-off project work assumes a sale, then
delivery, then a balance that closes. A membership is recurring, it has no closing balance, its
"jobs" are scheduled visits that repeat on a cadence rather than work streams produced by a signed
scope, and its money is a subscription rather than milestone draws against a master invoice.

Two things already in the group's models bear on this and should be read together with it:

- **DRAFT v3 puts Service Plan in the new Spine lane**, alongside Project. That is a claim that a
  service plan sits at the same level as a project rather than inside one.
- **Joel's map already carried the flywheel**: a completed job sells a service agreement, which
  schedules recurring service events, which book further jobs. Warranty plans cover installed
  equipment registered against the property.

**The question this opens for Model C.** Model C's work stream currently says periodic service and
maintenance can also be stored in it, which was a placeholder rather than a considered answer. If a
membership is recurring and has no contract value to close out, either the work stream has to stretch
to cover something quite unlike a sold scope, or memberships need their own path. Worth deciding
deliberately rather than by extension.

## The four models, in one table

| Whose | Artefact | Spine | Unit below the sale | Demand object |
|---|---|---|---|---|
| **Model C** (Andrew) | This folder, plus both boards | Project, mandatory, exists before pricing | Scope → Job | Opportunity, per trade, survives decline |
| **Daidipya** | Base Entity Map + glossary | None; the Lead is the deal | sub-Job, a schedulable unit with crew and appointment | Lead, doing double duty as demand and deal |
| **Joel** | Full entity map, DRAFT v2 | Project existed but was optional and grouped Jobs *after* the sale | Scope Component, trade-typed, not schedulable | Lead, thin |
| **Team, DRAFT v3** | Pros Entities board | **Project — the spine, models one customer journey** | Job — execution of one committed scope component | Lead, unchanged |

The full even-handed comparison of the first three, with entity inventories, ten agreed points and
fourteen open questions, is in `pros-web-three-models-snapshot.md` and its HTML twin. **That
document predates DRAFT v3** and needs reconciling against it — that is the first task of the next
session.

---

## Model C as it now stands

A **container** is created when a contractor decides some collection of work will be pursued
together. It is mandatory, exists before anything is priced, and is never sent to anyone. It is
called **Project (Lifecycle object)** — the diagram briefly went neutral on the name while it was
contested, and reverted once DRAFT v3 adopted Project. The unit below the sale is called **Job**
again, for the same reason.

**Andrew's Model v3 now lives on the team board**, at
`https://www.figma.com/board/pNgQNZTXaNC8CFK2yFTItu/Pros-Entities?node-id=498-5293`, beside DRAFT
v3 rather than only on the Upgrade to Pros board. The local
`diagram-model-c-structure-v3.html` has been brought into line with it.

Under the customer, outside the container: **properties** (one or more) and **opportunities** (one
or more, one per trade). Opportunities carry an origin and a line of detail, survive being declined,
and link into the container rather than moving into it. A **customer-level record** holds notes and
history, the financial roll-up, and the project and job roll-up.

Inside the container, two groupings. **Selling and Work are not proposed as entities.** They are
groupings in the experience: in several parts of the product a person needs a clear line between
what is being sold and what is being delivered. Everything else in the model is an entity claim;
these two are a UI claim, and the distinction matters when showing the diagram to people who are
modelling data.

- **Selling** — one or more proposals (each carrying a statement or scope of work, estimate and
  itemisation, plus financing), then the contract.
- **Work** — one or more **jobs**, one per signed scope, each with its records: crew and schedule,
  material order and delivery, permits and inspections, documents and photos, change order.

**Money** sits at container level, under both cards: master invoice as the total owed, payment
requests, transactions, cost and profit.

**The pipeline is deliberately not drawn.** Stages, statuses, tasks, gates and checklists are
cross-cutting rather than owned by any one card: they are seen and acted on at the project,
selling, work and job levels alike. Boxing them at a single level would understate where they
appear, so both pipeline rows were removed. This also retires the old straddling problem — the ten
configured stages no longer have to belong to one level, because the pipeline is surfaced at all of
them.

**A good deal is deliberately left out of the model.** Documents, notes, measurements, history,
site assessments and insights all attach to more than one object: not only the customer, but the
project, selling, work, jobs and money too. Drawing them at a single level would assert an
ownership the model is not claiming. The diagram is complete on structure and not exhaustive on
contents, and any UI work will need to decide where each of these actually surfaces.

### Still true, and still only settled here

1. The container is mandatory. Not created only when there is something to bundle.
2. Opportunity, proposal and job are associated, not nested.
3. The simple case stays simple: one opportunity, one proposal, one job looks like today.
4. A customer is a person, above the address. One customer, several properties.
5. Financing is presented at the proposal but modelled below it.
6. A change order attaches to one scope, and shows both the scope value and the contract total.
7. Notes and history are one event stream, filtered twice.
8. Three product tiers per organisation: payments only; payments and selling; payments, selling and
   operations.

### Change orders: the three-grade taxonomy

Agreed in discussion, drawn only as a single card in memo 4.

| Grade | What it is | Where it lives |
|---|---|---|
| No price change | Scope clarification, swap of equal value | A **task** |
| Price change within financing headroom | Rot found, small addition | A **sub-status** |
| Price change beyond headroom | Needs re-underwriting or a cash split | Its own object, with a cash-split path |

---

## Open questions to carry into the next session

Numbered to match the snapshot document where they overlap.

1. **Is the DRAFT v3 Project thin or does it hold the roll-up?** Joel's Job Spine design says no
   financial roll-up storage, consumers compute from linked records. Model C puts the master invoice
   and balance on the container. This is the sharpest live disagreement.
2. **Is the container minted or declared?** DRAFT v3 and the repo have it auto-create when sibling
   jobs mint. Model C has it created before pricing. If it can only be minted from a proposal, it
   cannot hold pre-sale work, which is most of why it exists.
3. **Is it per-property or per-customer?** The spine design says one customer at one property. Model
   C has it under the customer, who may hold several. The Thompson scenario has one property, so the
   question has never been forced.
4. **Where does declined-but-still-wanted work live?** Still the thing only Model C answers. DRAFT
   v3's Lead is unchanged, so the deferred roof still has no home.
5. **What is the unit below the sale?** DRAFT v3 says Job executes one committed scope component,
   which is close to Model C's scope-drives-job. Check whether scope component and scope mean the
   same thing.
6. **At what level is margin answerable?** No model computes below the job, so per-trade margin
   inside a bundled sale is unavailable in all of them.
7. **Services and memberships.** Does a membership run through the same container and jobs as a
   sold project, or does it need its own path? See the section above; this is the live new frontier
   and Model C has no considered answer yet.
8. **Naming.** "Project" is already taken in Merlin as a design artefact carrying a bill of
   materials and an electricity profile. DRAFT v3 adopting Project makes this a real problem, not a
   theoretical one. Separately, "scope" collides with the insurance sub-status "Scope received".

---

## The Thompson scenario — canonical

Everything in the Model C memos uses this, and the team repo has adopted it as scenario **S15**.
Keeping it consistent is worth more than variety.

**Contractor:** Northgate Home Services. **Customer:** Robert & Sara Thompson, 1428 Maple Ave,
Sacramento CA.

**Opportunities.** Each carries an origin and a line of detail. The two customer-sourced ones carry
evidence, in the customer's words; the DeDe one carries a rationale instead, because it cannot carry
evidence. That difference is deliberate.

| Opportunity | Origin | Detail |
|---|---|---|
| **Roofing** | Raised by the customer in the Home App | "Found shingles in the yard after the storm in July. Want someone to look at it before winter." |
| **Siding** | Came up during the intake call | South elevation is faded and cracked in places. Asked what a full wrap would cost, and whether it could be done at the same time as the roof. |
| **Windows** | Suggested by DeDe | Original single-pane units on a 1978 build. Flagged as a same-visit add alongside siding, on the basis that the crew is already on the exterior. |

- **Prior project, closed Sep 2025.** "HVAC — central air, heat pump conversion". One opportunity
  (phone enquiry: the old system failed in the August heat), one proposal, one scope, one job,
  $14,800 on a 10-year loan. Proof that the simple case still looks like today.
- **Project.** "Exterior refresh for the Thompsons", created 12 Aug.
- **Proposal, prepared then decided in the room.** Prepared before the site visit carrying all three
  scopes: roofing $38,900 and siding $34,200 switched on for a total of $73,100, windows $18,600
  priced but switched off. In the session on 18 Aug, roofing and siding are presented first, then
  windows is raised. The customer declines roofing and commits to siding and windows. Roofing is
  switched off in the session and the rep notes why, so the opportunity can be updated rather than
  going quiet. Total becomes $52,800. The customer chooses financing covering both remaining scopes,
  15-year loan at 6.99%, $474/mo, then accepts and signs. Roofing stays on the customer as a live
  opportunity.
- **Money.** Master invoice MI‑4471, $52,800. Milestones 20 / 40 / 40.
- **Jobs.** JOB‑3101 Siding, $34,200, exterior crew. JOB‑3102 Windows, $18,600, install crew.
- **Early production, 21 Aug.** Siding at Ops intake, 4 of 4 tasks, held by the HOA gate. Permit
  P‑22841, material order MO‑7734.
- **Install day, 2 Sep.** Siding Installing, 4 of 8. CO‑01, rot behind siding on the north
  elevation, +$2,800. Scope goes to $37,000, master invoice to $55,600, collected $31,680.
- **Closeout, 24 Sep.** Siding Closeout, 5 of 6. Windows Closed. Final invoice $23,920 held by the
  closeout-to-invoiced permit gate. Margin 31%.

An object-agnostic telling of this scenario, plus a counts-based structural summary, is on the
Upgrade to Pros board in the section "The Thompson scenario — told without the model".

---

## What is in this folder

Moved into the ux-explore-andrew repository on 11 Sep 2026, as the entity modelling thread of the Upgrade to
Pros project. Previously `pros-web-model-c`, then `entity-modeling-andrew`. The project overview one
level up carries the current state of play; this document is the detailed thread handoff.

| File | What it is |
|---|---|
| `OVERVIEW.md` | This document |
| `KICKOFF-PROMPT.md` | The opening message for the next chat, ready to paste |
| `pros-web-three-models-snapshot.md` / `.html` | Even-handed record of Model C, Daidipya's and Joel's models. Structural summaries, full entity inventories, ten agreed points, fourteen open questions. **Predates DRAFT v3** |
| `diagram-model-c-structure-v3.html` | Current Model C diagram, matching "Andrew's Model v3" on the team board. Container splits into Selling and Work cards. Uses "Project (Lifecycle object)" and "Job" |
| `diagram-model-c-structure-v2.html` | Previous version. Single container with the job opened up. Superseded by v3 |
| `diagram-model-c-structure.html` | The original v1 structure diagram |
| `memo-0-why-a-new-model.html` | Why a new model at all. Three sections, one today-versus-needed diagram, no UI. For product and engineering leads |
| `memo-3-model-c.html` | The argument for Model C. Four sections, A to D |
| `memo-4-model-c-screens.html` | Eight screens following the Thompson scenario from first contact to closeout |
| `diagram-project-management-model.html` | Boards, stages, sub-statuses, tasks and gates, drawn |
| `reference-project-management-config.md` | Three boards, ten stages, five sub-statuses, five gates, plus minimal and maximal examples. Written before Model C |
| `reference-project-management-brief.md` | Why project management is configurable rather than shipped. The five primitives |

**Housekeeping.** There are two memo 0 files, `memo-0-why-a-new-model.html` and
`memo-0-why-the-model-has-to-change.html`. Establish which is current and delete the other. There is
also an empty `.__t2` directory in the GitHub root left by a tooling test; delete it.

---

## Where the other work lives

**The team repo.** `loanpal-engineering/u2p-project-planning`, cloned at `GitHub/u2p-project-planning`.
Owned by Joel; two code owners. This is what the group treats as the durable record: the entity
model, fifteen scenario walkthroughs, a 26-scenario pressure-test campaign, open items, a decision
log and meeting notes. **The Thompson scenario is in it as S15**, adopted 1 Sep, recorded as the
first scenario to light Project. Andrew is cited in its provenance file. **Nothing Andrew has
authored is in the repo.** Claude can read and edit files in the clone but cannot commit or push;
contributions go as a branch and PR for Joel to review.

**Boards.**

- *Upgrade to Pros* (`6MefcsO9RsEcIQzjCPBiiX`), page **Object mapping — Model C** (`461:5406`).
  Holds Model C v1, the build fork, the project-management diagram, the Thompson scenario told
  without the model, and the Model C v3 structure diagram built natively on 2 Sep.
- *Pros Entities* (`pNgQNZTXaNC8CFK2yFTItu`), the team's collaboration surface. **DRAFT v3**
  (`498:4910`) is the current model. DRAFT v2 (`45:282`) is the previous one. Daidipya's Base Entity
  Map (`591:2905`) and his glossary (`642:4228`) are on the Upgrade to Pros board.

**Confluence.** The scenario scripts live at
`https://goodleap.atlassian.net/wiki/x/KQCsTQE`. The Atlassian connector is not currently
authorised, so a chat cannot read these without the user connecting it first.

**Root of the GitHub folder.** Earlier cross-cutting work not moved into this folder: the A-versus-B
comparison, the open decisions list, the model overview, the customer model proposal, an alternative
Model C diagram, the design memo format spec, four design-system investigations, Atlas notes and the
site map.

**Unfinished side task.** Migrating Origin financing pages into Pros Web via Claude Design. Cases is
in `cases-mfe`; both Leases/PPAs pages are in `pipeline-mfe` under the TPO naming. The two **Loans**
pages are in the main Origin app, deployed as `@goodleap/origin-mfe`, and that repository could not
be located in the org. A Slack message asking Joel's team for it was drafted but the answer has not
come back.

---

## Working agreements

- **Work in this folder by default.** Only put things in the GitHub root when told to.
- **Ask before building or rebuilding any artifact.** Every time.
- **Design memos, not prototypes**, when moving into UI. Format specified in
  the repository's `renders/claude-ai-project-instructions.md`,
  with the departures from it recorded in `standards/design-memo-format.md`. Mockup on the left, argument on the
  right, and the argument column carries the thinking.
- **`[i]` marks annotation inside a mockup**, and only inside a mockup.
- **Connectors are always orthogonal.** Right angles, never curves. Everywhere.
- **Ask before adding the closing four-card row or the closing note.**
- Keep replies short, plain, and free of file paths and code unless asked. Lead with the decision
  and the trade-off. No em dashes.

---

## Earlier work, in brief

Before the modelling, this thread read the Merlin, Pros Flutter, pay-mfe and origin-shell
repositories directly rather than trusting stale Confluence; produced four design-system
investigations, the most severe being that the shared token package ships two disagreeing colour
palettes so web and Flutter diverge silently; extracted site maps for all three products from code;
and wrote several briefs and prompts for Claude Design. Those outputs are in the GitHub root. The
model work then ran through an early customer-model proposal, nine open decisions put to
engineering, a Model A versus Model B comparison, and finally Model C, which dissolved that argument
by making the container the parent rather than the proposal.
