# Kickoff: Upgrade to Pros 2

**Written 16 September 2026. Upload this whole file to the new Claude Design project as its first
document, then paste the section headed "Your first instruction" as the first message.**

**One file, not a reading list.** The last round named seven files for CD to go and read and it could
not reach five of them. Everything CD needs to start is below. Where it has to read something else,
the thing is named with what it is for and what is wrong with it.

---

## What this project is

**A clean start.** Three earlier canvases exist for this work and **none of them should be opened.**
They were built against a scenario that has since been rewritten, they carry three trades where there
are now two, a change order that no longer happens, and an off-system final payment that is now a
card. Anything carried forward from them will be wrong in a way that is hard to see. **Start empty.**

**What is being built, in one sentence:** the screens a contractor and a homeowner see across one
multi-trade project, drawn so that the components they are made of can be reused for sixteen other
scenarios rather than redrawn each time.

**The long-run aim**, which is a stated principle and not a plan: an atomic design system, with
enough components carrying enough variants and states, driven by logic reacting to the entity model
and to the scenario's own detail, can compose a scenario's screens rather than having each drawn by
hand. **It is a belief and it has not been demonstrated. Nothing may be justified on the grounds that
it requires this.** What it changes today is only that a component record has to be a specification
rather than a trail.

---

## The plan, and why it is shaped this way

### Screens are built one at a time

Whole-flow prompts have been tried and they hurt. Not because of size: **a whole-flow prompt forces
dozens of unstated decisions at once, and each wrong one contaminates everything after it.** One
screen at a time, with the decisions already made before drawing starts.

**The decisions are already made.** A memo exists that fixes the screen list, the script beat each
screen covers, the money reading at each, and what is deliberately not drawn. It is named in Sources
below. **It is the specification. Build what it shows, and say so when you disagree rather than
quietly diverging.** The last two rounds produced their best findings from CD disagreeing, and one of
them saved a page a brief had told it to delete.

### Fourteen screens are six containers in fourteen states

This is the most important line in this document.

| Container | States | Which |
|---|---|---|
| **Customer record** | 1 | A year after the previous job, nothing owed |
| **Inbound call** | 4 | Caller matched; one trade added; two trades added; next step chosen |
| **Site assessment** | 1 | Two trades measured on one visit |
| **Project** | 6 | Day after the sale; permits issued; crews and dates set; mid-week with one job done; both complete and balance due; paid and closed |
| **Job** | 1 | The same facts at job level rather than project level |
| **Create invoice** | 1 | Pre-filled at the remaining balance |

**Build containers, not screens.** A state is a variant of its container, never a new page. **If two
states of one container end up as two designs, that is a finding and it should be reported, not
worked around.**

**Within a container, build the hardest state first**, then derive the simpler ones by taking things
away. For the project that is "both complete and balance due", which carries four signals of one
fact. Subtracting is faster and more consistent than adding, and it shows the container's full extent
on the first attempt.

### Five screens carry the story

If time runs short, these five tell the scenario completely: **the customer record, the call with
both trades on it, the project the day after the sale, the mid-week screen with one job done and one
running, and the close.** The mid-week one is the only screen that shows why a project umbrella exists
at all, so it does not get dropped.

### The escape log

**One line per screen, written when the screen is finished, naming anything you had to invent or
reach outside the component set for.** Not a component record. Just the escape.

This matters more than it looks. A finished screen never shows what was missing when you started, so
the escapes cannot be reconstructed later while everything else can. **The component records get
written from the escape log afterwards.** Do not stop to write records now.

### After this scenario, so you know what the screens are for

Two variants of the same scenario, changing only whether the household has a service agreement with
monthly payments, then one much thinner scenario. The variants test whether the customer record and
the money card can hold a recurring money stream beside a one-off project, and whether an absent
capability advertises itself or is left out. **That is why states matter more than screens here.**

---

## Principles

**Two are about the domain and bind what a screen may show.**

