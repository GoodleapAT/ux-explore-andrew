# Configurable project management: reference

**Working reference. August 2026.** Companion to the design brief.

---

## Part 1: Vocabulary and rules

### Stage

The primary pipeline position a job occupies. Visualized as a kanban column.

- A job occupies exactly one stage at a time.
- Stage is what determines a job's position on the board.
- Stages are ordered. Movement is normally forward, but backward movement must be possible.
- A stage may be conditional: eligible only for jobs matching an attribute rule.
- Industry guidance suggests eight to ten stages total, with granularity pushed into tasks.

Note on terminology: "stage" is the data model concept, "column" is its visual representation. Stage is the term used almost universally across CRM tools. We avoid "state" because it reads as a synonym for stage to anyone with a software background.

### Sub-status

A secondary tracking field representing an external process the contractor is waiting on and cannot accelerate through their own effort.

- **Independent of stage.** A sub-status does not change because the stage changed, and the stage does not change because a sub-status changed. The only connection is where a gate explicitly links them.
- A job may have any number of active sub-statuses simultaneously.
- Each sub-status has an ordered set of values.
- A sub-status may be universal (applies to every job) or conditional (activates based on an attribute rule).
- Which set of values a sub-status uses may itself be attribute-driven. A first-party claim and a third-party liability claim need different value sets.
- Displayed on the job card as a labeled pill, not as a column.

### Task

Work the contractor's own team must do, entirely within their control.

- Attaches to a stage.
- Four states: complete, incomplete, not applicable, skipped.
  - **Not applicable** is system-set, driven by an attribute rule. The task does not apply to this job.
  - **Skipped** is person-set. The task applies but was deliberately passed over. Distinguishing these matters because a pattern of skipping is a signal the default is wrong.
- Optionally gating. Most tasks are reminders rather than blockers.
- Optionally assigned to a role. Deferred from current scope.
- Displayed on the job card as a completion count, for example 3/5.

Three sources of tasks:

1. **Universal.** Loaded on every job.
2. **Attribute-driven.** Loaded based on job type, material, funding path, or other attribute.
3. **Generated.** Compiled by DeDe from instructions the contractor has saved in Organization Context. The primary example is a permit document checklist specific to a municipality.

### Gate

A condition that prevents a job from advancing.

- Sits on a transition: between two stages, or between two boards.
- Driven by a sub-status reaching a value, or by task completion.
- Each gate should have an articulable real-world reason. Gates without one accumulate and get ignored.
- Only applies to jobs where the driving sub-status or task is active.
- Overridable, with the hard versus soft distinction still open.

### Board

A filtered view over a range of stages, usually aligned to a team.

- A job does not live on a board. It becomes visible on a board when its stage falls in that board's range.
- Boards exist to reduce noise, give specialists a relevant view, and let generalists focus on one part of the lifecycle.
- Currently stage-range based. Filtering boards by other attributes (trade, job type) is a plausible extension.

### The attribute-rule engine

One conditional mechanism, four targets:

1. Stage eligibility (does this stage apply to this job)
2. Sub-status activation (does this sub-status appear on this job)
3. Sub-status value set selection (which set of values does it use)
4. Task set loading (which tasks appear on this job)

Attributes that commonly drive rules: funding path (cash, financed, insurance), jurisdiction, HOA membership, job type (replacement, repair, new construction, maintenance), material, property type (residential, commercial).

### Eligibility versus gating

| | Eligibility | Gating |
|---|---|---|
| Meaning | Does not apply to this job | Applies, but not yet satisfied |
| Set by | Attribute rule | Sub-status value or task state |
| Treatment | Hidden or marked not applicable | Blocked, pending |
| Contractor reads it as | Ignore permanently | Work toward this |

### Configuration model

Every primitive follows preset, recommend, customize:

- **Preset.** GoodLeap ships defaults per trade.
- **Recommend.** DeDe proposes configurations and new options from what the contractor describes.
- **Customize.** The contractor accepts, modifies, or builds their own, via DeDe or directly.

---

## Part 2: Example configurations

### 2.1 Dana's Roofing (worked example, used in design)

Mid-size, mixed retail and insurance, three roles touching a job: office manager, sales rep, production manager.

**Boards and stages**

