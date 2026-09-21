# CD build: Designing against a moving model

**A rebuild spec. 16 September 2026. Paste the section headed "The prompt" into CD and upload this
whole file alongside it.**

> **This is a rebuild, not a new design.** The page exists and works. It is being recreated in Claude
> Design so Andrew can edit it there. **Every word below is final copy. Do not rewrite it, do not
> improve it, and do not add to it.**
>
> **What you are deciding is only how it is drawn**, using the bound design system rather than the
> hand-rolled CSS the original uses.

---

## What the page is

A four-panel explanation for Andrew's team, covering why three of four screen attempts stopped being
valid between 11 and 16 September, what now sits between the model and the screens, the five-step
route to a component library, and how that library is structured.

**Four sections, lettered A to D**, each with a lettered badge, a title, a right-aligned subtitle, an
intro paragraph, a full-width diagram, and in A's case only, a three-column text block underneath.
Then a closing block.

**Panels B, C and D have no text under their diagrams.** That is deliberate and was an explicit
edit. Do not add any.

---

## Page frame

**Eyebrow**, monospace, uppercase, four items spaced apart:
`Upgrade to Pros` · `Design method` · `16 September 2026`

**Title:**
> Designing against a moving model, and the mechanism that stops it hurting

**Two lede paragraphs**, at a narrow measure, bold on the marked phrases:

> Over three days, four attempts at the Thompson screens were built and three of them stopped being
> valid. **Not because the screens were wrong, but because the ground under them moved while they
> were being drawn.**

> This is normal for exploratory design and it is not a reason to stop exploring. It is a reason to
> **put something between the model and the screens**, so that when the model moves, the screens do
> not all have to be redrawn. That something is the thing being built next, and this explains what it
> is.

---

## Panel A

**Badge** A. **Title:** Three layers were moving at once. **Subtitle:** 11 to 16 September

**Intro:**
> Each layer rests on the one above it. **When the model moves, the script becomes wrong. When the
> script moves, every screen drawn from it becomes wrong.** Nothing measured that, so the effect
> showed up as screens that looked bad rather than as ground that had shifted.

### The diagram

**A three-lane timeline.** Lanes are horizontal bands running left to right. Four date columns,
unevenly weighted, because most of the activity is in the last two.

**Column headers**, monospace uppercase, with a faint vertical rule between each:
`11 TO 13 SEP` · `14 SEP` · `15 SEP` · `16 SEP`

**Lane labels**, on the left, outside the bands. Each is a monospace uppercase title with two small
lines under it:

| Lane | Label | Under it |
|---|---|---|
| 1 | THE MODEL | what the / nouns mean |
| 2 | THE SCRIPT | what happens / in the story |
| 3 | THE SCREENS | what gets / drawn |

**Lane 3 is roughly twice the height of the others**, because it holds two rows of items in the last
two columns.

**Every item is a small card with a bold first line and one lighter line under it.** Cards sit inside
their lane and their date column.

**Lane 1, the model:**

| Column | Card | Tone |
|---|---|---|
| 11 to 13 Sep | **Standards, first records** / The library is started | neutral |
| 14 Sep | **Opportunity added** / Interest retired | neutral |
| 15 Sep | **Demand model rebuilt four times** / and the board moves to a fourth pass | **warning** |
| 16 Sep | **Pipeline reference found stale** / Asset, Lead, Job emerges | **warning** |

**Lane 2, the script:**

| Column | Card | Tone |
|---|---|---|
| 11 to 13 Sep | **S15 as the team wrote it** / Three trades, app contact | neutral |
| 14 Sep | **S4 rewritten to the new model** / Others left as they were | neutral |
| 15 Sep | **S15 rewritten end to end** / Two trades, a phone call, no change order | **warning** |
| 16 Sep | **Calendar revised twice** / Seven weeks becomes three | **warning** |

**Lane 3, the screens.** Nothing in the first column.

