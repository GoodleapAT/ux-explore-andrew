> **Moved into the repository on 13 Sep 2026**, from the Claude Design project, per the component
> library standard: the library is repository-resident and CD is where components are designed rather
> than where they are kept. Written by CD at the moment each component was created.
>
> **Fourteen components and templates.** Two things postdate them and are not reflected below:
> badges are no longer banned, so any record saying a state cannot use one should be reread against
> the density standard; and templates now declare behaviour per lifecycle stage as well as per
> product tier, which none of these do yet.

# Component records, Iteration 2

Written at the moment each component was created or adapted, per the component library standard.
Reads without the canvas: no screenshots, no class names you need to see rendered to understand.

Levels use atomic design: **atom**, **molecule**, **organism**, **template**.

Each record carries the six required fields, then a position for each of the three product tiers
wherever the component's subject may not exist. The three tiers are payments only; payments and
selling; payments, selling and operations. Tier is set per organisation.

Source of each: **new** means invented here. **Adapted** names what it came from.

---

## PeerRow

**Level** molecule. **Adapted** from the Iteration 1 prototypes.

A row in a list of sibling things. Name and detail on the left, value on the first line of the
right column, status on the second line of it in secondary text.

**States** default; dimmed, for a thing that is closed or historical and should recede; attention,
where the status line takes the warning colour and a warning glyph. No value, and no status, are
both legal and render as absence rather than a dash.

**Use it** for any list of associated peers: leads, projects, jobs, service plans, invoices,
payment parts, material orders. It is the workhorse of every card in this grid.

**Do not use it** for label and value pairs describing one thing. That is FactGrid. Do not use it
where a row needs more than one value, because a second value competes with the status line and
the row stops being scannable.

**When its subject is absent** the row does not render. An empty list is the card's problem, not
the row's.

**Tiers** payments only: used for invoices, payment parts and transactions, which all exist there.
Selling: adds leads and proposals. Operations: adds jobs and service plans. The row itself does
not change by tier; only which lists exist do.

---

## SelectableLeadRow

**Level** molecule. **New**, built for treatment A of the pursuit moment.

PeerRow with the design system's checkbox in a leading 24px column. Selecting several and acting
on them together is how a project comes into being in treatment A.

**States** unchecked; checked; and the same dimmed and attention states PeerRow has. There is
deliberately no indeterminate state, because a lead is not a parent of anything selectable.

**Use it** when the action is on several rows at once and the rows are of one kind.

**Do not use it** as the default lead row. A permanent checkbox column on a list nobody
multi-selects costs 38px of name width on every row for an affordance almost nobody uses. It
should appear when selection starts, which means a card-level selection mode rather than a row
variant. That is the anti-rule and the one thing about treatment A I would want to fix before
building it.

**When its subject is absent** same as PeerRow: it does not render.

**Tiers** payments only: absent, there are no leads. Selling and operations: present.

---

## SelectionBar

**Level** molecule. **New**, treatment A.

The foot of a card in selection mode. Counts what is selected, says something true about the
selection that is not just the count, and carries the actions.

**States** one selected; several selected; and a blocked state for a selection the action cannot
be performed on, which this scenario never produces but two properties would.

**Use it** at the foot of the card whose rows are selected, never as a floating page-level bar.
The scope of a selection should be visually inside the thing that holds it.

**Do not use it** for a single-row action. That belongs on the row or in its overflow menu.

**When its subject is absent** nothing is selected, so the bar is not there. It appears with the
first selection.

**Tiers** follows SelectableLeadRow: absent at payments only.

---

## AbsentCapabilityPanel

**Level** molecule. **New**, and the most load-bearing new thing here.

A dashed panel standing where a capability will be, naming what arrives and what has to happen
first. Used for a project's operations half before anything is sold.

**States** not yet, where the capability will exist once something happens in this journey; not
bought, where the capability belongs to a tier the organisation does not have and the panel
advertises it; and absent, where it renders nothing at all.

**Use it** where a capability that certainly will exist has no content yet, and where an empty
region would otherwise read as a broken page. Also where an adjacent tier's capability is worth
advertising, which is how a payments-only contractor discovers selling exists.

**Do not use it** for a gap the model has no answer for. Per-job margin has no panel, no row and
no dash, because naming a gap on screen invites somebody to fill it badly. The boundary is: a
capability advertises, a gap is left out.

**When its subject is absent** that is the whole component.

