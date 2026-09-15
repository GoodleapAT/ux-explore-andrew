# Working a review queue

**Scope:** a batch of review comments on a mockup, canvas, memo or prototype, on any surface.

**Surfaces:** all.

---

## How hard to hold each rule

| Marker | Meaning |
|---|---|
| **Always** | Breaking it is a defect. If you must break it, say so before you do, not after |
| **Default** | Do this unless you have a reason. Having a reason is fine; not saying it is not |
| **Prefer** | A leaning. Use judgement and move on |

---

## The rules

### Always

- **Record the comment text verbatim before doing anything with it**, typos included, with what each
  one was pinned to. A paraphrased comment is a copy, and the paraphrase is where the meaning goes.
- **Check every comment against the decision log before acting on it.** A queue takes days to arrive
  and the model moves faster than that. A comment can be overtaken by a decision made the day before
  it was written, and acting on it then draws a model that has been rejected, on the reviewer's own
  instruction.
- **Say when a comment is overtaken, and do not act on it.** Name the decision that overtook it and
  what the comment would have drawn. This is not a disagreement with the reviewer; it is telling them
  something changed under them.
- **Say when a comment reverses a settled decision.** Route it as a ruling, not as a task. A reviewer
  asking for something that contradicts their own earlier decision usually does not know they are.

### Default

- **Sort the queue before answering any of it**, into three piles:

  | Pile | What is in it | Where it goes |
  |---|---|---|
  | **Structural** | It changes what a screen claims | The memo, or the next round of thinking |
  | **Visual and copy** | It changes how a screen looks, not what it says | A build brief for the design surface |
  | **Cannot be acted on** | Ambiguous, truncated, or pinned to something unidentifiable | Back to the reviewer, quoted, with what is missing |

- **Report the shape of the queue**, not just its contents. How many of each pile, and which comments
  are the same argument arriving more than once. A restructure wearing eight comments is one decision,
  and answering it eight times gets eight local fixes and no restructure.
- **Count the queue and correct the count wherever it is recorded.** **And check what the old number
  was counting before you replace it.** A figure recorded against one subset of one round, reused as
  that round's total, produces a new wrong number that looks like a correction. That happened on
  15 September and it took two passes to get right.

### Prefer

- Group comments by the region they are about rather than by the frame they landed on. Where they
  cluster is usually the finding.

---

## Why the structural and visual split matters more than it sounds

**A design memo cannot carry a visual comment.** Its argument column is about claims, so a correction
about stroke weight, button style, text size, alignment, card height or column order has nowhere to
go in one. Put visual comments in a memo and they are quietly dropped, and the reviewer discovers it
by finding the same fault again next round.

**And a build brief cannot carry a structural one.** A brief that says "swap these columns" alongside
"the customer is now the root of every breadcrumb trail" invites the second to be treated as a layout
instruction.

**Half of a queue being visual is normal**, not a sign the review was shallow. It means the structure
is close enough to argue about details, which is the point of drawing it.

## Worked example

Twenty four comments on two files. Nine structural, twelve visual, three unactionable.

**Wrong.** Work through them frame by frame in the order they appear. Eight comments on one column
get eight separate fixes, none of which is the restructure all eight were asking for. The twelve
visual ones go into the memo and vanish. One comment draws a model rejected the day before.

**Right.** Sort first. The eight on one column resolve into one argument about that column's section
model, which is one decision. The twelve visual go into a list for the brief. The overtaken one is
named as overtaken with the decision that did it. The three unactionable go back quoted, and the
memo is drawn against nine comments rather than twenty four.

## Learned from

- **15 Sep 2026.** Twenty four comments arrived on two files. Sorting them by whether they change a
  claim or an appearance found that **half the queue could not go where it was heading**, and that
  eight comments on one screen were one restructure rather than eight fixes.
- **15 Sep 2026.** **The count was got wrong while being corrected**, because the figure being
  replaced turned out to be counting a subset rather than a round. Found by a verification pass, not
  by the person doing the correcting.
- **15 Sep 2026.** One comment was overtaken by a model change made the day before it was written,
  and one asked for something that reverses a decision Andrew made two days earlier. **A queue read
  cold would have acted on both**, correctly by the letter of the instruction and wrongly in fact.
- **14 Sep 2026, carried in.** The earlier round's rule that comment text is quoted and never edited,
  and that the response is a separate column. That held and is restated here as an Always.
