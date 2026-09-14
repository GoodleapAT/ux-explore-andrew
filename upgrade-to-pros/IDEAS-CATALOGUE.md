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
| M-003 | Move | One shared entity map, lit per beat from the beat's own entity list | Raw | A week | 2026-09-14 |
| M-004 | Move | Three panes: the beat's words, the screen, and the lit map | Raw | A session | 2026-09-14 |
| M-006 | Move | Surface the upsell opportunity on the view where it occurs | Raw | A session | 2026-09-14 |
| N-004 | Need | Demand that arrives later cannot join a sale already in progress | Raw | A cycle | 2026-09-14 |
| M-007 | Move | Merge two projects | Raw | A week | 2026-09-14 |
| M-008 | Move | Qualify a new inquiry into an existing lead | Parked | A session | 2026-09-14 |

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

**Andrew's position, 14 Sep 2026.** This is one of the elements he wants, and it is now covered by a
decision: the framework is not adopted, individual elements may be adopted or translated. So this
record changes from "worth raiding" to **wanted, route undecided**. The route is the open part, and
the decision above says which route is closed.

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

---

## M-006 · Surface the upsell opportunity on the view where it occurs

- **Kind:** Move
- **Origin:** Andrew, 14 Sep 2026, listing what he would eventually want shown for each view. Prompted
  by elements in Joel's UX factory, but this one is his rather than borrowed
- **Rationale:** The other four things he named are documentation about a screen. This one is not. An
  upsell opportunity is a claim that the screen itself should surface a moment to sell, which makes it
  a product feature rather than an annotation. Nobody has asked for it, so this is rationale and not
  evidence
- **Status:** Raw
- **Links:** Serves N-003, recurring work has no selling surface. Overlaps M-002, raising a lead from
  a service visit finding, which is the same idea at one specific moment. **The board's wedge-first
  rule is the adjacent external idea**, Joel's, not adopted: a dark entity renders as an empty panel
  advertising the capability next to it
- **Appetite:** A session, to decide whether it is an annotation or a feature. That decision is most
  of the work
- **Where it would land:** Unclear, and that is the point. If it is annotation it belongs beside a
  mockup. If it is a feature it belongs in the component library as a declared position, which is the
  same mechanism as advertising an absent capability
- **Last touched:** 2026-09-14

**The question to settle first.** Whether an upsell opportunity is something the design surfaces to a
reviewer, or something the product surfaces to a contractor. Those are different pieces of work and
the phrase covers both without distinguishing them.

**Andrew's position, 14 Sep 2026.** Wanted. He named five things he would eventually like on each
view: the entities in use and the connections between them, the part of the script being addressed,
why this screen, gaps, and upsell opportunities. **Four of the five already exist somewhere in this
system**, which is the useful finding:

| What he named | Where it already is |
|---|---|
| Entities used, and their connections | M-003, the shared map lit per beat |
| The part of the script addressed | This record's verbatim pane |
| Why this screen | The argument column of the design memo format, rendered per view rather than per memo. A relocation, not a new thing |
| Gaps | The object register, filtered to one view. A rendering of a store we keep, not a new store |
| Upsell opportunities | **Nothing.** It is not a documentation element at all. See M-006 |

So this record grows a fourth pane rather than staying at three, and the two new panes are cheap
because their content is already written down somewhere.

---

## N-004 · Demand that arrives later cannot join a sale already in progress

- **Kind:** Need
- **Origin:** Fell out of the team's latest model, 14 Sep 2026, where creating a lead creates a project.
  Andrew named the consequence himself: project merging may be needed
- **Rationale:** A lead holds several interests, so three trades discussed in one conversation are one
  lead and one project and nothing needs joining. **The gap is across time.** A customer who enquires
  about a roof in July and a driveway in September has two inquiries, two leads and two projects, and
  the second cannot be sold as part of the first. That is the same bundling this container exists for,
  arriving late. Nobody has said they want it, so this is rationale rather than evidence
- **Status:** Raw
- **Links:** Served by M-007. **Note this is the original argument for the container, reappearing.** The
  container exists so a decision to sell several things together leaves a trace; one-lead-one-project
  handles that within a conversation and not across two
- **Appetite:** A cycle
- **Where it would land:** The lead, the project, and whatever a salesperson works from
- **Last touched:** 2026-09-14

**The cheap alternative worth testing first.** If a second inquiry could be qualified **into an
existing lead** rather than into a new one, no merge is ever needed. That moves the problem from
merging projects, which is expensive, to routing demand, which is a decision somebody makes anyway
when they pick the thing up.

---

## M-007 · Merge two projects

- **Kind:** Move
- **Origin:** Andrew, 14 Sep 2026: "since a lead creates a project, project merging may be needed at
  some point"
- **Rationale:** The direct answer to N-004. Two projects become one, so the work can be sold,
  scheduled and billed together
- **Status:** Raw
- **Links:** Serves N-004. Recorded as T-11 because it follows from a team position rather than from
  anything we chose
- **Appetite:** Unknown, needs shaping, and deliberately so. **The shaping is most of the work**
- **Where it would land:** The project, and every register that carries a project reference
- **Last touched:** 2026-09-14

**The boundary is set, 14 Sep 2026: a merge is prohibited once a project has a won proposal.** That
is what moved the appetite from unknown to a week. Every expensive case is now out of scope by
definition, because a project holding a contract, an invoice, jobs or a payment plan has a won proposal
behind all four. **What is left to shape is a merge of two containers that hold only demand**, which is
mostly a question of what happens to two leads and their interests.

**It may still not be the right shape.** M-008 avoids the merge entirely by qualifying a second
inquiry into the lead that already exists. Andrew's view, 14 Sep: a good idea, for the future. So this
record stays live and M-008 is parked rather than the other way round.

---

## M-008 · Qualify a new inquiry into an existing lead

- **Kind:** Move
- **Origin:** C, 14 Sep 2026, working out why project merging would be needed at all. **Endorsed by
  Andrew the same day** as a good idea to consider in the future
- **Rationale:** Merging projects is expensive because a project accumulates commitments. Routing
  demand is cheap, because somebody is already making a decision at the moment they pick a new inquiry
  up. If a second inquiry can be qualified **into the lead that already exists** rather than into a new
  one, there is never a second project and nothing to merge. **The problem moves from repair to
  routing.**
- **Status:** **Parked**, with a revive condition: **revive when project merging is picked up, or when
  demand routing is designed, whichever comes first.** It should be ruled in or out before M-007 is
  built, because if this works M-007 is mostly unnecessary
- **Links:** Serves N-004. **Competes with M-007** rather than complementing it
- **Appetite:** A session to decide whether it holds
- **Where it would land:** Whatever surface a new inquiry is worked from
- **Last touched:** 2026-09-14

**The strongest argument for it, found while restating the worked example.** The Thompson case already
needs this on day one. Robert contacts about the roof on 21 July and Sara contacts about the siding on
22 July: **two separate contacts, one lead.** So qualification is already an act of routing demand into
a lead rather than minting one per inquiry, and this move is not a new mechanism. It is the same
mechanism applied later in time.

**The argument against, which is real.** Qualifying into an existing lead means the lead's scope grows
after it has been qualified, and the project created from it grows with it. A salesperson who accepted
a lead about a roof can find a driveway in it. That may be exactly right, or it may be the thing that
makes people distrust the container.