**Tiers** payments only: not bought, advertising selling and operations. Selling: not bought for
operations, not yet for anything unsold. Operations: not yet only.

**Note** this component exists because two binding standards disagree. Mockup density says leave
a gap out rather than draw it as unavailable. The component library standard says declare a
position and allows empty and self-advertising. The boundary above is a proposal, not a ruling.

---

## Lineage

**Level** organism. **Adapted** from the Iteration 1 prototypes, where it had three variants.

A diagram of how a project was assembled: leads on the left, the container around what it holds,
jobs on the right. Connectors are orthogonal, per the diagram standard.

**States** pursuit, several leads feeding a container that holds nothing else yet; sold, leads
into committed scope components into jobs, with declined leads producing nothing; and siblings,
two jobs under one project with one marked as the one you are looking at.

**Use it** where the question on the page is how these things relate, which in practice means a
project before it has any content of its own, and a job that needs to know it has a sibling.

**Do not use it** on a page whose job is the day's work. It is provenance you consult, not
content, so from the moment a project has jobs and money it should be collapsed by default. And
do not use it where a list already says the same thing: a customer record that lists leads and
projects as peers does not also need a picture of the relationship.

**When its subject is absent** a project with one lead and one job renders the diagram as a
straight line, which is worse than nothing. Below two leads or two jobs, do not render it.

**Tiers** payments only: absent. Selling: pursuit and sold states only. Operations: all three.

---

## MoneyCard

**Level** organism. **Adapted** from memo 6's running balance, restructured to be swappable.

The project's money. One receivable with parts, a total owed, what has been collected and what
remains.

**States** no tender chosen, where a contract exists and no invoice does; cash, three parts the
customer pays; financed, three draws a lender releases against each job's work evidence; and
closed. The cash and financed states share one row shape and differ only in each row's label and
trigger.

**Use it** at the project and only at the project. A job may show these figures read-only, and
must say where they are held.

**Do not use it** for a service plan, which has no closing balance at all. And do not let any
tender fact live outside it: memo 6 puts the tender and the monthly payment in the project's
overview fact sheet next to the build year, which couples the money to the facts and means
changing tender means editing two cards.

**When its subject is absent** before a contract there is no money at the project, so the card
is not there and the overview pairs with the property instead.

**Tiers** payments only: this card is the page. Selling: present from contract. Operations:
unchanged, plus per-job costs elsewhere.

---

## StageRail

**Level** organism. **Adapted** from the Iteration 1 prototypes.

The contractor's configured stages down the page, grouped under board headers, with the current
stage marked and a gate line in the card's footer.

**States** stage done; current; ahead. The rail is clipped with its own scroll when there are
more stages than fit, and the current stage is positioned third so two are behind and two ahead.

**Use it** on a job, because those are the contractor's own configured stages. The board name is
a group header said once, not a subtitle repeated on every row.

**Do not use it** on a project. That was drawn once and removed: a project's status is derived
from its proposal and its jobs, so a rail there is a diagram of the model rather than something
anyone needs on a Tuesday. Do not reach for the design system's stepper either, which is a
multi-step wizard with a progress bar and sliding panels and has nothing to do with pipeline
position.

**When its subject is absent** an organisation with no configured stages gets no rail, and the
job's position falls back to the status word in the meta line.

**Tiers** payments only and selling: absent, there are no jobs. Operations: present.

---

## TaskRow

**Level** molecule. **Adapted** from the Iteration 1 prototypes.

One task in a stage checklist.

**States** five. Complete, a filled box with the real check glyph and the label receded.
Incomplete, an empty box. Blocked, a warning box and warning label, and the only state allowed
colour because it is the only one that is somebody's problem right now. Not applicable, a dashed
box and italic label, set by the system. Skipped, a full-contrast label with a strike through it
and a person-set reason, because a pattern of skipping is a signal and has to stay countable.

**Use it** inside a stage's checklist card.

**Do not use it** as a to-do list at the project or the customer. A task belongs to a stage of a
job, and lifting it out of that context loses the thing that makes it meaningful.

**When its subject is absent** a stage with no configured tasks renders no checklist card, and the
stage's progress count disappears with it rather than reading zero of zero.

**Tiers** payments only and selling: absent. Operations: present.

**Note** four devices carry five readings, and the design system's checkbox offers three. This is
the sharpest place the density rules and the state count are in tension, and it is worth settling
the mapping before another job screen is drawn.

---

## SubStatusRow

**Level** molecule. **Adapted** from the Iteration 1 prototypes.

