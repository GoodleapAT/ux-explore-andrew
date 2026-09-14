# UI composition

**Scope:** how to lay out a Pros Web screen. Read alongside `mockup-density.md`, which governs what
goes in the cards this file arranges.

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

- **Bundle content into cards, in pairs, under a group heading.** Do not stack full-width blocks down
  one column. A record with eight things to show is four group headings and eight cards, not eight
  rows.
- **A group may contain one card, and it keeps its heading.** Settled 14 Sep 2026. A group heading is
  a semantic grouping, not decoration for a pair, and **a page whose structure changes shape according
  to how many cards happen to be in it is harder to hold.** So a lone card sits under its heading and
  takes the full width.
### Default

- **Two cards abreast is unconditional.** The cards shrink rather than stacking, because side by side
  is the decision. Rows stay legible down to about 330 pixels of card.
- **Pair cards that answer the same kind of question.** What might this customer buy, and what have
  we asked them to buy. What is being sold, and what is being delivered. Notes and history, which are
  one store read two ways.
- **Use a segmented control in the card header to collapse several lists into one card.** Put the
  counts in the segment labels, so the card answers its question before anything is clicked.
- **Detail that does not fit goes sideways into a sheet**, not down into an accordion and not into a
  wider row. A row opens a right-hand drawer.
- **Small peer lists become links in the page header**, not sections. Contacts and properties are two
  near-empty blocks if given sections, and a link if not.
- **Facts about the thing go in a card, not in a subtitle.** A subtitle is where content goes when
  there is nowhere for it. Two columns of label-above-value, no rules between them.
### Prefer

- **Group headings do not get a rule above them.** The cards below carry their own edges, so a rule
  would draw a box around a box.
- **Parked content goes in one full-width list at the bottom**, under a heading that says what it is,
  with each item labelled as not drawn.
- Section order is **a function of the product tier**, not a fixed layout. A payments-only contractor
  sees financials first, because it is the only thing they have.

## Worked example: a customer record

Eight things to show: leads, projects, jobs, service plans, a balance, activity, notes, history.

**Wrong.** Eight full-width blocks down one column. Correct, readable, and four screens tall, so
nobody sees the relationship between any two of them.

**Right.** Four group headings over eight cards in pairs. Sales pairs leads with projects, because
they answer the same kind of question. Operations pairs jobs with service plans. Financials pairs the
balance with the activity that produced it. Record pairs notes with history, which are one store read
two ways. The whole thing fits in the height the four blocks took.

**Then it gets harder.** The leads card needs four status segments and the card is at half width, so
the segmented control is close to clipping. That is the cost of two abreast being unconditional, and
the answer is shorter segment labels rather than stacking the cards, because side by side is the
decision.

## Where the values come from

The card shell, the row rhythm, the segmented control, the stage rail and the sub-status block are all
lifted from Andrew's standalone Pros Web recreations, which took their values from Merlin's compiled
production stylesheet and from Daidipya's Customer Profile. The extracted token stylesheet is at
`reference/merlin-sol-tokens.css` and is listed in the global `SOURCES.md`. **Use it rather than
inventing a palette.**

Badge variant colours are not in the extracted stylesheet, because the design system bundle ships
them minified. They have been inferred from the accent token families. This does not matter while
`mockup-density.md` forbids badges, but it will matter if that rule is ever relaxed.

## Learned from

- **10 Sep 2026.** Andrew shared two standalone Pros Web screens, a customer record and a job view,
  built weeks before the modelling started, and said the memo mockups were laying out UI badly by
  comparison: everything in rows, nothing bundled. Every rule above is read out of those two files.
- **10 Sep 2026.** The full-width-mockup memo layout was chosen specifically so that card pairs have
  the width this composition needs. See `design-memo-format.md`.
- **14 Sep 2026.** CD named the lone-card collision before it bit, on a canvas frame that was a search
  with one thing on it. It bit two screens later. **Memo 8 drew both treatments to compare them and CD
  pointed out they ended up five frames apart**, so no comparison was possible. Settled as a rule
  instead, which is cheaper than drawing a question nobody can look at.
- **13 Sep 2026.** Rigidity markers and a worked example added, because seven standards with no sense
  of how hard to hold any of them had become impossible to follow.
