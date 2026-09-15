# Pros Web: project context for Claude Design

**Version 3.1 · 15 September 2026 · Andrew Thompson, UX / Product Design**

> ## Amended 15 September 2026
>
> **Version 3.0 is wrong about demand.** A new object exists, **the Opportunity**, and the canonical
> S15 story changed with it. The what-changed table and the demand paragraphs below carry the
> amendment. **Everything else in version 3.0 stands.**
>
> **If you are holding a stored copy dated 14 September, it does not know the opportunity exists.**

> ## Read this before starting
>
> **This is context, not a build brief.** Read what is listed below, tell me what you have understood
> and where you disagree, and wait to be told what to design.
>
> **This replaces version 2.0 of 11 September**, which was wrong in three places by the end of the
> same week: it described Andrew's model as a rival to the team's, it said a lead was one per trade,
> and it stated when a project is created. All three have changed. **If you have a stored copy of
> version 2.0, discard it.**
>
> **The single most important rule in this document:** the team's positions live in **one file** and
> are **cited, never restated**. That file is `TEAM-POSITIONS.md`. When you need to know what the
> team holds, read a row and cite it as T-1, T-2 and so on. **Do not paraphrase a row into a memo**,
> because a paraphrase is a copy and copies go stale. This rule exists because the team changed when
> a project is created **five times in one day** and each change cost a rewrite of seven documents.

---

## What changed since you were last briefed

Read this section even if you read nothing else.

| | Then, 11 Sep | Now |
|---|---|---|
| **Our model** | A rival model with five differences from the team's | **Not a rival model.** The comparison was ruled: 22 of 37 rows adopt the team's version wherever ours was coarser. One deferred disagreement remains |
| **Demand** | A Lead, one per trade | **Opportunity, then Inquiry or Prospect, then Lead, then Project.** Four grains, each a different job rather than a different grading |
| **The Opportunity**, new 15 Sep | Nothing like it | **Ours, not the team's. The durable demand object.** One record per customer, per property, per trade. **Where the demand came from is an attribute**, so a trade the customer asked for and a trade the system recommended are the same record. **It outlives every lead and every project.** Statuses: Open, On a lead, Won *(terminal)*, Dismissed. **A declined trade returns to Open** with a revive date and a history |
| **The Interest**, retired 15 Sep | One trade inside a lead, with its own six-value status set | **Gone.** An opportunity is on a lead or it is not, and a proposal option prices the opportunity directly. **The behaviour T-1 describes is untouched**: a lead still carries several trades. Only the object is gone |
| **The S15 story**, changed 15 Sep | Two inquiries, roofing and siding, resolving into one lead | **One inquiry and three opportunities.** Roofing from the customer, windows and siding recommended by DeDe on evidence. **Every figure, date and outcome is unchanged** |
| **Demand status levels** | Four | **Four, having been five in between.** Opportunity, inquiry or prospect, lead, project. **First time this count has gone down** |
| **Qualification**, settled 15 Sep | One deliberate act | **Automatic on expressed intent**, meaning a contact that names a trade and a property. **The Home App always qualifies**, because its form cannot produce a contact without both. A phone call qualifies when somebody writes both down. **So the normal case is that nobody qualifies anything**, and the discrete mark is the exception path for a contact naming neither. Booking an appointment and assigning to sales also qualify. **Completeness logic prompts but does not qualify** |
| **One lead per customer and property**, settled 15 Sep | Implicitly one lead per contact | **A new contact joins the open lead** rather than creating a second one. **Contacts accumulate opportunities on a lead instead of multiplying leads**, which is what makes automatic qualification safe. **One lead still has one project**, and later demand that sells lands in that project as another proposal and another job. **Project merging is therefore dead**, because there is never a second project |
| **The S15 dates**, changed 15 Sep | Lead and project born 10 August | **Born 4 August**, when the app contact qualified itself. **10 August is Start selling and creates nothing.** The lead and the project are alive for twenty two days before anything is pursued, which is the state no mock has drawn |
| **The project** | Minted on pursuit | **Created when the lead is created.** T-2. Do not take the trigger from anywhere but that row |
| **Estimate, Scope Component, Job Financials, Commission** | Entities | **Satellite records**: data hanging off a step, never a step itself. T-4 |
| **Job lifecycle** | Ours | **Uniform outer states**, with trade-specific steps as sub-states inside in-progress. T-5 |
| **Checkpoints** | Not stated | **Per-org policy, not structure.** A screen that hard-codes deposit-paid or financing-NTP is drawing one contractor's configuration as the product. T-6 |
| **Badges** | Banned outright | **Limited use**, with a test. The ban was an overreach and it cost two real signals. See the density standard |
| **Component records** | Six fields | **Seven.** The new one is what variation the component absorbs, and what would mean a new component instead |
| **Worked example** | One, the Thompsons | **Two.** Thompsons for S15, Brenners for S14 |

