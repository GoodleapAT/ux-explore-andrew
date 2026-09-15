# Prompt for Claude Design: the S14 canvas

> # HISTORY. Round one build brief, superseded 14 September 2026.
>
> Replaced by `CD-PROMPT-s14-round-two.md`. **And its model claims are now wrong**: it asks whether
> four status levels can be hidden and names them as inquiry, interest, lead, project. **The Interest
> was retired on 15 September** and the four are now opportunity, inquiry or prospect, lead, project.
> Qualification is also automatic now rather than an act. **Do not take any model claim from this file.**

**Paste this into Claude Design after it has read the context document. 14 September 2026.**

> **This is a build brief, unlike the context document.** It says what to draw and in what order.
> Everything it does not say is governed by the standards, which are binding.

---

## Before you draw anything

**Read, in this order:** `upgrade-to-pros/CLAUDE-DESIGN-CONTEXT.md` version 3.0, then
`upgrade-to-pros/TEAM-POSITIONS.md`, then `standards/INDEX.md`, then `standards/mockup-density.md`
and `standards/ui-composition.md` in full, then `upgrade-to-pros/WORKED-EXAMPLE-S14.md`, then
`upgrade-to-pros/memo-7-s14-end-to-end.html`.

**Say the date of the newest entry in `CHANGELOG.md` before you start.**

**Then tell me what you have understood and where you disagree, and wait.** Do not begin the canvas
until I have answered.

---

## What to build

**One canvas, fourteen frames, left to right in the order below.** This is a sequence and the order
is the argument: it is one customer's journey from a phone call to a closed job, and the canvas
should read as a strip.

**Two frames are placeholders.** Draw them as labelled dashed frames at the same size as the others,
not as finished screens. They hold their place in the strip so the gap is visible.

| # | Frame | Memo | Draw |
|---|---|---|---|
| 01 | **Looking her up** | new | Real |
| 02 | **Taking it down** | new | Real |
| 03 | **The inquiry, ready to qualify** | A | Real |
| 04 | **Booking the advisor** | B | Real |
| 05 | **What exists when she puts the phone down** | C | Real |
| 06 | **The assessment, in the attic** | D | **Placeholder** |
| 07 | **The assessment, from the office** | E | Real |
| 08 | **The hand-off** | H | Real |
| 09 | **Getting it ready** | I | Real |
| 10 | **The backorder** | J | Real |
| 11 | **Install day** | K | **Placeholder** |
| 12 | **The close, and the cheque** | L | Real |
| 13 | **The county, the rebate, and completion** | M | Real |
| 14 | **The tail** | N | Real |

**Memo sections F and G are deliberately not on the canvas.** F is the kitchen-table proposal
presentation and G is the proposal record. **Andrew has excluded the proposal screens from this
round.**

**Say so on the canvas.** Between frames 07 and 08 leave a labelled gap reading that the proposal,
the payment promise and the two-night stall are out of scope for this round, so a reader does not
think the sale happens by magic. Frame 08 opens with the work already sold.

---

## The two new frames, which are the point of this round

These do not exist in memo 7. **They are the reason the canvas starts before section A**, and the
thing being tested is what a CSR actually does in the first ninety seconds of a call.

### 01 · Looking her up

**7:50am. The call is live. Dana has a name and an address and nothing else.**

The first act is a **search, not a form**. Dana types what she has been told and the product tells
her whether this person already exists. Everything about the screen should say that creating a
customer is the second choice, not the first.

**What is in the worked example:** Carla Brenner, (559) 555-0173, 2214 Tulare Street, Fresno CA
93721. **There is one near-match in the system**, "Brenner, W & C · 2214 Tulare St", with a different
spelling and no phone on file. It is not the same household and Dana dismisses it at 7:51am.

**What this frame has to get right.** The near-match is the whole reason the frame exists. A CSR
under time pressure in a heat wave will either create a duplicate or wrongly merge two households,
and which of those happens is decided here. **The dismissal needs a reason, and it needs to be
visible later**, which is why the row appears again on frame 03.

**Do not** put the whole intake form on this screen. This frame is one question: does she already
exist.

