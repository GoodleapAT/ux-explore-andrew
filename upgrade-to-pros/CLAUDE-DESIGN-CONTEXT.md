# Pros Web: project context for Claude Design

**Version 3.0 · 14 September 2026 · Andrew Thompson, UX / Product Design**

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
| **Demand** | A Lead, one per trade | **Inquiry or Prospect, then Lead.** A lead is an engagement carrying several **interests**. T-1, T-3 |
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
8. **`components/ITERATION-2.md`** and **`ITERATION-3.md`**. Nineteen records.

**The registers, when you need them:** `OBJECT-REGISTER.md` for things no model has,
`DEVIATIONS.md` for where a mock departs from a scenario, `JOBS-TO-BE-DONE.md` for what people are
trying to accomplish, `DRIFT-CHECK.md` for what somebody else can change under us,
`in-depth/` for questions worked through and concluded.

---

## Where the model stands

**Demand.** A customer contacts the contractor: that is an **Inquiry**. A **Prospect** is an
unverified customer or expression of interest. Either becomes a **Lead** when qualified. A lead
carries several **interests**, one per trade, each with its own origin, detail and status.

**The container.** Creating a lead creates a **Project**. It is the spine, it models one customer
journey, its state is **derived and one-way**, and every record carries a reference back to it.
**The word Project need not appear in the interface**; the container is called by its contents.

**Below the sale.** A **Proposal** holds **Options**. An option is priced by an **Estimate**, which
is a satellite record. A **Contract** pins a proposal version. One committed **Scope component**
becomes one **Job** at the hand-off.

**Money.** Stored where it occurs, derived upward. Costs on the job, revenue at the project, roll-up
at the customer. That is principle P-1 and it explains why per-job margin is unavailable rather than
missing.

**Four status levels now exist** on the demand side: inquiry or prospect, interest, lead, project.
**That is the single biggest risk to any demand screen** and it is why S14 matters: with one interest,
a screen showing four status words would be absurd. If the levels cannot be hidden, the model is
telling us something.

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
| **Project merging**, and whether routing demand avoids needing it | N-004 and M-007 |

---

## What must survive any screen you draw

**From the standards, which are binding.** No reference codes or record identifiers. No explanatory
copy inside a screen; suggestions go in a list underneath. Placeholder what the current question does
not touch, and label it. Cards in pairs under a group heading, two abreast unconditionally. Colour
only where somebody must act, at most one region per screen. Badges only where a state must be seen
before the row is read, three or four a page.

**From the model.** Nothing indents on the customer record. A project may hold several proposals. A
deferred interest stays alive on its lead with a reason and a revive date. Templates flex by product
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
