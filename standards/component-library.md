# The component library

**Scope:** any component or page template created or adapted for Pros Web, on any surface. Read before
building a screen, not after.

**Surfaces:** all. CD designs components, C and CC consume and describe them.

---

## The destination

A component repository built on **atomic design principles**, where every component carries its
**logic** and not only its markup: what it is, which level it sits at, its states, when to use it,
when not to, and what it does when the thing it displays is not there.

The library is the output. Screens are how it gets discovered.

## The rules

- **Record a component at the moment you create or adapt it.** Never later. The usage rule and the
  anti-rule only exist while the reasoning is in the room; afterwards they have to be re-derived from
  markup, and the anti-rules are lost entirely because a screen never shows what somebody decided not
  to do.
- **Six fields, minimum.** Name. Atomic level. States. When to use. When not to use. What it does when
  its subject is absent.
- **Page templates are components too**, at the highest level, and carry the same six fields.
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
- **Do not stop designing in order to build the library.** Keep working the scenario and leave the
  trail. A library extracted from real screens is worth more than one designed in advance, and the
  record is what makes the extraction possible.

## Why the absence rule matters most

Most of the flexibility this needs is not visual. It is about what a component does when its subject
does not exist: no proposal at the payments tier, no jobs before a hand-off, no financing on a cash
deal, no closing balance on a service plan. A component with no declared answer there gets one by
accident, usually an empty card that looks like a bug.

It is also where the upside is. An absent capability rendered as an empty panel that advertises what
it would do is how a payments-only contractor finds out selling exists. That is a product mechanism,
not a fallback.

## Learned from

- **11 Sep 2026.** Andrew, setting the direction: the eventual output is a component repository on
  atomic design principles with the usage logic described, and it needs enough logic and flexibility
  to serve every scenario and every customer tier from full platform down to payments only.
- **11 Sep 2026.** Same conversation: colleagues will want to use the repository from CC and other
  programs rather than from CD, which is what makes the library repository-resident rather than a set
  of canvas artefacts.
