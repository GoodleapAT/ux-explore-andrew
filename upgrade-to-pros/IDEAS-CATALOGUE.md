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
| M-005 | Move | Read the board's UX DRAFT page designs, and decide whether to raid them | Raw | A session | 2026-09-11 |
| M-003 | Move | One shared entity map, lit per beat from the beat's own entity list | Raw | A week | 2026-09-11 |
| M-004 | Move | Three panes: the beat's words, the screen, and the lit map | Raw | A session | 2026-09-11 |

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

---

## M-005 · Read the board's UX DRAFT page designs, and decide whether to raid them

- **Kind:** Move
- **Origin:** Noticed while reading Joel's pull request 18 on the team repository, 11 Sep 2026
- **Rationale:** There is a section on the Pros Entities board, at node `137:2376`, titled "UX DRAFT,
  top-level pages, four lenses over one spine". Nine page designs with their rationale, which Joel's
  factory treats as binding on itself. I did not author it and have not read it. Reading it is cheap
  and there may be something in it worth taking
- **Status:** Raw
- **Links:** Nothing. It serves no need in this catalogue, which is the honest position
- **Appetite:** A session, and only when I choose to spend one
- **Where it would land:** Possibly nowhere
- **Last touched:** 2026-09-11

**What is in it, as far as I know without reading it.** A nav contract of four lenses over one spine:
Pipeline, Customers, Properties, Money. Detail surfaces embedded and list surfaces never. One row per
thing. And that Project is not a nav item, you land on it from a row's umbrella chip. The last of
those is the one that would touch my five views, which treat the project workspace as a first-class
page.

**None of it applies unless I adopt it.** If I do, that becomes a decision with a date and from then
on it is mine. Until then it is somebody else's position that happens to be about the same screens.

**A correction to how this was first written up.** The first version of this record was cast as a
need, on the grounds that another effort was building against a contract I had not engaged with. That
was wrong twice: it treated their position as a gap in mine, and it treated their pace as a reason for
me to act. See `../standards/external-work.md`.

---

## M-003 · One shared entity map, lit per beat from the beat's own entity list

- **Kind:** Move
- **Origin:** Joel's ux-factory, team pull request 18, read 11 Sep 2026
- **Rationale:** The constraint is the good idea, not the picture. One generated map is shared by all
  seventeen scenarios, no scenario holds map data of its own, and each beat lights it by matching
  nodes against that beat's entity chips. So the map and the entity list are one set of facts rendered
  twice and cannot drift apart. An edge lights only when both endpoints are touched, which is the rule
  the board's own overlays use. Their version is a re-layout rather than a copy of the board's
  coordinates, with lanes as rows so it sits wide and short under a screen
- **Status:** Raw
- **Links:** Nothing yet. It would serve any future design memo rather than a need in this catalogue
- **Appetite:** A week
- **Where it would land:** Design memos, and any scenario walkthrough
- **Last touched:** 2026-09-11

**What would have to change to use it.** Theirs is generated from a serialised snapshot of DRAFT v3,
so it carries DRAFT v3's mint rule, its single lead with several interests, and Service Plan beside
Project. Borrowing the mechanism means either generating it from my own model or accepting that the
map shows theirs.

---

## M-004 · Three panes: the beat's words, the screen, and the lit map

- **Kind:** Move
- **Origin:** Joel's ux-factory, commit of 9 Sep 2026, read 11 Sep 2026
- **Rationale:** A walkthrough where each step shows the beat's own words verbatim, the screen for that
  beat, and the entity map lit for it. The verbatim rule is the part worth keeping: the text is never
  paraphrased, so the screen can be checked against the team's own account rather than against
  somebody's summary of it
- **Status:** Raw
- **Links:** Pairs with M-003, which supplies the third pane
- **Appetite:** A session to try one scenario
- **Where it would land:** A design memo format, as an alternative to mockup plus argument
- **Last touched:** 2026-09-11

**The tension with the memo format.** Our memos put the argument beside or under the mockup, and the
argument carries the thinking. A three-pane walkthrough puts the *scenario* there instead. They answer
different questions: a memo argues a design, a walkthrough tests whether a flow holds. Probably both,
not one.
