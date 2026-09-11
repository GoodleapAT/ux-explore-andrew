# Pros Web: customer, opportunity and job — design brief

**Version 1.0 · 27 August 2026**

> ## Read this before starting
>
> **The parent structure in these files is under revision (28 August 2026).** A newer model, Model
> C, makes a **project** the container: opportunities, proposals and jobs sit inside it as peers,
> and the proposal is *not* the parent of jobs. Memo 1 and structural claim 3 below assume
> otherwise.
>
> Everything about the screens themselves still holds: the customer list, the customer detail
> composition across tiers, the job status header, the sheet pattern, the money vocabulary. What is
> changing is what owns what.
>
> If you have not started, wait for the revised package. If you have, build the screens and do not
> harden the parent relationships.

Paste this into Claude Design and attach the five files listed under "What you have been given".

---

## Before you build anything

### 1. Store the two memos verbatim

Save `memo-1-three-views.html` and `memo-2-two-models.html` in full, unedited, each recorded as
**version 1.0, 27 August 2026**. Do not summarise them and do not paraphrase them into your own
notes. They are the baseline we will diverge from, and I need the original text intact so the
divergence is legible later.

### 2. Keep a change log from the first change onward

Create and maintain `CHANGES.md` in the project. Every time we alter the model, a screen, a
component, a piece of vocabulary or a decision that appears in either memo, add an entry:

```
## 2026-08-28
- **Job view, stage list.** Changed from a clipped list to a horizontal stepper.
  Reason: the fade did not read as overflow in testing.
  Diverges from: memo 1, section C, "Two behind, two ahead, and a fade".
- **Vocabulary.** "Folio" renamed to "plan" for customer-facing copy only.
  Diverges from: memo 2, naming.
```

Each entry needs what changed, why, and which part of which memo it contradicts. Group by date,
newest last. This file gets handed back so the memos can be brought up to date, so write it for
someone who has read the memos but has not been in the room.

If a change is a decision on something the memos left open, say so explicitly. Those are the most
valuable entries.

---

## What you have been given

| File | What it is |
|---|---|
| `memo-1-three-views.html` | The primary brief. Customer list, customer detail and job view, drawn with the argument for each layout and the open questions. Also covers the three product tiers. |
| `memo-2-two-models.html` | Model A versus Model B for bundled work. Explains why a proposal has scopes, and the alternative we may still move to. Read for context; do not build from it. |
| `reference-project-management-config.md` | Dana's Roofing configuration: stages, sub-statuses, tasks, gates, boards. The job view uses this verbatim. |
| `reference-project-management-brief.md` | Why project management is configurable rather than shipped. Explains stage, sub-status, task, gate and board as concepts. |
| `reference-model-a-vs-b.md` | The written version of memo 2, easier to quote from. |

The memos are editorial documents, not specifications. **The argument column beside each mockup is
the important part.** Where you disagree with a layout, check the argument first, because most of
the choices are defended and the defence may change your mind. Where it does not, change the layout
and log it.

### Reading the mockups

**Small grey text prefixed with `[i]` inside a mockup is annotation, not interface copy.** It is
there to explain a choice to a reader of the memo. Do not build it, do not treat it as helper text,
and do not carry it into the design. Everything else inside a mockup frame is intended as real UI.

Anything labelled "placeholder", drawn with a dashed border, is a region the memo deliberately does
not address. Leave it as a region and do not invent content for it without logging that you did.

---

## What to build

Three views across three product tiers. Because two views do not exist at the lowest tiers, this is
**seven screens, not nine**.

| | Payments only | Payments + selling | Payments + selling + operations |
|---|---|---|---|
| **Customer list** | Build. Different columns to the other tiers, not the same columns with gaps. | Build. | Build. This is the one drawn in memo 1, section A. |
| **Customer detail** | Build. Four sections. The balance is the page, not a section within it. | Build. Seven sections. | Build. Nine sections. Drawn in memo 1, section B. |
| **Job view** | Does not exist. | Does not exist. | Build. Drawn in memo 1, section C. |

Memo 1 section D shows the three customer records side by side with the sections present at each
tier. Use it as the composition spec.

Tier is set **per organisation**, so no screen needs to handle mixed permissions within one account.

---

## Design system

I already have a design system set up in this project.

- **Use existing components wherever one fits.** Adapt content to the component rather than bending
  the component to the mockup.
- **Make your own judgement about where content goes.** The memo mockups are drawn to argue a
  structure, not to specify spacing, type or component choice. If the argument survives a different
  arrangement, use the better arrangement.
- **Create new components only where nothing suitable exists.** When you do, log it in `CHANGES.md`
  with what you tried first and why it did not fit.
- If a memo layout is impossible or ugly in the real system, say so plainly and propose the
  alternative. Do not silently approximate.

