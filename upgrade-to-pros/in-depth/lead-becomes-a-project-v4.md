# Beats: qualification opens the project

> # CONCLUDED 15 September 2026. Read `the-opportunity.md` for the live model.
>
> **This document's question has been answered and overtaken.** It asked what it looks like when
> qualification creates the project, and the answer moved four times in one day. **Its settlements are
> in `DECISIONS.md` and the current account of demand is in `the-opportunity.md` beside this file.**
>
> **What is still live here, and worth reading:**
>
> - **Section 3a**, the reasoning that produced automatic qualification and the join rule.
> - **Section 3b**, on why project merging died and what replaced it.
> - **Section 3c**, on the container's name shrinking. **Still open.**
> - **Section 2**, on validation, which nothing has touched.
>
> **What is history and must not be designed from:**
>
> - **The one-line summary below**, which says both objects live until the close. **The lead closes at
>   the hand-off.**
> - **Section 1**, and **section 3's route table**, both of which predate the retirement of the
>   Interest and say "interests" where they mean opportunities.
> - **Sections 4, 5 and 6**, written when the engagement and the project were the two objects in play.
>   **The Interest no longer exists** and the split they describe is between the opportunity and the
>   project instead.
> - **Anything in here that treats an interest as an object.** It was retired on 15 September.

**Written, not drawn. 14 September 2026. Status: concluded 15 September 2026.**

> **The question:** the project is now created when intent to sell is expressed, at qualification or
> automatically when a proposal is drafted from a qualified lead. **What does that look like, and what
> does the engagement hold that the project does not?**
>
> **The rule this is built on is T-2.** It is stated once, in `TEAM-POSITIONS.md`, and not restated
> here. If T-2 changes, this document is wrong and nothing else needs touching.
>
> **This replaces `lead-becomes-a-project.md`**, which was concluded when the premise moved. Its
> account of validation in beat 2 still stands and is not repeated here. Read it there.

**What is different from the previous document.** That one argued the trigger should be assignment or
a claim. The answer is **qualification**, which is later and better: assignment can happen before
anybody has decided the lead is worth selling, and qualification is an act with a state of its own.
The earlier reasoning was right about when and wrong about what.

---

## The new shape, in one line

**Lead from the first contact that names a trade and a property. Project with it. The lead closes at the
hand-off; the project runs to the money being paid.** Amended twice on 15 September: qualification turned out to be automatic on expressed
intent, so there is no gap between the contact arriving and the lead existing. **The earlier wording
put the engagement before qualification, which is no longer a distinction.**

## The beats

### 1. Arrival

**Corrected 15 September 2026.** This beat described the engagement existing from the first interest,
gathering two more within a day, with siding raised by Sara on a call. **All of that changed when the
demand story was reworked.**

In the worked example an **inquiry** opens on 4 August when Robert raises roofing in the Home App.
**It names a trade and a property, so it qualifies itself**, and the lead and the project exist that
morning with nobody at Northgate present. **Windows and siding are opportunities too**, recommended by
DeDe the same day on the property's build year and on photographs from the heat pump job a year
earlier. Both are marked **worth raising** and both stay **Open** while Priya captures detail against
them on the 5 August intake call. **They go on the lead at Start selling, 10 August.**

**One lead. One opportunity on it from 4 August, three from 10 August.** See T-1. This is the part the team changed
against us, and their reason is job J-11: somebody discussing three trades in one conversation should
not be switching views. **That conversation is now the intake call**, which tests the same thing and
tests it better, because the trades being discussed were not all raised by the customer.

**Amended twice on 15 September**, first when siding became an opportunity and then when qualification
became automatic. The second pass moved the lead's birthday from 10 August to 4 August.

**The opportunity is a new object and it is ours.** See `the-opportunity.md` beside this file.

### 2. Validation

Unchanged, and the previous document covers it properly. Material accrues: notes, transcripts,
documents, investigation. It is a fortnight of accumulation rather than a status change.

**Still the biggest hole in both models.** v4 adds Qualified Lead as the thing validation ends at, per
T-3, but says nothing about what validation consists of.

### 3. Qualification, which creates the lead and the project

