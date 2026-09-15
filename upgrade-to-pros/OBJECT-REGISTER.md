# Objects not in the model

**Things a screen needed that the entity model has no entity for.**

> **Who may write to this file:** any surface that can write. One row in the index, one section
> below. Edit a section when its status changes. Nothing is deleted; an object that dies becomes
> **dropped** with a reason.

**The model is neither perfect nor comprehensive.** It was an attempt to find the entities needed to
address a wide range of scenarios, not a complete inventory of everything a product touches. So
screens will keep needing things it does not have. That is normal, and the point of this file is to
stop each one being either silently invented or silently refused.

## The fields

| Field | What it means |
|---|---|
| **Object** | What it is, in a few words |
| **Purpose** | What it does for somebody. Not what it is made of |
| **Criticality** | What happens if it never exists. **Blocking**, a scenario cannot be drawn honestly without it. **Degrading**, drawable but the screen tells a worse or less truthful story. **Exploratory**, drawn to see what it would be like |
| **Intent** | Why it was drawn. **Fill**, to complete a UX so the rest can be judged. **Probe**, to test whether it should exist. **Propose**, we think it belongs in the model. More than one is normal |
| **Hold** | How tightly we are holding it. **Loose**, drawn once, do not build on it, and **if a later decision contradicts it the object loses without argument**. **Watch**, keep it in view and revisit when something changes. **Pursue**, actively heading towards it |
| **Where it was needed** | Which mock, which step, which comment |
| **To the team** | Whether it should go to Joel as a model contribution, and whether it has |

**Why criticality is three named values and not a number.** A one-to-five scale with only its
endpoints defined puts everything on three and stops discriminating. Each name here says what happens
if the object is missing, which is the only thing anybody wants to know.

**Hold is the field that keeps this honest.** Most of these are possibilities, and a possibility that
nobody is holding loosely quietly becomes a requirement. Loose is the default until somebody argues
otherwise.

---

## Index

| Object | Criticality | Intent | Hold | Status |
|---|---|---|---|---|
| Communications | Degrading | Fill, propose | Loose | Open |
| Live call transcription | Degrading | Fill, probe | Watch | Open |
| Lead origin as a first-class attribute | Blocking | Propose | Pursue | **Folded into the model, 15 Sep 2026** |
| A lead nobody has raised with the customer | Degrading | Probe | Watch | Open |
| A receipt for a derived status | Degrading | Propose | Watch | Open |
| A queue that surfaces a revive date | Blocking | Propose | Pursue | **Folded into the model, 15 Sep 2026** |
| After-render of the property | Exploratory | Fill, probe | Loose | Open |
| Per-customer profit | Degrading | Probe | Loose | Open |
| Pipeline value from open leads | Degrading | Fill, propose | Watch | Open |
| Equipment as a schedulable resource | Degrading | Propose | Watch | Open |
| Cross-organisation crew assignment | Blocking | Propose | Watch | Open |
| Elements stored by the job | Degrading | Fill | Pursue | Open |
| Customer role against a property | Blocking | Propose | Pursue | Open |
| How site detail references the property | Blocking | Probe | Pursue | Open |
| Advisor availability and travel time | Blocking | Fill, propose | Watch | Open |
| Readiness gating between an order and a visit | Blocking | Propose | Pursue | Open |
| A follow-up after the work is finished | Degrading | Probe | Loose | Open |
| Near-match search before a record is created | Blocking | Fill, propose | Pursue | Open |
| A retained reason for a dismissal | Degrading | Propose | Watch | Open |

---

## Communications

- **Purpose.** Calls, texts, notifications and the threads they form, shown on a history or activity
  card so a person can see what was said as well as what was recorded.
- **Criticality:** Degrading. Every scenario has people phoning each other and none of it leaves a
  trace, so a history card reads as a list of database events rather than a relationship.
- **Intent:** Fill and propose. It was drawn to make the activity card look like a real thing, and
  it is also a reasonable candidate for the model.
- **Hold: loose.** A possibility, not a direction. **Do not build on it.** If the model settles in a
  way that leaves no room for it, it goes without argument.
- **Where it was needed.** The customer record, in the request for a fuller history covering notes,
  objects created and edited, and communications.
- **To the team.** Yes, eventually. The team's own scenarios flag it repeatedly as having no entity
  anywhere, so this is a shared gap rather than ours.

## Live call transcription

- **Purpose.** Show what is being said while a call is happening, beside the form somebody is typing
  into, so the person taking the call is not the only record of it. Andrew asked for it on the capture
  screen on 15 September, in place of the trade picker.
