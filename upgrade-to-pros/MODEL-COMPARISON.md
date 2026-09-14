# Our model against DRAFT v3

**Every difference, with a proposed reading and a column for Andrew's ruling.**

> **Who may write to this file:** any surface that can write. **Andrew fills the ruling column.** A
> proposed reading is mine and carries no authority. Once a row is ruled, act on it: a conflict
> becomes a decision, an omission becomes a scope note or an addition, a naming difference becomes a
> vocabulary entry.

> **Stale in places, 14 September 2026.** The team moved twice after this was closed and then
> published **v4** of their model. **Do not read the team's position out of this file.** It is in
> `TEAM-POSITIONS.md`, recorded once and dated, which is the only place it is stated.
>
> **D-05 is superseded**: a lead is an engagement. **D-01 and D-02 resolved close to our position.**
> Do not read the trigger out of this file at all; it moved five times in one day and T-2 is the only
> current statement of it. And **four adopt-theirs rows are worded wrongly**: Estimate, Scope Component, Job Financials and Commission are satellite records in v4, not
> flow entities. See the note at the foot. Everything else stands.

---

## What was compared

| | Ours | Theirs |
|---|---|---|
| **Artefact** | "Andrew's Model v3" on the Pros Entities board, node `498:5293` | DRAFT v3, serialised by their skill into the team repository |
| **As at** | Read 13 Sep 2026, by eye | Snapshot 8 Sep 2026, generated |
| **Size** | About 18 named things, no edge list | 7 lanes, 47 entities, **59 edges with styles** |

**This is the first comparison with their edges rather than just their entity names**, which changes
several readings. Their edge list says what produces what, and that is where the real differences
live.

**Read the four board deltas first.** Our board is behind our own decision log on four points, in the
model snapshot beside this file. The comparison below uses the **decided** positions, not the board's.

## The classifications

| Term | Meaning |
|---|---|
| **Conflict** | Both models have a position and they disagree. Needs a decision |
| **Undecided** | A genuine open question. Neither has ruled |
| **Ours omits** | Territory our model never covered. Scope, not a position |
| **Ours simplifies** | We have it, coarser. Theirs is more precise |
| **Theirs omits** | The reverse |
| **Naming** | Same thing, different words |
| **Agreement** | No difference, listed because it was thought to be one |
| **Adopt theirs** | **Added 14 Sep.** The difference is real and theirs wins. Ours was thinner and theirs goes into ours. **Not the same as Agreement**, which closes a row and generates nothing. This one puts something into our model, **though v4 shows that something is sometimes a satellite record rather than a flow entity**, which is a distinction this column cannot carry |

---

## First, six things that are not differences

Worth stating, because several were believed to be disagreements as recently as this week.

| | Both models say |
|---|---|
| **A-1** | **Project is the spine** and models one customer journey |
| **A-2** | **Job is the execution of one committed scope component** |
| **A-3** | **Selling has no lifecycle anchor.** Ours calls Selling a grouping rather than an entity; theirs has no selling anchor and puts the states on the Lead, Proposal and Contract |
| **A-4** | **The invoice sits at the project.** Their edge is solid: Invoice to Project. This was thought to be the sharpest live disagreement and it is not one |
| **A-5** | **Jobs are created at the hand-off**, once the contract is signed and tender is secured |
| **A-6** | **Permits attach to the job**, not the project |

---

## A. The spine, and when it exists

