# The factory

**What stands between the library we have and the one G-1 describes. 15 September 2026. Status:
route agreed in outline, nothing started.**

> **Written from a conversation on 15 September 2026.** The factory is ours, built from the last
> several weeks of exploration. **Joel's implementation is not its starting point and is not
> referenced below as a baseline**, per the decision of 14 September and the sharpening of 15
> September. Where external reading is used it is named as reading.
>
> **Its settlements are in `DECISIONS.md` and its rules belong in `standards/`.** If they disagree
> with this file, they win. **The layer scheme it depends on is in `in-depth/three-layers.md`.**

---

## It already has a definition, and a success test

**G-1, in the root decision log:** an atomic design system, with enough components carrying enough
variants and states, driven by logic that reacts to the entity model and to the scenario's own
detail, can compose a scenario's screens rather than having each one drawn by hand.

That is the factory. The four elements Andrew described, a design system, a component registry with
states and lifecycle behaviour, UX principles with dos and don'ts and copy rules, and parts of the
Product Thinking System, are its parts.

**It also already carries its own success test**, in the revisit condition attached to the 14
September decision: *our own component set reaching the point where a scenario can be composed from
it.* So the question is not what to build. It is what stands between here and that one demonstration.

**And G-1 already says what it does not license.** It is a belief and not a demonstration, and
nothing may be justified on the grounds that the generative end state requires it, until a scenario
has actually been composed. **Everything below is sequenced to respect that**, which is why the
browsable interface comes last rather than first.

---

## What we have

| Element | State | Where |
|---|---|---|
| **Design system** | Nineteen components ported from Merlin as browser-safe source, with known issues and a drift report. 113 tokens extracted, **colour and elevation only** | Claude Design, the Pros Web Design System project |
| **Component library** | Twenty-two components and two page templates, seven fields each, prose only | The repository |
| **Principles** | G-1 on the library, P-1 on where money is stored, P-2 on the project as one workspace that transforms | Both decision logs |
| **Standards** | Eleven files with rigidity markers, one index on a screen, a seven-level authority stack | The repository |
| **Model** | The object model with the Opportunity, a register for what the model lacks, a vocabulary file, one worked example | The repository |
| **Evidence** | Four iteration files. The fourth compared two scenarios and found eleven components carried both unchanged, one died, one failed in the opposite direction to its own prediction | The repository |
| **Mocks** | Four memos and several canvases, hundreds of component instances in situ | The repository and Claude Design |

**Three of the four elements exist.** The gap is the registry, and the valuable half of that is not
the browsable interface.

---

## The five things in the way

### 1. Two layers exist and nothing connects them

Nineteen ported components are **core**. Twenty-two written components are mostly **recipes**. Those
are not the same kind of thing and nothing in either list says which core components a recipe
composes, so **a recipe is prose and nobody can build from it.**

This is the cheapest fix and the highest leverage one, and it is the thing that makes "compose a
scenario" mean something concrete rather than aspirational. The scheme and the first sort are in
`in-depth/three-layers.md`.

### 2. The library is all guidance and no examples, which is the wrong way round

**A mock and an example are different artifacts answering different questions.**

- **A mock** is the component in situ: one instance, one state, surrounded by other components. It
  answers *does this screen work*.
- **An example** is the component alone, rendered in every state its record declares. It answers
  *what does this thing do*.

We have hundreds of the first and none of the second. The strongest evidence on component
documentation, from Nathan Curtis's specification of what a component page contains, is that
**rendered examples are required content and prose design guidance is the expensive, legitimately
skippable part.** Ours is the inverse.

**The consequence is already visible.** `PeerRow`'s record declares default, dimmed and attention,
plus two legal absences, no value and no status. Across four memos, default and dimmed appear
everywhere, attention appears about twice, and the two absences do not appear at all. **The record
asserts more than the evidence shows and nothing distinguishes the tested parts from the claimed
ones.**

