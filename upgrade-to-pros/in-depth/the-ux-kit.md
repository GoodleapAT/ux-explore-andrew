# The UX Kit

**What stands between the library we have and the one G-1 describes, and who builds it. Rewritten
21 September 2026. Status: route agreed, step one half done, nothing else started.**

> **Renamed 21 September 2026, at Andrew's instruction, and the name is provisional.** This was
> called the factory. Three reasons it is not any more. **The name collided with Joel's UX factory**,
> which is a real artefact in the team repository and is also five invokable skills in any Claude
> Code session opened in the enclosing folder, so two things in one folder answered to one word.
> **Factory promises volume**, which G-1's own belief clause explicitly refuses until one scenario
> has been composed. And **factory recruits badly**: to a designer on another team it means their
> judgement is being replaced, which is the wrong first thing to say to somebody you are asking to
> own a domain's recipes.
>
> **Joel keeps the word. It is his, and his skills are not to be invoked**, per Andrew's standing
> instruction of 21 September and the rules in `standards/external-work.md`.
>
> **The Kit is ours, built from our own exploration.** Joel's implementation is not its starting
> point and is not a baseline anywhere below, per the decision of 14 September and its sharpening on
> 15 September. Where external reading is used it is named as reading.
>
> **This file replaces the version of 15 September.** What carried over unchanged: the definition,
> the success test, the belief clause, the five obstacles, and the take-and-refuse list from external
> reading. What is new: the name, a corrected status, who contributes what, the language workstream,
> the exercises, the Sol backlog mechanism, and a changed order.
>
> **Its settlements are in `DECISIONS.md` and its rules belong in `standards/`.** If they disagree
> with this file, they win. **The layer scheme it depends on is in `in-depth/three-layers.md`.**

---

## In one page

**Written 21 September 2026 to be handed to somebody who has not seen any of this.** It is a
restatement, so it is a copy: **if it disagrees with the sections below, they win**, and a change to
the route is a change to this section in the same sitting.

The UX Kit is a component library plus the rules for putting it together, so that the screens for a
scenario can be composed from known parts instead of each one being drawn by hand. The parts are the
Sol design system. The rules are what turns a pile of components into something a person on another
team can build with.

**It is grounded in atomic design, on two axes rather than one.**

**Size**, which is atomic design as normally understood: atoms, then molecules, then organisms, then
templates and pages. Every component record names its level.

**Ownership**, which is the axis atomic design on its own does not give you, from Brad Frost's own
later revision of it. **Core** components are content-agnostic and know nothing about the business,
contributed to by designers and engineers as a group. **Recipes** are named compositions where object
names are allowed, and this is where a domain team owns its domain. **Snowflakes** are labelled
one-offs. A snowflake becomes a recipe when a second scenario needs it, and a recipe becomes core
when three do. The evidence decides, not a person.

Both axes are recorded, because how big a thing is and who owns it are different questions. **A
molecule can be a recipe, and an organism can be core.**

**Five steps, in order:**

1. **Connect the two axes.** Record what each recipe is built from. This also produces the list of
   what Sol is missing, ordered by how much is blocked on each piece.
2. **Build the example set.** Every component rendered in every state it claims, so claims and
   evidence can be compared.
3. **Build the coverage matrix.** Components against scenarios. This is the gap list, the promotion
   evidence and the progress measure in one table.
4. **Settle the stage rules.** What a page shows during selling as against during install.
5. **Compose one scenario without drawing it.** That is the test of whether any of this works.

**A browsable component site comes last, on purpose.** It is the most visible part and the least load
bearing.

**One caveat worth saying out loud: the words are not settled.** The nouns in this work are
provisional until they have been tested with contractors, and that research runs alongside the five
steps.

---

## It already has a definition, and a success test

**G-1, in the root decision log:** an atomic design system, with enough components carrying enough
variants and states, driven by logic that reacts to the entity model and to the scenario's own
detail, can compose a scenario's screens rather than having each one drawn by hand.