| # | Ours | Theirs | My reading | Your ruling |
|---|---|---|---|---|
| **D-01** | The project **mints on pursuit**, when somebody starts working a lead intending to write a proposal. Exists before pricing | A solid edge: **creation of the proposal mints the Project** | **Conflict.** The live one. One beat apart in the scenario, and it decides whether the bundling decision leaves a trace | **Restated 14 Sep**, and it is a position rather than a hesitation. A lead has a validation phase where notes, transcripts, documents and investigation accrue. That is not pursuit. **Sales decides the validation is done and that the customer is worth pursuing, and that decision opens the project.** Beats drafted separately. The difference from theirs is not that they lack validation, their Lead can reasonably hold it, but that **nothing in their model marks the end of it**. &nbsp; **SUPERSEDED 14 Sep, by the team.** The project is created when a proposal or proposals are won. **That is a third position**, not ours and not the snapshot's: theirs minted at proposal creation, ours at pursuit, and the team has now put it after the win. So this row is wrong in both directions and the comparison is stale here. &nbsp; **CORRECTED again, 14 Sep:** the team moved a third time, to **intent to sell expressed**, at qualification or on proposal creation. **That is close to our original position.** See T-2, which is the only place the current wording lives |
| **D-02** | **Not optional for anything proposed or delivered.** A lead nobody pursues has no project | Effectively mandatory once a proposal exists, and nothing before that. Their Lead has no edge to Project at all | **Conflict**, downstream of D-01. Not separately arguable | **Challenged**, 14 Sep. "Mandatory if you want a proposal and jobs, but I don't see it being mandatory in other ways." **Andrew is right and my wording was wrong.** Ours restated above. The remaining difference is only D-01. **Stays classified Conflict**, 14 Sep, so it travels with D-01 and is resolved with it, but it is not separately arguable and must not be counted as a fifth conflict. &nbsp; **SUPERSEDED 14 Sep, by the team.** A proposal that never wins has no project at all, so the container is not mandatory for anything proposed, only for anything sold. &nbsp; **CORRECTED again, 14 Sep:** follows D-01 back. Under intent-to-sell the project exists before pricing again, so a proposal that never wins does have one. See T-2 |
| **D-03** | The project **holds the money**, and the customer record shows financial and project roll-ups | The project **points at nothing**. Its state is derived. But `Project rolls up Job Financials` is a real dotted edge | **Undecided on our side.** We never ruled stored against derived | **A third position offered**, 14 Sep. "Certain money items are stored at the project level, and certain at the job level, and those roll up. Many things ultimately roll up to the customer." **That is a rule, not a hesitation**: money is stored where it occurs, and higher levels derive. Now principle P-1 in the decision log. **Classification changed from Undecided to Ours simplifies**, 14 Sep: P-1 gives the rule but not the machinery, and theirs names an entity that holds the roll-up and computes from it, which is adoptable rather than opposed |
| **D-04** | Under the customer; property is **referenced, never owned** | Two dotted edges: `Customer work for Project` and `Property site of Project`. Dual anchor | **Ours simplifies.** Theirs is more precise and I would adopt it | **Undecided**, 14 Sep, changed from my reading. "This may not be an issue, and just a lack of detail in both models." A property is **transitory in relation to the customer**: they may move away, move to another property, or hold several. And **customer role against property is itself unresolved**, whether they own it or merely live there. So the dual anchor is not the question; the question is underneath it. &nbsp; **v4 widens this, 14 Sep.** Their visual language says ownership edges run from **every entity** to Customer and Property, omitted from the drawing for legibility. So dual anchoring is universal rather than a project question. See T-8. **The question underneath is still open**: customer role against a property is in the object register as blocking |

## B. Demand

| # | Ours | Theirs | My reading | Your ruling |
|---|---|---|---|---|
| **D-05** | **One lead per trade** | One Lead entity. Their scenarios run one lead carrying several interests by different authors | **Conflict**, but note theirs is carried in the scenarios rather than on the board. The board is silent | **Undecided**, 14 Sep, changed from my reading. **A slight preference for ours, not a ruling.** One trade per lead makes the provenance and journey of a lead easy to track. A lead holding several interests could possibly do the same, but **surfacing which interest was pursued, won or deferred would be hard**. With one trade per lead the customer's position on each is clear without digging. &nbsp; **SUPERSEDED 14 Sep, by the team**, against our position. **A lead is an engagement carrying several interests or trades.** Their argument is a UX one: a CSR discussing several trades in one conversation would otherwise be working across several tabs. Andrew designs against this and the implications come out of the UX work |
| **D-06** | A lead **survives being declined**, with a reason, a note and a revive condition | No status vocabulary on the board. Their scenarios say the interest stays open on the lead and that its reporting home has moved | **Theirs omits** at the model level. Behaviour lives in their scenarios, which is a weaker place for it | **Comment first**, 14 Sep. "For now, we need to be able to track leads throughout their lifecycle, so we will use what is implied in my model for now." Then **ruled Theirs omits, 14 Sep.** "Yes, use what is in ours for now." |
| **D-07** | The lead **carries its origin and a line of detail** | Nothing. No origin attribute | **Ours simplifies and theirs omits.** Neither models it properly. Already in the object register as blocking | **Undecided**, 14 Sep, changed from my reading. Tracking a lead across its lifecycle matters, so **the source and other detail should be recorded if possible**. Wanted rather than settled |
| **D-08** | Nothing | A **START** node feeding Lead | **Naming.** A diagram device marking the entry point, not an entity | **Naming**, confirmed 14 Sep. "Not an issue. Start was just used in the v3 model to indicate some starting point of the selling process" |

