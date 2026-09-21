# Core, recipes and snowflakes

**The ownership axis the component library did not have. 15 September 2026. Status: adopted in
principle, not yet applied to the records.**

> **Written from a conversation on 15 September 2026**, after Andrew asked whether recipes are
> compatible with atomic design nomenclature and with objects. The answer to both is yes, and the
> reason why is the whole content of this file.
>
> **Its settlements belong in `DECISIONS.md` and the rules belong in
> `standards/component-library.md`.** If they disagree with this file, they win. **This file is the
> reasoning, not the rule.**
>
> **Where it came from:** Brad Frost's own later revision of atomic design, in *Design system
> components, recipes, and snowflakes* and *The art of design system recipes*, with the pace-layer
> framing from Josh Clark. Recorded as external reading, not as a position anybody here has signed
> off. **Nothing in it crosses over until Andrew says so**, and this file exists because he said so.

---

## The problem it solves

A component library with one layer has two failure modes and no third option.

**Either the core fills up with product-specific components** until nobody can use it, because
`ProposalCard`, `JobCard`, `CustomerCard` and `InvoiceCard` are all the same card assembled
differently and now there are four of them. **Or the person who owns the library becomes a full-time
naysayer**, refusing every request for something the core should not hold, with nowhere to send it.

That is the pressure our own library is already under. The standard forbids near-identical siblings
and prefers one component with declared states. **It does not say where a genuinely
scenario-specific composition is allowed to live**, so the only available answers are "in the core"
or "nowhere".

The third option is a middle layer whose whole purpose is to hold those compositions.

---

## The three layers

**Core components are content-agnostic and context-agnostic.** They know nothing about the business.
Card, Button, Badge, Table, Field, Sheet. They are built for maximum reuse and they are the slow,
stable layer. **An object name may never appear in a core component**, and a core component may
never make an assumption about where on a journey it sits.

**Recipes are named compositions of core components that deliberately do not live in the core.**
A recipe is Card plus a heading plus a badge plus a button, assembled one way for a proposal and
another way for a job. **Object names are legitimate here and this is the only place they are.**
Recipes are the fast-moving layer and they are expected to be rewritten.

**Snowflakes are one-offs, and they are allowed, as long as they are labelled.** Something built for
one situation that nothing else needs. A snowflake is not a failure; an unlabelled snowflake sitting
in the library pretending to be reusable is.

The promotion path runs one way and has a threshold: **a snowflake becomes a recipe when a second
scenario needs it, and a recipe becomes core when three do.** Three independent needs is the
empirically defensible line and it is deliberately not a judgement call.

---

## Why it does not collide with the atomic ladder

**Because they measure different things.** This is the part worth holding on to.

| Axis | What it answers | Values |
|---|---|---|
| **Level**, the atomic ladder | How many pieces is this | atom, molecule, organism, template |
| **Layer**, ownership | Who maintains it, and may a product change it | core, recipe, snowflake |

A recipe is usually organism-sized, because complexity is what limits portability, so the two axes
correlate. **They are not the same axis.** A large thing can be core, a small thing can be a
snowflake, and the defining property of a recipe is not its size but that it is product-specific and
therefore not portable.

**Both fields stay.** An earlier version of this conversation said "three tiers, not five", which read
as replacing the ladder and was wrong. What has actually been abandoned in practice is **the strict
five-rung ladder as the organising structure of a library**; most teams collapse to three or four size
bands. Our records already use four, atom through template, which is the right number and does not
need changing.

---

## Why it is the right home for objects

This is the sharper question and it has a definite answer.

**The recipe layer is the translation layer between the entity model and the design system.** The
entity model is the slow, stable contract. The core library is the fast layer that has to be free to
change for visual reasons. Recipes sit in the seam and absorb the churn from both sides.

The failure this prevents is documented and has a decay curve. When UI structure and domain structure
are coupled directly, a library ends up with dozens of types, several of which represent the same
concept, and any visual change becomes a data migration. The prescription is **design-informed, not
design-driven**: a deliberate translation layer rather than a direct mapping.

So the rule is short:

- **Core: no object names, ever.** A Card must not know what a Proposal is.
- **Recipe: object names are the point.** A proposal card is a recipe and should say so.
- **The object model tells you what to call things and where consistency is owed. It does not tell
  you what to build.**

That last clause is the one to remember. The consistency argument is the real gift the object model
gives a design system: two things that represent the same object **should** match, and that is a
reason a rule is not arbitrary. What the object model must not do is organise the component
inventory, because one component per object per state is combinatorially the same failure as
`HeroWithTwoButtonsLeft` with different nouns.

---

## Our twenty-two, sorted

**A first pass, offered to be argued with rather than adopted.** The names are ours; the sort is a
reading of the records, not a ruling.

**Core, or nearly.** `Field`, `CollapsibleSection`, `SheetShell`, `DialogShell`, `SelectionBar`,
`CaptureFieldSet`, `TaskRow`. Several of these probably duplicate something already ported from
Merlin and the duplication should be checked before anything is written.

**Recipes.** `MoneyCard`, `ReadinessCard`, `TriageCard`, `DerivationReceipt`, `StageRail`,
`SubStatusRow`, `RoutingQuestion`, `CandidateMatchList`, `MatchDismissalRow`, `SelectableLeadRow`,
`SubordinateList`, `AbsentCapabilityPanel`.

**Snowflakes, by their own records.** `Lineage`, because it will not render below two leads and the
scenario that needed it has one. `CallTranscript`, because the capability does not exist.

### Three things the sort exposes

**`PeerRow` is core wearing a recipe's name.** Its own record says: "Use it for any list of
associated peers: leads, projects, jobs, service plans, invoices, payment parts, material orders. It
is the workhorse of every card in this grid." Iteration four then found it carried six kinds of
object unchanged. **Object-agnosticism is the definition of a core component.** It belongs in core
and its name should stop implying a domain.

**`MoneyCard` and `OffSystemMoneyCard` are one recipe written as two.** Iteration four already
recommended merging them. The layer split explains why the recommendation is right rather than
merely tidy: they are the same composition with a different state, and the standard already forbids
near-identical siblings.

**`AbsentCapabilityPanel` is the most interesting case and the sort does not settle it.** It exists
because two binding standards disagreed, and its subject is absence itself. It behaves like core, in
that it makes no claim about which object is missing, but it exists for a product mechanism that is
specific to our tier model. **Left as a recipe pending an argument.**

---

## What it costs, plainly

One field split into two on twenty-two records, plus one new field on recipes and snowflakes naming
the core components they compose. The existing seven fields are unchanged.

**The gain is that "compose a scenario" becomes checkable.** Today a recipe is prose, so nobody can
build from it, including its author three weeks later. A recipe that names what it composes is a
specification. That is the same argument the seventh field rests on, applied one level up.

---

## Learned from

- **15 Sep 2026.** Andrew, on being shown the three layers: he wants to lean into them while creating
  the factory, and he asked whether they are compatible with atomic nomenclature and with objects.
  **Both fields stay**, and the correction to "three tiers, not five" is recorded above because the
  earlier phrasing implied a replacement.
- **15 Sep 2026.** The sort above was only possible because every record carries its own usage rule
  and anti-rule. **`PeerRow` was identified as core from the sentence its author wrote when creating
  it**, which is the clearest return the record-at-creation rule has produced so far.