---

## What to read, and in what order

1. **`TEAM-POSITIONS.md`.** Eleven rows. The only statement of what the team holds.
2. **`OVERVIEW.md`.** State of play. Its later sections are marked as history; believe the markers.
3. **`DECISIONS.md`**, beside it. Two principles at the top, then dated rows with a **Standing**
   column, then two sections recording the 14 September resets and what survived them. **A Working
   decision binds your work exactly as an Agreed one does**; the difference is only how hard it is to
   reverse.
4. **`VOCABULARY.md`.** The nouns and the status sets. **The status sets are a working set and
   nothing ratifies them**, so say so when you use one.
5. **`../standards/INDEX.md`.** Every rule on one screen with a rigidity marker. Then
   `mockup-density.md` and `ui-composition.md` in full before you draw anything.
6. **`WORKED-EXAMPLE.md`** for S15, **`WORKED-EXAMPLE-S14.md`** for S14. Use the data, invent nothing.
7. **`memo-7-s14-end-to-end.html`** if you are working on S14. Fourteen sections, ten drawn.
8. **`components/ITERATION-2.md`** and **`ITERATION-3.md`**. **Twenty three records**, fourteen and
   nine. Corrected 15 Sep; this line said nineteen.
9. **`CD-REVIEW-02-routing.md`**, if you are acting on review comments. **Where the twenty four
   comments of 15 September go**, sorted into structural, visual and unactionable. **Read the routing
   before the two verbatim files beside it**, because one comment is overtaken by a model change and
   must not be acted on as written.

**The registers, when you need them:** `OBJECT-REGISTER.md` for things no model has,
`DEVIATIONS.md` for where a mock departs from a scenario, `JOBS-TO-BE-DONE.md` for what people are
trying to accomplish, `DRIFT-CHECK.md` for what somebody else can change under us,
`in-depth/` for questions worked through and concluded.

---

## Where the model stands

**Demand starts with the Opportunity.** Added 15 September and **ours rather than the team's**. One
record per customer, per property, per trade: a thing this household might buy at this address. **It
hangs off the customer and the property**, so a customer with no live demand still carries
opportunities, and they belong on the customer record.

**Where the demand came from is an attribute of it.** A trade the customer asked for through the app
and a trade the system recommended are the same kind of record with different origins. **That is the
part to hold onto**, because it means the screen does not need two ways of showing a trade.

**It outlives everything.** A trade that is offered and declined goes **back to Open** with a revive
date and its history intact, so roofing appears under the customer, free-standing, and opening it
shows the customer raised it in July, it went on a sale, it was priced, and they declined for the
season. **Nothing else in either model can answer "what has happened with the roof" in one place.**

**Then a customer contacts the contractor: that is an Inquiry.** A **Prospect** is an unverified
customer or expression of interest. **Either qualifies automatically where intent is expressed**,
meaning a trade and a property are named, and qualification creates a **Lead**.

**A lead is one selling episode.** One open lead per customer and property, which every new contact
joins. It carries the opportunities being sold and **it closes when everything on it is resolved**,
which is the hand-off. A customer has many leads over time, one at a time per property.

**The Interest is retired.** An opportunity is on a lead or it is not. The reasoning for all of this
is in `in-depth/the-opportunity.md`, which is worth reading once because it was written three times
in one day and the route explains the shape.

**The container.** Creating a lead creates a **Project**. It is the spine, it models one customer
journey, its state is **derived and one-way**, and every record carries a reference back to it.
**The word Project need not appear in the interface**; the container is called by its contents.

**Below the sale.** A **Proposal** holds **Options**. An option is priced by an **Estimate**, which
is a satellite record. A **Contract** pins a proposal version. One committed **Scope component**
becomes one **Job** at the hand-off.

**Money.** Stored where it occurs, derived upward. Costs on the job, revenue at the project, roll-up
at the customer. That is principle P-1 and it explains why per-job margin is unavailable rather than
missing.

**Four status levels exist** on the demand side: **opportunity**, inquiry or prospect, lead, project.
**It went four, five, four in one day**, and the retirement of the interest is what brought it back
down. **This has been the single biggest risk to any demand screen all week and it is the first time
it has moved in the right direction.**

**The mitigation is now structural rather than a caveat.** The four are genuinely different jobs: an
opportunity is a trade that might sell, an inquiry is one contact, a lead is one selling episode, a
project is the delivery container. **A screen showing several of them is showing different things, not
the same thing at different grains**, which is what made five uncomfortable.

---

## What is open, and where to look