## C. Selling

| # | Ours | Theirs | My reading | Your ruling |
|---|---|---|---|---|
| **D-09** | **Option** is implied by "multiple options per proposal", never named | **Option (Good / Better / Best)** is an entity. Priced 1:1 by an Estimate, selection triggers the e-sign, and the contract pins its version | **Ours simplifies.** Theirs is better and I would adopt Option as an entity | **Adopt theirs**, 14 Sep. Ours is the thinner model and DRAFT v3's entities are taken. "This is just an artifact of my less detailed, broken-down model. We should use the v3 entities here". **Option becomes an entity in our model** |
| **D-10** | "Statement of work, estimate, itemisation" as one box inside the proposal | **Estimate** is its own entity, with line items, margin and tax, and its lines reference SKUs | **Ours simplifies** | **Adopt theirs**, 14 Sep. Ours is the thinner model and DRAFT v3's entities are taken. "This is just an artifact of my less detailed, broken-down model. We should use the v3 entities here". **Estimate is adopted as a satellite record**, per T-4, not as a flow entity. Wording corrected 14 Sep after v4 |
| **D-11** | **Financing** is a box inside the proposal. "Presented at the proposal, modelled below it" | **Payment Plan (tender mix)** is a first-class entity with seven edges: set by the proposal, referenced by the contract, revised by change order, spawning a financing application, a card intent, or an external reference | **Ours simplifies heavily.** This is the single biggest gap, and it is where the financed run will bite | **Adopt theirs**, 14 Sep. Ours is the thinner model and DRAFT v3's entities are taken. "This is just an artifact of my less detailed, broken-down model. We should use the v3 entities here". **Payment Plan becomes an entity in our model**, which closes the largest single gap and the one the financed run needs |
| **D-12** | **Site assessment** deliberately left out, as one of the things attaching to several objects at once | An entity. `Site Assessment informs scope on the Proposal` | **Ours omits deliberately.** But our own mocks needed it, so the deliberate omission may not survive | **Comment first**, 14 Sep. What a site assessment *is* remains unresolved: possibly a discrete object, possibly a type of another object, possibly an experience geared to the trade that guides what gets captured, from a template we preset and the organisation refines. A tech assesses the parts of the property relating to their trades, but CSR, sales and the installing team all capture assessment detail too. **And how site detail and notes reference the property is unresolved.** Then **ruled Undecided, 14 Sep**, and promoted to its own thread. "Site assessment, and what it is, is TBD for sure." See `in-depth/site-assessment.md` |
| **D-13** | Nothing | **Appointment, typed SALES**, hanging off the Lead | **Ours omits.** Scope | **Adopt theirs**, 14 Sep. Ours is the thinner model and DRAFT v3's entities are taken. "This is just an artifact of my less detailed, broken-down model. We should use the v3 entities here". **Appointment, typed SALES, becomes an entity** |
| **D-14** | "Signed against what was selected, amended by change orders" | Contract **pins the proposal version**, with terms and snapshots frozen. Explicit dotted edge | **Naming.** Same intent, theirs more precisely stated | **Adopt theirs**, 14 Sep. Ours is the thinner model and DRAFT v3's entities are taken. "This is just an artifact of my less detailed, broken-down model. We should use the v3 entities here". Contract pinning the proposal version is taken as stated |

## D. The unit below the sale