The markup already exists. It is in the memo mock kit, copied from memo to memo, which is also why
three CSS rules vanished silently on 15 September. **Extracting it once and citing it from each memo
fixes both problems with one move.**

### 3. The stage axis is unsettled, and it is the logic in G-1

**What was ruled, on 13 September:** a project still in selling might have a limited operations
section or none at all, and a job in the install stage does not need much selling information.

**What the standard says now**, in its own section: tier flex answers what a component does when its
subject does not exist for this organisation. **Stage flex answers what it does when the subject
exists but does not matter yet, or does not matter any more.** A template declares, per stage, which
groups are prominent, which collapse to a summary line, and which are absent, preferring collapse
over removal. It is marked unsettled and any stage decision is provisional.

**Andrew's example, 15 September**, which is the same rule one level down, on a card rather than a
page: a project overview living on the customer page shifts in size, shifts sub-objects in and out,
and shifts the prominence and order of sub-objects across a project's life, from selling to
operations to close-out.

**Why it earns its place rather than being an extra axis to maintain.** G-1 says components *plus
logic reacting to the entity model and the scenario*. **Stage is that logic.** Without it,
composition means a person picks components by eye, which is the thing the factory exists to replace.
With it, composition has a rule: given this object at this stage, here are the groups, their
prominence and their order.

**Two things keep it cheap.** It belongs on **templates and recipes only, never on core**, because a
button has no lifecycle. And **the data already exists**: memo 10 walked one project from sold
through to paid and every screen silently took a position that nobody wrote down.

The iteration two banner already records that none of those fourteen records carry per-stage
behaviour. **The gap is known and dated**, which makes this a completion rather than a new idea.

### 4. The evidence is two scenarios deep, so nothing can be promoted

Iteration four compared one scenario against one other. Its most valuable finding is that
`SubStatusRow` failed in the opposite direction to the one its own record predicted, which is exactly
the kind of finding a second scenario can produce and a first cannot.

**But two cannot promote anything.** The defensible threshold is three independent needs, so the best
iteration four could report was *carried both unchanged*.

**The plan is four: S5, S6, S14 and S15**, and that four is well chosen. They span the two axes the
scenarios actually vary on: **adoption depth and money rail.** S5 and S6 are both wedges, on
different rails, answering different questions. S14 and S15 are both deep, one with money off and one
with money on.

**One caution.** S14 and S15 are not independent observations for the money question, because S14's
controlled twin is S14B. If money behaviour is the thing to settle, that pair is the experiment and
S15 adds multi-trade on top of it.

**And the honest limit.** Four of seventeen proves the library survived four genuinely different
shapes. It does not prove it composes seventeen. It is still much stronger than anything available
today, and it is the first point at which promotion becomes possible at all.

### 5. Nothing can currently answer whether G-1 is true

There is no artifact that would tell us when the belief clause in G-1 can be retired. **The coverage
matrix is that artifact**, and it does not exist.

---

## The route, in order

**One. Name the layers and add the fields.** Layer on all twenty-two, keeping level. A composes field
on every recipe and snowflake. Fix the three the sort exposes: `PeerRow` to core with a name that
stops implying a domain, `MoneyCard` and `OffSystemMoneyCard` merged to one recipe with a state,
`Lineage` and `CallTranscript` labelled snowflake. Add the promotion rule: snowflake to recipe at
two scenarios, recipe to core at three.

**Two. Lift the mock kit out of the memos and make it the library's example set.** Extract once, cite
from each memo rather than copying into each. Render every declared state, so a record's claims and
its evidence can be compared.

**Three. Build the coverage matrix: components by scenarios.** Not pages by scenarios; the unit is
the component. Four columns to start, S5, S6, S14, S15. Every cell reads used, not applicable, or
missing. **This one table is the gap list, the promotion evidence, the near-identical-sibling detector
and the G-1 test, all at once.**

**Four. Settle the stage tables on the two page templates and the recipes that need them.** Per
stage: prominent, collapsed to a line, or absent, plus order. Nothing on core.

