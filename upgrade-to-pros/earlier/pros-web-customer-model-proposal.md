# Pros Web: customer, opportunity and job model

**Author:** Andrew Thompson (UX / Product Design)
**Status:** early thinking. Section 2 records what is decided, section 3 what is still open.
**Context:** these experiences require entities that do not exist in Merlin's current data model. See "Cross-platform design system strategy" and the Origin payments research for the surrounding landscape.

---

## 1. The model

### Customer

A person-level identity, which Merlin does not currently have. A customer can have **multiple properties**.

Stage ladder, monotonic — it only moves forward:

| Stage | Definition |
|---|---|
| **Lead** | Unqualified or unvalidated. We do not yet know if this is real |
| **Prospect** | Sales is, or will be, actively engaging them |
| **Customer** | Has, or has had, a job with us |

Reaching Customer is permanent. Pursuing further opportunities afterwards does not move them backwards.

Plus exits, so the pipeline has a way out that is not forward:

| Exit | Kind | Applies to |
|---|---|---|
| **Disqualified** | A judgement about fit. Wrong region, not a homeowner, no viable roof, credit | Lead, Prospect |
| **Lost** | Viable, but they declined or went elsewhere | Lead, Prospect |
| **Dormant** | Derived from inactivity, not chosen. Reversible on any new activity | Any stage, including Customer |

Dormant is deliberately not a peer of the other two. It is a flag that overlays a stage rather than replacing it, so a dormant prospect is still a prospect.

### Customer detail

**People.** Names, contacts, roles (owner, primary payer, and so on), small notes about individuals.

**Properties.** A peer list. Property attributes, measurements, satellite imagery, site model.

**Notes.** One note entity with a polymorphic parent — customer, opportunity or job — surfaced as a merged, filterable stream at customer level. No separate global notes store.

**Opportunities.** Potential jobs. Sourced from the customer directly, from CSR or sales, or from **DeDe** (our AI) based on what we know about the property and region.

- Carry a state reflecting whether sales has engaged, whether a proposal has been sent, and whether a job was created
- Proposals are created against an opportunity and iterate
- On conversion the opportunity **remains** in the list but is de-emphasised and shows that it became a job

**Proposals.** A priced offer against one opportunity, which iterates. The proposal is the container for a lot of what matters:

- **Scope of work** lives here, not on the job
- **Change orders** live here, and are noted on the job
- **Financing and loan options** live here, and loan information is then surfaced in both customer financials and job financials
- Estimate, and a reference to the property's site model

**Jobs.** Created when a contract is signed. Associated with an opportunity and with the accepted proposal. Multiple job types, from large projects down to a simple service.

Opportunities and jobs appear in customer detail as **high-level summary cards** — type, status, and enough to orient — acting as entry points into dedicated views.

**Financials.** The customer tier from the table below: what this customer owes across all of their jobs. A roll-up and a set of entry points, not a transaction ledger — individual transactions belong to the job, and the org-wide view is separate top-level navigation.

- Total invoiced, total paid, total outstanding across all jobs. Merlin's lead detail already has this pattern at lead scope, so it is being elevated rather than invented
- Aging — what is overdue and by how long
- Financing across jobs, with loan status per job
- Payment methods on file
- Possibly lifetime value or total revenue

**History.** A merged, filterable event stream for the whole relationship. Same pattern as Notes: events attach to whatever they concern — customer, opportunity or job — and the customer view rolls them up.

Events would include stage transitions (became a Prospect, became a Customer, went Dormant), opportunities created, won or lost, jobs created and completed, communications, payments received, and properties added.

Needs filtering by type from the start. For a customer with three jobs, an unfiltered stream is noise.

### Job detail

Thirteen areas, reached as entry points from a job detail page rather than crammed into one view:

1. Associated proposal, and its change orders noted here
2. Notes
3. Associated property and measurements
4. Scope of work, from the proposal
5. Scheduling — crews, deliveries, permitting, inspections
6. Work order
7. Materials order
8. Bill of materials
9. Documents, internal and customer-facing
10. Site inspection
11. Permitting and HOA
12. Financials — invoicing (one-off or milestone-based), transaction history, loan status from the proposal's financing
13. Job history — scheduling changes, transactions, change orders, customer communications

### Financial tiers

| Tier | Question it answers | Where it lives |
|---|---|---|
| **Job** | What is invoiced and paid on this job, and what is the loan status | Job detail |
| **Customer** | What does this customer owe across all their jobs | Customer detail, rolled up |
| **Org** | What is outstanding across everything. AR, payouts, disputes, exports | **Separate top-level nav**, not inside Customers |

---


## 2. Decided

**Stage naming is Lead → Prospect → Customer.** "Active" was rejected because it reads as *currently has work in progress*, whereas the intent is *has ever bought*.

**Stage is derived, not stored.** The ladder is monotonic, so it cannot drift. Derived from: has ever had a job → Customer; else has an engaged opportunity → Prospect; else Lead.

**Exits exist**, per the table in section 1. Disqualified and Lost are decisions; Dormant is derived and reversible.

**Origin's org-level views are not replaced by the customer view.** They remain as separate top-level navigation items. Both tiers need to exist: the customer view answers relationship questions, the org views answer financial-object questions.

**Jobs and opportunities are flat lists with the property shown on each card**, not nested under properties. Most customers will have one property, so nesting would add a level for no benefit in the common case. Property becomes a filter rather than a hierarchy.

**Job detail uses summary cards as entry points, not tabs.** Cards suit checking status across everything, which is what three different readers of the same job all need to do first. It also keeps a role-based lens possible later without restructuring.