| Board | Stages | Tasks |
|---|---|---|
| Leads & Sales | New lead | 4 |
| | Working | 6 |
| | Sold | 4 |
| Production | Ops intake | 4 |
| | Orders & scheduling | 6 |
| | Final checks (day before install) | 4 |
| | Installing | 8 |
| Closeout & Payment | Closeout | 6 |
| | Invoiced | 3 |
| | Closed | 2 |

Note: Working collapses what other configurations split into Contacted, Inspected, and Proposal sent, because Dana's reps frequently inspect and quote in a single appointment.

**Sub-statuses**

Applies to every job:

| Sub-status | Values |
|---|---|
| Financing | Cash, Submitted, Approved, NTP |
| Materials | Not ordered, Ordered, Confirmed with date, Delivered |

Applies only to some jobs:

| Sub-status | Values | Driven by |
|---|---|---|
| Insurance | Claim filed, Adjuster assigned, Adjuster inspected, Scope received, ACV released, Depreciation released | Funding path |
| Permit | Not required, Applied, Approved, Final inspection passed | Jurisdiction and scope |
| HOA | Not applicable, Submitted, Approved | Property in HOA |

**Gates**

| Transition | Condition | Reason |
|---|---|---|
| Leads & Sales to Production | Financing NTP or insurance claim approved | Do not start work that may not get paid for |
| Ops intake to Orders & scheduling | HOA approved | HOA controls color and material; ordering early means eating a restock |
| Orders & scheduling to Final checks | Permit approved | Cannot schedule a crew against an unapproved permit |
| Final checks to Installing | Day-before checks complete | Rolling a crew to a job that is not ready is the expensive mistake |
| Closeout to Invoiced | Permit final inspection passed | Open permits cause problems at sale and with insurers |

**Tasks by stage**

| Stage | Tasks |
|---|---|
| New lead | Qualify lead, Confirm service area, Confirm ownership, Capture funding path |
| Working | Initial contact made, Inspection scheduled, Inspection performed, Measurements captured, Proposal sent, Follow-up attempted |
| Sold | Contract signed, Deposit collected, Financing application submitted, Color and material confirmed |
| Ops intake | BOM finalized, Permit application submitted, HOA submitted, Scope verified against contract |
| Orders & scheduling | Materials ordered, Delivery date confirmed, Dumpster ordered, Crew assigned, Date committed, Customer notified |
| Final checks | Weather checked, Materials verified on site, Dumpster verified on site, Customer check-in |
| Installing | Pre-install property photos, Tear-off, Deck inspected and rot documented, Change order approved if needed, Dry-in photos, End-of-day photos, Magnet sweep, Cleanup |
| Closeout | Final walkthrough, Punch list cleared, Municipal inspection scheduled, Municipal inspection passed, Warranty registered, Photo package sent |
| Invoiced | Final invoice sent, Depreciation released if insurance, Payment received |
| Closed | Job costed against estimate, Review requested |

Attribute-driven additions: insurance jobs add Meet adjuster on site (Working) and Document damage for supplement (Ops intake).

Generated: permit document checklist per municipality, attached to Ops intake. Brookline example: Historic district form attached, Town contractor license verified, Abutter notice mailed.

---

### 2.2 Sunrise Roofing (minimal)

Three crews, retail replacement and repair only, no storm or insurance work. Owner sells, one coordinator handles everything post-sale.

**Boards and stages**

| Board | Stages | Tasks |
|---|---|---|
| Jobs | Lead | 2 |
| | Quoted | 3 |
| | Sold | 3 |
| | Scheduled | 4 |
| | Done | 3 |

One board, because one person handles the whole post-sale lifecycle and a board split would only add navigation.

**Sub-statuses**

| Sub-status | Values | Applies |
|---|---|---|
| Financing | Cash, Submitted, Approved, NTP | Every job |
| Permit | Not required, Applied, Approved, Final passed | Conditional. Roughly half their work falls under the local repair threshold |

No insurance, no HOA, no materials sub-status. They buy off the shelf same-week and do not track orders formally.

**Gates**

| Transition | Condition | Reason |
|---|---|---|
| Sold to Scheduled | Financing NTP | Scheduled a job once on a loan that never funded |

One gate. They considered a permit gate and declined it, because they routinely schedule against a pending permit and have never had it bite them.

**Tasks by stage**

| Stage | Tasks |
|---|---|
| Lead | Confirm address in service area, Confirm homeowner |
| Quoted | Measure roof, Send quote, Follow up |
| Sold | Contract signed, Deposit collected, Color confirmed |
| Scheduled | Materials picked up, Dumpster ordered, Crew told, Customer told |
| Done | Cleanup and magnet sweep, Final invoice sent, Payment received |