That is the Kit. The four elements Andrew described, a design system, a component registry with
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
| **Design system** | Nineteen components ported from Merlin as browser-safe source, with known issues and a drift report. 113 tokens extracted, **colour and elevation only**, because Merlin's compiled output carries no geometry layer deliberately. **The ported set stops at molecule** | Claude Design, the Pros Web Design System project |
| **Component library** | Twenty-two components and page templates, seven fields each, prose only. **Four records carry the ownership axis; everything written before 16 September carries neither layer nor composes** | The repository |
| **Principles** | G-1 on the library, P-1 on where money is stored, P-2 on the project as one workspace that transforms | Both decision logs |
| **Standards** | Twelve files with rigidity markers, one index on a screen, a seven-level authority stack | The repository |
| **Model** | The object model with the Opportunity, a register for what the model lacks, a vocabulary file, one worked example. **The nouns in it are provisional**, see the language section below | The repository |
| **Evidence** | Five iteration files, numbered 2 to 6. The fourth compared two scenarios and found eleven components carried both unchanged, one died, one failed in the opposite direction to its own prediction | The repository |
| **Mocks** | Eight memos, numbered 7 to 14, and several canvases, hundreds of component instances in situ | The repository and Claude Design |

**Three of the four elements exist.** The gap is the registry, and the valuable half of that is not
the browsable interface.

**The status line on the old version of this file said nothing started, and that was wrong by the
time it was written.** Iterations 5 and 6 record layer and composes on four components. The
twenty-two written before them record neither. **A library in two formats is worse than a library in
either**, and that is now the first thing in the way rather than a completion.

---

## The five things in the way

### 1. Two layers exist and nothing connects them, and the fix is half applied

Nineteen ported components are **core**. Twenty-two written components are mostly **recipes**. Those
are not the same kind of thing and, for eighteen of them, nothing says which core components a recipe
composes, so **a recipe is prose and nobody can build from it.**

This is the cheapest fix and the highest leverage one, and it is the thing that makes "compose a
scenario" mean something concrete rather than aspirational. The scheme and the first sort are in
`in-depth/three-layers.md`.

**What was found on 21 September and changes what this step is for.** The library's records run
molecule, organism and template. **No record has ever been written at atom level**, which is already
logged as an open item, and **the Sol ports stop at molecule.** So our organisms and templates are
composed from a core that has no organisms in it, and the composes field on most recipes currently
has nothing above molecule level to point at. That is not a reason to skip the field. **It is the
reason to fill it**, because every name with nothing behind it is a Sol gap with a cause attached.
See the Sol section below.

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

**And it becomes load bearing the moment more than one person contributes.** With many hands the
thing that drifts is states, and a rendered state is the only cheap way to notice that somebody on
another team has just built a near duplicate of something that already exists.

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
composition means a person picks components by eye, which is the thing the Kit exists to replace.
With it, composition has a rule: given this object at this stage, here are the groups, their
prominence and their order.

**Two things keep it cheap.** It belongs on **templates and recipes only, never on core**, because a
button has no lifecycle. And **the data already exists**: memo 10 walked one project from sold
through to paid and every screen silently took a position that nobody wrote down.

**It also moves up the order once other teams are involved**, and that is new on 21 September. On our
own it is a completion. With five domains contributing it is the only thing stopping each of them
inventing its own answer to what a project overview looks like during selling as against during
install, and those answers will not reconcile afterwards.

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

## Who contributes what

**New on 21 September, and the three layers already are an ownership model, so they are used as one
rather than a second structure being invented next to them.**

| Layer | Who | What a contribution is |
|---|---|---|
| **Core, and Sol** | **Designers and engineers, as a group.** Not an owner with helpers | A component with its states, carrying no object name and no assumption about where on a journey it sits |
| **Recipes** | **A domain's designer and PM**, one domain at a time. **This is where a team's ownership of its domain actually lives** | A named composition, object names allowed, expected to be rewritten |
| **Snowflakes** | Anybody exploring. No review, no ceremony | A labelled one-off. Unlabelled is the only failure |