| # | Ours | Theirs | My reading | Your ruling |
|---|---|---|---|---|
| **D-15** | Job is **one per signed scope**. Scope produces job | **Two edges pointing opposite ways.** `Option hand-off seeds 0..N, one per committed scope component, to Job`. And `Job decomposes into 0..N, trades derived, to Scope Component` | **Ambiguous in theirs**, and worth asking them. Either scope produces job or job decomposes into scopes, and their board says both | **Comment first**, 14 Sep. "Scope produces a job, or one job per scope, is where I want to aim right now." **That settles our side**, and their board still says both, so the ambiguity is theirs. Then **ruled Undecided, 14 Sep. Ours is settled: one scope equals one job.** What remains undecided is theirs, since their board still points both ways, so this is a question to take to them rather than a ruling we can make. **Note the vocabulary has no value for "ambiguous in theirs"**, which is why this reads as undecided |
| **D-16** | Scope is untyped | **Scope Component is typed** by trade: solar, battery, roofing, HVAC | **Ours omits.** Probably worth adopting, since our own leads are per trade | **Adopt theirs**, 14 Sep. Ours is the thinner model and DRAFT v3's entities are taken. "This is just an artifact of my less detailed, broken-down model. We should use the v3 entities here". **Scope Component is adopted as a satellite record, typed by trade**, per T-4. Wording corrected 14 Sep after v4 |

## E. Work

| # | Ours | Theirs | My reading | Your ruling |
|---|---|---|---|---|
| **D-17** | "Crew and schedule", one record on the job | **Appointment, typed WORK VISIT**, with **Crew Assignment** hanging off it. Two entities, and the crew attaches to the visit rather than to the job | **Ours simplifies.** The separation matters: a job has several visits and the crew can differ per visit | **Adopt theirs**, 14 Sep. Ours is the thinner model and DRAFT v3's entities are taken. "This is just an artifact of my less detailed, broken-down model. We should use the v3 entities here". **Appointment typed WORK VISIT, and Crew Assignment, become entities.** The crew attaches to the visit rather than to the job |
| **D-18** | "Material order and delivery", one box | **Material Order** fulfils via **Purchase Order**. Two entities | **Ours simplifies** | **Adopt theirs**, 14 Sep. Ours is the thinner model and DRAFT v3's entities are taken. "This is just an artifact of my less detailed, broken-down model. We should use the v3 entities here". **Material Order and Purchase Order become entities** |
| **D-19** | Not drawn, part of the deliberately omitted cross-cutting set | **Forms / Checklists**, an entity on the job | **Ours omits deliberately**, and again our mocks drew task lists, so revisit | **Comment first**, 14 Sep. "Forms and checklists are not really official entities at this time. We just know we want them to be part of the experience, so we will continue to include them." **That is a deliberate draw-without-backing**, so it belongs in the object register rather than being adopted. Then **ruled Ours omits, 14 Sep.** "These four elements can be stored by the job. There will be other objects that aren't even listed here, but these are some we decided to note." **The four are forms, checklists, documents and photos**, covering this row and D-21. Not adopted as entities, and we keep drawing them. **The list is explicitly not exhaustive**, which matters more than the four named |
| **D-20** | Nothing | **Rebate Application**, marked a gap in their own model | **Ours omits.** Scope | **Adopt theirs**, 14 Sep. Ours is the thinner model and DRAFT v3's entities are taken. "This is just an artifact of my less detailed, broken-down model. We should use the v3 entities here". **Rebate Application becomes an entity**, marked a gap in their own model |
| **D-21** | "Documents and photos" | **Photos / Docs** on the job | **Naming** | **Naming**, confirmed 14 Sep. One of the four elements stored by the job, with D-19. Both models hang documents and photos off the job; only the dignity differs |

## F. Money

