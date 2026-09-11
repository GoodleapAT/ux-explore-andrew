# Design memo format

**Scope:** the format for moving from thinking into UI. Mockups, screens, components, prototypes, and
prompts to paste into Claude Design. A memo, not a working prototype.

**Surfaces:** all. The original specification is the Claude project instructions, kept as a render at
`renders/claude-ai-project-instructions.md`; this file records where practice has departed from it and
why.

---

## The rules

- **Ask before building or rebuilding any memo.** Every time. Use the questions to settle scope
  first: which screens, what fidelity, and which parts should be real rather than placeholder.
- **A small uppercase eyebrow line:** project, topic, and "mockup" with the date.
- **A title, then a short intro at a narrow measure** saying what the memo is testing.
- **A settled card** listing what is being carried in, worded as settled *for the purposes of this
  memo* rather than settled in general, because these are usually working assumptions. Key phrase of
  each point in bold.
- **A to-decide card** naming what has to be resolved before anything gets built. Same visual
  treatment as the settled card, not a warning colour. If a failure there means the model is wrong
  rather than the layout, say so.
- **Lettered sections, one per screen**, each with a boxed letter badge.
- **The mockup at full page width, with the argument underneath** in short labelled blocks, then the
  numbered open questions. Each block gets a small label naming the claim it makes, then two or three
  sentences defending it.
- **The argument carries the thinking.** Prose must not migrate into the mockup, and the mockup must
  not be left to speak for itself.
- **Editorial, not interactive.** Do not make it clickable unless asked.
- **Mark annotation inside a mockup with an `[i]` prefix** and declare the convention near the top.
  This applies only to mockups, where annotation could be mistaken for interface copy. A diagram is
  annotation throughout, so it needs neither.
- **Mockups look like believable UI** with real labels and values. The editorial framing is what
  signals it is not a design.
- **Placeholder anything the current question does not touch**, and label it.
- **Where a layout choice is uncomfortable or costly, say so in the memo** rather than hiding it.
- **Ask before adding** a closing four-card row, or a closing note on what the next round should
  specify rather than sketch. Both are often useful and often padding.

## Two departures from the original specification

**The mockup is full width, not left, with the argument underneath rather than beside it.** The
original specification puts the mockup on the left and the argument in a column on the right. That
column takes enough width that a pair of cards abreast becomes cramped, and card pairs are how a Pros
Web screen is composed. Width went to the mockup. Decided 10 Sep 2026.

**The to-decide card can sit at the bottom and can carry more than one item.** The original
specification puts it near the top and limits it to the single thing that has to be resolved. Andrew
asked for all of the open items collected in one place at the end. Decided 10 Sep 2026.

## The mocks-only variant

A memo can be reduced to mockups plus, under each one, a list of what was taken out and what needs a
home. Use this when the question is the UI itself rather than the argument for it. The list is split
three ways:

- **Taken out.** Something that was in the mock and has been removed for density.
- **Suggested copy.** A message worth considering as a tooltip or a one-time explanation, rather than
  permanent page furniture.
- **Needs a home, or a question.** Something the model requires and the mock has nowhere to put.

In this variant there is **no annotation inside the mockups at all**, so no `[i]` convention is
declared. The list under the mock does the work the annotation used to.

## Learned from

- **10 Sep 2026.** Full-width layout chosen, and the to-decide card moved to the bottom, both at
  Andrew's request.
- **10 Sep 2026.** The mocks-only variant was asked for directly: mockups plus the removed items, with
  the rest of the memo to follow once the mocks are satisfactory.
