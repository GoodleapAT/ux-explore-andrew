# Model snapshot

**What our model contains, on a date, so "not in the model" is a claim with an anchor.**

> **Who may write to this file:** any surface that can write. **Re-read the board and rewrite the
> list**, rather than editing entries one at a time. Then update the read date and note what moved.
>
> **This is ours.** Joel's team keeps their own dated serialization of DRAFT v3 and it is excellent,
> but it is theirs and it is a different model. We diff against it; we do not adopt it as our
> baseline. See the external work standard.

---

## Read

**Source:** "Andrew's Model v3" on the Pros Entities board, node `498:5293`.
**Read:** 13 September 2026, as a rendered screenshot.
**Method:** read by eye. The board's text extraction fails on large nodes, so this is transcription
rather than serialization, and it is only as good as the reading.

---

## The board is behind the decision log

**Found on this read, and it matters more than the list below.** The diagram still says things three
decisions have since replaced.

| The board says | The decision log says | Decided |
|---|---|---|
| **Opportunity** | **Lead** | 10 Sep |
| Job is **one per signed scope** | Job is **one committed scope component** | 10 Sep |
| "Signed contract produces one or more **worksteams**" | Jobs are created at the hand-off. Also a typo, and the word is retired | 10 Sep |
| Job holds "periodic service and maintenance can also be stored here" | **Service runs as its own project type** | 10 Sep |

**The decision log wins.** The board is a picture of where the model was, not where it is. Four edits,
and they are small.

**Corrected 13 Sep 2026.** The first version of this section claimed five differences and said the
board was silent on when the project is created. **That was wrong.** The board carries the mint rule
in two places: the Project card reads "exists before anything is priced", and the connector from
Opportunity reads "Pursuing 1 opp. or multp. opportunities together created this lifecycle object".
The board has been right about the sharpest claim in the model all along.

---

## What our model contains

As drawn, with the decided names rather than the board's.

### Anchors

| Entity | Note |
|---|---|
| **Customer** | A person, above the address |
| **Property** | One or more. The site the work happens at. Referenced, never owned, by the project |
| **Contact** | Not drawn on the board. Assumed by every mock, where a customer has two |

### Demand

| Entity | Note |
|---|---|
| **Lead** | One or more, one per trade. Carries an origin and a line of detail. Survives being declined. Was Opportunity |

### The spine

| Entity | Note |
|---|---|
| **Project** | The container. **Created when intent to sell is expressed**, per T-2, so it exists before anything is priced. May hold several proposals. Holds Selling history and Work as groupings, and the money. **State is derived and one-way**, per T-7. The mint point moved four times on 14 Sep 2026 and landed close to where we started |

### Selling

| Entity | Note |
|---|---|
| **Proposal** | One, or several bundled. Multiple options each. Versioned |
| **Option** | Not named on the board, implied by "multiple options per proposal". Carries a presentation state and a decision state |
| **Statement of work, estimate, itemisation** | Drawn inside the proposal. Probably one entity, probably Estimate. **Unresolved** |
| **Financing** | Presented at the proposal, modelled below it |
| **Contract** | One acceptance, one signature, one financing per bundled sale. Amended by change orders |

### Work

| Entity | Note |
|---|---|
| **Job** | One or more, one per committed scope component. Siblings run independently |
| **Crew and schedule** | A record on the job. Granularity unresolved: one entity or two |
| **Material order and delivery** | A record on the job |
| **Permits and inspections** | A record on the job |
| **Documents and photos** | A record on the job |
| **Change order** | Attaches to one scope. Shows the scope value and the contract total |

### Money, held at the project

| Entity | Note |
|---|---|
| **Master invoice** | The total owed |
| **Payment request** | Draws against the master invoice, or stands alone |
| **Transaction** | Money moving |
| **Cost and profit** | A roll-up rather than an entity. **Unresolved**, and tangled with the stored-versus-derived question |

### Service, as a project type

Decided 10 September and **not on the board at all**. A service project with one job per visit, a
cadence from the plan terms, and no closing balance. Its own entities are unenumerated.

---

## What is deliberately not an entity

- **Selling** and **Work**. Groupings in the experience. They exist because the product needs a clear
  line between what is being sold and what is being delivered.
- **The customer-level record.** A view over the customer, not a thing.

## What is deliberately not drawn