- **Money is stored where it occurs, and higher levels derive.** A payment belongs to the thing it
  settles; a total is computed. **The consequence you will hit: per-job margin does not exist**,
  because revenue occurs at the project and cost occurs at the job, and no allocation rule has been
  specified. It is not drawn, not greyed, not labelled unavailable. It is simply absent.
- **A project is one workspace that transforms.** It does not become a different object when it is
  sold. The same container carries selling, then work, then close-out, with different parts of it
  prominent. **This is why the project has six states rather than three pages.**

**One is about the library.**

- **One component with declared states, never near-identical siblings.** If you feel the pull to fork
  a component for the second scenario, say so instead of forking it.

### Three layers, and this is new

**Level and layer are two different axes and both are recorded.**

- **Level** is size: atom, molecule, organism, template. The familiar ladder.
- **Layer** is ownership: **core**, **recipe**, **snowflake**.

**Core components are content-agnostic and context-agnostic.** Card, Button, Badge, Field, Sheet.
**An object name may never appear in a core component** and it may not assume where on a journey it
sits.

**Recipes are named compositions of core components**, and **object names are legitimate here and
only here.** A proposal card is a recipe. Recipes live in the product layer and are expected to be
rewritten.

**Snowflakes are one-offs and they are allowed, if labelled.** An unlabelled snowflake pretending to
be reusable is the problem, not the snowflake.

Promotion runs one way: **snowflake to recipe when a second scenario needs it, recipe to core when
three do.**

**Why this is the structure.** The entity model is the slow, stable contract. The core library is the
fast layer. **Recipes are the seam between them and they absorb the churn from both sides.** Coupling
UI structure directly to domain structure has a documented decay curve, which is dozens of types
several of which mean the same thing. So: **the object model tells you what to call things and where
consistency is owed. It does not tell you what to build.**

---

## The rules that will bite

**Markers mean: Always, breaking it is a defect and you say so before rather than after. Default, do
it unless you have a reason and say the reason. Prefer, a leaning.**

### Composition

- **Always. Bundle content into cards, in pairs, under a group heading.** Not full-width blocks down a
  column.
- **Always. A group may contain one card, and it keeps its heading.** A lone card takes full width.
- **Default. Two cards abreast is unconditional.** Cards shrink rather than stacking.
- **Default. Pair cards that answer the same kind of question.**
- **Default. Detail that does not fit goes sideways into a sheet, not down into an accordion.** One
  declared exception: capture during a live call, where collapsible sections win, with counts on the
  headers.
- **Default. Facts about the thing go in a card, not in a subtitle.**
- **Default. Small peer lists become links in the page header, not sections.**

### Density

- **Always. No reference codes or record identifiers.** No job numbers, no invoice numbers, no
  proposal numbers. Call the thing by its name: "the siding job", "the master invoice".
- **Always. No explanatory copy inside a screen.** Anything you want to say goes in the write-back.
- **Always. Placeholder what the current question does not touch, and label it as a placeholder.**
- **Default. Colour only where somebody has to act, at most one coloured region per screen.** In this
  scenario almost nothing is ever blocked, so expect very little colour. **If a screen has two
  coloured regions, say why.**
- **Default. Badges only where they carry a state the row cannot say in words.** New, blocked,
  deferred, yes. Won, paid, active, no. Three or four a page, not twelve.
- **Default. Status in the second line of the right-hand column, in secondary text.**
- **Default. Provenance and history read as prose in the sub line.**

**When a state cannot use colour and cannot use a badge, reach in this order and stop when one
works:** the status word, weight, a leading glyph, position, a badge, colour. **Do not invent a
seventh.** If none works, the screen carries too many states.

### Absence, and this is the one people get wrong

> **A capability that will exist advertises. A gap the model cannot answer is left out.**

The test is whether somebody could make it appear by doing something.

