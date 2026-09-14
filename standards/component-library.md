# The component library

**Scope:** any component or page template created or adapted for Pros Web, on any surface. Read before
building a screen, not after.

**Surfaces:** all. CD designs components, C and CC consume and describe them.

---

## How hard to hold each rule

| Marker | Meaning |
|---|---|
| **Always** | Breaking it is a defect. If you must break it, say so before you do, not after |
| **Default** | Do this unless you have a reason. Having a reason is fine; not saying it is not |
| **Prefer** | A leaning. Use judgement and move on |

---

## The destination

A component repository built on **atomic design principles**, where every component carries its
**logic** and not only its markup: what it is, which level it sits at, its states, when to use it,
when not to, what it does when the thing it displays is not there, and what variation it can absorb.

The library is the output. Screens are how it gets discovered.

**Why the logic matters more than it looks.** The long-run aim, recorded as global principle G-1, is
that the library plus logic reacting to the entity model and the scenario can compose a scenario's
screens rather than each one being drawn by hand. That is a belief and not a demonstration, and
nothing may be justified by it until a scenario has actually been composed. What it settles now is
only this: **a record is a specification, not a trail**, and it has to be usable by something that was
not in the room.

## The rules

### Always

- **Record a component at the moment you create or adapt it.** Never later. The usage rule and the
  anti-rule only exist while the reasoning is in the room; afterwards they have to be re-derived from
  markup, and the anti-rules are lost entirely because a screen never shows what somebody decided not
  to do.
- **Seven fields, minimum.** Name. Atomic level. States. When to use. When not to use. What it does
  when its subject is absent. **What variation it absorbs**, and what would instead mean a new
  component.
- **Page templates are components too**, at the highest level, and carry the same seven fields.

### Default

- **It has to stretch three product tiers.** Payments only; payments and selling; payments, selling
  and operations. Tier is set per organisation, so no component handles mixed permissions in one
  account. Every component needs a declared position for each tier where its subject may not exist:
  **absent**, **empty and self-advertising**, or **replaced by something else**. Silence is not a
  position.
- **The payments-only tier is a real product and a large part of the customer base, not a stub.** A
  record where the balance is the page is a different design problem, not a subset of the full one.
  A component that assumes the full platform will be invisibly broken there until somebody opens it.
- **It has to cover seventeen scenarios, not one.** A component that fits this scenario and needs a
  near-identical sibling for the next was drawn too specifically. Prefer **one component with declared
  states** over three that look alike. When you feel the pull to fork one, say so rather than forking
  it.
- **The library is repository-resident.** Prose plus markup, readable by anything. **CD is where
  components are designed, not where they are kept**, because colleagues will consume this from CC and
  other tools and most of them will never open CD.

### Prefer

- **Do not stop designing in order to build the library.** Keep working the scenario and leave the
  trail. A library extracted from real screens is worth more than one designed in advance, and the
  record is what makes the extraction possible.

---

## Absence: advertise, or leave out

**This resolves a contradiction.** The density standard says a gap is left out rather than drawn as
unavailable. This standard says declare a position and allows empty and self-advertising. Those
disagreed, and a project's unsold operations half is exactly the cell where they collide.

**The boundary, settled 13 Sep 2026:**

> **A capability that will exist advertises. A gap the model cannot answer is left out.**

| Situation | What it does | Why |
|---|---|---|
| A project has no jobs yet, because nothing has been sold | **Advertises.** A panel naming what arrives at hand-off | Jobs will exist. Saying so tells a person what this page becomes |
| A payments-only contractor has no selling capability | **Advertises.** An empty panel describing what selling would do | This is a product mechanism, not a fallback. It is how somebody finds out the capability exists |
| Per-job margin, which needs a revenue allocation nobody has specified | **Left out entirely.** Not drawn, not labelled unavailable | The model cannot answer it. Naming it on screen invites somebody to fill it badly |
| Communications, which have no entity anywhere | **Left out**, unless the object register says otherwise for a specific mock | Same reason |

The test: **can somebody make this appear by doing something?** If yes, advertise. If it would take a
model decision that has not been made, leave it out.

---

## Flex by lifecycle stage, not only by product tier

**Added 13 Sep 2026.** Tier flex answers what a component does when its subject does not exist for
this organisation. **Stage flex answers what it does when the subject exists but does not matter
yet, or does not matter any more.** They are different and a component needs both.