**This is the beat that changed twice on 15 September.** The first pass had somebody deciding the
engagement was worth selling to. **The second pass made that the exception**: qualification is
automatic on expressed intent, so in the normal case nobody decides anything.

**Five routes, settled by Andrew on 15 September 2026.** T-2 allows any of them, because it names the
moment and not the mechanism.

| | What happens | What it means for a screen |
|---|---|---|
| **Automatic, on expressed intent** | **The primary route.** A contact names a trade and a property, so intent is expressed and the lead is created. The Home App always satisfies it; a phone call satisfies it when somebody writes both down | **No act and no moment.** The lead exists because somebody got in touch. **This is the case every screen has to be built for** |
| **Booking an appointment** | An advisor's time is committed to this customer. Qualified as a consequence | **No separate act.** A side effect of doing the obviously useful thing |
| **Assigning to sales** | The lead is routed to somebody to sell. Qualified as a consequence | Same shape, and it is the route that existed in an earlier form as assignment or claim |
| **The discrete mark** | Somebody says plainly that this is worth selling to. **Retained on 15 Sep, and demoted the same day** | **The exception path**, for a contact that names neither a trade nor a property and which somebody judges worth selling to anyway |
| **Implicit, from pricing** | A proposal gets drafted and the project is created automatically | **No moment at all.** Carried from the earlier version of this document; still allowed by T-2 |

**Completeness logic is deliberately not on this list.** Andrew raised it as a possibility and it was
ruled out as a trigger the same day. **See the objection below**, which is the reason.

**Why the discrete mark had to come back.** It was going to be renamed to "Next steps", which would
have hidden the most consequential act in the model behind a phrase promising nothing. **With five
routes, "Next steps" is the right label for the menu and the wrong label for the act.** The menu
offers book an appointment, assign to sales, or mark as qualified. That resolves the objection rather
than overriding it.

**The objection to completeness logic, and it is not a small one.** Completeness is about whether we
have enough fields. Qualification is about whether the demand is worth selling to. **Those come apart
in both directions.** A lead can be perfectly complete and commercially worthless: every field filled,
customer wants a two hundred dollar repair the contractor does not do. And a lead can be badly
incomplete and obviously worth pursuing: storm damage, roof off, customer desperate, three fields
filled in.

**So a completeness rule qualifies on data hygiene and calls it commercial judgement.** The three
other routes all involve a person committing something: time, ownership, or a statement. This one
involves nobody. **Recommendation: keep it as a prompt rather than a trigger.** A lead that looks
complete can surface itself as ready to qualify, which is a queue behaviour, without the rule setting
the state.

**The pattern worth naming.** Four of the five routes qualify without anybody pressing a qualifying
control, and the primary route has no human act in it at all. **So the normal case is that nobody
qualifies anything.** That is the fourth time this container's trigger has turned out to be invisible
in practice, and it is the same lesson each time: do not build the experience around the trigger.

**The design has to work when the second path is the common one.** If most contractors never
explicitly qualify, then the project's creation is invisible in practice and every screen has to
tolerate a container that arrived without being asked for. That was true of the old assignment path
too, and it is the same lesson: **do not build the experience around the trigger.**

**Backend only, or in the experience too?** T-2 leaves this open, and it is the sharpest open
question here. A project created in the backend and not surfaced is free: nothing to teach, nothing to
name, no new concept on day one. A project surfaced at qualification has to justify itself immediately.

### 3a. Qualification is automatic on expressed intent. Settled 15 September 2026

**Andrew's ruling:** qualification tests **expressed intent**, so a contact where the customer says
what they want is qualified without anybody marking it. **And a new contact lands on the open lead
for that customer and property rather than creating a new one.**

**The second half is the larger decision** and it is what makes the first half safe. Without it, every
app contact makes a lead and a project, and a returning household accumulates both.

**What the rule makes the lead.** An engagement in the fullest sense, which is what T-1 says it
already is. One customer, one property, one open lead, and every contact joining it. **Contacts
accumulate opportunities on a lead rather than multiplying leads.**

**The mechanism, and this part is C's reading rather than Andrew's ruling, so confirm it.** Intent is
expressed when a contact **names a trade and a property**. Those two fields are what intent consists
of: without a trade there is nothing to sell, and without a property there is nowhere to sell it.

