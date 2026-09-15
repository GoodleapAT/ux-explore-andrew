# Build brief for Claude Design: S15 script walk, fourteen frames

**Written 15 September 2026. Paste the section headed "The prompt" into CD. Everything above it is
for Andrew.**

**This supersedes the memo 9 brief written earlier today.** That one builds twelve frames of a story
that no longer exists: three trades, a Home App contact, a change order and an off-system payment.
**Do not run both.**

---

## Before you run this, four things, and the second one is the one that bites

**1. Decide what CD reads, because the pack is stale twice over.** It was generated on 14 September
against the three-trade Home App story, its own banner already says regenerate, **and it now also
predates the two-trade rewrite.** Two choices:

- **Regenerate it against the new script.** Best outcome, real work, and the reason to do it is the
  finding from the last round: CD could not read five of the seven files a brief named, and one file
  beats seven uploads.
- **Or skip it and upload the memo alone.** The memo is unusually self-sufficient this time: **every
  value any screen needs is drawn on a screen**, the beat text and the UX instruction sit beside each
  mock, and the actor is named in every rail. **The prompt below is written so this works**, and it
  tells CD to take its data from the memo rather than from the worked example.

**Recommendation: skip the pack this round.** It is the cheaper half of the choice and the memo is
the only document in the repository that is correct about this story.

**2. The worked example and the memo now disagree, and the memo is the newer one.** The worked
example still describes three trades, the Home App contact, one permit-free job, a change order and a
three-milestone plan. **The memo has two trades, a phone call, permits on both jobs, no change order
and two milestones.** Its own rule says do not invent a value without adding it here, and **the memo
invented four**: the siding crew lead, the maintenance plan price, the fibre cement siding, and the
office manager appearing at the invoice.

**So the mock data file is a trap for the next surface that reads it**, which is the exact failure it
exists to prevent. **Either rewrite it for the new script or add a second telling to it**, and until
one of those happens the prompt below has to tell CD to ignore it. **This is the largest outstanding
item in the project and it is not in the prompt, because a prompt cannot fix it.**

**3. The token file is still colour only, verified today.** 113 tokens: 46 backgrounds, 42 chart, 32
icons, 30 borders, 28 actions, 20 text, 20 states, 8 elevation. **No radius, no spacing, no type
scale.** Flagged since 11 September with "re-extract before the next round", and this is the second
round it has survived. **The prompt tells CD to take radius, spacing and type from its own components
and to list what it had to choose**, which is the only honest instruction available while this holds.

**4. The memo has no annotation to strip.** Memo 9 carried `[i]` lines and the brief had to tell CD
to leave them behind. **This one is a mocks-only variant, so there is nothing to travel.** The
argument lives under each mock in three blocks: what was taken out, what needs a home, and the
question.

## What changed in the memo after the first build, and CD needs to know

**Nine revisions on Andrew's review, and five of them change component behaviour.**

- **Money is a section on every screen that has it**, headed simply Money, and **the card's own title
  came off** because the group heading said it already. The tender badge now sits where the title was.
- **The proposal card is gone.** Its figures are a nested breakdown inside the money card.
- **The balance-due condition is nested** rather than sitting in a column of figures pretending to be
  one.
- **Job statuses are badges**, Complete in a success tint and everything else neutral.
- **Create invoice moved off the page header into the money card.**
- **The all/active/complete filter came off** the mid-week project screen.
- **The transcript is back**, under Trades on the intake screen, and **we still cannot do it**.
- **Every Work group is now Jobs.**
- **What was left at the property came off the close screen**, because it outlives the project.

---

## The prompt

**Copy from here.**

---

You are building a canvas of fourteen screens for Pros Web, from an existing memo.

## What you are working from

**`memo-10-s15-script-walk.html` in the repository is the specification.** It carries fourteen
lettered sections, A to N. Each one has the script beat and its UX instruction in a rail on the left,
the mockup on the right, and three blocks of argument underneath. **Build what it shows.** Where you
disagree, say so and wait: the last two rounds produced their best findings from you disagreeing, and
one of them saved a page a brief had told you to delete.

