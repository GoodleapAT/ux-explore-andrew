# CD prompt: the roofing job page, two states

**Paste this into Claude Design alongside the canvas file. 17 September 2026.**

---

## What you are receiving

Two states of one screen: **the roofing job page from scenario S15**, the Thompson job at
1428 Maple Ave. One HTML file with two artboards and nothing else on it.

- **State A, Thursday 6 August.** The job has just been created at the hand-off. Nothing has been
  done to it.
- **State B, Wednesday 12 August.** Work order and materials list are done, materials are booked for
  delivery, permits are approved, the crew and dates are confirmed.

There is a memo that carries the argument for these two screens, the open questions and the jobs to
be done they serve. **It is deliberately not in the canvas file.** A canvas is read as a design, so
annotation on a frame becomes noise on the thing being judged. If you want the reasoning, ask for
the memo; do not reconstruct it from the screens.

---

## What to do with it, and what not to

**These sit beside the job pages already in this project. They do not replace them.**

Andrew has job pages here he is working on. **Do not reconcile the two.** Do not edit his pages to
match these, do not merge them into a single version, and do not describe either as newer or more
correct. Put these two artboards on the canvas as their own pair, leave everything else alone, and
let him decide what he takes from which.

**He will mix and match.** Expect him to pull one group from these and drop it into a page of his
own, or the reverse. So keep each group independently liftable: do not introduce shared state
between groups, do not merge two groups into one card, and do not renumber or rename a group to fit
its new neighbours.

**Do not invent anything to fill a gap.** Every value on these screens is either from the scenario
or is flagged below as ours. If a group looks thin, it is thin on purpose.

---

## The layout rule that holds the pair together

**The groups appear in the same order on every state, and a group that is not needed collapses in
place or disappears from where it was.** Nothing moves up the page to fill the space.

The seven groups, in order, at both states:

1. **Where this job is** — stage rail, the current stage's checklist, a waiting-on line beneath
2. **The work** — scope, property and access
3. **Crew and schedule** — crew, dates
4. **Materials and documents** — material order, documents and photos
5. **Money** — one card, full width, which keeps its group heading
6. **How this job came about** — provenance, notes and assets
7. **The other job** — the siding sibling, one card

Above the groups: breadcrumb, title, a meta line, actions, then three tiles.

**Only one thing collapses between A and B.** The provenance card goes from four rows to a single
line, because after the work is booked it is history rather than the thing you came for. Everything
else fills rather than moves.

**Two cards abreast is the default and the cards shrink rather than stacking.** A group may hold one
card, and it keeps its heading and goes full width. Group headings get no rule above them.

---

## The facts, so nothing gets invented

### The job

| Field | Value |
|---|---|
| Trade | Roofing |
| Price | $38,900 |
| Part of | Roofing and siding, Thompson. Contract $73,100 |
| Area | 2,410 sq ft |
| Layers to remove | 1 |
| Roof age | About 19 years |
| Material | Architectural shingle, underlayment, ridge vent, flashing |
| Condition at assessment | South slope lifted by the storm. Decking sound where visible |

### Customer and property

Sara Thompson, customer since August 2025. 1428 Maple Ave, Sacramento CA 95818. Two storey,
2,140 sq ft, built 1978. Gate code 4417. Dog in the back yard, friendly but loud. Ladder on the
south elevation, dumpster on the north driveway.

### People

Marcus Ellery, production coordinator, is the viewer at both states. Priya Raman, sales consultant,
did the assessment. Renata Silva, CSR, took the storm call. Dwight Okafor leads the roofing crew of
four. Luis Ferrara leads the siding crew of three.

### The dates