- **The Home App guarantees both by form design**, so every app contact qualifies. That is why it felt
  like the app was special; it is not, its form just cannot produce an unqualified contact.
- **A phone call qualifies when the person taking it writes down those two things.** Same rule, same
  moment, no channel exception.
- **A call that names neither does not qualify.** "Do you service Fresno" is an inquiry that stays an
  inquiry, and this is why an unqualified state still has to exist.

**So it is not completeness logic.** Completeness asks whether the record is full. This asks whether
two specific facts are present, and those two facts are the definition of the thing being qualified
rather than a measure of how well filled in it is. **That distinction is the whole difference** and it
is worth holding, because the two look identical from a distance.

**Where the discrete mark now lives.** It becomes the exception path rather than the main one: a
contact that does not name both, which somebody judges worth selling to anyway. **That is a better
place for it than the primary action on a capture screen**, and it is roughly where booking an
appointment and assigning to sales already sat.

**And the consequence for what gets drawn next.** Opportunities are marked on a **lead**, not on an
inquiry, because the lead exists by the time anybody opens the record. **So the capture screen we were
about to draw is a lead screen for every contact that names a trade and a property**, which is most
of them. An inquiry screen is still needed, for the contact that names neither.

**What it does to the canonical example.**

| | Before 15 Sep | Now |
|---|---|---|
| **The lead is born** | 10 August | **4 August**, the moment Robert submits the Home App form |
| **The project is born** | 10 August | **4 August.** Nobody is present for it |
| **Roofing goes on the lead** | 10 August | **4 August**, with the lead |
| **Siding and windows are captured** | 10 August | **5 August** on the call, and they go on the lead at Start selling on 10 August |
| **10 August becomes** | Qualification | **Start selling, and nothing else** |

**The gain, and it is the one S15 was chosen for.** Start selling and qualification are now three
weeks apart with the lead alive throughout. That is O-15, which S14 could not test because the two
happen two minutes apart there.

**Not a sixth position on the mint point.** T-2 is untouched: creating a lead still creates the
project. What moved is when the lead is created. **The rule held and the date moved**, which is the
first time that has happened in this direction.

### 3b. What the join rule does to merging

**Project merging has stopped being a requirement.** M-007 existed because demand arriving later made
a second project that could not join the first. Under the join rule, later demand joins the open lead,
and one lead has one project, so **there is never a second project to merge.** And M-008, the cheap
alternative, is no longer an alternative: it is the default behaviour of every contact.

**And merging really is gone rather than relocated. Settled by Andrew, 15 September.**

Consider a customer whose roof is sold, contract signed, work under way, who then contacts about a
driveway. The lead is still open, so the driveway joins it as a new opportunity. **Where does it go when
it sells?**

**Into the existing project, as another proposal and another job.** One lead, one project, and the
project holds multiple jobs. **C got this wrong and proposed a second sibling project**, on the
reasoning that a committed project should be closed to new scope. Andrew corrected it: the project is
the container, jobs are what it holds, and nothing about demand arriving late needs an exception.

**So the project grows.** A second proposal, a second contract or an amendment, a further job. **That
is neither a merge nor a change order**: a merge joins two containers and a change order amends an
existing scope. The team already allows a project to hold one proposal or several, so nothing new is
being claimed.

**Two things this exposes, and they are the useful part.**

**One, and it was answered later the same day: the project may never reach a final state.** Its status set ends at Paid, and nothing in it
skips or reopens. A project that gains a driveway job in year three cannot read Complete, and a
project that read Paid in year two cannot go back to In progress. **The set was designed for a
project that ends, and the join rule means the project is closer to the customer's whole relationship
at that address.**

**Two: the answer to both is what closes a lead.** If a lead closes when the work completes and the
money is paid, then a later contact finds no open lead, creates a new one, and gets a new project.
Everything resolves. **So what closes a lead is now doing double duty**: it is the join rule's end
condition and it is the only thing that lets a project ever finish. The only authored value in the
lead's set is Closed, and **nobody has said what sets it.**

