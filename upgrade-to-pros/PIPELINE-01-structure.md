# The pipeline structure

**Five primitives a contractor's pipeline is built from. Reading document, 16 September 2026.**

> # Do not act on this yet
>
> **This is for understanding, not for building.** Nothing here has been mapped to a scenario, no
> screen has been agreed, and no decision has been taken about how much of it Upgrade to Pros will
> carry. **Read it, ask about it, and wait.**
>
> **A companion document, `PIPELINE-02-mapping-s15.md`, sketches how this might map onto S15.** That
> one is even more provisional than this one.
>
> **Where it came from.** Condensed from a design brief and a working reference written in August
> 2026, both in this repository. **The primitives and their rules below are unchanged from that
> reference.** The worked configuration in section 6 is unchanged from it too. What has changed is
> the entity model underneath, which section 7 sets out honestly rather than hiding.

---

## 1. The argument, which is the reason any of this exists

**Do not ship a pipeline. Ship the primitives a contractor builds one from, and let DeDe do the
building.**

Every contractor tracks projects differently, and **the variation is real and rational rather than a
symptom of disorganisation.** A storm restoration company running insurance claims needs different
tracking from a retail replacement shop taking cash and financed work. A company across forty
jurisdictions needs different permit handling from one working a single town. A five-person shop
where one person touches a job end to end needs a different view from a forty-crew operation with
dedicated claims specialists.

**The evidence is not only external.** Two internal attempts at sketching a roofing pipeline produced
two structurally different but equally defensible configurations, disagreeing with each other about
whether loan and insurance status should be columns or secondary fields. **If that variance exists
inside one designer's exploration, it exists many times over across the customer base.**

**This argument is untouched by anything that has changed in the entity model.** It is a position
about product shape.

---

## 2. Stage

**The primary pipeline position, visualised as a kanban column.**

- Exactly one at a time. **Stage is what determines a card's position on the board.**
- Ordered. Movement is normally forward, **but backward movement must be possible.**
- A stage may be **conditional**: eligible only where an attribute rule matches.
- Industry guidance suggests **eight to ten stages total**, with granularity pushed into tasks.

**On the word.** "Stage" is the data model concept and "column" is its visual representation. Stage
is near-universal across CRM tools. **"State" is deliberately avoided**, because it reads as a synonym
for stage to anyone with a software background.

---

## 3. Sub-status

**A secondary tracking field for an external process the contractor is waiting on and cannot
accelerate through their own effort.**

- **Independent of stage.** A sub-status does not change because the stage changed, and the stage does
  not change because a sub-status changed. **The only connection is where a gate explicitly links
  them.**
- **Any number active at once** on one card.
- Each has an **ordered set of values**.
- **Universal** (on every job) or **conditional** (activated by an attribute rule).
- **Which value set it uses may itself be attribute-driven.** A first-party claim and a third-party
  liability claim need different sets.
- **Displayed as a labelled pill on the card, never as a column.**

**That last rule is the whole distinction.** If the contractor can move it themselves it is a stage or
a task. If they can only wait on somebody else, it is a sub-status.

---

## 4. Task

**Work the contractor's own team must do, entirely within their control.**

- **Attaches to a stage.**
- **Four states**, and the last two are the interesting pair:
  - **Complete**
  - **Incomplete**
  - **Not applicable.** **System-set**, driven by an attribute rule. The task does not apply to this
    job.
  - **Skipped.** **Person-set.** The task applies and was deliberately passed over.
- **Optionally gating.** Most tasks are reminders, not blockers.
- Optionally assigned to a role. Deferred.
- **Displayed as a completion count on the card**, for example 3/5.

**Why not applicable and skipped are separate.** They look identical on screen and mean opposite
things. **A pattern of skipping is a signal that the default is wrong**, and collapsing the two states
destroys that signal.

**Three sources of tasks:**