- **The pipeline.** Stages, statuses, tasks and gates are surfaced at the lead, project, selling,
  work and job levels alike, so boxing them at one level would understate where they appear.
- **Documents, notes, measurements, history, site assessments and insights.** They attach to several
  objects at once, so drawing them at one level asserts an ownership the model is not claiming.

**The model is complete on structure and not exhaustive on contents.** It was an attempt to find the
entities needed to address a wide range of scenarios, not an inventory of everything a product
touches. That is why the object register exists.

---

## Diff against DRAFT v3

**Their snapshot:** 8 September 2026, 7 lanes, 47 entities, 59 edges, generated from the board by a
skill so board edits land as reviewable git diffs. Kept in the team repository.

### In both, under different names in places

Customer, Contact, Property, Project, Lead, Proposal, Option, Estimate, Contract, Change Order, Job,
Material Order, Permit, Photos and Docs, Crew Assignment, Invoice, Payment.

Their **Scope Component** is our signed scope, and the two are believed to mean the same thing.

### In DRAFT v3 and not in ours, thirty of them

Contractor Org · User and Role · Pricebook · SKU · Installed Equipment · Service Agreement ·
Recurring Service Event · Warranty Plan · Appointment, sales · Appointment, work visit · Site
Assessment · Rebate Application · Service Plan · Purchase Order · Forms and Checklists · GoodLeap
Financing App · Approval · Funding Events · Financing Agreement · 3rd-Party Financing Ref · Insurance
Claim · Supplement · Contractor Payout · Job Financials · Commission · Card and ACH Transaction ·
Payment Plan · Cash and Check · START.

**Most of these are not disagreements.** They are territory our model never covered because it was
scoped to the container question. Financing, payouts, service agreements and appointments are real
and ours simply does not name them. Treat the absence as scope, not as a position, unless a decision
says otherwise.

### In ours and not in DRAFT v3

- **Payment request** as a thing distinct from the invoice. They have Invoice and Payment and nothing
  between.
- **Service as a project type.** They have Service Plan as a separate spine object beside Project.
  This is a genuine disagreement, not a scope difference.
- **The Selling and Work groupings.** Not entities, so not comparable, but worth saying because a
  reader of both will look for them.

### Worth knowing from their snapshot

**Service Plan is carried dark in every one of the seventeen scenarios, as a placeholder rather than
a classification.** Their note says an on-board label missing from the canonical list would default
to lit, so dark-everywhere is neutral parking until a session settles what a Service Plan is. **Do
not read its dark row as a finding.** It bears directly on the least settled part of our model.

---

## Every object the mocks needed that neither model has

Checked 13 September against their forty seven. **All ten are absent from DRAFT v3 as well**, so they
are gaps in both models rather than us reading theirs wrong.

Communications · Lead origin as a first-class attribute · A lead nobody has raised with the customer ·
A receipt for a derived status · A queue that surfaces a revive date · After-render of the property ·
Per-customer profit · Pipeline value from open leads · Equipment as a schedulable resource ·
Cross-organisation crew assignment.

Two of those are theirs already: equipment as a schedulable resource and cross-organisation crew
assignment are both named as gaps in their own scenarios. Details are in the object register.

---

## Superseded, 14 September 2026, and where the team's position now lives

**This file no longer states what the team holds.** That is in `TEAM-POSITIONS.md`, once, with a date.
What follows records what happened to our own snapshot rows, which is a different thing.

**Net position after two team changes and v4:** the project's creation point came back to
substantially ours, at intent to sell rather than pursuit. Lead granularity did not come back. See
T-1, T-2 and T-3.

## Superseded, 14 September 2026

**Two rows of this snapshot were overtaken by the team on the day after it was written**, and both
were ours rather than theirs:

- **The project's creation point.** Was mint-on-pursuit. Is now the win. **This also supersedes the
  DRAFT v3 snapshot we diffed against**, which minted at proposal creation, so the team's position is
  a third one rather than either of the two compared.
- **Lead granularity.** Was one lead per trade. **A lead is now an engagement carrying several
  interests**, and the engagement is the selling workspace.

**The lesson for this file, which is the point of keeping it.** A snapshot is a copy with a date on
it, and this one was accurate for about thirty hours. That is not a failure of the snapshot; it is
the reason the date is mandatory. **What the drift check did not catch is that the change arrived by
conversation rather than by the board**, so no source we were watching moved.
