# UI composition

**Scope:** how to lay out a Pros Web screen. Read alongside `mockup-density.md`, which governs what
goes in the cards this file arranges.

**Surfaces:** all.

---

## The rules

- **Bundle content into cards, in pairs, under a group heading.** Do not stack full-width blocks down
  one column. A record with eight things to show is four group headings and eight cards, not eight
  rows.
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
- **Group headings do not get a rule above them.** The cards below carry their own edges, so a rule
  would draw a box around a box.
- **Parked content goes in one full-width list at the bottom**, under a heading that says what it is,
  with each item labelled as not drawn.
- Section order is **a function of the product tier**, not a fixed layout. A payments-only contractor
  sees financials first, because it is the only thing they have.

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