1. **Universal.** Loaded on every job.
2. **Attribute-driven.** Loaded by job type, material, funding path or another attribute.
3. **Generated.** Compiled by DeDe from instructions the contractor has saved in Organization Context.
   The primary example is **a permit document checklist specific to a municipality.**

---

## 5. Gate, Board, and the rule engine

### Gate

**A condition that prevents advancing.**

- Sits on a transition, **between two stages or between two boards.**
- Driven by **a sub-status reaching a value, or by task completion.**
- **Every gate must have an articulable real-world reason.** Gates without one accumulate and get
  ignored.
- Only applies where the driving sub-status or task is active.
- Overridable. **Hard versus soft is still open.**

### Board

**A filtered view over a range of stages, usually aligned to a team.**

- **A card does not live on a board.** It becomes visible on one when its stage falls in that board's
  range.
- Boards exist to reduce noise, give specialists a relevant view, and let generalists focus on one
  part of the lifecycle.
- **Currently stage-range based.** Filtering by another attribute, such as trade, is a plausible
  extension and is not built.

### The attribute-rule engine

**One conditional mechanism, four targets:**

1. **Stage eligibility.** Does this stage apply.
2. **Sub-status activation.** Does this sub-status appear.
3. **Sub-status value set selection.** Which values does it use.
4. **Task set loading.** Which tasks appear.

Attributes that commonly drive rules: **funding path** (cash, financed, insurance), **jurisdiction**,
**HOA membership**, **job type** (replacement, repair, new construction, maintenance), **material**,
**property type**.

### Eligibility versus gating, which are easy to confuse

| | Eligibility | Gating |
|---|---|---|
| **Meaning** | Does not apply to this job | Applies, but not yet satisfied |
| **Set by** | Attribute rule | Sub-status value or task state |
| **Treatment** | Hidden, or marked not applicable | Blocked, pending |
| **Read as** | Ignore permanently | Work toward this |

### The configuration model

**Every primitive follows preset, recommend, customise.**

- **Preset.** Defaults shipped per trade.
- **Recommend.** DeDe proposes configurations and new options from what the contractor describes.
- **Customise.** The contractor accepts, modifies, or builds their own, through DeDe or directly.

---

## 6. The worked configuration: Dana's Roofing

**Mid-size, mixed retail and insurance, three roles touching a job: office manager, sales rep,
production manager. This is the configuration every existing mockup drew its stage and gate values
from.**

### Boards and stages

| Board | Stage | Tasks |
|---|---|---|
| **Leads & Sales** | New lead | 4 |
| | Working | 6 |
| | Sold | 4 |
| **Production** | Ops intake | 4 |
| | Orders & scheduling | 6 |
| | Final checks, day before install | 4 |
| | Installing | 8 |
| **Closeout & Payment** | Closeout | 6 |
| | Invoiced | 3 |
| | Closed | 2 |

**On "Working".** It collapses what other configurations split into Contacted, Inspected and Proposal
sent, because Dana's reps frequently inspect and quote in a single appointment.

### Sub-statuses

**On every job:**

| Sub-status | Values |
|---|---|
| **Financing** | Cash · Submitted · Approved · NTP |
| **Materials** | Not ordered · Ordered · Confirmed with date · Delivered |

**On some jobs, by attribute rule:**

| Sub-status | Values | Driven by |
|---|---|---|
| **Insurance** | Claim filed · Adjuster assigned · Adjuster inspected · Scope received · ACV released · Depreciation released | Funding path |
| **Permit** | Not required · Applied · Approved · Final inspection passed | Jurisdiction and scope |
| **HOA** | Not applicable · Submitted · Approved | Property in an HOA |

### Gates

| Transition | Condition | Reason |
|---|---|---|
| Leads & Sales → Production | Financing NTP, or insurance claim approved | Do not start work that may not get paid for |
| Ops intake → Orders & scheduling | HOA approved | The HOA controls colour and material; ordering early means eating a restock |
| Orders & scheduling → Final checks | Permit approved | Cannot schedule a crew against an unapproved permit |
| Final checks → Installing | Day-before checks complete | Rolling a crew to a job that is not ready is the expensive mistake |
| Closeout → Invoiced | Permit final inspection passed | Open permits cause problems at sale and with insurers |