**Core has no single owner, and that is deliberate.** Andrew's correction, 21 September: there will
not be one designer and one front end engineer on Sol, it will be a group of both. **A single owner
plus helpers is the arrangement that produces the adoption statistic this file is sceptical about
below**, because the owner becomes a full-time naysayer with nowhere to send refused work, which is
the failure mode `in-depth/three-layers.md` was written to solve.

**So the layer needs an admission gate rather than an owner, and one already exists.** The promotion
rule: **snowflake to recipe when a second scenario needs it, recipe to core when three do.** Anybody
may propose a core component and the evidence decides. **It is deliberately not a judgement call**,
which is exactly what makes it contributable by a group and what keeps domain concepts out of Sol
when five domains are pushing at once.

**Back end engineers are not consumers of any layer**, and pretending otherwise wastes their time.
They are the most valuable people in the room for one of the exercises below, because the questions
that exercise produces are model questions and nobody else can answer them.

**The cost of adding people, stated rather than discovered.** Every contributor is another consumer
of twelve standards, and the standards' own history records that they had become hard to follow at
seven. **If people are coming, the one-screen index has to be the real entry point**, and `renders/`
is the only way anybody without repository access reads any of it. A render is a copy, so it is wrong
the moment a standard changes.

---

## The language is not settled, and it is a workstream rather than a copy pass

**Andrew, 21 September: none of the UX nomenclature is set in stone, and neither is the entity model's.
Research and testing are needed to land on the most universal language.** This is the largest open
thing in the Kit and it was previously buried inside a suggestion about PMs proofreading copy.

**What it means for everything already written.** Every memo, the glossary, the project vocabulary
and the object model cite their nouns as though the nouns were settled, and **nothing distinguishes a
word that was tested from a word that was invented in a session and then repeated for two weeks.**
Three renames have been pending since 14 September, which is the symptom rather than the problem.

**The cheap mechanism is a status per term**, in the glossary, which already holds every controlled
vocabulary in one place. Where the word came from, and whether it is **provisional**, **tested** or
**settled**. One column. It immediately separates the load-bearing unverified words from the rest,
and it stops a memo citing a session invention as canon. Logged as an open item; not yet built.

**Who is in it.** Designers and PMs, and **BD and marketing**, per Andrew on 21 September. They are
not proofreaders in this. They hold a corpus nobody else has: the words that win deals.

**And the conflict to settle before it is discovered on a screen.** Marketing's corpus and the
operator's corpus diverge. **The copy standard already says Pros Web is contractor and back office**,
which means that where the two disagree the product speaks the operator's word and marketing keeps
its own. Better settled explicitly, because the alternative is a product that renames itself every
time a deck is written.

**How to actually land it**, in the order the effort pays back:

1. **A term inventory from what contractors already say.** The scenario scripts, the pipeline
   documents, existing product UI, and the competitor tools, because tool naming is de facto industry
   language.
2. **A say-it-back exercise.** A contractor describes the object in their own words, recorded
   verbatim, counted for frequency **across trades**. Trade variance is the real risk: roofing, fence
   and deck, and mechanical may not agree on job, project or work order, and a word that works for one
   trade and fails for another is the worst possible outcome because it looks like success.
3. **Comprehension testing on screens, not on word lists.** Show the screen, ask what would happen
   if you clicked. A word list tests recognition; a screen tests understanding.

---

## The exercises

**Five, each producing something that lands in the repository rather than in a photograph of a wall.**