**Take all mock data from the memo and from nowhere else.** The worked example file in the repository
describes an earlier version of this story with three trades and a change order, **and it is wrong for
this round**. If a value you need is not on a screen in the memo, say so rather than filling the gap.

**The scenario is S15, "Multi-trade expansion (project umbrella, cash)"**, on the team's own
Confluence page at version 15. **Its UX Specific column is what decided which beats are drawn**, and
six beats are deliberately not drawn: the proposal, the tender and contract, the hand-off, the lead
closing, and the materials delivery. **The memo lists them with reasons before section A.** Do not
draw them.

**Read, in this order:** the memo, then `components/ITERATION-2.md`, `ITERATION-3.md` and
`ITERATION-4.md`, then `standards/INDEX.md` and from it `mockup-density.md` and `ui-composition.md`
in full.

## The three things this round is actually for

**1. Merge the memo's layout with the components you already have.** The memo is drawn in a local
mock kit. **You have real components from the S14 and S15 rounds and from the design system.** Rebuild
these fourteen screens with those. **Where the memo's layout and your component disagree, the
component wins and you say so.** That is the point of the round.

**2. One money card is now doing five jobs, and that is the sharpest test in the library.** The same
card appears on six screens in five states, and **the states are not variants of a style, they are
different readings of the same figures**:

| Where | State | What it shows |
|---|---|---|
| **A** | Nothing owed | $0 balance, a $29 monthly plan, three plan charges. No contract exists |
| **G, H** | Not yet due | Contract $73,100 with the two job prices nested, collected $500, outstanding $72,600, and a **nested block naming the condition** rather than a date |
| **K** | Not yet due, one job left | Same figures, and the nested block now reads off two job states |
| **L** | **Due and uninvoiced** | Same figures, outstanding coloured, a warning badge, a status line, and **Create invoice inside the card** |
| **N** | Settled | Contract and collected both $73,100, outstanding $0, both milestones paid, one by cheque and one by card |

**Answer whether that is one component with five states or more than one.** You are better placed to
answer it than the memo is, because you have both the money-off S14 screens and these in real
components. **And say whether the nested breakdown survives**: the script defers a cost breakdown to
a later round, and **it would have to occupy the same slot the job prices now occupy.** Two
breakdowns of one total in one place is the collision to catch now.

**3. Three settled treatments that this script breaks.** Say which way each should go.

- **Money is absent from the job screen entirely.** Memo 9 drew it read-only with a badge saying
  where it is held. **This script gives a job no money at all.** Both cannot be right.
- **There is no Waiting on card anywhere in fourteen screens.** The permits are the only external
  dependency and they are issued without incident, so a card built to separate what the team controls
  from what it cannot **would read as good news and say nothing**. That failure is already recorded
  against the component.
- **Two tender instruments on one plan.** The deposit is a cheque and the balance a credit card, and
  the plan is badged Cash throughout. **Nothing in the model resolves this** and the badge is
  currently lying on the last screen.

## Frame labels

**Frames are lettered A to N to match the memo's sections.** Every frame label carries four things,
in this order, and **the memo carries all four on every section** so you can copy them:

1. **The memo name and letter.** "Memo 10 · A". The memo name is there because there are now two
   memos with lettered sections and their letters mean different screens.
2. **The screen's name**, as the memo's section heading gives it.
3. **The S15 beats it covers.** These are on the right of each section heading.
4. **Who is on the screen.** This is the last line of each section's left rail.

**Nothing else goes on a frame.** A canvas is judged as a design, so annotation on a frame competes
with the reviewer's comments. Put anything you need to say in the frame label or in your write-back.

## The fourteen frames

