# Mockup density

**Scope:** any mockup, screen, component or prototype built for Pros Web or Merlin, on any surface.
Check before building and again before presenting.

**Surfaces:** all.

---

## How hard to hold each rule

Every rule below carries one of three markers. They mean what they say.

| Marker | Meaning |
|---|---|
| **Always** | Breaking it is a defect. If you must break it, say so before you do, not after |
| **Default** | Do this unless you have a reason. Having a reason is fine; not saying it is not |
| **Prefer** | A leaning. Use judgement and move on |

---

## The rules

### Always

- **No reference codes or record identifiers.** No job numbers, proposal numbers, invoice numbers,
  permit numbers or change-order numbers. Call the thing by its name: the siding job, the master
  invoice, the change order. Real names and real values still matter; identifiers do not.
- **No explanatory copy inside a screen.** No information boxes, no footnotes explaining how the
  model works, no captions telling the user what a field means. If a message seems necessary, list it
  under the mock as a suggestion so it can be judged on its own.
- **Placeholder anything the current question does not touch**, and label it. A dashed box already
  reads as a placeholder and does not need a chip saying so.

### Default

- **Status goes in the second line of the right-hand column**, in secondary text, under the value.
  Name and detail on the left, value and status on the right.
- **Provenance and history read as prose in the sub line.** "Home App, 21 Jul" and "Suggested by
  DeDe, 21 Jul" are the opening words of a sentence, not labels.
- **Colour only where somebody has to act**, and at most one coloured region per screen. If two
  things are amber, check whether they are the same fact surfacing twice, and if so say so rather
  than colouring both.
- **A gap the model cannot answer is left out, not drawn as unavailable.** Naming a gap on screen
  invites somebody to fill it badly.

### Prefer

- An icon may pair with text where it earns its place. A warning triangle for a block, a clock for a
  deadline. Not one icon per row.

---

## Badges, pills and chips

**This rule was wrong and has been corrected.** The earlier version banned them outright. That was an
overreach, and it cost two real signals before anybody noticed.

**Default: use a badge only where it carries a state the row cannot say in words.**

The test is whether the state needs to be seen before the row is read. A person scanning a list of
twelve leads for the one that needs picking up should find it without reading twelve sub lines. That
is what a badge is for.

| Use a badge | Do not |
|---|---|
| **New.** Something has arrived and nobody has touched it | **Won**, **Paid**, **Active**, **Complete**. Settled states. Nothing to act on, and they are the majority, so badging them makes the exceptions invisible |
| **Blocked.** Something is stopping it and it is not moving | **Provenance.** Where a lead came from is prose, not a state |
| **Deferred.** Alive, parked, and due back | **Placeholder.** The dashed border says it |
| | **A status already obvious from position.** A row inside a Closed segment does not need a Closed badge |

**Three or four badges on a page is the shape to aim for. Twelve is the failure.**

A badge is not the same as colour. A quiet badge with no colour is legitimate and often right; colour
is still governed by the rule above, so a New badge in neutral tone and a Blocked badge in amber are
both correct.

## When a state cannot use colour and cannot use a badge

There will be states that matter and qualify for neither. Reach for these in order, and stop as soon
as one works.

1. **The status word itself**, in the status line. Say New.
2. **Weight.** The row's name in medium rather than regular.
3. **A leading glyph** on the row.
4. **Position.** Sort it to the top, or give it its own segment.
5. **A badge**, if it passes the test above.
6. **Colour**, if somebody must act now.

**Do not invent a sixth device.** If none of these works, the screen is being asked to carry too many
states and the answer is fewer, not louder.

---

## Worked example: a lead row

Three leads on a customer record. One is new and unassigned, one is won, one is deferred to spring.

**Wrong.** Every row carries two pills: a status pill and a provenance pill. Six coloured objects, in
four colours, and the one row somebody has to act on is the same weight as the two that are history.
The eye lands nowhere.

**Also wrong**, and this is the version the earlier rule produced. No badges at all, no colour, all
three rows identical in weight, status as grey text in the second line of the right column. Correct
by the letter of the old rule, and the new lead is invisible. **A rule that hides the thing the page
exists to surface is not being held rigidly, it is being held wrongly.**

**Right.** The new lead carries a **New** badge in neutral tone and its name in medium weight.
Provenance reads as prose in the sub line on all three: "Home App, 21 Jul". The won lead carries no
badge and reads Won in grey in the status line. The deferred lead carries a **Deferred** badge, also
neutral, because it is alive and due back and a rep scanning the record needs to see it without
reading. One badge-free row out of three, two quiet badges, no colour anywhere, because nothing on
this screen needs acting on today.

**Then the screen changes.** At the step where a job is blocked, that job's row takes amber and a
warning glyph, and it is the only coloured thing on the page. The two neutral badges stay neutral
and the hierarchy holds.

---

## Why

**On colour.** Colour is a budget, not a palette. Every coloured element spends some of the reader's
attention, and a page that spends it on twelve status pills has nothing left for the one job stuck at
a permit desk for fourteen days. The Sol green is also a practical problem: it is the only green in
the system and it fails contrast as small text, so a success state cannot be coloured compliantly
anyway.

**On reference codes.** They cost horizontal space in a row that is already tight and buy nothing
when the question is structural. Worse, they make a screen look drawn against a system of record that
exists, which invites a reader to accept the structure rather than argue with it. A row that says
"Siding" is easier to disagree with than one that says "JOB-3101 Siding".

**On the badge overreach.** The original rule was written after a mockup carried twenty seven badges.
The fix for twenty seven is not zero. Banning the device removed the only way to make a state visible
before a row is read, and the cost showed up twice before anybody spotted the cause.

## Learned from

- **10 Sep 2026.** Andrew, reviewing a rebuilt project workspace: too many badges, pills and chips,
  and too many informational messages. Asked for plain text with an optional icon, and colour used
  sparingly and only where something needs attention.
- **11 Sep 2026.** Andrew: drop the job and project codes.
- **13 Sep 2026.** Andrew, correcting the overreach: not no badges ever, much more limited use.
  Written up here with the test, the two lists and the fallback ladder.
- **13 Sep 2026.** The cost of the overreach, found by CD across two rounds: a new lead cannot shout,
  and an earlier edit removed the only genuine sub-status from the page where it bites. Both were the
  rules working as written.
- **13 Sep 2026.** Andrew: the rules had become too many and too abstract to follow. Rigidity markers
  and worked examples added in response.