- **Criticality:** Degrading. The screen works without it. **But the capture screen's whole problem is
  that somebody is typing while somebody else talks**, and a transcript is the only thing on the page
  that addresses that directly rather than organising around it.
- **Intent:** Fill and probe. Drawn so the layout can be judged, and drawn to find out whether a
  transcript beside a form helps or competes.
- **Hold: watch.** Stronger than loose, because if transcription exists the capture screen is a
  different design, and weaker than pursue, because nobody has said it exists.
- **Where it was needed.** The S14 canvas, frame 01, in Andrew's comment of 15 September: "let's
  simulate a live transcript of the call".
- **To the team.** Not yet. **This is a capability question before it is a model question**, and the
  first thing to establish is whether calls are recorded at all, which is a platform fact rather than
  a design one.
- **Note.** Drawn as a proposal and labelled as one, per the ruling of 15 September. **Anything that
  shows it must not imply the transcript is a fact.**

## Lead origin as a first-class attribute

- **Purpose.** Record which surface and which party raised a lead, so it can be filtered, counted and
  routed. A homeowner in the app, a suggestion from the system, and a person on a call are three
  different things that currently all read as prose in a sub line.
- **Criticality:** Blocking. Step 2 of the S15 grid is the case: a lead nobody has spoken to the
  customer about looks exactly like one somebody raised. No screen can tell them apart.
- **Intent:** Propose. This is not decoration, it is missing structure.
- **Hold: pursue.**
- **Where it was needed.** Every step of the customer record in the S15 grid, and named by CD as the
  first thing the model made impossible.
- **To the team.** Yes, and it matches their own register item about actor and channel attribution,
  which they call sharpest when the suggestion comes from a system rather than a person.

## A lead nobody has raised with the customer

- **Purpose.** A state between existing and being worked, for a lead the system or a rep created
  which has never been mentioned to the customer. Distinct from new and unassigned.
- **Criticality:** Degrading. Drawable as new, but a rep working the record cannot tell what has been
  said out loud, which is exactly the thing they need to know before they call.
- **Intent:** Probe.
- **Hold: watch.** Revisit when the lead status set is next opened.
- **Where it was needed.** Step 2 of the S15 grid, where the windows lead has an estimate's worth of
  detail and has never been mentioned to anyone.
- **To the team.** Not yet. Settle whether it is a status or an attribute first.

## A receipt for a derived status

- **Purpose.** A way for a computed status to show what produced it. The project reads pursuing, then
  sold, then in progress, and the derivation is visible nowhere.
- **Criticality:** Degrading. People do not trust a status they cannot set and cannot explain, and
  they work around it.
- **Intent:** Propose.
- **Hold: watch.** The explanation box that carried this was removed as explanatory copy, correctly.
  What is missing is a disclosure affordance, which is a component question as much as a model one.
- **Where it was needed.** The project workspace at every step, and named by CD as impossible.
- **To the team.** Not yet.

## A queue that surfaces a revive date

- **Purpose.** Something that makes a deferred lead arrive. The roofing lead reads deferred to March
  2027 across three steps of the grid and nothing makes March happen.
- **Criticality:** Blocking, for the claim the model rests on. Deferred is not lost is the sharpest
  thing in the model, and without a queue it is a note in a database.
- **Intent:** Propose.
- **Hold: pursue.**
- **Where it was needed.** The customer record, steps 7 to 9, and in the five views memo before that.
- **To the team.** Yes. Their scenarios record the same need as deferred must be distinguishable from
  lost, and say its home has moved without saying where to.

## After-render of the property

- **Purpose.** An image on the project showing the home as it would look once the work is done,
  beside one showing it now.
- **Criticality:** Exploratory.
- **Intent:** Fill and probe. Asked for as a small image on the project, with the after render
  described as a possibility rather than a requirement.
- **Hold: loose.** **A product idea being looked at, not a direction.** Drawn as a placeholder so
  real photographs can go in; the render half should not be mocked as though it exists.
- **Where it was needed.** The project workspace at step 5.
- **To the team.** No.

## Per-customer profit

- **Purpose.** A profit and loss figure on the customer record, across everything ever sold to them.
- **Criticality:** Degrading. Wanted, and not currently answerable.
- **Intent:** Probe.
- **Hold: loose.**
- **Where it was needed.** The customer record financials card.
- **Blocked by something real.** Revenue lands at the project and costs land on the jobs, so a profit
  figure on a person needs a revenue allocation nobody has specified. This is the same gap that makes
  per-job margin unavailable, surfacing one level up.
- **To the team.** Not until the allocation question is settled.

## Pipeline value from open leads

- **Purpose.** The sum of retained estimates on open and deferred leads, shown on the customer record
  as potential revenue.
