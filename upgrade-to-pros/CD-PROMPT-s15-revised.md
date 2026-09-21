# CD prompt: S15 revised, and the scope refinement

**17 September 2026. Read this, then read the data pack.**

---

## What you are being given

Two files, and this one is the shorter.

- **`S15-DATA.md`** is the only source of mock data for S15. **Do not invent a value that is not in
  it.** If something is missing, say so and it gets added there, so the next screen uses the same one.
- **`S15-ROOFING-SCOPE-AND-ITEMIZATION.md`** carries the roofing scope of work text and the
  itemization, in both versions, as sold and as refined. Every figure in it is invented and flagged as
  such. **Use it rather than making a second breakdown.**

Optionally, two more:

- **`CD-CANVAS-job-and-refine-surface.html`** is five artboards with no annotation: the job page at
  two moments and the refine overlay at three.
- **`memo-13-refine-the-scope.html`** carries the argument and the open questions behind those five.
  **Do not put memo prose on a canvas.** A canvas is read as a design, so annotation on a frame is
  noise on the thing being judged.

---

## What changed on 17 September, and what did not

**Three beats go in and one moves.** They are lettered rather than renumbered, because four memos and
the team's Confluence script cite beats by number.

| Beat | When | What |
|---|---|---|
| **10a** | Booked Thu 6 Aug, carried out **Fri 7 Aug, 8:05 to 9:40am** | **The post-sale inspection.** One visit, both trades |
| **11** | **Fri 7 Aug**, from about 11:20 | **The scope refinement**, rewritten. Same date |
| **17a** | **Mon 17 Aug** | Day-before checks on the roofing job |
| **18** | Roofing **Tue 18 to Wed 19**, siding **Thu 20 to Fri 21** | Moved, so Final checks can take the Monday |
| **18a** | **Wed 19 Aug** | Day-before checks on the siding job |

**Nothing downstream moves.** Both jobs still complete Friday 21 August, the invoice is still Monday
24 August, payment is still Wednesday 26 August.

**Two consequences to hold on to.** Siding is now **two days, not three**, which is tight and is
deliberate. And **beat 18's canonical screen day moves from Tuesday 18 to Wednesday 19 August**, which
is still the only day where one job is complete and the other is merely scheduled.

**Two files are now stale on dates.** `memo-11-project-two-moments.html` dates the post-sale
inspection 10 August, three days after the refinement it is supposed to produce, and its install week
is the old one. `memo-12-job-two-moments.html` has the old install week. **Do not copy dates out of
either.**

---

## The refinement, which is the new thinking

### The rule

**The signed itemization is frozen at signature and the job gets a working copy.** The only thing that
changes the signed one is a change order amending the proposal and the contract.

**The total is owned by the contract, not by the table.** Marcus can split lines, re-categorise them
and move money between them. He cannot change the sum.

**Per-line variance is normal and is not an error.** Sold lines are round numbers built from
allowances; refined lines are real quantities. They rarely match. What is held is the total, so the
surface should show per-line variance without alarm and warn only when the sum moves.

### What happens on 7 August

1. **8:05 to 9:40am, the inspection.** Marcus finds staining in the attic over the south slope,
   measures the main ridge at 48 feet, confirms one layer at the eave, confirms the dumpster fits the
   north driveway. Six photographs.
2. **From 11:20, he refines.** Six signed lines become twenty two. The attic staining raises the
   decking allowance from 12 sheets to 16, which is **$260 over**. He finds it back by cutting site
   protection from three days to two, because a third cleanup day on a two day install was a sales
   estimate rather than a plan. **The total stays at $38,900.**
3. **He commits.** The materials list falls out of the refined itemization and the materials are
   ordered. The permit can now be filed, because you cannot describe this work to a jurisdiction from
   six lines.

### What the refinement produces

**The materials list and the work order are not documents Marcus authors.** They are two views of the
refined itemization, which is why beat 11 does all of it in one sitting.

- **Materials list** is the Materials category with quantities. In future it feeds distribution
  ordering directly, so the material order comes from it.
- **Work order** is the Services category plus the scope text and the access notes, **with prices
  stripped.** A crew lead does not need the sell price and should not see it.

**The work order is issued at crew assignment, beat 16, not at beat 11.** For an internal crew it is a
view of the job page. For a subcontractor it would have to be a record, because it carries its own
labour price and its own visibility boundary, and that case is not drawn.

