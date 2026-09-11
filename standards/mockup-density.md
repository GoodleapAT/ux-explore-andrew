# Mockup density

**Scope:** any mockup, screen, component or prototype built for Pros Web or Merlin, on any surface.
This is the rule most often broken, so check it before building and again before presenting.

**Surfaces:** all. Claude Design, Cowork and chat.

---

## The rules

- **No badges, pills or chips.** Status is plain text.
- Put status in the **second line of the right-hand column**, in secondary text, under the value.
  Name and detail go on the left, value and status on the right.
- **Provenance and history read as prose in the sub line**, not as a coloured tag. "Home App, 21 Jul"
  and "Suggested by DeDe, 21 Jul" are the opening words of a sentence, not labels.
- **Colour only where somebody has to act.** At most **one** coloured region per page. If two things
  are amber, check whether they are the same fact surfacing twice, and if so say so rather than
  colouring both.
- An icon may pair with text where it earns its place. Warning triangle for a block, clock for a
  deadline. Not one icon per row.
- **No explanatory copy inside a mockup.** No blue information boxes, no footnotes explaining how the
  model works, no captions telling the user what a field means.
- Suggested copy goes in a **list under the mock**, labelled as a suggestion, so it can be judged
  on its own rather than smuggled in.
- **No reference codes or record identifiers.** No job numbers, proposal numbers, invoice numbers,
  permit numbers or change-order numbers. Call the thing by its name: the siding job, the master
  invoice, the change order. Real names and real values still matter; identifiers do not.
- **Placeholder anything the current question does not touch**, and label it. A dashed box already
  reads as a placeholder; it does not need a chip saying so.
- Where a gap in the model has no UI answer, **leave it out rather than drawing it as unavailable**.
  Naming a gap on screen invites somebody to fill it badly.

## Why

**On reference codes.** They cost horizontal space in a row that is already tight, and they buy
nothing when the question is structural. Worse, they make a screen look like it is drawn against a
system of record that exists, which invites a reader to accept the structure rather than argue with
it. A row that says "Siding" is easier to disagree with than one that says "JOB-3101 Siding".

Colour is a budget, not a palette. Every coloured element spends some of the reader's attention, and
a page that spends it on twelve status pills has nothing left for the one job that has been stuck at
a permit desk for fourteen days. The same is true of explanatory text: a page that explains itself in
its own copy is a page that will be skimmed.

The Sol green is also a practical problem. It is the only green in the system and it fails contrast
as small text, so a success state cannot be coloured compliantly anyway. Dropping the colour from
settled rows is the better answer regardless, because it leaves amber as the only colour in the
block, which makes the one row anyone has to act on the only row that reads as coloured.

## Learned from

- **10 Sep 2026.** Andrew, reviewing the rebuilt project workspace mockup: too many badges, pills and
  chips, and too many informational messages. Named the blue derivation box specifically. Asked for
  normal text, optionally with an icon, and colour used sparingly and only where something needs
  attention.
- The same session established that removed messages should be listed under the mock as suggestions
  rather than simply deleted, so they can be reconsidered.
- The contrast reasoning is lifted from the comments in Andrew's own standalone Pros Web screens,
  which reached the same conclusion independently.
- **11 Sep 2026.** Andrew, reviewing a draft brief for a scenario walkthrough: drop the job and
  project codes. They had been carried through every memo since August without anyone asking for
  them.