| Column | Card | Tone |
|---|---|---|
| 14 Sep | **Two memos for S14** / Still valid. A different scenario | **success** |
| 15 Sep, upper | **Memo for S15, and a build brief** / Three trades, change order, cheque | neutral |
| 15 Sep, lower | **A second memo, on the new script** / Fourteen screens, two trades | neutral |
| 16 Sep, upper | **A memo of one screen, six states** / Rejected. Groups moved for no reason | neutral |
| 16 Sep, lower | **Data pack, brief, pipeline documents** / The turn. Section B | muted |

**Four warning-coloured arrows, orthogonal, pointing straight down**, each labelled `invalidates`:

- From the 15 Sep model card into the 15 Sep script card
- From the 15 Sep script card into the 15 Sep screens card
- From the 16 Sep model card into the 16 Sep script card
- From the 16 Sep script card into the 16 Sep screens card

**One dashed grey connector**, orthogonal, from the 15 Sep screens area across to the 16 Sep lower
screens card. It has no label.

**Two small pieces of coloured text inside lane 3:**

- Under the 15 Sep upper card, in warning colour: `Invalid the same evening`
- Under the 16 Sep upper card, in accent colour: `Failed on method, not on movement`

**A single line of warning-coloured text under the whole diagram:**
> Three of four attempts stopped being valid. Two because the layer above them moved. One because a
> theory about lifecycle stages was allowed to drive the layout.

### Caption, under the diagram frame

> **Complete on structure, not exhaustive on contents.** Work on other scenarios, the standards and
> the component records ran throughout and is left out.

### The three text blocks, A only

Three columns, each with a small monospace uppercase label and two short paragraphs.

**WHY THIS IS NOT A MISTAKE**
> **The model was supposed to move.** That is what the last three weeks were for, and it moved in the
> right direction every time: a demand object appeared, then a better one, then a better one again.

> The cost was not the thinking. **It was that the screens were the only record of the thinking**, so
> every improvement destroyed its own evidence.

**THE COMPOUNDING FACTOR**
> **Nothing fixed the data.** Every screen decided its own dates, names and figures as it was drawn,
> so two screens of the same page disagreed with each other and neither was wrong.

> That is why the last attempt failed differently. **With nothing fixed, each screen re-solved its own
> arrangement**, and the result read as arbitrary because it was.

**WHAT IT WAS NOT**
> **Not a tooling problem**, and not a question of drawing more carefully. Two of the three
> invalidated pieces were good work that stopped being true.

> A fourth thing also went wrong and is worth naming: **whole-flow prompts.** Asking for fourteen
> screens at once forces dozens of unstated decisions simultaneously, and one wrong decision
> contaminates everything after it.

---

## Panel B

**Badge** B. **Title:** The fix is not to stop the model moving. **Subtitle:** What changed on 16 September

**Intro:**
> The model will keep moving, and it should. **What was missing is anything between it and the
> screens.** Four things now sit in that gap, each absorbing a different kind of movement. The first
> three hold this scenario still. **The fourth holds the component library still, and it is the one
> that outlives the scenario.**

### The diagram

**Three zones across the width: a left card, a large bordered container, a right card.** Two
orthogonal accent-coloured arrows, left card into the container, container into the right card.

**Left card**, warning tone, vertically centred against the container. A heading line and three
smaller lines:
> **The model moves**
> and it should. That is
> what the last three
> weeks were for.

**The container** is a bordered panel with a monospace uppercase label at its top left:
`FOUR THINGS THAT ABSORB THE MOVEMENT`

**Inside it, four accent-tinted cards in a two by two grid.** Each has a bold numbered title and
three lines:

**1. The data pack**
> Every date, name, price and money state for
> all twenty one beats, fixed in one file.
> No screen decides a value again.

**2. Containers, not screens**
> Twenty one beats are six containers in
> fourteen states. A state is a variant of
> its container, never a new page.

**3. One layout rule**
> Groups keep their order across every state.
> A group that is not needed collapses in
> place. Nothing moves up the page.

**4. A recipe layer in the library**
> Core components know nothing about the
> business. Object names live one layer up,
> where they are expected to change.