| Date | What happened |
|---|---|
| Tue 4 Aug | Storm call. Shingles in the yard |
| Wed 5 Aug | Site visit and assessment. Proposal accepted in the room |
| Thu 6 Aug | Contract signed, $500 deposit by cheque. Two jobs created. **State A** |
| Fri 7 Aug | Scope refined, work order and materials list built, permits filed |
| Tue 11 Aug | Both permits approved |
| Wed 12 Aug | Crew and dates agreed with Sara by phone, both trades in one call. **State B** |
| Fri 14 Aug | Materials delivered |
| Mon 17 to Tue 18 Aug | Roofing installed |
| Wed 19 to Fri 21 Aug | Siding installed. Both complete 21 Aug |

### The money, which the job does not hold

Contract $73,100 for both trades. Collected $500, the deposit, by cheque on 6 August. Outstanding
$72,600, due when both jobs are complete. One invoice, raised at the project. **The money is
identical at both states and is not collapsed.**

---

## Hard rules. Breaking any of these is a defect

- **No per-job cost and no per-job margin.** Revenue occurs at the project and cost at the job, and
  no allocation rule exists. The figure is absent. Not greyed, not labelled unavailable, not
  explained on screen.
- **No reference codes.** No job number, no permit number, no invoice number, no proposal number.
  The job is called Roofing.
- **No roofing line items.** No breakdown of the $38,900 exists anywhere in the scenario. Do not
  produce one.
- **No inspection.** S15 has none. If you have seen a post-sale inspection on a project page here,
  that was invented in an earlier memo and carries an open question.
- **Never total the service plan charges with the project payments.** They are two streams. A
  previous memo added them and produced a meaningless number.
- **No explanatory copy inside a screen.** No information boxes, no footnotes, no captions telling
  the user what a field means. If a message seems necessary, list it outside the screen as a
  suggestion.
- **Colour only where somebody has to act, at most one coloured region per screen.** Neither of these
  two states is amber. The only amber moment in the whole scenario is 21 to 24 August, when $72,600
  is owed and nothing has asked for it.
- **State B has no buttons at all.** Everything is done and nothing is due until Sunday. A button
  here would be inventing work.

---

## Two things on these screens that nobody has agreed

Say so if you build on them.

**1. The stage names come from a configuration that is a sketch.** Ops intake, Orders and
scheduling, Final checks, Installing and Closeout are from Dana's Roofing, a worked pipeline
configuration. Both pipeline documents open with "do not act on this". Two task names are reworded
for the screen: BOM finalised reads Materials list finalised, and scope is moved to the top of the
list.

The stage rail is the only element on this page that a project page could not also carry. **If the
model turns out to be right that a job has six outer states and no stages, the rail comes off and
this page has almost nothing left to say about progress.**

**2. The permit value set has no word for required but not yet applied.** The values run Not
required, Applied, Approved, Final inspection passed. On 6 August the roofing permit is none of
those, so state A shows no permit pill at all. That is a duck, not a decision.

The ratified job states, if you need a status word rather than a stage, are: **Review, Ready, In
progress, Complete, Blocked, Cancelled.** State A reads Review. State B reads Ready. Do not use
"Not started"; it is not in the set.

---

## Things that are ours rather than the scenario's

Flag them if you build on them, and do not treat them as fixed.

- The 2,410 sq ft roof area, the 19 year roof age, the single layer to remove and the material list.
- The crew names and sizes, and the split of the install week into roofing 17 to 18 and siding
  19 to 21.
- Twelve site assessment photos, and every document count.
- The dumpster as a row on the material order.
- Final checks dated Sunday 16 August. The scenario has no day-before beat; that date is derived
  from the install date.
- All five notes.

---

## What the pair is testing

Whether a job page earns its existence beside the project page, or whether it is the project page
with fewer rows.

Three findings worth keeping if you rework these:

- **The waiting-on card is empty on the day the job is created**, because the permit and the
  materials are the coordinator's own work at that point rather than things he is waiting for. It is
  drawn as a single line at both states rather than a card, and the line's content is what tells you
  whether to worry.
- **The money group holds a price and a pointer, not a balance**, because the rule that revenue
  occurs at the project makes a balance meaningless on a job.
- **The week track on state B carries both trades, not just this one**, because the constraint that
  matters on 12 August is two crews at one address in one week.