**A hole in the lead's derived status, found while working this through, and answered later the same
day by the lead closing at the hand-off. Kept because the reasoning is the useful part.** The lead is Active if
any interest is being pursued or quoted, and Dormant if none are but one is deferred with a revive
date. **Take the roof sold and in delivery, nothing else being sold, nothing deferred.** No interest
is pursued or quoted, none is deferred, and nobody has closed it. **The lead is none of Active,
Dormant or Closed.** That is the same shape as the money-absent hole in the project set, and it is
ours rather than theirs.

### 3c. The naming decision gets a new case: the name shrinks

**Settled 15 September:** there is no naming moment. The container arrives named by its contents and
anybody can rename it in place, wherever it appears. That gives a typed custom name without asking
for one at the moment somebody wants to get on with it.

**But the canonical example now exercises something the naming decision did not anticipate.** The
decision says the name **grows** when a lead gains contents, and that growing is the advertisement.
Under the new dates:

| Date | Contents | Generated name |
|---|---|---|
| 4 August | Roofing | "Roofing, Thompson" |
| 5 August | Roofing, siding, windows | "Roofing, siding and windows, Thompson" |
| 18 August | Siding and windows, roofing deferred | **"Siding and windows, Thompson"** |

**So the name grows and then shrinks**, and a name shrinking reads as something being lost rather than
something being decided. **Nothing in the decision covers it.** Three options, none taken: the name
freezes once a proposal is accepted, the deferred trade stays in the name until it is lost, or the
name is left to shrink and the history carries the explanation.

### 3d. Superseded: does the Home App skip qualification entirely? Ruled above

**Kept because the working-out is what produced the ruling above, and because the cost it names is
real and was accepted rather than avoided.**

**Andrew, 15 Sep:** "We may have to concede that the customer reaching out via the home app
automatically qualifies it as a lead, as the customer has already expressed their interest and to
some extent their intent."

**What it does to the canonical example.**

**Both columns below are history. The right-hand one was adopted.** Section 3a carries the live
account.

| | As written before this ruling | Under auto-qualification, which was taken |
|---|---|---|
| **The lead is born** | 10 August, when Priya qualifies | **4 August**, the moment Robert submits |
| **The project is born** | 10 August, with the lead | **4 August.** Three weeks earlier, and nobody is present for it |
| **Opportunities are marked on** | The inquiry | **The lead.** The capture screen becomes a lead screen |
| **Interests exist from** | 10 August, on conversion | **5 August**, because a lead already exists to convert onto |
| **10 August becomes** | Qualification | **Start selling, and nothing else** |

**The first real gain, and it is a good one.** Start selling is currently the act that moves interests
from new to pursuing, and it has never been cleanly separable from qualification because both landed
on the same day. **Under auto-qualification they are days apart with the lead alive
throughout**, which is exactly what S15 was chosen to test and could not.

**The first real cost, and it is what produced the join rule.** Every app contact auto-qualifies into
a lead, and a lead creates a project. **So a customer who uses the app three times would have three
leads and three projects**, unless something routes the second and third contacts into the lead that
already exists.

**That cost was accepted and paid for in the same ruling.** The join rule in 3a is the payment: a new
contact joins the open lead for that customer and property, so the three-leads outcome cannot occur.
**M-008 stopped being a cheap alternative and became the default behaviour of every contact**, which
is section 3b.

**The second cost: qualification stops being a gate and becomes a reversal.** A worthless app inquiry
becomes a lead and a project immediately, and the only way out is to disqualify or close afterwards.
Their board's edge reads "qualified, not disqualified", which is written as a gate. **A screen for
undoing a qualification is a different screen from one for granting it**, and nobody has drawn either.

**And the tension worth resolving before anything else.** The two answers of 15 September pull in
opposite directions on what qualification is actually testing.

- **If the test is expressed intent**, then a phone call expresses at least as much of it as a form.
  So phone should auto-qualify too, and then **nothing is ever unqualified**, the inquiry never holds a
  state other than Qualified, and the four-value inquiry status set is unused.
- **If the test is that the app collects structured fields** and a phone call does not, then this is
  completeness logic under another name, and the objection to completeness above applies to it
  unchanged.

**Neither is wrong. They are different products**, and the difference shows up as whether an
unqualified lead queue exists at all.