**The category tag on every refined row is the sort key**, not decoration. Materials, Equipment,
Services are what let one table produce two documents, which is why the category is chosen per line
rather than per section.

---

## How the surface works

**A full screen takeover, not a page and not a drawer.** No breadcrumb, a close control on the left, a
title reading *Refine the scope* with the job and address beneath it, the commit on the right.
It opens from the job and closes back to it, so the job page stays the only address this work has.

**This is a declared departure** from the rule that detail goes sideways into a sheet. A drawer cannot
hold a name, two figures and four columns at a readable width.

**A sticky totals strip** under the bar carries signed, working and the refined count. It is the only
thing that stays put while twenty two rows scroll past, so it is also where the amber goes when the
working total is over. **The line's own variance stays in plain text**, because colouring both would
be the same fact alarming twice.

**The inspection findings are a collapsible strip at the top.** Open on arrival, because he has just
walked in with them. Closed on every later screen once he is working.

**He starts from a copy of the contract, not from blank.** The working total already reads $38,900 and
every line already balances, so the surface can never show an unexplained total. Refinement adds
specificity underneath figures that are already correct.

**Committing closes the overlay.** The job page's scope card takes over, reading *22 lines, $38,900*.
Reopening gives the same overlay read only, with Amend where the commit was. One surface to edit and
read, one summary on the job, no third address.

---

## How refinement is reached from the job page

Three routes, and only one is the start.

1. **The first checklist row**, *Scope validated and refined*, in the Ops intake panel, with a chevron.
   This is the canonical entry. **The chevron is the point: the row opens the work rather than
   recording that it happened.**
2. **The primary action.** On 6 August it reads **Book the inspection**, not Refine the scope, because
   nothing can be refined until the visit has happened. **The primary action tracks what is actually
   possible.**
3. **The scope card link**, *See the itemization*, which opens the same overlay read only. A read
   route, not a start.

**A job shows a dependency it does not own as a wait, not as a task.** The post-sale inspection stays a
single task held at the project, because one visit covers both trades. From the roofing job's side it
is a thing the job can only wait for, so it appears in the waiting-on line: *Post-sale inspection, not
booked*. This keeps each job's checklist count honest at three rather than duplicating the row on both.

**One state is not drawn and you may need it:** the job page on the morning of 7 August, after the
inspection and before the refinement, where the primary flips to Refine the scope and the waiting-on
line empties.

---

## Hard rules. Breaking any of these is a defect

- **No per-job cost and no per-job margin.** Revenue occurs at the project, cost at the job, and no
  allocation rule exists. The figure is absent. Not greyed, not labelled unavailable, not explained.
- **No reference codes.** No job, permit, invoice or proposal numbers. The job is called Roofing.
- **Never total the $29 service plan charges with project payments.** Two streams, never summed.
- **No explanatory copy inside a screen.** If a message seems necessary, list it outside the screen as
  a suggestion.
- **Colour only where somebody has to act, at most one coloured region per screen.** The only amber in
  the whole scenario is 21 to 24 August, when $72,600 is owed and nothing has asked for it. The one
  exception in this set is the totals strip while the working total is over.
- **The groups appear in the same order on every state**, and a group that is not needed collapses in
  place or disappears from where it was. Nothing moves up the page.
- **Two cards abreast is the default**, the cards shrink rather than stacking, and a lone card keeps
  its group heading and goes full width.

---

## Two things on these screens that nobody has agreed

**The stage names come from a configuration that is a sketch.** Ops intake, Orders and scheduling,
Final checks, Installing and Closeout are from Dana's Roofing. Both pipeline documents open with "do
not act on this". Two task names are reworded for the screen: BOM finalised reads Materials list
finalised, and scope is moved to the top of the list.

The stage rail is the only element on the job page that a project page could not also carry. **If the
model is right that a job has six outer states and no stages, the rail comes off and the page has
almost nothing left to say about progress.**

**The permit value set has no word for required but not yet applied.** The values run Not required,
Applied, Approved, Final inspection passed. On 6 August the roofing permit is none of those, so the
screen shows no permit pill at all. That is a duck, not a decision.

The ratified job states, if you need a status word rather than a stage: **Review, Ready, In progress,
Complete, Blocked, Cancelled.** Do not use "Not started"; it is not in the set.
