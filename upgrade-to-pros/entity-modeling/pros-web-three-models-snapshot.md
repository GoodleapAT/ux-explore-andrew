# Pros object models: where the three of them stand

**Snapshot, 2 September 2026.** Compiled by Andrew Thompson from the three current maps.

This is a point-in-time record of three independently developed object models for Pros, written so
that the three authors can work from one description rather than three boards. It describes each
model on its own terms and does not pick between them. Nothing here has been signed off by anyone
outside the design and engineering work, and all three models are still moving.

Where a model is silent on something, this document says so rather than filling the gap.

## Sources

| Model | Author | Artefact | Version as read |
|---|---|---|---|
| Model C | Andrew Thompson | [Object mapping — Model C](https://www.figma.com/board/6MefcsO9RsEcIQzjCPBiiX/Upgrade-to-Pros?node-id=461-5406), plus memos 0, 3 and 4 | v1 of the board diagram, memos dated 28–31 Aug 2026 |
| Base Entity Map | Daidipya | [Base Entity Map](https://www.figma.com/board/6MefcsO9RsEcIQzjCPBiiX/Upgrade-to-Pros?node-id=591-2905) and [entity glossary](https://www.figma.com/board/6MefcsO9RsEcIQzjCPBiiX/Upgrade-to-Pros?node-id=642-4228) | "Projection of entity-registry.md · v11 · 2026-08-30" |
| Full entity map | Joel | [DRAFT v2 — full entity map](https://www.figma.com/board/pNgQNZTXaNC8CFK2yFTItu/Pros-Entities?node-id=45-282) | DRAFT v2 |

Daidipya's map states that `entity-registry.md` is the source of truth and the board is a
projection of it. This document reads the board and the glossary, not the registry.

---

# Part 1 · The three spines

## Model C

**Customer → Project → { Opportunity · Proposal · Job · Money }**

A project is the container for one piece of business, and it is mandatory. It is the workspace for
selling and, if the work sells, for operations. Inside it, nothing is
nested: opportunities, proposals, jobs and the money sit alongside one another as peers and point
at each other. Opportunities live on the customer and are linked into a project rather than moved
into it, so one that is declined survives with its link intact.

A proposal is versioned and holds one or more **scopes**. A scope carries its own statement of
work, estimate and itemisation, and is what a job traces back to. One job per signed scope, each
running its own pipeline.

The money sits at project level: one master invoice as the total owed, payment requests drawing
against it or standing alone, and transactions. A job never owns an invoice.

**Distinctive positions.** The container exists before anything is priced and is never sent to
anyone. Depth stops at two. Change orders are graded three ways by whether they change price and
whether the change fits inside financing headroom. Project management is configurable from five
primitives — stage, sub-status, task, gate, board. Three product tiers are set per organisation.

**Open inside the model.** Whether a proposal can hold several scopes, or whether proposals stay
whole and a new object gathers them, is unresolved and is a development-shape question. Options and
tiers on the proposal are supported but were not previously stated.

## Daidipya's Base Entity Map

**Customer → Lead → Proposal → Contract → Job → sub-Job**

The Lead is the hub of selling. It carries its source, stage, qualification, outcome and the type
of work or trade; a customer can have many leads; and a lead converts into a Job. A lead may have
several proposals.

A Proposal is a priced offer built from a template and the pricebook, governed by pricing rules,
holding one or more tier offers (good/better/best) with add-ons embedded, and moving through draft,
final, presented and selected. It holds no financing link. A Contract is the contractor's HIC,
derived from the selected proposal, holding the original and its amendments, specifying scope and
agreed price but not payment method.

Financing is a **Financing Option** scoped to the deal and held on the Lead. It carries the
selected payment method and terms, reads the deal total live, and its amount shows on the master
invoice.

A Job references its contract for scope and revenue and originates from a converted lead. The
**sub-Job** is the unit of execution, carrying the work package, crew and installation appointment.
Every job has at least one; an undivided job has exactly one default sub-Job; division is additive,
never re-parenting.

**Distinctive positions.** Financing is deliberately on neither the proposal nor the contract.
Appointments are one shared, typed entity — sales appointments belong to a lead, inspection and
installation appointments to a sub-job. A Master Invoice is a customer-anchored running balance.
Payment Terms is its own entity, set at job creation. Execution phase is tracked per sub-Job in
notes only and is not diagrammed.

## Joel's full entity map

**START → Lead → Proposal → Option → Contract → JOB → Scope Component**

Six lanes: catalog and org, anchors, agreements, demand and selling, work, money. The map declares
its own visual language: core flow, optional steps that occur zero or more times, and satellite
records that hang off a step but are never a step themselves.

Selling runs from a Lead through zero or more sales appointments and a site assessment into a
Proposal. The Proposal offers **Options** — good, better, best — of which one is selected, and that
selection triggers e-signature of the Contract. The Contract pins the proposal *version*, and takes
zero or more Change Orders as amendments. An **Estimate** is priced one-to-one off the Option, its
lines referencing SKUs. A **Payment Plan**, a tender mix, is selected per Option; the contract's
terms reference the plan, and a plan revision corresponds to an amendment.

The **JOB** is described on the map as the pivot. A Contract sells into it at stage SOLD; the map
also draws the first proposal minting the job and flags that link as borderline. A **Project** is
an optional group that gathers zero or one jobs. The job decomposes into zero or more **Scope
Components**, typed by trade — solar, battery, roofing, HVAC. Work visits, material orders,
permits, rebate applications, photos and checklists all hang off the job, and crew assignments hang
off the appointment.

Money is a lane of its own, tracing inbound sources into Payments: the first-party financing app
through approval, financing agreement and milestone funding events; third-party financing by
external reference; card and ACH; cash and cheque settling outside the rails; and insurance claims
through supplements in carrier tranches. An Invoice is settled by one or more Payments, and
Payments bundle outward into contractor payouts by source. Job Financials rolls up into Commission.

**Distinctive positions.** A stated uniform rule: rails create Payments, payouts bundle Payments,
and a single receivable can mix zero or more funding sources. A stated start gate: the transition
from SOLD to IN_PROGRESS may require nothing, a paid deposit, or financing notice to proceed, and
"money before work" is per-organisation configuration on a stage transition rather than structure.
A recurring-revenue flywheel: a completed job sells service agreements, which schedule recurring
service events, which book further jobs. Installed equipment is registered against the property and
covered by warranty plans.

---

# Part 2 · Entity inventories

Listed as each model states them. Definitions are paraphrased from the source artefacts. "Not
present" means the model does not carry the entity, not that its author rejects it.

## Model C

### CRM

| Entity | As stated |
|---|---|
| Customer | A person, above the address. One customer may have several properties |
| Contact | A person we do business with, belonging to a customer |
| Property | A site where work happens, belonging to a customer |

### Container

| Entity | As stated |
|---|---|
| Project | Mandatory. The workspace for selling and, if sold, operations. Exists before anything is priced and is never sent to anyone. Contains the proposal, the jobs and the money as peers; nothing inside it is nested under anything but the project |

### Selling

| Entity | As stated |
|---|---|
| Opportunity | A piece of work someone thinks might be sold. One or more per customer, one per trade. Belongs to the customer, links into a project. Carries an origin and a line of detail, and a status: not yet pursued, quoted, won, deferred, lost |
| Proposal | A priced document, versioned, holding one or more scopes. Carries options and tiers |
| Scope | A priced unit of a proposal, with its own statement of work, estimate and itemisation. Drives one job |
| Contract | Project level. One acceptance, one contract, one financing per bundled sale |
| Financing | Presented at the proposal, modelled below it. A job shows financing it does not own and must say so |

### Work

| Entity | As stated |
|---|---|
| Job | Work being delivered. One per signed scope. Two jobs in one project run independently and will not stay in step |
| Stage | A position in a board's sequence |
| Sub-status | An external process the contractor is waiting on and cannot speed up. Independent of stage; several may apply at once |
| Task | Work the contractor's own team does |
| Gate | A condition on the transition between two stages, not on a stage |
| Board | A grouping of stages |

### Money

| Entity | As stated |
|---|---|
| Master invoice | The total owed. Project level, not owned by the proposal or by a job |
| Payment request | Draws against the master invoice, or stands alone |
| Transaction | Money moving |
| Cost and profit | Project level |

### Change

| Entity | As stated |
|---|---|
| Change order | Graded three ways. No price change is a task. A price change inside financing headroom is a sub-status. A price change beyond headroom is its own object with a cash-split path. Attaches to one scope, and shows both the scope value and the proposal total |

### Organisation

| Entity | As stated |
|---|---|
| Product tier | Three, set per organisation: payments only; payments and selling; payments, selling and operations |
| Project status | pursuing → production → closing → closed, with archived as the alternative ending |

## Daidipya's Base Entity Map

### CRM

| Entity | As stated |
|---|---|
| Customer | Committed. Contractor-scoped identity anchor. Owns contacts and properties, anchors all money entities and jobs, has one or more leads, created at lead capture |
| Contact | Committed. A person we do business with, belonging to a customer |
| Property | Committed. Physical site where work happens, belonging to a customer |

### Org level

| Entity | As stated |
|---|---|
| Pricebook | Catalog of sellable items and prices |
| Template | Reusable proposal template the org defines, used to pre-build proposals |
| Pricing Rule | Org pricing and margin rules governing proposal pricing, for margin protection |
| Equipment Catalog | Org-level catalog of equipment, referenced by materials lists |

### Selling

| Entity | As stated |
|---|---|
| Lead | A potential deal; the hub of Selling; converts into a Job. Carries source, current stage and qualification, outcome, and the type of work or trade. A customer can have many |
| Salesperson | The rep assigned to work a lead |
| Appointment | Shared and typed: sales, inspection or installation. Sales appointments are for a lead; inspection and installation for a sub-job. Date, person and availability deferred |
| Site Model | Technical capture of the site: 3D model, roof measurements, home or property report, load calcs. Not always present |
| Proposal | Priced offer, built from a template and the pricebook. Holds one or more tier offers (good/better/best) and add-ons embedded. Governed by pricing rules. Moves draft → final → presented → selected. Holds no financing link. A lead can have one or more |
| Presentation | A custom presentation shown to the customer, presenting a proposal. Flagged borderline — may be an activity |
| Financing Option | Cash or financing choice for the deal, deal-scoped on the lead. Holds selected payment method and terms, reads the deal total live, its amount shows on the master invoice, a financed payment records to it |
| Contract | The contractor's HIC. Holds original contract and amendments, derived from the selected proposal, specifies scope and agreed price, not payment method |
| Notes | Notes, pictures, questionnaires. Shared: attaches to Lead and Job. May be captured during an appointment |

### Work

| Entity | As stated |
|---|---|
| Job | Sold work to be executed, belonging to a customer, referencing its contract for scope and revenue. Originates from a converted lead. Overall status tracked as job state; execution phase tracked per sub-Job, notes only, not diagrammed |
| sub-Job | The unit of execution, carrying the work package, crew and installation appointment. Every job has at least one; an undivided job has exactly one default sub-Job. Division is additive, never re-parenting |
| Work Order | Execution package for the sub-job: instructions, materials list, task list |
| Materials List | The materials required, referencing the equipment catalog |
| Task List | The tasks to complete the work. Permit pull and close, and warranty registration, live here as tasks |
| Materials Order | An order placed to a distributor to fulfil the materials list |
| Crew | The crew assigned to perform the installation |

### Operational finance

| Entity | As stated |
|---|---|
| Master Invoice | Customer-facing balance, AR. Anchored to a customer, may bill a job, references the contract for the amount owed, reflects the financing option amount when the deal is financed |
| Payment Terms | How the job bills: schedule type and planned draws. Set at job creation |
| Cost | A job-level cost line item, manual or auto-added, with optional reference to the source record |
| Job P&L | Computed profitability per job. Revenue is contract price including amendments, cost is the sum of the job's costs. Computed, not stored. Reviewed after all costs are incurred, at close |

### Money

| Entity | As stated |
|---|---|
| Invoice | A request for payment, anchored to a customer, may roll up to a master invoice. Each invoice is one draw of the payment terms |
| Transaction | Money changing hands, in only for now. Anchored to a customer, may pay an invoice. A financed payment records to the financing option. Can occur with or without an invoice or master invoice |

## Joel's full entity map

### Catalog and org

| Entity | As drawn |
|---|---|
| Contractor Org | Top of the catalog lane |
| User / Role | Alongside the org |
| Pricebook | Contains SKUs |
| SKU: Service · Material · Equipment | Referenced by estimate lines |

### Anchors

| Entity | As drawn |
|---|---|
| Customer | Has contacts and properties |
| Contact | Belongs to the customer |
| Property | Belongs to the customer. Site of a job |
| Installed Equipment | Asset registry on the property |

### Agreements

| Entity | As drawn |
|---|---|
| Service Agreement | Held by the customer. Schedules zero or more recurring service events. Sold by a job |
| Recurring Service Event | Books a job |
| Warranty Plan | Covers installed equipment |

### Demand and selling

| Entity | As drawn |
|---|---|
| Lead | Entered from START. Has zero or more sales appointments. Proposal is scoped and drafted from it |
| Appointment — type SALES | For a lead. Leads to a site assessment |
| Site Assessment (any trade) | Informs proposal scope |
| Proposal | Selects one of N Options. Minted from the lead. The first proposal is drawn as minting the job, flagged borderline |
| Option (Good / Better / Best) | One of N selected. Selection triggers contract e-sign. Priced one-to-one by an estimate. Sets the payment plan |
| Estimate | Satellite record: line items, margin, tax. Lines reference SKUs |
| Contract (e-signed) | Pins the proposal version. Takes zero or more change orders as amendments. Terms reference the payment plan. Sells into the job at stage SOLD |
| Change Order | Amends the contract, zero or more. Corresponds to a payment plan revision |
| Payment Plan (tender mix) | One selected per option, setting pricing. Referenced by contract terms. Points at the financing sources |

### Work

| Entity | As drawn |
|---|---|
| JOB — the pivot | Central entity of the map. Sold from the contract. Site is a property |
| Project (optional group) | Groups zero or one jobs |
| Scope Component | The job decomposes into zero or more, typed by trade: solar, battery, roofing, HVAC. Referenced by the financing app |
| Appointment — type WORK VISIT | Phase 2. Zero or more per job. Carries a crew assignment |
| Crew Assignment | Satellite record on the appointment |
| Material Order | Zero or more per job. Fulfilled via a purchase order |
| Purchase Order | Satellite record fulfilling a material order |
| Permit | Zero or more per job. Marked GAP |
| Rebate Application | Zero or more per job. Marked GAP |
| Photos / Docs | Satellite record on the job |
| Forms / Checklists | Satellite record on the job |

### Money

| Entity | As drawn |
|---|---|
| GoodLeap Financing App (1st party) | Leads to approval. References scope components |
| Approval | Credit, offers, stips. Leads to the financing agreement and the payment plan |
| Financing Agreement (e-signed) | Leads to funding events |
| Funding Events (milestones) | Produce financing-typed payments |
| 3rd-Party Financing Ref | External id. A payment source |
| Insurance Claim | Negotiates supplements |
| Supplement | Carrier tranches, producing payments |
| Card / ACH Transaction | A payment source |
| Cash / Check | Settles outside the rails, producing payments |
| Invoice | Settled by one or more payments. Raised from the job |
| Payment | Funds applied to the invoice, source-typed |
| Contractor Payout / Disbursement | Bundles payments by source. Method: Stripe ACH or WAB wire |
| Job Financials | P&L roll-up on the job. Computes commission |
| Commission | Computed from job financials |

### Stated rules on Joel's map

- **Uniform rule.** Rails create Payments; Payouts bundle Payments. A receivable can mix zero or
  more funding sources per invoice — for example a deposit by card with the balance financed,
  first- or third-party.
- **Start gate.** The transition from SOLD to IN_PROGRESS may require nothing, a paid deposit, or
  financing notice to proceed. "Money before work" is per-organisation configuration on the job's
  stage transition, not structure.
- **Visual language.** Core flow always occurs. Optional steps occur zero or more times. Satellite
  records are data that hangs off a step but is never a step itself.

---

# Part 3 · What all three already agree on

Stated here only where all three models take the same position, or where two state it and the third
is consistent with it. Where agreement is partial, that is said.

1. **The customer is the anchor, and owns contacts and properties.** Identical in all three. All
   three also keep the customer above the address rather than tying identity to a site.

2. **The selling chain has the same links.** Something representing demand, then a priced offer,
   then a signed agreement, then work. The names differ and the levels differ, but no model
   proposes a different sequence.

3. **A proposal offers options or tiers.** Joel makes Option a first-class entity, selected one of
   N, with its own estimate and payment plan. Daidipya embeds tier offers with add-ons inside the
   proposal. Model C supports it but had not stated it, and it is stated here for the first time.
   *Unresolved:* how options compose with several independently acceptable scopes — whether each
   scope carries its own options. Deferred by agreement, not solved.

4. **Financing is not held on the contract.** Model C presents it at the proposal and models it
   below. Daidipya puts it on the lead and says explicitly that neither proposal nor contract holds
   financing detail. Joel selects a payment plan per option and has the contract's terms merely
   reference it. Three hosts, one shared instinct.

5. **An organisation-level catalog governs pricing.** A pricebook in all three. Daidipya adds
   templates and pricing rules; Joel adds SKUs typed as service, material or equipment.

6. **Appointments are one typed entity shared across selling and delivery.** Daidipya and Joel both
   state this explicitly and both type it. Model C does not model appointments, and nothing in it
   conflicts.

7. **Work sold decomposes below the sale.** All three place a unit beneath the agreement rather
   than treating the sale as indivisible. *Partial:* they disagree on what the unit is — see open
   question 5.

8. **Change after signature rides the existing agreement.** Model C's change order, Daidipya's
   contract amendments and Joel's change orders all amend rather than replace, and all three keep
   the amount owed derived from the amended agreement.

9. **Margin comes from agreed price minus captured cost.** Daidipya computes Job P&L; Joel rolls up
   Job Financials; Model C carries cost and profit. *Partial:* the level differs — Model C computes
   at project level, the other two at job level, and none computes below that.

10. **Process is partly per-organisation configuration.** Model C makes this a design principle with
    five primitives. Joel states it for the start gate specifically. Daidipya defers execution phase
    to notes and does not contradict it.

---

# Part 4 · Open questions

Numbered for reference in discussion. Each names who it affects and what would settle it.

1. **What holds a sale that spans several trades?**
   *Affects all three.* Model C answers with a mandatory project that exists before pricing.
   Daidipya has no equivalent; the lead is the deal. Joel has a Project, but it is optional and
   groups jobs after the sale, so it cannot hold a bundle before one exists.
   *Settled by:* deciding whether a pre-sale container exists at all.

2. **Can a proposal hold several independently acceptable scopes?**
   *Affects Model C directly, and the other two if they adopt multi-trade bundling.* If yes, the
   change is contained and acceptance, contract and financing stay where they are. If no, something
   must be invented above the proposal to carry one acceptance, one signing and one financing.
   *Settled by:* engineering, on whether today's single-scope proposal can hold many.

3. **How do options and scopes compose?**
   *Affects all three.* If a proposal can hold several scopes and also offer tiers, does each scope
   carry its own options, or does the proposal offer whole-bundle alternatives?
   *Settled by:* later, deliberately. Recorded so it is not mistaken for solved.

4. **Where does a declined-but-still-wanted piece of work live?**
   *Affects all three.* Only Model C has an object that survives being declined, and only because
   opportunities live on the customer and are linked rather than moved. In the other two, work not
   selected is simply absent from the chosen offer.
   *Settled by:* deciding whether the demand object is per-trade and outlives the sale.

5. **What is the unit below the sale?**
   *Affects all three, differently.* Model C's scope is a priced unit that drives a job. Daidipya's
   sub-Job is a schedulable unit with a crew and an appointment. Joel's Scope Component is a
   trade-typed decomposition that is not schedulable. These are three different things and a
   complete model may need two of them.
   *Settled by:* separating the priced unit from the schedulable unit, or proving they are the same.

6. **Is there a customer-level running balance?**
   *Affects Joel.* Model C and Daidipya both carry a master invoice as the total owed. Joel has
   invoices settled by payments and no customer-level balance.
   *Settled by:* deciding whether AR is in scope for this model.

7. **Where do inbound funding sources live?**
   *Affects Model C and Daidipya.* Joel models first-party financing through approval, agreement
   and milestone funding; third-party by reference; card, ACH, cash and cheque; and insurance
   claims through supplements. Neither of the other two models this surface.
   *Settled by:* deciding whether to adopt Joel's money lane wholesale.

8. **Is a permit an entity, a task, or a gate?**
   *Affects all three.* Joel draws it as an entity and marks it a gap. Daidipya makes permit pull
   and close tasks on a task list. Model C treats it as both a gate and a sub-status.
   *Settled by:* deciding whether external dependencies need their own records or only their status.

9. **Are gates structure or configuration?**
   *Affects Model C and Joel.* Joel says explicitly that "money before work" is per-organisation
   configuration on a stage transition, not structure. Model C makes the gate one of five
   primitives. These may be compatible; nobody has checked.
   *Settled by:* comparing Model C's gate primitive against Joel's stage-transition policy.

10. **What is a Lead?**
    *Affects Daidipya primarily.* The glossary supports two readings: one thing the customer might
    buy, given that a lead carries a single trade; and one deal that might be sold, given that a
    lead owns the proposals, holds the financing and converts into a job. A multi-trade sale forces
    these apart.
    *Settled by:* choosing one reading, then deciding what sits at the other level.

11. **How is execution status held when parts diverge?**
    *Affects Joel primarily.* Daidipya tracks execution phase per sub-Job. Model C gives each job
    its own pipeline. Joel's job has one status and his scope components carry none, so two parts
    of one sale finishing weeks apart has no representation.
    *Settled by:* deciding whether status lives on the job or below it.

12. **At what level is margin answerable?**
    *Affects all three.* Model C computes at project level, Daidipya and Joel at job level. None
    computes per scope, sub-job or scope component, so per-trade margin within a bundled sale is
    not available in any of the three.
    *Settled by:* deciding whether per-part margin is a requirement.

13. **Are recurring service, warranties, installed equipment, commission and payouts in scope?**
    *Affects Model C and Daidipya.* Only Joel models them, and his flywheel — a job selling a
    service agreement that schedules events that book further jobs — is a claim about the business
    as much as the data.
    *Settled by:* a scope decision above the model.

14. **Naming collisions.** Three, all live:
    - **Project.** Model C's project contains the sale and precedes it. Joel's project is optional
      and groups jobs after the sale. Agreeing the word would hide the disagreement in question 1.
      Separately, "project" is already taken in Merlin as a design artefact carrying a bill of
      materials and an electricity profile.
    - **Scope.** Model C uses it for a priced unit of a proposal; Joel uses "scope component" for a
      trade-typed decomposition of a job; and the insurance sub-status uses "scope received" for
      the carrier's damage document. Two of these appear on the same record.
    - **Lead and opportunity.** Model C's opportunity survives decline and is per-trade. Both other
      models call their demand object a lead, and Daidipya's is the deal hub. The words are not
      interchangeable.
    *Settled by:* a naming pass once questions 1, 5 and 10 are answered, not before.

---

**Not in this document.** The Thompson scenario traced through each model, and a full vocabulary
reconciliation table. Both exist as analysis and can be added as companions if the group wants
them.