| # | Ours | Theirs | My reading | Your ruling |
|---|---|---|---|---|
| **D-22** | **Payment request**, drawing against the master invoice or standing alone | No equivalent. `Invoice settled by 1..N Payments`, and nothing between | **Conflict or naming, and I cannot tell which.** Their own open items flag two unreconciled readings of Invoice, a running total and a request for payment. Our payment request may be their second reading | **Adopt theirs**, confirmed 14 Sep, changed from my reading of undecided. Ours is thinner and theirs is taken, so our payment request gives way to their Invoice and Payments. **Their own two unreconciled readings of Invoice are still theirs to reconcile** |
| **D-23** | "Transactions" | **Payment is source-typed**, and five things create one: Card/ACH, Cash/Check, Funding Events, Supplement, and a third-party reference | **Ours simplifies heavily** | **Adopt theirs**, 14 Sep. Ours is the thinner model and DRAFT v3's entities are taken. "This is just an artifact of my less detailed, broken-down model. We should use the v3 entities here". **Payment becomes source-typed.** Andrew's caveat: payments will carry more attributes than source, which was simply detailed further in their model |
| **D-24** | Nothing | **Contractor Payout**, bundling payments by source, net of processing and dealer fees, method typed | **Ours omits.** Scope, and it is the contractor's side of the money rather than the customer's | **Adopt theirs**, 14 Sep. Ours is the thinner model and DRAFT v3's entities are taken. "This is just an artifact of my less detailed, broken-down model. We should use the v3 entities here". **Contractor Payout becomes an entity** |
| **D-25** | "Cost and profit" on the money card | **Job Financials**, a P&L roll-up entity. `Project rolls up to it`, and it `computes Commission` | **Ours simplifies.** Note this bears on D-03: they made the roll-up an entity rather than a derivation | **Adopt theirs**, 14 Sep. Ours is the thinner model and DRAFT v3's entities are taken. "This is just an artifact of my less detailed, broken-down model. We should use the v3 entities here". **Job Financials is adopted as a satellite record**, per T-4. Note this is the machinery P-1 lacked, which is why D-03 reads as ours simplifying |
| **D-26** | Nothing | **Commission**, computed from Job Financials | **Ours omits** | **Adopt theirs**, 14 Sep. Ours is the thinner model and DRAFT v3's entities are taken. "This is just an artifact of my less detailed, broken-down model. We should use the v3 entities here". **Commission is adopted as a satellite record**, per T-4 |
| **D-27** | Nothing | **Insurance Claim** negotiating **Supplement**, with carrier tranches paying the invoice | **Ours omits.** Scope, and it is a whole scenario we never walked | **Adopt theirs**, 14 Sep. Ours is the thinner model and DRAFT v3's entities are taken. "This is just an artifact of my less detailed, broken-down model. We should use the v3 entities here". **Insurance Claim and Supplement become entities**, and the scenario behind them is one we have never walked |
| **D-28** | Nothing | **GoodLeap Financing App**, **Approval**, **Financing Agreement**, **Funding Events**, **3rd-Party Financing Ref**. Five entities, chained | **Ours omits.** The financing spine, and the reason D-11 matters | **Adopt theirs**, 14 Sep. Ours is the thinner model and DRAFT v3's entities are taken. "This is just an artifact of my less detailed, broken-down model. We should use the v3 entities here". **The five financing entities are taken**: financing application, approval, agreement, funding events and the third-party reference |

## G. Services

| # | Ours | Theirs | My reading | Your ruling |
|---|---|---|---|---|
| **D-29** | **Service is a project type.** One job per visit, cadence from the plan terms, no closing balance | **Service Plan sits beside Project in the Spine lane.** The agreement is held by the Customer, and a solid edge reads "agreement mints a service plan instead of a project" | **Conflict.** The sharpest one after D-01, and the least settled part of both models | **Comment first**, 14 Sep. "Still up for debate. Either model might work here, but I prefer at this time having service be a type of project, with service visits likely denoted as jobs: past, current and upcoming." **A preference, not a ruling.** This is the one remaining conflict outside the mint point. Then **ruled Conflict and deferred, 14 Sep.** "We'll defer this for now." The preference stands but is not a ruling. **Deferring this keeps D-33 contingent**, since the subscription invoice defect depends on whether a service agreement is a project type |
| **D-30** | Cadence comes from the plan terms. No scheduling entity | **Service Agreement schedules 0..N Recurring Service Event**, and **Recurring Service Event books a Job** | **Ours simplifies.** Theirs names the thing that fires, which ours leaves implicit | **Undecided**, confirmed 14 Sep, changed from my reading. "Still undecided and we need to see how the experience plays out." **The experience decides this one, not the model** |
| **D-31** | Nothing | **Option sells 0..N Service Agreement**, labelled the flywheel | **Ours omits.** How a plan gets sold at all | **Adopt theirs**, 14 Sep. Ours is the thinner model and DRAFT v3's entities are taken. "This is just an artifact of my less detailed, broken-down model. We should use the v3 entities here". **Option selling a Service Agreement is taken**, which is how a plan gets sold at all |
| **D-32** | Nothing | **Warranty Plan** covering Installed Equipment | **Ours omits** | **Adopt theirs**, 14 Sep. Ours is the thinner model and DRAFT v3's entities are taken. "This is just an artifact of my less detailed, broken-down model. We should use the v3 entities here". **Warranty Plan becomes an entity** |
| **D-33** | Service plan has no closing balance, by design | Their own scenario flags that **a subscription invoice has no valid parent**, because their rule is invoice to job or project and an agreement is neither | **Agreement on the problem, neither has a solution.** Worth saying: both models break here | **Undecided**, confirmed 14 Sep, changed from my reading of agreement-on-the-problem. "Still undecided, especially if we decide a subscription or service agreement is a project type." **So the defect is not conceded, it is contingent** on how D-29 lands |