**Right card**, success tone, same size and alignment as the left one:
> **The screens hold**
> because what moved
> was absorbed here,
> not redrawn there.

**One line of accent-coloured text under the container:**
> A fifth thing was settled the same day and is not a buffer: multiple trades stay bundled on one
> sales card, and separate at the hand-off.

**No text under this diagram.**

---

## Panel C

**Badge** C. **Title:** The route to a component library that composes. **Subtitle:** Five steps, and where we are

**Intro:**
> The destination is stated as a principle: **an atomic design system with enough components, driven
> by logic that reacts to the model and the scenario, can compose a scenario's screens rather than
> having each one drawn by hand.** It is a belief and it has not been demonstrated. **Step five is the
> demonstration**, and nothing before it may be justified by the destination.

### The diagram

**A row of five boxes left to right, joined by orthogonal arrows, then a sixth box below.**

**Box 0**, success tone, with a monospace uppercase label `DONE, 16 SEP` above its title:
> **The scenario is pinned**
> Data pack, handover brief,
> two pipeline documents.

**Boxes 1 to 4** each carry a large accent-coloured numeral above the title.

**1**, accent tone:
> **Name the two layers**
> Core or recipe on every
> record. One pass.

**2**, neutral:
> **Extract the examples**
> Every component rendered in
> every state it claims.

**3**, neutral:
> **The coverage matrix**
> Components against four
> scenarios. Used, or missing.

**4**, neutral:
> **Stage tables**
> What each group does at
> each point of a life.

**An orthogonal connector runs from box 4 down, left, and down again** into a wide box beneath the
row, roughly centred. That box is accent-toned, carries the numeral 5, and reads:

> **5** &nbsp; **Compose one scenario from the library alone**
> The thinnest one, built with no memo first, logging every place the library
> had to be left. Those escapes are the gap list. Days, not months.

**One line of accent-coloured text beneath it:**
> Four scenarios, not seventeen. Three independent needs is the threshold, so two could never promote
> anything.

**No text under this diagram.**

---

## Panel D

**Badge** D. **Title:** How the library is built, and why it has a middle. **Subtitle:** The thing step one names

**Intro:**
> Atomic design gives components a **size**: atom, molecule, organism, template. What it does not give
> them is an **owner**. Adding that second axis is the whole of step one, and it is what lets the model
> keep moving without the primitives moving with it. **An object name may never appear in a core
> component**, which is the rule that does all the work.

### The diagram, which has three parts in one frame

**Part one, on the left: a vertical stack, read bottom to top.** Monospace label above it:
`WHAT COMPOSES INTO WHAT`

Four bands, each a card, with **generous vertical gaps between them** so the arrows and their labels
sit in clear air:

| Position | Band | Tone | Lines |
|---|---|---|---|
| Top | **Screens** | muted | One scenario's views, assembled from / recipes. Not stored in the library |
| | **Recipes** | accent | Named compositions of core components. / Object names live here, and only here |
| | **Core components** | neutral | Card, button, badge, field, sheet. Content / and context agnostic. No object names |
| Bottom | **Design tokens** | neutral | Colour and elevation, from the real build |

**Three orthogonal arrows pointing up**, one in each gap, running up the middle of the stack, each
with its verb to the right of the arrow: `composed into`, `composed into`, `assembled into`.

**Part two, the two things hanging off the recipe band.**

**On the left**, a warning-toned card aligned with the Recipes band, with an accent arrow pointing
right into it:
> **The entity model**
> The slow layer.
> It names things

**Two lines of accent text below that card**, in its own column, clear of the stack:
> and it reaches no further
> up or down than this

**On the right**, a muted card aligned with the Recipes band, joined to it by a short dashed grey
connector:
> **Snowflakes**
> One-offs. Allowed,
> if they are labelled

**Part three, the promotion strip, below the stack.** Monospace label:
`PROMOTION RUNS ONE WAY, AND THE THRESHOLD IS COUNTED`

Three small boxes in a row joined by orthogonal arrows: **Snowflake** (muted), **Recipe** (accent),
**Core** (neutral). The arrow labels sit above the arrows: `2 need it`, then `3 need it`. To the
right of the strip, in small text:
> Independent scenarios, counted rather than argued about