| | Screen | When | S15 beats | Who |
|---|---|---|---|---|
| **A** | The customer, a year after the last job | Before the call | 1 | **Nobody.** The record at rest |
| **B** | The call lands, and the caller is already on file | Tue 4 Aug, 8:05am | 2 | Renata Silva, front desk |
| **C** | Roofing picked, and its questions arrive | 8:07am | 3 | Renata Silva |
| **D** | Siding added on the same call, and its own form with it | 8:11am | 4 | Renata Silva |
| **E** | Next step, and the two routes out of a call | 8:14am | 5 | Renata Silva |
| **F** | The site assessment, on the project, two days later | Thu 6 Aug, 4pm | 6 | Priya Raman, sales consultant, on site |
| **G** | The project, the day after the sale, with the money worked out | Mon 10 Aug | 11 | Marcus Ellery, production coordinator |
| **H** | Permits done, seen at the project, as two checklists | Thu 13 Aug | 14 and 15 | Marcus Ellery |
| **I** | The same fact at the job, where the checklist is the work | Thu 13 Aug | 14 and 15 | Marcus Ellery |
| **J** | Two crews, one week, dates on both jobs | Mon 24 Aug | 16 | Marcus Ellery, and Sara Thompson on the phone |
| **K** | Mid-week, one job done and one still running | Wed 9 Sep | 18 | Dwight Okafor and Luis Ferrara on site, Marcus watching |
| **L** | Both complete, and the balance becomes due | Fri 11 Sep | 19 | Marcus Ellery closing out, Sara on both walkthroughs |
| **M** | Create invoice, pre-filled at the remaining balance | Mon 14 Sep | 20 | Alicia Moss, office manager |
| **N** | Paid by card, and the project closes | Mon 21 Sep | 21 | Alicia Moss |

**Time order, left to right, one strip.** **B to E are one phone call**, four frames across nine
minutes, and they are the densest part of the run: a lead and a project come into existence between B
and C without anybody creating them, and **the container's name changes between C and D** because a
second trade was added to it. Draw those four adjacent and draw them identically except where they
differ.

**H and I are the same fact at two grains**, the project level and the job level, and **the script
offers both**. They are the pair to compare.

**E hands off to a screen we already have.** The script says so about sales availability, so the memo
placeholders it rather than proposing one. **Leave it placeholdered.**

## The rules that will bite

- **One coloured region per screen, and the memo already breaks it once, deliberately.** Complete
  takes a success tint, so **on L and N both jobs are green and the colour distinguishes nothing**,
  and L also carries an amber badge, an amber total and an amber status line. **The memo declares this
  and names the button as the only one of the four that earns its place.** Tell us whether you agree.
- **Two cards abreast is unconditional**, and a group may contain one card which keeps its heading and
  takes the full width. **The money group is a lone full-width card on five screens.**
- **No reference codes.** No job numbers, no invoice numbers, no proposal numbers.
- **Connectors are orthogonal**, right-angle corners rather than curves, everywhere.
- **Radius, spacing and type scale are not in our token file.** It is colour and elevation only, 113
  tokens, and that is a known gap. **Take those three from your own components and list what you
  chose**, so the re-extraction has something to check itself against.

## What to tell us afterwards

**A write-back block**, since you cannot write to the repository. Five things:

1. **Every component you used, and whether it needed changing.** Eleven carried both scenarios
   unchanged last time, in a mock kit. We want to know if that holds in real components.
2. **Your answer on the money card**: one component with five states, or more than one, and whether
   the nested breakdown survives the arrival of costs.
3. **Your answer on the three broken treatments** above: money at the job, the missing Waiting on
   card, and the tender badge.
4. **Anything you had to invent**, with what it is and why nothing existing fitted, **plus the radius,
   spacing and type values you chose.**
5. **Where the memo's layout and your component disagreed**, and which you took.

**Do not build the library while you build the canvas.** Leave the trail and we will record it.

---

**Copy to here.**

---

## Learned from

- **15 Sep 2026.** **Two briefs were live for the same scenario inside one day**, built from two
  memos with overlapping letters and incompatible stories. The letter-in-the-frame-label convention,
  reversed this morning and made safe by prefixing the memo name, is what stops that from becoming a
  silent collision. **It was needed within hours of being written.**
- **15 Sep 2026.** **The worked example went stale because the script under it changed, not because
  anybody edited it wrongly.** Its rule covers inventing values; it has no rule for the story moving.
  **A mock data file needs a version of the narrative it belongs to**, or the next surface reads it in
  good faith and builds the wrong customer.
- **15 Sep 2026.** **The token file has now survived two rounds of being flagged.** Telling CD to
  choose its own radius and spacing and to list the choices is the workaround, and a workaround
  repeated twice is a decision.
