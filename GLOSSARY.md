# Glossary

**Every controlled vocabulary the working memory runs on, in one place.**

> **Who may write to this file:** any surface that can write. **Add a vocabulary here the moment you
> invent one**, in the same session, not later. A value list that lives only in the file that uses it
> is a value list nobody else can obey.
>
> **This holds the words the registers run on.** The nouns of the business live in each project's own
> vocabulary file, and so do the domain status sets. For Upgrade to Pros that is
> `upgrade-to-pros/VOCABULARY.md`.

## Why this exists

Nineteen separate value lists had grown across the standards, the decision logs and the registers,
each defined in the file that used it. Two of them had already collided, and a third was about to.
A word that means one thing in a decision log and another in a register is worse than an undefined
word, because nobody notices.

**The rule: one word, one meaning, across the whole repository.** If a new vocabulary needs a value
that is already taken, pick a different word. The collisions section at the bottom records the ones
that got through and what was done about them.

---

## Index

| Vocabulary | The field is called | Where it applies | Values |
|---|---|---|---|
| **Rigidity** | (the marker column) | Every standard | Always · Default · Prefer |
| **Standing** | Standing | Both decision logs | Working · Raised · Agreed |
| **Surface** | From | Changelog, decisions, learned-from lines | C · CC · CD |
| **Access** | Access | Both sources registers | Local · Connector · Connector unauthorised · Paste only · Not located |
| **Idea kind** | Kind | Ideas catalogue | Need · Move |
| **Idea status** | Status | Ideas catalogue | Raw · Exploring · Parked · Folded in · Dropped |
| **Appetite** | Appetite | Ideas catalogue | A session · A week · A cycle · Unknown, needs shaping |
| **Support** | Evidence or rationale | Ideas catalogue, jobs to be done | Evidence · Rationale |
| **Criticality** | Criticality | Object register | Blocking · Degrading · Exploratory |
| **Intent** | Intent | Object register | Fill · Probe · Propose |
| **Hold** | Hold | Object register | Loose · Watch · Pursue |
| **Object status** | Status | Object register | Open · Folded into the model · Dropped |
| **Deviation kind** | Kind | Deviations register | Proposal · Simplification |
| **Deviation resolution** | Resolution | Deviations register | Open · Taken to the team · Accepted · Withdrawn · Settled |
| **Comparison classification** | My reading | Model comparison, and its review artefact | Conflict · Undecided · Ours omits · Ours simplifies · Theirs omits · Naming · Agreement · **Adopt theirs** · Confused |
| **Document status** | Status | In-depth documents | Open · Concluded, with a date |
| **Absence position** | (per tier) | Component records | Absent · Empty and self-advertising · Replaced |
| **Stage position** | (per stage) | Page template records | Prominent · Collapsed to a line · Absent |
| **Product tier** | Tier | Everything | Payments only · Payments and selling · Payments, selling and operations |

**Atomic level is required on every component record and has never been enumerated.** That is a gap,
not an omission from this file. Until somebody settles it, say which level you mean in words.

---

## Rigidity

*Owned by `standards/INDEX.md`. On every rule in every standard.*

| Value | Means | If you break it |
|---|---|---|
| **Always** | Breaking it is a defect | Say so **before** you do it, not after |
| **Default** | Do it unless you have a reason | Do the other thing, and say the reason |
| **Prefer** | A leaning | Nothing. Use judgement |

## Standing

*Owned by each decision log. On every dated row.*

| Value | Means | To change it |
|---|---|---|
| **Working** | Andrew's call. The path being designed against | He changes his mind. No ceremony |
| **Raised** | Put to the group, waiting on them | They answer |
| **Agreed** | The group settled it | Takes the group. Do not quietly reverse it |

**A Working decision still binds the design work.** What changes is how hard it is to reverse, not
how much it should be followed. Anything building screens treats Working and Agreed the same.

**The Carried in decisions have no standing**, because they predate the column. Read them as Working
unless a later row says otherwise.

## Surface

*Owned by `START-HERE.md`. Use the short form everywhere.*

| Value | Means |
|---|---|
| **C** | Claude Cowork |
| **CC** | Claude Code |
| **CD** | Claude Design |

Changelog rows before 11 Sep 2026 spell the names out. They stay, because that file is append only.

## Access

*Owned by both sources registers. How reachable a source is, not how good it is.*

| Value | Means |
|---|---|
| **Local** | Present in the enclosing folder. Readable by any surface with file access |
| **Connector** | Reachable through an MCP connector. May need authorising first |
| **Connector unauthorised** | The connector exists but is not connected. Say so rather than working around it |
| **Paste only** | No surface can fetch it. Andrew has to paste the content in |
| **Not located** | Believed to exist, not found yet |