**Part four, the axes grid, on the right of the frame.** Monospace label `TWO AXES, NOT ONE`, then
two lines:
> Size and ownership correlate, which is
> why they get mistaken for each other

**A three by four grid.** Rows are ownership, labelled down the left: `CORE`, `RECIPE`, `SNOWFLAKE`,
with `OWNERSHIP` above them. Columns are size, labelled below: `ATOM`, `MOLEC.`, `ORGAN.`, `TMPL.`,
with `SIZE` under the first column.

**Cells are shaded, and the shading is the whole point:**

| | Atom | Molecule | Organism | Template |
|---|---|---|---|---|
| **Core** | filled | filled | pale | empty |
| **Recipe** | empty | pale | filled | filled |
| **Snowflake** | empty | pale | filled | pale |

**Three lines under the grid**, the last two in accent colour:
> Filled cells are typical, pale cells possible,
> empty cells rare.

> The off-diagonal is the point: a large thing
> can be core, and a small thing can be
> a snowflake.

**No text under this diagram.**

---

## The closing block

A rule above it, then a monospace uppercase heading `THE ONE SENTENCE`, then three paragraphs at a
narrow measure:

> **Three days of work were spent discovering that the screens were the only place the thinking was
> written down**, so every improvement to the model destroyed its own evidence.

> **What has been built since is the layer that stops that happening**: the scenario's data in one
> file rather than in fourteen screens, a component library with a place for the parts that are
> supposed to change, and one layout rule that makes two states of a page comparable.

> The model will move again. **The next time it does, the cost should be a rewrite of one file rather
> than a redraw of everything.**

---

## The prompt

**Copy from here.**

---

You are rebuilding an existing four-panel explanatory page in Claude Design, so that it can be edited
here rather than in hand-written HTML.

**Read the build spec uploaded with this message. Every word of copy in it is final.** Do not rewrite
it, do not improve it, do not add to it, and do not shorten it. **If a sentence looks wrong to you,
say so in your reply and build it as written.**

**What you are deciding is only how it is drawn.** The original uses hand-rolled CSS. Rebuild it with
the bound design system's real components, and where the system has no equivalent, say what you had
to invent.

**Four sections, A to D.** Each has a lettered badge, a title, a right-aligned subtitle, an intro
paragraph, and one full-width diagram. **Only section A has text under its diagram**, in three
columns. Panels B, C and D deliberately have none, and that was an explicit edit. Do not add any.

**The diagrams matter more than the prose.** Three of the four are structural rather than decorative:

- **A** is a three-lane timeline with four uneven date columns and four downward arrows crossing
  between lanes. **The arrows are the argument.** The third lane is taller because it holds two rows.
- **B** is a left card, a bordered container of four cards, and a right card, joined by two arrows.
- **C** is five boxes in a row with a sixth below, reached by a connector that goes down, left and
  down again.
- **D** is four things in one frame: a bottom-up stack, two cards hanging off its middle band, a
  promotion strip below, and a shaded grid on the right.

**Rules that will bite:**

- **Connectors are orthogonal.** Right-angle corners, never curves, everywhere.
- **Every connector carries a verb.** `invalidates`, `composed into`, `assembled into`, `2 need it`.
- **Colour is meaningful, not decorative.** Warning tone marks a layer that moved or a thing that
  broke. Success marks work that survived. Accent marks the mechanism being proposed. **Neutral is
  the default and most things are neutral.**
- **No reference codes or record identifiers anywhere.**
- **No em dashes**, in the page or in your reply.
- **Give the containers enough room for their text.** The previous version had two cards whose text
  did not fill them and one panel where a caption ran into a band below it. **Size the boxes to their
  contents rather than to a grid.**

**When it is done, tell me three things.** Which components you used and which you had to invent.
Anything in the spec that contradicts itself. And the one place where you think the drawing could
carry the argument better than it does, since you are looking at it fresh.

---

**Copy to here.**