- A project still being sold has **little or no operations section**. Not absent, because it will
  exist. Not full, because there is nothing in it.
- A job in the install stage needs **almost no selling information**. The contract and the proposal
  are settled history; what matters is the crew, the materials and what is blocking.
- The same card can be prominent at one stage and a single collapsed line at another.

**Default:** a template declares, per stage, which groups are prominent, which are collapsed to a
summary line, and which are absent. **Prefer** collapsing to a line over removing outright, because a
person who wants the contract during install should still be able to reach it.

**This is not settled.** It was ruled on as the direction with more exploration needed, so treat a
stage-flex decision as provisional and say which stage a mock is drawn at.

## What a component absorbs

**Added 14 Sep 2026.** The seventh field. States say what a component handles **now**. This says what
it is built to take **later**, without being redrawn.

> **Absorbs:** a scope row absorbs any number of line items, a change order against it, and a value
> that moves after signature. **A new component instead** if the row has to carry a second party's
> price, because that is a different commercial object rather than a wider version of this one.

**Why it exists.** The library is being built while it is being used, so a component will change under
mocks that already cite it. Without this field nobody can tell whether a change was legitimate
widening or a quiet redefinition, and the difference decides whether the mocks are still valid.

**What it costs, plainly.** Seven required fields rather than six, on every record, including the
fourteen already written. Those fourteen are not wrong, they are incomplete, and the field gets added
when each is next touched rather than in a sweep.

**The collision it resolves.** Building the library while flying needs flexibility, and the Prefer rule
that says do not stop designing in order to build the library was read as being in tension with the
library being the deliverable. It is not. **What makes a component brittle is not the cost of writing
it down, it is a record that presents it as finished.**

## Why the absence rule matters most

Most of the flexibility this needs is not visual. It is about what a component does when its subject
does not exist: no proposal at the payments tier, no jobs before a hand-off, no financing on a cash
deal, no closing balance on a service plan. A component with no declared answer there gets one by
accident, usually an empty card that looks like a bug.

It is also where the upside is. An absent capability rendered as an empty panel that advertises what
it would do is how a payments-only contractor finds out selling exists. That is a product mechanism,
not a fallback.

## Worked example: the Work group on a project

**At step 5**, the project exists and nothing has been sold. The Work group shows a dashed panel
naming what arrives at hand-off: jobs, one per committed scope. It advertises, because jobs will
exist and a person opening a two-day-old project should learn what it becomes.

**At step 8**, two jobs exist. The panel is gone and the group is a list of two rows.

**At a payments-only organisation**, the Work group is absent entirely and so is the Selling group,
because the project itself does not exist at that tier. The component record for the project template
says exactly that, which is how somebody drawing the payments tier knows not to look for it.

**Per-job margin appears at none of these**, at any tier, at any stage. It is not drawn as
unavailable, not greyed, not labelled. It is simply not there, because the model cannot answer it.

## Learned from

- **11 Sep 2026.** Andrew, setting the direction: the eventual output is a component repository on
  atomic design principles with the usage logic described, and it needs enough logic and flexibility
  to serve every scenario and every customer tier from full platform down to payments only.
- **11 Sep 2026.** Same conversation: colleagues will want to use the repository from CC and other
  programs rather than from CD, which is what makes the library repository-resident rather than a set
  of canvas artefacts.
- **13 Sep 2026.** CD hit the contradiction between this standard and the density standard while
  drawing a project with nothing sold, chose a boundary, and flagged it as the one place it went past
  a binding rule. The boundary it proposed is the one adopted above.
- **13 Sep 2026.** Andrew, ruling on the customer record regrouping: a project still in selling might
  have a limited operations section or none at all, and a job in install does not need much selling
  information. That is stage flex, which this standard did not have.
- **14 Sep 2026.** Andrew, on whether the library being the engine contradicts the Prefer rule about
  not stopping to build it: "we are going to be building the plane while flying, some flexibility will
  be needed under this approach", and the hope that CD backed by our logic and content can produce
  components that are more flexible and able to change. Neither rule changed. **What changed is that a
  record now has to say what the component can absorb**, which is what lets it change under a mock
  without anybody having to guess whether the change was legitimate.