**Five. Compose one scenario without drawing it.** The thinnest, S5 or S6, built from the library
alone, no memo first, and log every place the library had to be left. **That is the G-1 demonstration
and the revisit condition on the 14 September decision.**

**What is deliberately last:** the browsable Storybook-like interface. It is the most visible part of
what was described and the least load-bearing. Build it as a render off the library once the library
has examples in it, and not before, or we will be maintaining a second copy of an incomplete thing.

---

## Four things from external reading worth taking, and one worth refusing

**Recorded as reading. None of it binds anything.**

**Refuse: deriving components from objects.** This has a documented decay curve, set out in Sanity's
argument that design-driven content modelling creates technical debt rather than velocity. The rule
that survives is that the domain model is the slow contract, the design system is the fast layer, and
there is a deliberate translation layer between them. **Our recipe layer is that translation layer.**

**Take: the ownership axis alongside the size axis.** Both fields, not one. See
`in-depth/three-layers.md`.

**Take: examples required, design guidance recommended.** Curtis's split, with his density rules: do
and don't pairs, at most two per row, one image per five to ten copy-only guidelines, and **two
sentences maximum per guideline.** Our records are considerably longer than two sentences.

**Take: the object guide and a matrix with our third axis.** From object-oriented UX, two artifacts
are cheap because the model already exists: a glossary-on-steroids per object, and a matrix of
objects against what can be done to them. **Object-oriented UX has no lifecycle axis at all**; it
carries an object axis and a role axis and treats stage as a status attribute with free-text
conditions in cells. **The third axis is ours to invent and no literature will help**, which is worth
knowing before looking for support that is not there. Skip the rest of the method, including the
fifteen steps; its own author recommends skipping most of them.

**One statistic to stay sceptical about.** Seven percent of surveyed design systems are fully
adopted, adoption has been the top reported challenge for five consecutive years, and Gartner has
design systems entering the trough of disillusionment. **Coverage is not what these efforts usually
fail on.** Our constraint is different, because the consumers are one person and several AI surfaces
rather than fifty engineers, so the composability problem is proportionally larger here than the
adoption problem. That is a reason to take the statistic seriously rather than to dismiss it.

---

## Two facts about the model, as at this date

**The board moved to a fourth pass on 15 September and our snapshot does not know.** Three changes:
`Estimate` became `Itemization`, `Payment Schedule` was deleted and decomposed into a milestone plus
a separate timer that marks it due, and **the spine became one record with a type enum** rather than
two records. Our snapshot is of our own third-pass model, read on 13 September. **Recorded as their
position; nothing here adopts it.**

**What matters for the factory is how little of that reaches a screen.** Two renames and a
simplification, and the spine enum is invisible to a person who still sees a project. **The churn
that has been moving the memos is vocabulary and ownership, not screen structure.** The screens have
been considerably more stable than the nouns, and nothing measures that today. The coverage matrix
would, and that is a second reason to build it.

**And the Opportunity is still not on their board**, sitting in a loose exploration that their own
serialization names as the most likely source of the next structural change. On the object we have
spent the most thinking on, we are ahead rather than behind.

---

## Learned from

- **15 Sep 2026.** Andrew asked how to go about building the factory. C found an external folder with
  that name, made it the baseline, and recommended he supply it. **The decision declining that
  framework was already in the log, dated the day before.** Three decision rows and four Always rules
  in the external work standard came out of the correction. **The route above is the answer to the
  question that was actually asked.**
- **15 Sep 2026.** The 14 September decision said what we are not doing and left the positive half
  unstated. **That is the opening the wrong recommendation walked into**, and it is why this file
  exists: a declined framework is not a default to fall back on.
- **15 Sep 2026.** Andrew, on the stage axis: he does not want it if it will not help build the
  factory. **It will, because it is the logic half of G-1 rather than a documentation burden**, and
  narrowing it to templates and recipes is what keeps it affordable.