- **Criticality:** Degrading.
- **Intent:** Fill and propose. Easier than per-customer profit, because it needs no allocation: the
  deferred roof already carries its estimate.
- **Hold: watch.**
- **Where it was needed.** The customer record financials card, asked for alongside profit.
- **The catch.** It needs more open leads than the worked example has, so either the example grows or
  the card is drawn unrealistically thin.

## Equipment as a schedulable resource

- **Purpose.** Plant and equipment booked against a job the way a crew is.
- **Criticality:** Degrading.
- **Intent:** Propose.
- **Hold: watch.**
- **Where it was needed.** Not in our mocks yet. Recorded because the team's own scenario names it as
  a gap with no entity anywhere.
- **To the team.** Already theirs.

## Cross-organisation crew assignment

- **Purpose.** A subcontractor's crew working on your job, with scoped visibility into it.
- **Criticality:** Blocking for the S15 telling, where the windows job goes to a subcontractor.
  Currently drawn as an ordinary crew assignment, which is not what it is.
- **Intent:** Propose.
- **Hold: watch.**
- **Where it was needed.** The job view from step 8, and the worked example names the subcontractor
  so a screen has something to show.
- **To the team.** Already theirs, flagged in their multi-trade scenario as unmodelled.

## Elements stored by the job

**Four named, and the list is explicitly not exhaustive.** Forms, checklists, documents and photos.
Andrew, 14 Sep 2026: "These four elements can be stored by the job. There will be other objects that
aren't even listed here, but these are some we decided to note."

**The non-exhaustiveness is the important part of this record.** It is the difference between a list
somebody can complete and a category somebody has to keep adding to. Anything else a job turns out to
store belongs here rather than in a new record.

- **Purpose.** The task lists, sign-off checklists, documents and photographs that accumulate against
  a job and are shown on the job view.
- **Criticality:** Degrading. Our mocks already drew task lists, so the screens are telling a story the
  model does not back.
- **Intent:** Fill. Not proposed as an entity, deliberately.
- **Hold: pursue**, unusually for something not being proposed. Andrew, 14 Sep 2026: "Forms and
  checklists are not really official entities at this time. We just know we want them to be part of
  the experience, so we will continue to include them."
- **Where it was needed.** The job view, and comparison rows D-19 and D-21. **DRAFT v3 has Forms /
  Checklists and Photos / Docs as entities on the job**, so this is the one place we decline to adopt
  theirs while still drawing the thing. Every other row where ours was thinner was ruled adopt-theirs.
- **To the team.** No. We are drawing it without claiming it, which is exactly the distinction the
  deviations register exists to keep.

**Why this is in the register rather than adopted.** Every other row where our model was thinner was
ruled Adopt theirs. These two were not. The screens keep drawing the four elements; the model stays
silent about them. If that combination ever needs defending, the reason is here rather than in the
comparison.

## Customer role against a property

- **Purpose.** What a customer actually *is* in relation to an address. Owner, occupier, landlord,
  buyer mid-purchase. Neither model says.
- **Criticality:** Blocking. It sits underneath the anchoring question and it decides who may authorise
  work, who is billed, and what survives a sale.
- **Intent:** Propose.
- **Hold: pursue.**
- **Where it was needed.** Andrew raised it, 14 Sep 2026, while ruling comparison row D-04: a property
  is transitory in relation to the customer, who may move away, move to another property, or hold
  several, "and we have yet to resolve customer role and property, that is, is the customer the owner,
  do they just live there, etc."
- **To the team.** **Yes, and it has not gone yet.** Their dual anchor does not answer it either, so
  this is a contribution rather than a question.

**Note the shape of this one.** D-04 looked like ours simplifying and theirs being more precise.
Adopting their dual anchor would have closed the row without touching the real question, which is a
worked example of why an omission is safe to leave but not safe to assume will stay quiet.

## How site detail references the property

- **Purpose.** A route between the notes, measurements, photos and findings captured about a site and
  the property they describe, so the next person to visit does not start blind.
- **Criticality:** Blocking for anything that shows a property's history.
- **Intent:** Probe.
- **Hold: pursue.**
- **Where it was needed.** Andrew, 14 Sep 2026, ruling comparison row D-12: "we also need to figure out
  how all these site details and notes are referenced to and by the property."
- **To the team.** Not yet. It is downstream of what a site assessment turns out to be, which is its
  own open thread.

## Advisor availability and travel time

- **Purpose.** Who can attend, when, and how far they are from the address, so a same-day arrival
  window can be promised honestly.
- **Criticality:** Blocking for S14. Beat 2 books a 4pm visit from a 7:54am call and the narrative
  says nothing about how the CSR knows the advisor is free.
