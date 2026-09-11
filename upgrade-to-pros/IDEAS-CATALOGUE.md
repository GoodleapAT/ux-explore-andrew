# Ideas catalogue, Upgrade to Pros

**The curated version. An idea gets a record here once somebody intends to do something with it.**

> **Who may write to this file:** any surface that can write. Add a row to the index and a section
> below it. Status changes are edits. Nothing is ever deleted; an idea that goes nowhere becomes
> **dropped** with a reason.
>
> **A record is either a need or a move, never both.** A need is a problem, a customer situation or
> a story. A move is something we might build or do. They are separated because a need survives the
> move that was meant to satisfy it, which is the same reason a declined trade keeps its lead.

---

## Index

| ID | Kind | Title | Status | Appetite | Last touched |
|---|---|---|---|---|---|
| N-001 | Need | Declined work goes quiet and nobody brings it back | Exploring | A cycle | 2026-09-11 |
| N-002 | Need | A job can be blocked for weeks with nothing in its record saying so | Exploring | A week | 2026-09-11 |
| N-003 | Need | Recurring work has no selling surface | Raw | Unknown, needs shaping | 2026-09-11 |
| M-001 | Move | Open demand as a figure on the customer record | Raw | A session | 2026-09-11 |
| M-002 | Move | Raise a lead from a service visit finding | Raw | A week | 2026-09-11 |

**Status values.** Raw, exploring, parked, folded in, dropped. Parked and dropped are different: a
parked idea has a revive condition, a dropped one does not. Both require a reason.

**Appetite is not an estimate.** It is how much time is worth spending before the idea has to show
something. An idea with no appetite is a note, not a plan.

---

## N-001 · Declined work goes quiet and nobody brings it back

- **Kind:** Need
- **Origin:** Raised by Andrew while walking the Thompson scenario, 28 Aug 2026. Independently
  confirmed as a live gap in the team's own scenario branches, which call it the survivor problem
- **Evidence:** In the canonical scenario the customer declines a $38,900 roof in the room and asks
  to come back to it in spring. In every model on the table except Model C, that roof has no home
  after the session ends. The team's scenario notes say plainly that reporting must distinguish
  deferred from lost and that the distinction currently has nowhere to live
- **Status:** Exploring
- **Links:** Served by M-001. Partly addressed by the decision to make deferred a lead status with a
  required reason and a revive condition
- **Appetite:** A cycle
- **Where it would land:** The customer record, the project workspace, and whatever queue a
  salesperson works from in the morning
- **Last touched:** 2026-09-11

**What is still open.** The status exists now, and the reason and revive condition are required. What
does not exist is anything that makes a deferred lead arrive. A revive condition with no queue
reading it is a note in a database.

---

## N-002 · A job can be blocked for weeks with nothing in its record saying so

- **Kind:** Need
- **Origin:** Found in the team's financed multi-trade scenario, read 10 Sep 2026
- **Evidence:** In that scenario a windows job sits for twenty six days waiting on a city permit. The
  blocking fact lives on the permit record and nothing connects the two, so the job's own record
  shows a job that simply is not moving. The scenario's own summary calls this readiness gating at
  its most expensive
- **Status:** Exploring
- **Links:** No move attached yet. The mocks show one treatment, a derived blocked state with a
  pointer to the blocker and an elapsed day count, but that is a sketch rather than a record
- **Appetite:** A week
- **Where it would land:** The job view, the project workspace, and any job list that needs to sort
  by how long something has been stuck
- **Last touched:** 2026-09-11

**What is still open.** Whether blocked is an outer state of its own or a flag sitting on top of the
state the job was in. The reporting differs and the mocks currently assume the first.

---

## N-003 · Recurring work has no selling surface

- **Kind:** Need
- **Origin:** Emerged from the team's membership scenarios, read 10 Sep 2026, and from drawing the
  service plan view the same day
- **Rationale:** A maintenance visit is the cheapest access anyone gets to a customer's equipment,
  and it is where failures are noticed first. In the team's membership scenario a technician spots a
  failing condenser fan on a routine visit and the resulting repair becomes a separate journey with
  no recorded link back to the visit that found it. Nobody has said they want this, which is why this
  carries a rationale rather than evidence
- **Status:** Raw
- **Links:** Served by M-002
- **Appetite:** Unknown, needs shaping. The model has no considered answer for services yet, so this
  cannot be sized until that settles
- **Where it would land:** The service plan view, and the lead model
- **Last touched:** 2026-09-11

---

## M-001 · Open demand as a figure on the customer record

- **Kind:** Move
- **Origin:** Andrew, reviewing the customer record mock, 10 Sep 2026
- **Rationale:** Deferred and unpursued leads keep their estimates, so the figure is already
  computable. Showing it is the cheapest thing that would make deferred demand feel like something
  rather than nothing
- **Status:** Raw
- **Links:** Serves N-001
- **Appetite:** A session
- **Where it would land:** The financials card on the customer record
- **Last touched:** 2026-09-11

**The argument against it, which is real.** None of it is committed. Putting an estimate next to
money that is actually owed invites somebody to add the two together, or to forecast against it. If
it ships it needs a label that cannot be mistaken for a receivable.

---

## M-002 · Raise a lead from a service visit finding

- **Kind:** Move
- **Origin:** Andrew, drawing the service plan view, 10 Sep 2026
- **Rationale:** The technician is the only person who has seen the equipment. A finding captured as
  a watch item on the covered equipment, with an action to raise a lead against it, keeps the
  provenance intact: the lead would carry evidence rather than a guess, because somebody stood in
  front of the unit
- **Status:** Raw
- **Links:** Serves N-003
- **Appetite:** A week
- **Where it would land:** The service plan view, the visit job, and the lead model
- **Last touched:** 2026-09-11

**What has to settle first.** Whether the resulting work becomes a job on the service project or
starts a project of its own. The team's scenario does the second and records no link between the two,
which is the part worth fixing.