| Situation | What it does |
|---|---|
| A project has no jobs yet because nothing is sold | **Advertises.** A panel naming what arrives at hand-off |
| A payments-only contractor has no selling capability | **Advertises.** This is how they find out it exists |
| Per-job margin, which needs an allocation nobody specified | **Left out entirely** |
| Communications, which have no entity anywhere | **Left out** |

### Writing

The UX writing guide is bound to the design system project and is **binding, not advisory**. Correct
tokens with the wrong word on the button is still an off-system screen. Sentence case, no
"Submit", and the audience terms matter: **homeowner**, not applicant or borrower.

### Other

- **Always. Connectors in any diagram are orthogonal.** Right angles, never curves.
- **Always. Ask before rebuilding anything.** Every time, including small revisions.
- **No em dashes anywhere**, in a screen or in a reply.

---

## Sources, and what is wrong with each

### The design system, which is bound to this project

**Pros Web Design System.** A mirror of Merlin/Sol, pinned at commit `cb9b1aa5`, deployed
2026-08-24. **Merlin deploys more than once a day, so always pin to an explicit SHA and never read
`main`.**

The distinction that organises it is **reference versus runtime**:

- **`_mirror/`** is 321 files of the real component source, byte-for-byte at the pin. **Read it to
  lift exact values. It cannot run**, because Radix, tanstack, tiptap, i18next and the shared aliases
  do not resolve in a browser. **The underscore is load-bearing: the compiler skips underscore
  directories, which is what keeps 476 broken exports out of the bundle. Do not rename it.**
- **`components/`** is nineteen hand-authored ports, **inline styles only**, values lifted from the
  mirror. **This is the only runnable component surface.** Nothing in the bundle comes from the
  mirror.
- **`Merlin Kitchen Sink.html`** is an independent one-to-one port with production CSS inline. **The
  renderable artefact.**
- **Anything beyond the nineteen comes from Merlin's registry:** `shadcn add @merlin/<name>`.
- **`templates/pros-web-page/`** is where to start. `templates/lead-details/` also exists. Both are
  self-contained so a copy keeps working; point a copy at a bound design system by editing the `base`
  line in its `ds-base.js`, which is the only path assumption.
- **`SKILL.md`** is the contract: part one tokens and components, part two the writing guide.

**On tokens, and read this before reaching for a spacing variable.** `styles.css` holds 113 Sol
semantic tokens, light and dark, 226 declarations, machine-extracted and never hand-edited.
**There are no radius, base-scale or font tokens, deliberately, because Merlin's compiled output has
none.** An earlier version had roughly 124 invented base-scale tokens and 64 tokens resolving to
nothing, and they were removed rather than patched.

**So: take radius, spacing and type from the nineteen ports and from the Kitchen Sink, and name the
file each value came from. Do not invent a scale.** Where you genuinely need a value that exists
nowhere, invent it, say so, and list it separately from the lifted ones.

**On the issue log.** `KNOWN-ISSUES.md` section one is for the Merlin team; section two is this
project's own record and **nobody's action item**. Read its method section before declaring any class
dead: arbitrary-value classes are bracket-escaped in compiled output and variant prefixes change the
selector, which together produced several false readings that section one corrects.

**And you may go beyond it.** The system serves a smaller product than this one. Where it has no
answer, extend it, and put what you added in the write-back so it can become a contribution rather
than drift.

### Our working memory, which is the specification

**Repository `GoodleapAT/ux-explore-andrew`.** Private, Andrew's. Not any team's record.

Read in this order:

1. **`upgrade-to-pros/memo-10-s15-script-walk.html`** is the specification. Fourteen lettered
   sections A to N, each with the script beat and its UX instruction beside the mock, and three
   blocks of argument underneath: what was taken out, what needs a home, and the question. **The
   money is worked out across the whole script in a panel before section A, and six beats are listed
   as deliberately not drawn.**
2. **`upgrade-to-pros/WORKED-EXAMPLE.md`** is the mock data, **and it is stale for this scenario.** It
   still describes three trades, an app contact, a change order and three milestones. **Take all data
   from the memo instead.** If a value you need is not in the memo, say so rather than filling the
   gap.