- **Intent:** Fill and propose. Drawn to make beat 2 possible, and it is also a reasonable candidate
  for the model.
- **Hold: watch.** A scheduling surface is a large thing and this is one screen's worth of it.
- **Where it was needed.** Memo 7, section B. **The script gives the evidence for it accidentally**:
  the advisor arrives ten minutes late, which is what happens when nobody can see that his previous
  call ends across town at 3:10.
- **To the team.** Worth raising. Neither model has it and every selling scenario assumes it.

## Readiness gating between an order and a visit

- **Purpose.** A link between the things a visit depends on and the visit itself, so a booked crew is
  not sent to a house where the equipment has not arrived.
- **Criticality:** Blocking. It is the mechanism beat 11 runs on.
- **Intent:** Propose.
- **Hold: pursue.**
- **Where it was needed.** Memo 7, sections I and J, drawn as one card that reads Blocking 0 and then
  Blocking 1 without changing shape. **The script names this as unmodelled in its own findings**, so
  this is their gap as much as ours.
- **To the team.** **Yes, and they already know.** It is in their register.

**Note what makes this one cheap.** Everything the card shows already exists as a record: an order
with a promised date, two permits with states, a visit with a date. **The gap is the link, not the
data**, which is unusual in this register and makes it the most buildable thing in it.

## A follow-up after the work is finished

- **Purpose.** Somewhere for the call to the customer after completion, and for a review request, to
  live and be owned.
- **Criticality:** Degrading. The work is done and paid for; this is the difference between a job and
  a customer relationship.
- **Intent:** Probe.
- **Hold: loose.**
- **Where it was needed.** Memo 7, section N, and **not drawn** because nothing in either model can
  hold it. The script's own last beat asks the question and leaves it open: a tail step on the job, a
  checklist at the lead, or a customer-level feature.
- **To the team.** Their question originally. Ours only inherits it.

## Near-match search before a record is created

- **Purpose.** A CSR under time pressure needs to know whether the person on the phone already
  exists, before anything is created. Neither model holds a candidate, a match reason, or the act of
  resolving one.
- **Criticality:** Blocking. The failure mode is a duplicate customer or a wrongly merged household,
  and it happens in the first ninety seconds of every inbound call.
- **Intent:** Fill and propose.
- **Hold: pursue.**
- **Where it was needed.** Frame 01 of the S14 canvas, drawn as `CandidateMatchList`. **Everything it
  shows already exists as records**, so the gap is the search and the judgement rather than the data,
  which puts it in the same cheap-to-build class as readiness gating.
- **To the team.** Worth raising. **Related to M-008**, qualifying a new inquiry into an existing
  lead, which is the same act applied later in time.

**The finding behind it.** Two frames were added to test the first ninety seconds of a call and they
found that **the first thirty seconds are unmodelled**. Beat 1 is three acts, not two: resolve whether
she exists, take down what she said, decide where it goes. Only the middle one is described by either
model.

## A retained reason for a dismissal

- **Purpose.** Why a near-match was judged not to be the same household, kept against the act.
- **Criticality:** Degrading, **rising to blocking the first time a duplicate is found after the fact
  and nobody can tell who dismissed what.**
- **Intent:** Propose.
- **Hold: watch.**
- **Where it was needed.** Frame 01 captures it; frame 03 shows it two minutes later with a time
  against it. Drawn as free text, per memo 7's open question on section A. Whether it needs a reason
  code is unsettled.
- **To the team.** Not yet. **Nothing in either model holds a judgement that something is not a
  relationship**, which is a more general gap than this one instance.

**Cheap, and worth noting why.** It is one field on an act that does not otherwise exist, so the cost
is the act rather than the field.

---

## Two rows folded into the model, 15 September 2026

**Both were blocking and both were answered by the same change**, the Opportunity becoming the durable
demand object. Recorded here rather than deleted, because the register's rule is that nothing is
deleted and because what closed them is worth knowing.

**Lead origin as a first-class attribute.** The row asked for which surface and which party raised a
lead to be recorded, countable and routable, rather than being prose in a sub line. **The opportunity
carries origin as an attribute**, and a trade the customer asked for and a trade the system
recommended are now the same kind of record differing only in that attribute. **That is a stronger
answer than the row asked for**, because it also removes the need for two ways of drawing a trade.

**A queue that surfaces a revive date.** The row asked for somewhere a deferred trade coming back into
season would appear. **The opportunity list under the customer, filtered by revive date, is that
queue.** It needs no new object: a declined trade returns to Open carrying its revive date, so the
queue is a filter over records that already exist.

**Worth noticing that neither was built.** Both were answered by a modelling change made for another
reason, which is an argument for keeping a register of gaps rather than working through it in order.