## H. Anchors, catalogue and organisation

| # | Ours | Theirs | My reading | Your ruling |
|---|---|---|---|---|
| **D-34** | **Contact** not on the board, assumed by every mock | An entity, dotted from Customer | **Ours omits by oversight.** Just add it | **Adopt theirs**, 14 Sep. Ours is the thinner model and DRAFT v3's entities are taken. "This is just an artifact of my less detailed, broken-down model. We should use the v3 entities here". **Contact becomes an entity.** This was an oversight rather than a scope choice |
| **D-35** | Nothing | **Installed Equipment**, an asset registry on the property | **Ours omits.** Our own service mock needed it | **Adopt theirs**, 14 Sep. Ours is the thinner model and DRAFT v3's entities are taken. "This is just an artifact of my less detailed, broken-down model. We should use the v3 entities here". **Installed Equipment becomes an entity**, which our own service mock already needed |
| **D-36** | Nothing. Tiers are a product concept in our notes | **Contractor Org** and **User / Role** | **Ours omits.** Scope | **Adopt theirs**, 14 Sep. Ours is the thinner model and DRAFT v3's entities are taken. "This is just an artifact of my less detailed, broken-down model. We should use the v3 entities here". **Contractor Org and User / Role become entities** |
| **D-37** | Nothing | **Pricebook contains SKU**, and SKU lines reference the Estimate | **Ours omits.** Scope, and it is where a price comes from | **Adopt theirs**, 14 Sep. Ours is the thinner model and DRAFT v3's entities are taken. "This is just an artifact of my less detailed, broken-down model. We should use the v3 entities here". **Pricebook and SKU become entities**, which is where a price comes from |

## I. Things neither model has

Ten, already recorded in the object register with criticality, intent and hold. Checked against their
forty seven on 13 Sep: **all ten absent from theirs as well.**

Communications · Lead origin as a first-class attribute · A lead nobody has raised with the customer ·
A receipt for a derived status · A queue that surfaces a revive date · After-render of the property ·
Per-customer profit · Pipeline value from open leads · Equipment as a schedulable resource ·
Cross-organisation crew assignment.

---

## The shape of it after the ruling, 14 September 2026

**All thirty seven rows ruled**, as of 14 September 2026.

**The headline is not any single row. It is that our model concedes.** Twenty two rows are Adopt
theirs, which is every place our model was the coarser one. Our model stops being a separate model and
becomes **DRAFT v3, plus three disagreements and six open questions**. That is a bigger change than any
row on its own and it should be said plainly in any handoff.

**What our model gains**, in one list, which is the actual output of the exercise:

Option · Estimate · Payment Plan · Appointment typed SALES · Appointment typed WORK VISIT · Crew
Assignment · Material Order · Purchase Order · Rebate Application · Contractor Payout · Job Financials
· Commission · Insurance Claim · Supplement · the five financing entities, being the application,
approval, agreement, funding events and third-party reference · Service Agreement with its recurring
event · Warranty Plan · Contact · Installed Equipment · Contractor Org · User / Role · Pricebook · SKU.
Plus Scope Component typed by trade, Payment source-typed, and the contract pinning a proposal version.