**What this illustrates:** almost nothing from the roofing preset survives. Five stages instead of ten, one board instead of three, two sub-statuses instead of five, one gate instead of five. Shipping them Dana's configuration would be worse than shipping them a blank slate, because they would spend their first hour deleting things.

---

### 2.3 Meridian Exteriors (maximal)

Forty crews across three states, roughly eighty percent insurance restoration. Separate canvassing, sales, claims, production, and AR teams.

**Boards and stages**

| Board | Stages | Tasks |
|---|---|---|
| Canvass & Leads | Door knocked, Inspection booked, Inspected, Damage confirmed, Nurture | 3 to 5 each |
| Sales | Estimate prep, Presented, Follow-up, Signed | 4 to 6 each |
| Claims & Compliance | Claim filed, Adjuster meeting, Scope negotiation, Supplement, Approved for production | 5 to 8 each |
| Production | Ops intake, Orders, Day-before checks, Installing, Install complete | 4 to 9 each |
| Closeout & AR | Final inspection, Warranty filed, Invoiced, Collections, Closed | 3 to 6 each |

Twenty-four stages across five boards. Notable: they want a dedicated Claims & Compliance board with real stages, which is the structure we sketched early and then deleted as unnecessary for Dana. For a company where claims work is a distinct department with its own specialists and its own queue, it is essential.

**Sub-statuses**

Applies to every job:

| Sub-status | Values |
|---|---|
| Financing | Cash, Submitted, Approved, NTP |
| Materials | Not ordered, Ordered, Confirmed with date, Delivered, Verified on site |

Applies only to some jobs:

| Sub-status | Values | Driven by |
|---|---|---|
| Insurance | Claim filed, Adjuster assigned, Adjuster inspected, Scope received, ACV released, Depreciation released | Funding path |
| Supplement | Not needed, Gap identified, Submitted, Under review, Approved, Partially approved, Denied | Scope gap found. Repeats; carries requested, approved, and added amounts |
| Mortgage endorsement | Not applicable, Check received, Sent to mortgagee, Under review, Endorsed, Escrow draws, Released | Insurance funding plus mortgage on property |
| Permit | Not required, Applied, Under review, Approved, Dry-in passed, Final passed | Jurisdiction |
| HOA | Not applicable, Submitted, Under review, Approved, Denied | Property in HOA |
| Warranty registration | Not applicable, Eligible, Submitted, Registered | Enhanced warranty sold. Deadline-bearing |

Eight sub-statuses. Supplement is their most-used field and does not appear in Dana's configuration at all. Mortgage endorsement exists because it routinely adds weeks to collection on insurance jobs.

**Gates**

Nine, including the five from Dana's configuration plus:

| Transition | Condition | Reason |
|---|---|---|
| Claims to Production | Supplement resolved or not needed | Do not build against a scope still under negotiation |
| Ops intake to Orders | Mortgage endorsement not blocking | Cash flow. Will not buy materials against funds sitting in escrow |
| Installing to Install complete | Dry-in inspection passed | Required in two of their three states |
| Invoiced to Closed | Depreciation released | Job is not closed until the second check lands |

**Tasks**

Heavy. Their Installing stage carries fourteen tasks, most of them photo documentation, because insurance carriers expect three distinct photo sets and thirty to sixty images per storm claim.

Generated tasks do the most work here. They operate across dozens of municipalities in three states, and the permit document checklist varies by every one. This is the capability that would be hardest for them to replace with manual configuration.

**What this illustrates:** the model has to stretch to twenty-four stages, eight sub-statuses, nine gates, and hundreds of tasks without collapsing. Their configuration and Sunrise's are almost unrecognizable as the same product.

---

## Part 3: Deferred and open

**Deferred**

- Migration of in-flight jobs from an existing system
- Saved filtered views
- Role assignment on tasks
- Automations (active movement) as distinct from gates (passive blocking)
- Personal Context as a second tier below Organization Context
- HVAC and solar presets

**Open**

- Hard versus soft gates, and whether override is universal
- Whether AI-inferred activation is proposed or automatic
- Whether ten default stages is too many
- Whether materials-confirmed is a genuine gate in practice or a vendor's idea of one
- Whether contractors think of proposal and signed contract as one moment or two