| Exercise | Who | What comes out |
|---|---|---|
| **The data walk, made multiplayer** | A domain's PM, designer, front end and **back end** | Model defects. Walk the scenario's data in date order and ask of every record whether it has somewhere to live at the moment it appears. **Already an Always rule in `standards/walk-the-data-first.md`**; this makes it a room rather than a reading |
| **Objects and actions, per domain** | PM and designer | An object guide and a matrix of objects against what can be done to them, **plus our third axis**. Cheap because the model already exists, and fillable by somebody who knows nothing about the library |
| **A composition trial** | A whole domain team | A gap log. Hand them a beat script and the library and ask them to compose the screens without drawing anything new. **This is step five, it is the G-1 test, and it is the fastest onboarding there is**, because nothing teaches a library like being unable to finish with it |
| **A states session** | Designers and front end, as a group | The example set, which is step two. Render every state each record declares, which exposes the records that assert more than the evidence shows |
| **The language work** | Designers, PMs, **BD and marketing** | Above. Its own workstream, not an afternoon |

---

## Sol's backlog comes out of the composes field

**New on 21 September, and it is why step one is worth doing before anything else.**

Filling in composes on every recipe forces each one to name the core parts it is built from.
**Every name with nothing behind it is a Sol gap with a reason attached**, so the backlog stops being
a guess and becomes a list ordered by how many recipes are blocked on each item.

Two kinds of answer come out, and they want different responses:

- **A recipe that composes molecules directly**, where the gap is a missing molecule. That is Sol
  work, straightforwardly.
- **A recipe that wants a core organism that does not exist**, where the real question is whether
  that thing is generic or domain specific. **The promotion rule answers it**: three independent needs
  or it stays a recipe.

**This is also what protects the refusal below.** Deriving components from the object model has a
documented decay curve. Sol stays the fast layer, the recipe layer stays the translation, and a
domain organism that three domains do not need never reaches core, however badly one team wants it
there.

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
fail on.** Our constraint has been different, because the consumers were one person and several AI
surfaces rather than fifty engineers, so the composability problem was proportionally larger here
than the adoption problem. **That changes the moment other teams contribute**, which is the strongest
argument for the example set and the admission gate being in place before people arrive rather than
after.

---

## The route, in order

**Revised 21 September. The steps are the same five; what changed is why step one matters, where the
stage tables sit, and when people join.**

**One. Name the layers and add the fields, on every record rather than the newest four.** Layer on
all twenty-two, keeping level. A composes field on every recipe and snowflake. Fix the three the sort
exposes: `PeerRow` to core with a name that stops implying a domain, `MoneyCard` and
`OffSystemMoneyCard` merged to one recipe with a state, `Lineage` and `CallTranscript` labelled
snowflake. Add the promotion rule: snowflake to recipe at two scenarios, recipe to core at three.
**This also produces Sol's backlog**, per the section above.

**Two. Lift the mock kit out of the memos and make it the library's example set.** Extract once, cite
from each memo rather than copying into each. Render every declared state, so a record's claims and
its evidence can be compared.

**Three. Build the coverage matrix: components by scenarios.** Not pages by scenarios; the unit is
the component. Four columns to start, S5, S6, S14, S15. Every cell reads used, not applicable, or
missing. **This one table is the gap list, the promotion evidence, the near-identical-sibling detector
and the G-1 test, all at once.**

**Four. Settle the stage tables on the two page templates and the recipes that need them.** Per
stage: prominent, collapsed to a line, or absent, plus order. Nothing on core. **Moves ahead of
step three if other teams start contributing first**, because it is the divergence risk.

**Five. Compose one scenario without drawing it.** The thinnest, S5 or S6, built from the library
alone, no memo first, and log every place the library had to be left. **That is the G-1 demonstration
and the revisit condition on the 14 September decision.** It is also the composition trial in the
exercise table, so the first time it runs it can be somebody else's team doing it.

**When people join: after steps one and two, not before.** Right now the library is in two formats
and has no examples. Five new contributors would each invent their own conventions inside it, and the
month after that would go on reconciling them. **Steps one and two are days of work.**

**What is deliberately last:** the browsable Storybook-like interface. It is the most visible part of
what was described and the least load-bearing. Build it as a render off the library once the library
has examples in it, and not before, or we will be maintaining a second copy of an incomplete thing.