**The Sales / Operations / Financials split is deferred as navigation**, but retained as a future *lens*. See section 4. Choosing summary cards over tabs is what keeps it possible.

**Leads is removed from the navigation.** The projected sidebar:

- Analytics
- **Customers** — with Lead / Prospect / Customer as stage filters
- **Payments** — from Origin: transactions, invoices, subscriptions, payment schedules
- Pricebook
- Settings — plus Origin's payment settings

**"Lead" is being redefined.** Going forward it means a customer stage, not Merlin's current address-plus-property entity. That entity needs a different name.

Worth separating two jobs here, because they have very different costs. **Changing the displayed language is cheap** and can happen now. **Renaming the entity in code is not**, because `Lead` appears in the route tree (`/leads/$leadId` and eight child routes), roughly 30 generated API models (`LeadReadAPIModel`, `LeadPipelineReadAPIModel`, `LeadNoteReadAPIModel` and so on), permission claims (`canReadLeads`, `LEAD_WRITE`), and the Pros App's own routes and Pipeline sub-tab. The UI can move ahead of the schema.

---

## 3. Still open

### The spine inverts

Merlin is address-keyed today: `Lead → propertyId`, proposals per lead, routes at `/leads/$leadId`. This model makes the customer the spine with properties beneath. So Merlin's current Lead becomes either a join between customer and property, or it disappears. Everything already built assumes the address is the root.

### Which of the thirteen job areas actually exist

Each needs one of three labels before this is scopeable:

- **Pros builds it**
- **Pros surfaces it from an integration**
- **Out of scope**

This is a design input, not an engineering detail. An entry point to a system that does not exist is a dead link. One pointing at an integration may have no summary at all, just a "view in X" link. Those look very different on the page.

Several already exist in some form as Pros App loan task cards, so parts of this are reconciliation rather than greenfield.

### Card anatomy

Opportunities and jobs probably should not share a card shape. An opportunity's key facts are intent, stage, proposal value and last activity. A job's are type, phase, next scheduled date and balance outstanding. One shape forces a lowest common denominator.

Converted opportunities need a real de-emphasis mechanism — two visual tiers, or a group collapsed by default. "Less prominent" is where things quietly become either invisible or clutter.

### DeDe-sourced opportunities need provenance

An opportunity the customer asked for and one an AI inferred are not the same object, even with the same shape. Without a source, a confidence signal, distinct treatment and a way to dismiss, the list fills with speculation and people stop reading it.

### The opportunity state machine

"Stays in opportunities but less prominent" implies a terminal state such as `converted`. Defining the full set now is cheap; retrofitting once there is data is not.

### Dormancy threshold

Dormant is derived from inactivity, which needs a definition. What counts as activity, and after how long? Different answers for a Prospect and a Customer are plausible.

### Are Notes and History one thing or two?

They overlap. Adding a note *is* a history event. Both use the same pattern: attached to a customer, opportunity or job, and rolled up at customer level.

One reading is that they are a single event stream viewed two ways. **Notes** is the authored subset, the things a human deliberately wrote. **History** is everything, including system events like stage changes and payments received. If that is right, they should share a data model and differ only in filter, which also means a note written on a job appears in the customer history for free.

The alternative is two separate stores, which is simpler to build and guarantees they drift.

Worth settling before either is built, because it is a data decision wearing the costume of a UI decision.

### Does dormancy also need a job-level equivalent?

A customer can be Dormant. A job that has not moved in three weeks is arguably a more urgent signal, and nothing in the model currently expresses it.

---

## 4. Future concept: the customer view changes by role

Not for the first prototypes, but documented now because the decisions being made today either enable it or foreclose it.

### The idea

The same customer detail view emphasises different things depending on who is looking. Three lenses, from the PM's original Sales / Operations / Financials split:

| Lens | Cares about | Promoted in the view |
|---|---|---|
| **Sales** | Winning the work | Opportunities, proposals, contacts, last activity, next step |
| **Operations** | Delivering the work | Jobs, scheduling, crews, materials, permits, inspections |
| **AR / Financials** | Collecting the money | Balances, invoices, payment history, financing status, aging |

### The principle that makes it safe

**A lens changes prominence and default expansion. It never changes availability.**

Role-based views are a common way to accidentally hide something critical. The mitigation is that no card is ever removed, only reordered or collapsed. Everything stays reachable by scrolling or expanding.

This matters most for small contractors, where the owner *is* all three roles. Hiding the financials from someone in a Sales lens would break exactly the users least able to work around it.

### How it would work

**Default from role, overridable by the user.** Derive the initial lens from the person's role, then let them switch and remember the choice. Someone with several roles gets a switcher rather than a guess.

**Implemented as card order and default expansion**, not as separate views. One page, three configurations of it.

### Why the current decisions matter

**Summary cards rather than tabs** is what makes this a configuration change instead of a rebuild. Tabs would harden the structure and force three separate views.

**The customer financial tier** is effectively the AR lens's home. Defining it now means the AR lens has something to promote later rather than needing new surface area.

### Precedent already exists in both systems

Origin models this today with five roles and an own-versus-all claim split, so a sales rep sees the money they brought in while an admin sees the organisation's. Pros Web already permission-filters its sidebar on `canReadLeads`, `canReadPricebook`, `canReadOrgSettings` and `canReadAnalytics`.

So the mechanism is not new. What would be new is using role to shape a view's emphasis rather than only to grant or deny access.

### Open questions

- Which lens does someone with all three roles get by default?
- Does the lens affect the customer **list** as well as the detail view? An AR person's useful list is probably sorted by outstanding balance, not by last activity.
- Are three lenses right, or does Operations split further once scheduling and materials are real?