A label and value pair for one external process nobody on the crew can accelerate.

**States** three registers. Working toward, where the value takes the warning colour. Satisfied,
plain ink at medium weight, deliberately not green because the only green in the system fails
contrast as small text. Not applicable, italic and secondary.

**Use it** in a card called Waiting on, on a job, beside the stage rail. The rail says where the
job is; this says what nobody here can speed up, and holding those two apart is the whole point.

**Do not use it** for anything the team controls, which is a task. And do not colour a working row
when the same fact is already coloured elsewhere on the page.

**When its subject is absent** and this is the common case, the card nearly empties. In this
scenario there is no permit, no financing and no home owners association at this address, so the
card has one row at step 8. A card that exists to prove a distinction, with one row in it, may not
earn its place. Below two rows, consider folding them into the stage card.

**Tiers** payments only and selling: absent. Operations: present.

---

## SheetShell and DialogShell

**Level** organism. **Local ports** of the design system's Sheet and Dialog.

**States** as the originals: open and closed, four sides for the sheet, with or without a close
button.

**Use them** exactly as the design system's own, and prefer the real components anywhere a page
is rendered at full size. A row opens a sheet; a decision that needs confirming opens a dialog.

**Do not use these local ports in production.** They exist for one reason: the real components
portal to the document body and position fixed, so inside a mock scaled into a grid cell they
cover the browser window rather than the page they belong to. Every value is lifted from the
originals, and the only difference is that these are positioned within their page.

**When their subject is absent** not applicable.

**Tiers** unchanged across all three.

---

## Field

**Level** molecule. **New**, for treatment C's dialog.

A label, the design system's input, and an optional hint under it.

**States** default; with hint; and the input's own states, which include a clear button and icon
slots. No error state is drawn here because nothing in this scenario validates.

**Use it** in a dialog or sheet where something has to be typed or confirmed.

**Do not use it** to display a value nobody edits. That is a fact in a FactGrid, and an input
around a read-only value invites somebody to try.

**When its subject is absent** not applicable.

**Tiers** unchanged.

---

## Template: customer record

**Level** template.

A person above an address. Latest notes, then group headings with two cards abreast under each:
Sales holds leads and projects, Operations holds jobs and service plans, Financials holds the
across-all-projects balance and the activity stream, Record holds notes and history. Parked
content is one full-width list at the bottom labelled not drawn.

**States** by what the customer has, not by tier alone. A customer with no project still has all
four group headings, because the prior project and the maintenance plan fill three of them.

**Use it** as the person anchor. Every associated thing appears as a peer row and nothing indents
under anything.

**Do not use it** to show a proposal, a contract or a change order. Those live inside a project,
and putting them here would undo the containment the model rests on.

**When its subject is absent** a brand new customer with one lead and nothing else is the thinnest
case, and the Financials and Operations groups then have nothing at all. Untested here.

**Tiers** payments only: Sales and Operations absent or advertising, Financials leads and is most
of the page. Selling: Sales present, Operations advertising. Operations: all four.

---

## Template: project workspace

**Level** template.

The container. Overview fact sheet paired with money, the lineage while it is still the point,
then Selling with leads and proposals, then Work with jobs, then Record.

**States** pursuing, before anything is priced, where the Work half advertises and there is no
money card; sold, where money appears with no tender chosen; in progress; closed.

**Use it** for anything that is one customer's one journey at one address.

**Do not use it** for a service plan. A plan outlives every journey beneath it and has no closing
balance, and the absence of a balance is how that page says it is not a project.

**When its subject is absent** the pursuing state is the answer, and it is thin on purpose. It has
four things: a name, three leads, a property carried from the customer, and a diagram of how it
came together.

**Tiers** payments only: absent, there is no project. Selling: present without the Work group.
Operations: full.

---

## Template: job

**Level** template.

One committed scope component being executed. Stage rail paired with a job overview, then the
current stage as a row of three cards, then the sibling, the money it does not own, and what it is
waiting on.

**States** by stage. The rail and the current-stage group change together; everything else is
stable.

**Use it** for the execution of one scope component, with its own crew, schedule, materials and
checklists.

**Do not use it** as the place money is owned. A job never owns an invoice, so the money card here
is read-only and says where it is held.

**When its subject is absent** a job does not exist before the hand-off, and nothing stands in for
it. That is the seven empty cells in the third row of this grid.

**Tiers** payments only and selling: absent. Operations: present.