**And the language workstream runs alongside all of it**, because it has a research lead time that
none of the five steps have, and because a term that changes after the coverage matrix is built
changes every row label in it.

---

## Two facts about the model, as at 15 September 2026

**Carried forward with their date and deliberately not refreshed.** They are the team's position, not
ours, and the rule is that their position lives in one dated place and is cited rather than restated.

**The board moved to a fourth pass on 15 September and our snapshot does not know.** Three changes:
`Estimate` became `Itemization`, `Payment Schedule` was deleted and decomposed into a milestone plus
a separate timer that marks it due, and **the spine became one record with a type enum** rather than
two records. Our snapshot is of our own third-pass model, read on 13 September. **Recorded as their
position; nothing here adopts it.**

**What matters for the Kit is how little of that reaches a screen.** Two renames and a
simplification, and the spine enum is invisible to a person who still sees a project. **The churn
that has been moving the memos is vocabulary and ownership, not screen structure.** The screens have
been considerably more stable than the nouns, and nothing measures that today. The coverage matrix
would, and that is a second reason to build it.

**And the Opportunity is still not on their board**, sitting in a loose exploration that their own
serialization names as the most likely source of the next structural change. On the object we have
spent the most thinking on, we are ahead rather than behind.

---

## Learned from

- **21 Sep 2026.** **An overview was added at the top because Andrew needed something to hand somebody, and
  nothing short existed.** Eight memos, a route and five obstacles, and **the shortest thing in the project was
  still a twenty minute read.** It is marked as a restatement and subordinate to the sections below, because a
  summary that can drift from what it summarises is worse than no summary.
- **21 Sep 2026.** **Renamed from the factory to the UX Kit, provisionally, at Andrew's
  instruction.** The collision with Joel's artefact was the practical reason; the two better reasons
  are that factory promises the volume G-1's belief clause refuses, and that it tells a designer from
  another team their judgement is being replaced. **One word was standing for parts, rules, standards
  and an end state, and a name doing four jobs cannot be checked against any of them.**
- **21 Sep 2026.** **Andrew's correction on ownership: Sol will be a group of designers and
  engineers, not one of each.** The version of this file that said otherwise had described the
  arrangement that produces the adoption failure it cites three sections later. **The promotion rule
  turns out to be the admission gate a group needs**, which is a use it was not written for.
- **21 Sep 2026.** **Andrew: the nomenclature is not set in stone, and BD and marketing belong in the
  language work.** It had been written down as a copy pass PMs could do on day one, which understated
  it by an order of magnitude. **The words are the least tested and most cited thing in the project.**
- **21 Sep 2026.** **The status line said nothing started while four records were already in the new
  scheme.** Found by reading the records rather than the document. A status line is a claim like any
  other and this one had not been checked since the day it was written.
- **21 Sep 2026.** **The Sol backlog falls out of step one rather than needing a survey.** Found while
  answering a question about Sol being thin above molecule level: the composes field, added for a
  different reason, is a gap detector, because a name with nothing behind it is a missing component
  with a cause attached.
- **15 Sep 2026.** Andrew asked how to go about building this. C found an external folder with the
  name it then had, made it the baseline, and recommended he supply it. **The decision declining that
  framework was already in the log, dated the day before.** Three decision rows and four Always rules
  in the external work standard came out of the correction. **The route above is the answer to the
  question that was actually asked.**
- **15 Sep 2026.** The 14 September decision said what we are not doing and left the positive half
  unstated. **That is the opening the wrong recommendation walked into**, and it is why this file
  exists: a declined framework is not a default to fall back on.
- **15 Sep 2026.** Andrew, on the stage axis: he does not want it if it will not help build the Kit.
  **It will, because it is the logic half of G-1 rather than a documentation burden**, and narrowing
  it to templates and recipes is what keeps it affordable.