### Tasks by stage

| Stage | Tasks |
|---|---|
| **New lead** | Qualify lead · Confirm service area · Confirm ownership · Capture funding path |
| **Working** | Initial contact made · Inspection scheduled · Inspection performed · Measurements captured · Proposal sent · Follow-up attempted |
| **Sold** | Contract signed · Deposit collected · Financing application submitted · Colour and material confirmed |
| **Ops intake** | BOM finalised · Permit application submitted · HOA submitted · Scope verified against contract |
| **Orders & scheduling** | Materials ordered · Delivery date confirmed · Dumpster ordered · Crew assigned · Date committed · Customer notified |
| **Final checks** | Weather checked · Materials verified on site · Dumpster verified on site · Customer check-in |
| **Installing** | Pre-install property photos · Tear-off · Deck inspected and rot documented · Change order approved if needed · Dry-in photos · End-of-day photos · Magnet sweep · Cleanup |
| **Closeout** | Final walkthrough · Punch list cleared · Municipal inspection scheduled · Municipal inspection passed · Warranty registered · Photo package sent |
| **Invoiced** | Final invoice sent · Depreciation released if insurance · Payment received |
| **Closed** | Job costed against estimate · Review requested |

**Attribute-driven additions.** Insurance jobs add *Meet adjuster on site* to Working and *Document
damage for supplement* to Ops intake.

**Generated.** A permit document checklist per municipality, attached to Ops intake. The worked
Brookline example: *Historic district form attached · Town contractor licence verified · Abutter
notice mailed.*

---

## 7. What has changed underneath this, and it matters

**The reference above says "a job occupies exactly one stage" and walks a job across all three boards,
from New lead to Closed. The entity model no longer supports that.**

Under the current model:

- **A Job does not exist until the hand-off.** It is the execution of one committed scope component.
- **Selling states live on the Lead**, which is one selling episode and **closes at the hand-off.**
- **The Project is the spine.** It derives a one-way label from the records beneath it and
  **explicitly carries no gates, no checkpoints, no configuration and no manual transitions.**
- **Jobs run uniform outer states** with trade-specific sub-states inside the middle one.

**So the ten stages split three ways and the document does not know it.**

| Dana's stages | Belongs to |
|---|---|
| New lead, Working, Sold | **The Lead** |
| Ops intake, Orders & scheduling, Final checks, Installing | **The Job** |
| Closeout | **The Job**, arguably |
| Invoiced, Closed | **The Project and the money**, not the job |

**Nothing about this was recorded until 16 September 2026**, and every mockup that used a stage or a
gate value took it from this document without noticing. It is now an open item.

**What survives the change untouched:**

- **The argument in section 1.** Untouched.
- **The five primitives and their rules.** Untouched. They describe a configuration mechanism, not an
  entity model.
- **The four task states**, and the reason not applicable and skipped are separate.
- **The sub-status definition and its value sets.** An external process you wait on and cannot
  accelerate is a coherent idea regardless of which record carries it.
- **Eligibility versus gating.**

**What does not survive:**

- **The claim that one card traverses all ten stages.** Three records do.
- **Boards as stage ranges over a single lifecycle.** If three records carry the stages, a board is a
  view over a record type as much as over a stage range.

---

## 8. What was already open before any of this

From the reference's own list, unchanged:

- **Hard versus soft gates**, and whether override is universal.
- Whether AI-inferred activation is proposed or automatic.
- **Whether ten default stages is too many.**
- Whether materials-confirmed is a genuine gate in practice or a vendor's idea of one.
- **Whether contractors think of proposal and signed contract as one moment or two.**

**Deferred:** migration of in-flight jobs, saved filtered views, role assignment on tasks, automations
as distinct from gates, Personal Context below Organization Context, HVAC and solar presets.