**Conflicts: one, and it is deferred.** D-29, where a service agreement sits. **D-01, D-02 and D-05
were all settled externally on 14 September**, by the team, all three against our position. See the
supersession note below.

**Six open questions**, which is where the remaining work is: the property anchor and the unresolved
question of customer role against property, lead granularity, lead origin, the scheduling entity for
recurring service, and the subscription invoice, whose defect is now **contingent on D-29** rather than
conceded.

**The last six, ruled 14 Sep.** D-06 keeps ours. D-12 became its own thread rather than a
classification. D-15 settles our side, one scope equals one job, and leaves the ambiguity as theirs to
resolve. D-19 and D-21 are two of **four elements stored by the job**, forms, checklists, documents and
photos, **and the list is explicitly not exhaustive**. D-29 is deferred, which keeps D-33 contingent.

**Two comments that are threads rather than rulings.** Site assessment, where the object may be a
discrete thing, a type of another thing, or an experience with a template we preset and the
organisation refines, and where how site detail references the property is unresolved. And forms and
checklists, which we will keep drawing without model backing, which is an object register entry rather
than an adoption.

---

## The shape of it, before you rule

**Superseded by the section above, 14 Sep 2026. Kept because the reasoning is cited elsewhere.**

**Four conflicts**, and only four: D-01 the mint point, D-02 which follows from it, D-05 lead
granularity, and D-29 where a service agreement sits. Everything else is scope, precision or naming.

**Two ambiguities to take to them rather than decide**: D-15, where their two edges point opposite
ways, and D-22, which their own open items already flag as two unreconciled readings.

**Twenty one omissions on our side**, almost all of them territory the model never covered because it
was scoped to the container question. Financing is the largest by far: five entities plus the tender
plan, and it is the part that will hurt first, because the financed run is next.

**Two omissions worth fixing immediately regardless of ruling**: Contact, which is an oversight, and
Installed Equipment, which our own service mock already needed.

**One place both models break**: the subscription invoice with no valid parent. Theirs names the
defect, ours avoids it by having no closing balance, and neither actually solves it.


---

## Overtaken by the team, 14 September 2026, twice

**The team's current position is not in this file.** It is in `TEAM-POSITIONS.md`, stated once with a
date. This section records only what happened to these rows, because a row that was resolved from
outside deserves to say so.

| Row | What happened | Where we ended up |
|---|---|---|
| **D-05** | **Superseded.** A lead is an engagement carrying several interests, per T-1. Their reason was a UX one and a good one, recorded as job J-11 | Against us. One lead per trade is dead |
| **D-01** | Moved three times in a day: their snapshot minted at proposal creation, then the team said the win, then the team said **intent to sell**, per T-2 | **Close to our original position.** Pursuit under another name |
| **D-02** | Follows D-01, so it also came back | Largely ours |
| **D-10, D-16, D-25, D-26** | Ruled adopt-theirs, and the wording said these become entities. **v4 makes them satellite records**, per T-4: data hanging off a step, never a step itself | Corrected in place. The adoption stands, the description was wrong |

**Two things v4 adds that this comparison never had a row for**, because neither model had them when it
was written: **an explicit end to validation**, and **uniform job outer states with trade-specific
sub-states**, with checkpoints as per-org policy rather than structure. Both are adopted. See T-3, T-5
and T-6.

**The first of those changed shape again later the same day.** v4 drew it as a Qualified Lead entity
sitting between Lead and Proposal. The current board collapses that: demand starts at **Inquiry** or
**Prospect** and the **Lead is the qualified thing**. The point stands, the object moved. T-3.

**What the exercise is worth knowing for, beyond the rulings.** We compared against a snapshot dated 8
September and published rulings on 14 September, by which time the team had moved twice and published
v4. **A comparison is a photograph.** The adoption decision survives that, because it was a decision
about our own posture rather than about any particular row. The individual rows are more perishable
than they look.

**Still a live disagreement:** T-9, where a service agreement sits. Our deferral on D-29 stands.