---

## What must survive

These are the structural claims the whole thing rests on. If a layout decision breaks one of them,
that is a reason to change the layout, not the claim.

1. **Opportunity, proposal and job are associated, not nested.** One proposal can answer several
   opportunities and produce several jobs. Nothing is indented under anything on the customer record.
   Three opportunities collapsing into two priced scopes must remain representable.
2. **The simple case stays simple.** One opportunity, one proposal, one job must look like today. No
   new concept appears until there is something to bundle.
3. **A proposal contains additive scopes.** Each has its own statement of work, itemisation and
   value, and produces one job or one service. "Scope" is a working name, chosen over section, part,
   job line and work package.
4. **Financing is presented at the proposal but modelled below it.** A job shows financing it does
   not own, and must say so.
5. **A change order attaches to one scope**, and shows both the scope value and the proposal total,
   because the proposal figure is what triggers re-underwriting.
6. **Stage, sub-status, task and gate are four different things.** Stage is position. Sub-status is
   an external process nobody on the crew can accelerate. Task is work the team controls. Gate blocks
   a transition. Never let "waiting on the city" and "someone needs to make a call" look the same.
7. **Not applicable and not yet must look different.** A contractor has to tell "ignore forever" from
   "work toward this" without reading.
8. **Notes and history are one event stream, filtered twice.** Not two stores.
9. **A customer is a person, above the address.** One customer can have several properties.
10. **A job never owns an invoice.** A master invoice is the total owed, attached to the proposal and
    rolling up to the customer. Payment requests draw against it or stand alone. Transactions are
    money moving.

---

## Where the memos are undecided

Do not treat these as gaps to fill silently. Make a call, build it, and log the call in `CHANGES.md`.

**Customer list.** Whether a customer row needs a stage at all. Whether the value column should
include work still out for decision.

**Customer detail.** Whether pinned notes belong to the customer or to the property, since a gate
code is a property fact. Whether the synopsis earns its space. Whether nine stacked sections need
tabs. Whether segmented controls remember their state.

**Job view.** Whether the stage list needs all ten stages or only the current board. Whether a
blocked task looks different from an unstarted one. Whether the fade reads as overflow or as
styling. Whether the change order is really a task or a sub-status, given it is waiting on the
lender.

**Tiers.** Whether a master invoice at the payments tier is created by hand, or whether that tier
runs on standalone payment requests with no total to draw against. This changes the balance card
materially: a contract total with draws against it is a different component from a running tally.

**Not drawn at all yet.** The sub-status block on the job view, gates other than the next one, board
context, and task ownership. Memo 1 section C has the sub-status card parked under "components to
explore later" with a note on why it is hard.

---

## Worked example

Every mockup uses one customer, and keeping it consistent is worth more than variety.

**Robert and Sara Thompson**, 1428 Maple Ave, Sacramento CA. Two contacts, Sara decides and Robert
handles billing. Two properties, the second a rental with no work on it. Customer since March 2024.

- **Opportunities.** Three open: gutter replacement (surfaced by DeDe), HVAC replacement (spotted by
  a contractor on a service visit), EV charger (customer asked). Three quoted, three won, one lost.
- **Proposals.** P‑1042 roofing and siding, accepted 14 Aug, two scopes. P‑1043 solar and battery,
  sent 21 Aug, one scope. P‑1044 HVAC replacement and care plan, ready to send, two scopes where
  one becomes a job and the other becomes a service.
- **Jobs.** JOB‑2291 roofing, $38,900, currently Installing, four of eight tasks done. JOB‑2292
  siding and windows, $34,200, Orders & scheduling, starts 2 Sep. Scope 2 covers two opportunities.
- **Service.** SVC‑102 annual HVAC care plan, active since April 2024, $34/mo.
- **Change order.** CO‑04, deck rot on the north slope, +$2,800. Scope 1 goes $36,100 to $38,900,
  proposal total $70,300 to $73,100, financing awaiting re-approval.
- **Money.** Total owed $73,100, paid $28,740, balance due $44,360.

The contractor is **Dana's Roofing**, running the configuration in
`reference-project-management-config.md`: three boards, ten stages, five sub-statuses, five gates.

---

## How to start

1. Store the memos and open `CHANGES.md`.
2. Read memo 1 end to end, including the argument columns.
3. Inventory the design system and tell me which memo components map to something existing, which
   need adapting, and which are genuinely new. **Do that before building anything.**
4. Build the operations tier first, since it is the fullest and the other two are reductions of it.
5. Then the selling tier, then payments.

One caution on the last step. The payments tier is a real product and a large part of the current
customer base, not a stub. A four-section record where the balance is the page is a different design
problem, not a subset of the nine-section one. Give it its own pass rather than deleting sections
from the full record.