## Idea kind

*Owned by the ideas catalogue. A record is one or the other, never both.*

| Value | Means |
|---|---|
| **Need** | A problem, a customer situation, or a story |
| **Move** | Something we might build or do |

They are separated because a need survives the move that was meant to satisfy it, which is the same
reason a declined trade keeps its lead.

## Idea status

*Owned by the ideas catalogue.*

| Value | Means |
|---|---|
| **Raw** | Captured, not worked |
| **Exploring** | Actively being worked |
| **Parked** | Stopped, **with a revive condition** |
| **Folded in** | It became part of something, which is named |
| **Dropped** | Stopped, with no revive condition |

Parked and dropped both require a reason. The revive condition is the only difference.

## Appetite

*Owned by the ideas catalogue. **Not an estimate.** How much time is worth spending before the idea
has to show something. An idea with no appetite is a note, not a plan.*

A session · A week · A cycle · Unknown, needs shaping

## Support

*Owned by the ideas catalogue and the jobs to be done. **One or the other, labelled, never both.***

| Value | Means |
|---|---|
| **Evidence** | Quotes a person, a scenario beat, or something observed |
| **Rationale** | States the reasoning. Nobody has said they want this |

The label is the whole point. An unlabelled paragraph reads as evidence whether or not it is.

## Criticality

*Owned by the object register. What happens if the object never exists.*

| Value | Means |
|---|---|
| **Blocking** | A scenario cannot be drawn honestly without it |
| **Degrading** | Drawable, but the screen tells a worse or less truthful story |
| **Exploratory** | Drawn to see what it would be like |

**Three named values rather than a one-to-five scale**, because a scale with only its endpoints
defined puts everything on three and stops discriminating.

## Intent

*Owned by the object register. Why it was drawn. **More than one is normal.***

| Value | Means |
|---|---|
| **Fill** | To complete a UX so the rest can be judged |
| **Probe** | To test whether it should exist |
| **Propose** | We think it belongs in the model |

## Hold

*Owned by the object register. How tightly we are holding it. **Loose is the default** until somebody
argues otherwise.*

| Value | Means |
|---|---|
| **Loose** | Drawn once. Do not build on it. **If a later decision contradicts it, the object loses without argument** |
| **Watch** | Keep it in view and revisit when something changes |
| **Pursue** | Actively heading towards it |

**Hold is the field that keeps the register honest.** A possibility nobody is holding loosely quietly
becomes a requirement.

## Object status

*Owned by the object register.*

| Value | Means |
|---|---|
| **Open** | Still a gap |
| **Folded into the model** | A decision gave it a home. Name the decision |
| **Dropped** | It died. Give the reason. **Nothing is deleted** |

## Deviation kind

*Owned by the deviations register, and the distinction that makes the file worth keeping.*

| Value | Means | Does it reach Joel? |
|---|---|---|
| **Proposal** | The mock is right and the scenario should change | **Yes.** These are the valuable ones |
| **Simplification** | The mock departs for its own reasons: fitting a grid, avoiding an undrawn surface, keeping one example consistent | **No**, and it must not quietly become a model claim |

## Deviation resolution

*Owned by the deviations register.*

Open · Taken to the team · Accepted · Withdrawn · Settled

**Settled** appears in the register and was never defined: it means the deviation stopped being one,
usually because the thing it departed from was itself changed.

## Comparison classification

*Owned by the model comparison and its review artefact. The only vocabulary here that Andrew fills in
himself rather than a surface filling in for him.*

| Value | Means |
|---|---|
| **Conflict** | Both models have a position and they disagree. Needs a decision |
| **Undecided** | A genuine open question. Neither has ruled. **About the world** |
| **Ours omits** | Territory our model never covered. Scope, not a position |
| **Ours simplifies** | We have it, coarser. Theirs is more precise |
| **Theirs omits** | The reverse |
| **Naming** | Same thing, different words |
| **Agreement** | No difference, listed because it was thought to be one |
| **Adopt theirs** | **The difference is real and DRAFT v3 wins.** Ours was the thinner model and theirs goes into ours |
| **Confused** | The row is badly written or needs more from me. **About my explanation.** Comes back to me to fix rather than counting as decided |

**Agreement and Adopt theirs are the pair most easily confused, and the consequences differ.** An
Agreement row closes and generates nothing. **An Adopt theirs row puts an entity into our model**, so
it generates work. Added 14 Sep 2026, when three rows had been marked Agreement to mean "no argument
here" while their comments plainly meant "take theirs". Twenty two rows carry it.

