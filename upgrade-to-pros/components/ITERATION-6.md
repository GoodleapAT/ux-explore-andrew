# Component records, iteration 6

**17 to 21 September 2026. Four records: one amendment, one new organism, one new molecule, one new
template.**

> **Fields.** Level is the size axis, atom through template. **Layer** is the ownership axis: `core`,
> `recipe` or `snowflake`. **Composes** names the core components a recipe is built from. Both axes
> are recorded, because they are different questions. See `in-depth/three-layers.md`.

---

## MoneyCard, amended

**Level** organism. **Layer** recipe. **Amends the iteration 5 record. Does not supersede it.**

### The action tier's condition changes with the product tier

The iteration 5 record says the action tier holds **at most one button, and only when somebody must
act.** That is right at the selling and operations tiers and it is wrong at payments only.

On the S5 customer record nothing is owed, nothing is overdue and nobody must act. **Taking a payment
is the entire product at that tier**, so the button is there and it is correct.

**So the condition is per tier:**

| Tier | When the action appears |
|---|---|
| **Payments only** | Always. It is the one thing the product does |
| **Selling** | When somebody must act |
| **Operations** | When somebody must act |

**This is an amendment, not a departure.** It was drawn before it was recorded, which is the order the
library is supposed to work in, and the alternative was a screen whose only purpose had no control on
it.

### And the money group on a job holds no card at all

A job does not own money: revenue occurs at the project and cost at the job. So on a job page the
Money group keeps its heading and holds **one sentence naming the price, plus the derived facts from
the project and a link to it.** Not a MoneyCard.

That is the iteration 5 rule about an absent subject doing exactly what it says: *the card is
replaced by a single sentence naming why there is no money yet.* **The subject here is not absent, it
is somewhere else**, which the record did not anticipate and which produces the same treatment.

---

## RefineOverlay

**Level** template. **Layer** **recipe**. **New, 17 September 2026.**

**Composes** Card, Button, Separator, Badge, and a list of rows. No table.

A full screen takeover for turning a signed commercial document into an operational one. **Drawn for
scope refinement and the shape is not specific to scope.**

**Anatomy, top to bottom.**

| Part | What it holds |
|---|---|
| **Bar** | Close control on the left, title and subject beneath it, the commit on the right. **No breadcrumb, and that is the whole of the difference from a page** |
| **Totals strip** | Sticky. The locked figure, the working figure, and a count of how much is done. **The only coloured region, and only when the working figure is out** |
| **Findings strip** | Collapsible. What the person walked in with. **Open on arrival, closed once they are working** |
| **Lines** | One expandable block per line of the locked document, each showing its locked amount beside its working amount and a variance when they differ |
| **Roll-up** | On the committed state only. What the refinement produced |

**States** **opened**, where the working copy is a copy of the locked one so every line already
balances; **refining**, where some lines are expanded and the total may be temporarily out;
**committed**, read only, with Amend where the commit was.

**The rule that makes it work: the working copy opens as a copy, not as blank.** So the total is never
unexplained, and refinement adds specificity underneath figures that are already correct.

**Use it** where a locked total has to gain detail without moving. Scope refinement is the first case.

**Do not use it** for anything without a commit, or anything whose total is free to change. **Both
would make it a page.**

**When its subject is absent** it does not open. The route into it is a task row on the record, and
that row is what reports whether there is anything to refine.

**What it absorbs** any number of lines, a locked document with no detail at all, and per-line
variance in both directions. **A new component instead** if the locked side can also be edited,
because that is two documents and this is one with a shadow.

### The two rules it has to hold

**The total is owned by the contract, not by the table.** Lines may split, re-categorise and trade
money between themselves. The sum may not move without a change order.

**Per-line variance is normal and is not an error.** Sold lines are allowances, refined lines are
quantities, and they rarely match. **So the surface reports variance in plain text and warns only at
the total**, which is also why the colour lives in the strip and not on the row.

---

## WaitingOnLine

**Level** molecule. **Layer** **recipe**. **New, 17 September 2026. Supersedes the SubStatusRow
recommendation in iteration 4.**

**Composes** a row and a link. Not a card.

One line naming what a record is waiting on and nothing else. **It replaces the card form whenever
the blocking count is zero or one**, which iteration 4 recommended and this exercises.

**States** **nothing**, where the line says so in three words; **one thing**, where the line names it
and its date; **several**, where the card form returns and the line does not apply.

**Why it is a line.** On S15 the card form was given four rows and all four were settled, so it read
as four pieces of good news on a page where nothing was waiting. **A full card with nothing blocking
says nothing.** And on a job at the hand-off it is empty, because the permit and the materials are the
coordinator's own work at that point rather than things he waits for.

**The test for what goes in it:** if the contractor can move it themselves it is a task or a stage.
If they can only wait, it belongs here. **A task held on a parent record that this record cannot
perform also belongs here**, which is how the post-sale inspection surfaces on a job without being
counted twice across two siblings.

**Do not use it** for anything anybody on the crew can accelerate.

---

## DiscoverRow

**Level** organism. **Layer** **recipe**. **New, 21 September 2026.**

**Composes** Card, three across, each with a heading, a sentence and a link.

What the product does that this contractor is not using. **Three columns, not three rows**, and the
distinction is the component: rows read as a checklist of things the person has failed to do, columns
read as a set of offers.

**Use it** at the foot of a record at a tier below the top one. **It is the only thing on a working
screen that serves the seller rather than the person using it**, so it goes last, under a heading that
says what it is.

**Do not use it** above the working content, and **do not use it at the operations tier**, where there
is nothing left to advertise.

**When its subject is absent**, meaning the contractor already has everything, the whole group goes.

**No footer line and no plan name.** The heading carries the pitch and each card carries its own link,
so the component never has to know what the tiers are called.

**What it absorbs** two capabilities rather than three, by keeping three columns and leaving one
empty rather than reflowing. **A new component instead** if a capability needs a price beside it,
because that is a pricing table.

---

## Learned from

- **17 Sep 2026.** RefineOverlay was drawn as a sub-page first and Andrew corrected it to an overlay.
  **The correction was right against our own standard**, which already says detail goes sideways
  rather than into a new page, and the sub-page had departed from it without declaring so. The
  standard now carries the takeover as its second declared exception.
- **17 Sep 2026.** WaitingOnLine is the first component in the library **recommended by a previous
  iteration and then exercised rather than specified.** Iteration 4 predicted the card would fail
  because it had too few rows; the actual failure was that a full card with nothing blocking says
  nothing, which is a different fault and a different fix.
- **21 Sep 2026.** DiscoverRow changed from rows to columns **on Andrew's instruction, and the reason
  is worth keeping**: the same content in a vertical list reads as a list of failures. The layout is
  carrying the tone.
- **21 Sep 2026.** The MoneyCard amendment came from the thinnest screen in the set rather than the
  richest. **A tier where the product does one thing is what exposed a condition written as though
  every tier had many.**