### 02 · Taking it down

**7:51am. No match, so Dana is creating. The call is still live.**

Name, mobile, address, and **one question that is not a field**: how old is the system. The customer
said "our AC died overnight, how soon can someone look at it", and Dana's answer to that question is
what decides whether this goes to a comfort advisor or a service technician.

**Draw this mid-flight**, not complete. Some fields filled, the age question unanswered or just being
answered, the primary action not yet available. **Frame 03 is the same screen finished**, and the
pair is what shows that beat 1 is a triage rather than a capture.

**What this frame has to get right.** The system-age question must not look like the other three
fields. It is a routing decision wearing a field's clothes, and the memo's argument is that the
screen should say so.

---

## The twelve frames from the memo

**Draw them from the memo, not from your own reading of the scenario.** Each section carries a
mockup, an argument in labelled blocks, and numbered open questions. **The argument is the
specification** where the mockup is ambiguous.

**Three things to carry across faithfully.**

**Frame 09 and frame 10 share one component.** The readiness card reads "Blocking 0" on frame 09 and
"Blocking 1" on frame 10, and **nothing else about it changes**. That is deliberate and it is the
test the component has to pass: one component with declared states, not two near-identical siblings.
If you find yourself drawing two cards, stop and say so.

**Frame 12 contains a knowing rule break.** The close screen carries one line of explanatory copy
inside the mock, saying where cheques go. It violates an Always. It is there because a crew lead
standing in a driveway with a cheque will not read a memo. **Keep it, and keep the flag on it.** If
you think it should come out, say so rather than removing it.

**Frame 13 is the most interesting card in the set.** It is a receipt for a derived status: three
records agreeing is what makes the job complete, and a person who did none of the three needs to see
which three and when each landed. It answers a need that has been open since the Thompson work.

---

## What the canvas is for

**Three questions, in order of how much they matter.**

**1. Does anything tell anyone the project exists?** It is created at 7:52am on frame 03, it holds
nothing until frame 08, and no frame mentions it. **Frames 05, 08 and 14 are where that decision
bites.** The memo draws the version where it is never mentioned. **If the honest answer turns out to
be that nothing can be shown usefully until the hand-off, the model is wrong rather than the
layout**, and that is a finding worth having.

**2. Can four status levels be hidden?** Inquiry, interest, lead, project. S14 has one interest, so
a screen showing all four would be absurd. **No frame should show more than two.** If you cannot draw
a frame without exposing the levels, say which frame and why.

**3. Does the strip read as one journey?** Fourteen frames, one customer, twenty-six days. A reader
should be able to follow it left to right without the memo open.

---

## What not to do

- **Do not invent data.** Everything is in the S14 worked example. If a screen needs a value that is
  not there, name it as missing rather than filling the gap.
- **Do not draw the proposal**, in any frame. It is out of scope this round.
- **Do not make it interactive.** This is editorial.
- **Do not add a first-run introduction, a tour, or a tooltip explaining what a lead is.** If a call
  to action needs explaining, the wording is wrong.
- **Do not put the word Project on any frame.** The container is called by its contents.
- **Do not use reference codes**, job numbers, permit numbers or identifiers of any kind.
- **Do not fill an empty state with "none yet" furniture.** Unknown is written out where it is a fact,
  and left out where the model cannot answer it. The test is whether somebody could make it appear by
  doing something.

---

## When you finish

**Record every component you create or adapt**, with seven fields, in a write-back block. Frames 01
and 02 will produce at least two new ones: a search-and-resolve surface and whatever the system-age
question turns out to be.

**And produce the write-back block**, covering: the component records, anything that turned out to be
undrawable, any place a standard got in the way, and a changelog row. **Both write-back questions**:
what we learned about the problem, and what we learned about how to work on it.

**One thing already known to need a write-back.** Memo 7's section A shows the near-match as a
dismissed row, which implies the system matched in the background and reported afterwards. **Frames
01 and 02 change that**: the match is now discovered by searching. So section A of memo 7 is
slightly out of step with the canvas, and the deviations register should say so.