3. **`upgrade-to-pros/components/ITERATION-2.md`, `ITERATION-3.md`, `ITERATION-4.md`** are the
   component records. Seven fields each. **None of them carries a layer field or a per-stage table
   yet**, which is work this round will inform.
4. **`upgrade-to-pros/in-depth/three-layers.md`** and **`in-depth/the-factory.md`** are the reasoning
   behind the layer scheme and the plan. Read if a layer call is unclear.
5. **`standards/INDEX.md`** is every rule on one screen, then `mockup-density.md` and
   `ui-composition.md` in full.

### The team's record, which is reference and not input

**Repository `loanpal-engineering/u2p-project-planning`**, owned by Joel. **Read as reference, never
as requirement.** Its entity model serialization is the current master of the object map and is
useful. **Nothing in it constrains this work**, and its own UX work is a separate effort that is not
being adopted. Do not align to it and do not cite it as a reason.

**The scenario scripts are in Confluence**, space ProsOperat, under a page called Scenarios. **S15 is
the one being built**, rewritten on 15 September to version 15. Its UX Specific column is what decided
which beats are drawn. **Five sections below its script still describe the old story and each carries
a banner saying so. Do not read them.**

### What is known to be drifting

**The object map moved to a fourth pass on 15 September and our model snapshot does not know.** Three
changes: `Estimate` became `Itemization`, `Payment Schedule` was replaced by a `Milestone` plus a
separate `Scheduled Payment` that marks it due, and **the spine became one record with a type enum**
rather than separate Project and Subscription records.

**Almost none of that reaches a screen.** Two renames and a simplification, and a person still sees a
project. **Use "project" on screen.** It is recorded here so that if you see the newer words in the
team repository you know which generation they belong to.

---

## Your first instruction

**Copy from here.**

---

You are starting a canvas for Pros Web, scenario S15, a multi-trade project paid in cash.

**Read the kickoff document in this project before anything else**, then confirm three things back to
me in a short reply, and **do not draw yet**:

1. **Which of the nineteen ported components you expect to use**, and which of the six containers you
   think has no adequate component in the system today.
2. **The radius, spacing and type values you found**, and which file each came from. If you had to
   invent any, list those separately.
3. **Anything in the kickoff document that conflicts with itself or with the design system's own
   contract.** There is at least one place where a density rule and an absence rule pull in opposite
   directions, and I would rather you name it now than resolve it silently later.

**Then build one screen only: the project, at the state where both jobs are complete and the balance
is due and uninvoiced.** That is section L of the memo. It is the hardest state of the most-used
container, it carries the one piece of colour in the whole scenario, and it contains a fact stated
four different ways that I want to reduce to one.

**When it is done, give me:** the screen, one line naming anything you invented or reached outside
the component set for, and your view on whether the four signals of "due and uninvoiced" should be
one signal and which one.

**Do not build the library while you build screens.** Leave the trail and I will record it.

---

**Copy to here.**

---

## Notes for Andrew, not for CD

**The deliverable format is not settled in this document.** It assumes a set of screens in order
rather than a clickable prototype. **If it needs to be clickable, add one line to the first
instruction saying so**, because it changes how each container is built and it is cheaper to say now
than to retrofit.

**Why section L is the first screen rather than section A.** It is the hardest state of the container
used most, so it establishes the full extent of the project page immediately, and the five other
project states are then subtractions. Starting at A would mean discovering the container's demands on
the sixth screen instead of the first. **The cost is that the first thing you see is not the first
thing in the story**, which is worth knowing before you look at it.

**The conflict planted in the first instruction is real, not a test.** The density rule says at most
one coloured region per screen. The absence rule and the money reading together produce a screen
where the balance is due, the total is coloured, a badge says so, a status line says so, and a button
offers to act. **Four signals of one fact.** I think the button is the only one that earns its place.
Asking CD to name it first is cheaper than arguing about it afterwards.
