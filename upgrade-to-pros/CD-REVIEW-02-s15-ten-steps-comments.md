# Andrew's review comments on the ten-step S15 file, verbatim

**Collected 15 September 2026.** Comment text is reproduced exactly as written, including typos. The
element line says what each comment was pinned to. **No comment has been acted on**. This file is
the record, not a response.

Scope: the twelve open comments on `S15 ten steps/S15 cash, ten steps.html`. This is the *next*
round on that file. The nineteen comments from 11 September and eleven more from 14 September were
already answered in it, and that account is in `S15 ten steps/README-iteration-4.md` and the file's
own "What the review changed" section.

The file is a grid: each **column is a step** in the run, each **row a surface** (customer record,
project workspace, siding job). Comments cite the step through the `data-screen-label` on the page,
e.g. `Customer record · step 1`.

---

## Customer record, step 1

Eight of the twelve comments land here. It is the column carrying the most weight.

**On the aside text in a card header.**

> Remove

**On the same card header aside, pinned a second time.**

> Remove

*Two comments on the same element, same instruction.*

**On a row inside the card rows list.**

> This message/text is way too large

**On the `sr-more` footer, "1 closed project, 1 job / See previous work".**

> I don't know what the three lines on the left are for. Left align '1 closed project, 1 job' and put
> 'See previous work' as a link next to that

**On the two-card pair holding Leads and the roofing lead list.**

> Make these two cards the same height

**On the "Property and equipment" card.**

> I would put this to the left of 'Latest activity'

**On the "Service plans" card.**

> I would put this in 'Operations'

**On the "Active projects" pair.**

> This section should show a placeholder when there are no active projects/jobs. Also, jobs should
> always be nested under projects. And it should be indicated if there were previous projects/jobs,
> and a way to see more information on them.

## Customer record, step 3

**On the "Latest activity" block.**

> I only want this showing the latest 1 or 2 activity items. Use a fade to idnicate there is more on
> scroll, rather than increasing the vertical size of this container.

## Customer record, step 5

**On the Leads card, the one showing the leads being pursued.**

> Instead of showing the leads being pursued here, just nest them under the project on the right.
> They can be still be found under 'All' or add another segment to the control called 'Pursuing'

**On a row in the same card's lead list.**

> Remove

## Customer record, a later step

**On a row in the lead list.**

> I don't know where this came from. Remove it.

*The step label was truncated in the comment record and reads `Customer record · step …`. The pinned
element is the fourth row of a `pw-crowlist` inside the second card of a pair. It needs checking
against the file before it is acted on.*

---

## The shape of it

Three of the twelve are bare "Remove" instructions on single elements, and one of those is a
duplicate. The substantive ones are all one argument: **the customer record's step 1 column carries
too much, and the object hierarchy on it is wrong.** Jobs nested under projects, leads nested under
the project that pursues them, service plans moved out to Operations, activity truncated with a
fade rather than grown. Taken together they are a restructure of that column's section model, not
eight separate fixes, and the leads-under-project point recurs at step 5, which is the same
argument arriving twice.