**Resolved by the ruling in 3a.** Intent is the test, and intent is defined as a trade and a property
being named. **That keeps an unqualified state alive** for the contact that names neither, so the
queue exists but is much smaller than it was, and no channel gets its own rule.

**What does not change either way.** The inquiry survives as the record of the contact: the channel,
the customer's own words, the timestamp. It is the event, and the lead is the engagement. Auto
qualification only means the event never sits in an unresolved state.

### 4. History. Both live, which was the real design problem

> **Written before the Interest was retired, and the two objects it compares no longer both exist.**
> The engagement it describes is the lead, and what holds the interests is now the **opportunity**,
> which hangs off the customer rather than inside anything. **The roofing test below still works and
> is still the right test**; only the objects have moved. Read `the-opportunity.md` for the live split.


From qualification to the hand-off, **the lead and the project both exist**. From the hand-off to the
money being paid, only the project does. The
previous two versions of this question each had only one of them alive at a time.

**So the question is what each holds.** A first attempt, and it is a proposal rather than a finding:

| | The engagement | The project |
|---|---|---|
| **Holds** | The interests, all of them, including ones never sold. The validation material. The customer's words. The origin of each interest | What is being sold and then delivered: proposals, contracts, scopes, jobs, money |
| **Survives** | Everything. A deferred interest outlives the project it was never part of | The journey it was created for |
| **Answers** | "Where does this customer stand on each thing they mentioned?" | "What did we sell, and how is it going?" |

**The test.** Roofing in the worked example. It is an interest on the engagement, it was priced as an
option on the proposal, it was declined, and it never becomes a scope or a job. **If the engagement
does not hold its whole story in one piece, the split is wrong.**

### 5. Sold, and the transformation. Still accurate

The contract signs, tender is secured, and the hand-off seeds one job per committed scope component.
The project's subject changes from selling to work.

**This is still principle P-2**, one workspace that transforms. What is new from v4 is that **the
project's state is derived and one-way**, per T-7, and that **jobs run uniform outer states** with
trade-specific steps as sub-states, per T-5. So the project's label is computed from its jobs rather
than set by anybody, and a screen must not offer to change it.

**Checkpoints are per-org policy rather than structure**, per T-6. That matters for a mockup: deposit
paid, financing NTP, approvals and customer sign-off are configuration, so a screen that hard-codes
them is drawing one contractor's setup as though it were the product.

### 6. History. Not sold

> **Written when the project was the only thing that could hold a declined trade.** It now returns to
> being a free-standing **opportunity** with a revive date and a history, so the question below about
> whether an empty lost project is worth keeping is much smaller than it was: nothing of value is
> stored in it.


The proposal is declined and no scope is committed. **The project exists and has nothing in it.**

**This is the case worth drawing and the one nobody has drawn.** Under project-at-won it could not
happen. Under project-at-qualification it happens every time a deal is lost, which is often. The
project is marked lost, and the interests stay on the engagement with their reasons and revive
conditions.

**Open: is an empty lost project worth keeping?** It records that a sale was attempted, which is real
reporting value. It also means a busy contractor accumulates lost projects that hold nothing. Neither
model says.

---

## What this settles, and what it does not

**Settles nothing by itself.** T-2 settles the trigger; this document only works out what follows.

**The three open questions, in the order they matter:**

1. **Is the project surfaced at qualification, or backend only until there is something in it?** The
   escalation argument from the previous document applies here almost unchanged, and this is the one
   worth a mockup first.
2. **What does the engagement hold and what does the project hold**, while both are live? Beat 4 is a
   proposal, not an answer. The roofing case is the test.
3. **Does an empty lost project stay?** Beat 6.

**Carried over and still true.** The container is named by its contents. The word Project need not
appear in the interface. Sales can see unvalidated leads behind a default filter. None of those were
touched by any of the four changes to the trigger.

## Learned from

- **14 Sep 2026.** The trigger for this container held four positions in one day. **Anything built
  against a trigger should be built so the trigger is cheap to move**, which in practice means the
  design should not depend on there being a visible moment. Both surviving paths in beat 3 are
  invisible to the user, which is a hint that this was always the right conclusion.