**It is not the same as Ours simplifies either.** Ours simplifies describes the difference; Adopt
theirs also disposes of it. A row can be both, and the ruling is the one that says what happens next.

## Document status

*Owned by the in-depth documents.*

**Open**, or **concluded on a date**. A document can conclude in parts: settle five things, log them,
leave four open, keep going.

## Absence position

*Owned by the component records. **Declared per product tier where the component's subject may not
exist. Silence is not a position.***

| Value | Means |
|---|---|
| **Absent** | Not rendered at all |
| **Empty and self-advertising** | Rendered as a panel naming what it would do. **A product mechanism, not a fallback** |
| **Replaced** | Something else stands in its place |

**The boundary with the density rule:** a capability that will exist **advertises**; a gap the model
cannot answer is **left out**. The test is whether somebody could make it appear by doing something.

## Stage position

*Owned by the page template records. Declared per lifecycle stage, alongside the tier positions.*

Prominent · Collapsed to a line · Absent

**Prefer collapsing to a line over removing outright**, because a person who wants the contract
during install should still be able to reach it.

## Product tier

*Set per organisation. No component handles mixed permissions in one account.*

Payments only · Payments and selling · Payments, selling and operations

**Payments only is a real product and a large part of the customer base, not a stub.**

---

## Collisions

**Recorded whether or not they are fixed**, because a collision somebody resolved quietly is a
collision nobody else can learn from.

### Live, and needing a ruling

| The word | First meaning | Second meaning | Proposed fix |
|---|---|---|---|
| **Raised** | A decision standing: put to the group | How a lead arrived: raised by the homeowner in the Home App. Also the verb, to raise a lead | Rename the standing value to **With the group**. It is used on no row yet, so the rename is free |
| **Agreed** / **Agreement** | A decision standing: the group settled it | A comparison classification: the two models do not differ | Rename the classification to **No difference**. Clearer anyway. **Costs an artefact rebuild**, so it waits for Andrew. **Now more urgent, 14 Sep:** Agreement was used on three rows to mean "no argument", which is what Agreed suggests. The confusion this collision predicted has happened |
| **Proposal** | A deviation kind: the mock is right and the scenario should change | An entity in the model | Rename the deviation kind to **Challenge**. The mock challenges the scenario, which is what it does |
| **Open** | A status in the object register, the deviations register and the in-depth documents | Also used loosely of a lead | Leave it. Three registers using Open to mean "not finished" is consistent, and the lead sense is domain |
| **Opportunity** | Retired twice in the domain: the demand object, now Lead, and a per-trade unit of work, now Interest | **Un-retired 15 Sep 2026** for cross-sell demand: a trade we think they might buy that they have not mentioned | **Ruled by Andrew, knowingly.** The word is live with the third meaning only. The decoder in the project vocabulary carries all three and the rule for reading dated material. **The A against B sense is the one that will bite**, because it is adjacent to the live sense without being it |

### Noted, and deliberately left

| The word | Why it is tolerable |
|---|---|
| **Kind** | Three different fields are called Kind: idea, deviation, source. They never appear in the same table, and renaming the field says less than renaming its values |
| **Working** | A decision standing, the working memory, and working a lead. Different parts of speech, and no reader has stumbled |
| **Pursue** and **Pursuing** | A hold value and a project status. Related on purpose: both mean actively heading at something. **A third was proposed on 15 Sep, Should pursue on an opportunity, and was rejected for this reason.** The value is To discuss instead |
| **Presented** | On the proposal lifecycle axis and again on the delivery axis, as Presented in person. The same event recorded on two axes, which is the design rather than an accident |
| **Complete** | A job outer state and a visit state. The same idea at two levels |
| **Surface** and **View** | **Surface** now means the thing being designed, in the UX Kit's own summary, and it already meant an AI surface such as Cowork or Claude Code throughout the protocol. **View** means a derived document, a work order or a materials list read off the itemization, and Andrew has said it would also be acceptable for the thing being designed. **Both collisions are accepted rather than resolved, 21 Sep 2026, on Andrew's ruling**: surface is his word for it knowing it is designer vocabulary, and the two senses never appear in the same sentence |

---

## Learned from

- **14 Sep 2026.** Andrew asked whether an agent had a glossary of the statuses. It did not. Nineteen
  vocabularies had been defined locally in the files that used them, two had already collided, and
  nothing named the collisions. The fix is this file and a rule: **a new vocabulary is added here in
  the session that invents it.**
- **15 Sep 2026.** The count in this file's own opening said eighteen against nineteen index rows, and
  had said it since the file was written. **Corrected to nineteen.** Found by a verification pass.
  Worth knowing that the file recording every controlled vocabulary miscounted its own, which is an
  argument for counting rather than carrying a number forward.