| Open | Where |
|---|---|
| **Whether the project is visible at all** while it holds nothing | Memo 7's to-decide card. The live question |
| **Whether Inquiry and Prospect are one object**, since one is an event and one is a party | Note against T-3 |
| **What a site assessment is**: object, type, or experience | `in-depth/site-assessment.md` |
| **Customer role against a property**: owner, occupier, something else | Object register, blocking |
| **Where a service agreement sits.** The one live disagreement | T-9 |
| **The project status set has no money-absent path** | `VOCABULARY.md`, and it is our defect |
| **Project merging.** **Closed 15 Sep: not needed.** Later demand joins the open lead, and a contact after one closes starts a fresh lead and project | M-007, dropped |

---

## What must survive any screen you draw

**From the standards, which are binding.** No reference codes or record identifiers. No explanatory
copy inside a screen; suggestions go in a list underneath. Placeholder what the current question does
not touch, and label it. Cards in pairs under a group heading, two abreast unconditionally. Colour
only where somebody must act, at most one region per screen. Badges only where a state must be seen
before the row is read, three or four a page.

**From the model.** Nothing indents on the customer record. A project may hold several proposals. A
declined trade returns to being an open opportunity with a reason and a revive date. Templates flex by product
tier **and** by lifecycle stage. Every component declares what it does when its subject is absent.

**Three product tiers**, set per organisation: payments only; payments and selling; payments, selling
and operations. **Payments only is a real product and a large part of the customer base, not a stub.**

**And one distinction S14 introduced:** an organisation that has a capability and does not use it is
not the same as one that never had it. Brightline runs its money through QuickBooks by choice.

---

## The component library

**It is repository-resident. You design components; you do not keep them.** Colleagues will consume
the library from Claude Code and other tools and most will never open Claude Design.

**Record a component the moment you create or adapt it**, never later, with seven fields: name,
atomic level, states, when to use, when not to, what it does when its subject is absent, and **what
variation it absorbs**.

**The seventh field is new and it is the important one.** The library is being built while it is being
used, so a component will change under mocks that already cite it. Without a declared absorption
nobody can tell whether a change was legitimate widening or a quiet redefinition.

**Atomic level is required and has never been enumerated.** Say which level you mean in words.

**The long-run aim**, recorded as global principle G-1: a library complete enough that logic reacting
to the entity model and the scenario can compose a scenario's screens rather than each being drawn by
hand. **It is a belief, not a demonstration.** Nothing may be justified on the grounds that it
requires this until a scenario has actually been composed from the library.

---

## Somebody else's UX effort

There is a parallel effort by Joel, a **UX factory** that generates a walkthrough from a scenario
script. **It is not Andrew's effort and none of it is binding.**

**Andrew's position, settled 14 September:** the framework is not adopted, because it would likely be
too constraining and would likely carry logic incompatible with ours. **Individual elements may be
adopted or translated**, and the idea itself is now our own ambition, which is what G-1 records.

**Wanted, route undecided:** a shared entity map lit per beat, a verbatim scenario pane, and per view
a statement of why this screen, its gaps and its upsell opportunities. Four of those five turn out to
be things this system already holds, rendered per view.

**There is also a nav contract on the team's board**, four lenses over one spine, including a claim
that Project is not a nav item. **Recorded so the position is known, not so it is followed.** Nothing
in it has been adopted.

---

## Design system

**Use `../reference/merlin-sol-tokens.css` rather than inventing a palette.**

**Two warnings.** That file is the **Merlin mirror**: 113 semantic tokens only, with **no radius,
spacing or font scales**. It is incomplete rather than wrong, and it wants re-extracting from Sol
before the next round of mockups. And **badge variant colours are not in it**, because the design
system bundle ships them minified, so the values in memo 7 are inferred from the accent families.

**The Sol green fails contrast as small text**, so a success state cannot be coloured compliantly.
Reach for the fallback ladder in the density standard instead: status word, weight, leading glyph,
position, badge, colour. Do not invent a seventh device.

---

## Because you cannot write to this repository

**End every session with a write-back block**, which Andrew carries to a surface that can write. A
block names:

- the file
- the section or table
- the exact text to add or replace
- whether it is an append, an edit, or a new row

**Make it paste-able as one message.** Do not summarise what should change; write what should be
written. **Include a changelog row every time**, because that file is the only thing that tells the
other surfaces anything moved.

**Two things always go in it.** What we learned about the problem, and what we learned about how to
work on it. The second is the one that gets skipped, and skipping it is why the same correction gets
made three times.

**And say the date of the newest changelog entry at the start of every session.** That one sentence
is how Andrew finds out you are working from a stale copy.

---

## How to start

Read `TEAM-POSITIONS.md`, then `OVERVIEW.md`, then the standards index. Say the date of the newest
changelog entry. Then tell Andrew what you have understood and **where you disagree**, and wait.

**If something you need is missing from the model, do not invent it and do not refuse.** Say what the
screen needs, name it as a gap, and it goes in the object register with a criticality, an intent and
a hold. That register is how a screen gets drawn honestly without the model quietly growing an entity
nobody agreed to.
