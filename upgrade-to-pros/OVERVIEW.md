# Upgrade to Pros

**Project overview. Read this before doing anything in this folder.**

> **Who may write to this file:** any surface that can write. Edit in place. Keep the state of play
> current; that is most of what this file is for.

Taking GoodLeap's contractor tooling from payments only into selling and operations. Pros Web needs
entities Merlin does not have: something to represent work that might be sold, and something to hold
work sold together.

The root of this repository carries how the work is done. This file carries what the work is.

---

## State of play, 14 September 2026, end of day

**The team's positions are not restated here.** They are in `TEAM-POSITIONS.md`, each with a date and
a source, and that is the only place they are stated. This changed today because the mint point moved
twice in an afternoon and each move meant rewriting the same fact into seven documents.

**Where things stand.**

**The demand chain is now Inquiry or Prospect, then Lead, then Project.** Qualification is the
boundary between the first and the second, and **creating a lead creates a project**. See T-2 and T-3.
The separate Qualified Lead entity of the earlier revision is gone: the lead is itself the qualified
thing.

**That resolved close to our original position**, because qualification is the pursuit moment under
another name, and the chain now marks the end of validation explicitly, which is the exact thing we
said their model failed to mark. **The mint point held five positions in one day.**

**A lead is an engagement** carrying several interests. See T-1. That went against us and it stands.
The reason is a UX one, recorded as job J-11, and the worked example is restated on it.

**Two questions are open against the positions**, both in that file: whether Inquiry and Prospect are
one object, since one is an event and the other a party, and where several trades live. **And one need
falls out of it**: demand arriving later cannot join a sale in progress, which is N-004, with project
merging as M-007.

**Three things in v4 are new and adopted**: the satellite record distinction, which generalises
Andrew's own ruling about forms and photos on the job; uniform job outer states with trade-specific
sub-states; and checkpoints as per-org policy rather than structure. See T-4, T-5 and T-6.

**One live disagreement remains**, T-9, where a service agreement sits. Ours runs service as a project
type. Deferred by Andrew rather than settled.

**The comparison still stands on everything else**, including the decision that our model adopts
theirs wherever ours was the coarser one.

**What the UX work has to answer**, and it is a better question than it was this morning: the project
now exists during selling again, so the question is not whether the container is needed before a win.
It is **what the engagement holds and what the project holds, when both exist through the same
period**. Three interests, one of them deferred, a project minted at qualification, and a proposal
that may cover two of the three.

---

## Earlier on 14 September: the comparison. Kept as history

**Our model has stopped being a separate model.** The comparison was ruled on 14 September and
twenty two of its thirty seven rows are adoption: wherever ours was the coarser model, DRAFT v3's
entities are taken. What remains of ours as a distinct position is **three disagreements and six open
questions**, listed at the foot of `MODEL-COMPARISON.md` along with the entities our model gains.

**The three disagreements.** When the project mints, the row that travels with it, and where a service
agreement sits. **The last is a preference rather than a ruling**, and Andrew's leaning is service as
a project type with visits as jobs.

**Anything that describes ours as a rival model is now out of date**, including the section below and
the Claude Design context document. **And the three disagreements named above are down to one**, T-9,
because the mint point resolved. Do not read the count from this section.

---

## Earlier state of play, kept because it is cited

**The model has converged.** A team model called DRAFT v3 and Andrew's Model C arrived at the same
shape from different directions: a container called **Project** is the spine, and **Job** is the work
entity beneath it, meaning the execution of one committed scope component. That resolves the collision
John Gaquin spotted, where Job was being used for two different things.

> **This section is history, kept because its reasoning is cited. Its four bullets are all overtaken.**
> Minted-or-declared is answered by T-2. Per-property-or-per-customer is answered by T-8. Do not
> design from this section.

**What is settled and what is not** is in `DECISIONS.md` beside this file. The nouns are in
`VOCABULARY.md`. Four questions were outstanding going into the comparison, and three now have
answers:

- **Money at the container.** Effectively agreed. DRAFT v3 attaches the invoice, the tender plan and
  the milestones at project level and reads margin there. The remaining difference is storage against
  derivation, not level.
- **Minted or declared.** The live disagreement. DRAFT v3 mints the project at the first proposal.
  Andrew's position, now recorded as a decision, is that it mints when someone starts pursuing a lead
  with the intention of writing a proposal, so it exists before anything is priced. The gap is one
  beat wide in the scenario and the correction is small.
- **Per property or per customer.** Both. Every entity is anchored to a customer and a property, so a
  project is one customer at one address. A house sale is handled by an attribute on the property.
- **Declined but still wanted.** Answered by DRAFT v3, but split across two places: the option stays
  on the proposal with its price, and the interest stays open on the lead. Andrew's lead carries it as
  one object with a status, a reason and a revive condition.

**Services and memberships are the open frontier.** A service agreement in DRAFT v3 sits on the
customer and the property rather than inside a project, and outlives every journey beneath it. Money
is a subscription with no closing balance, and the team's own scenario flags that a subscription
invoice has no valid parent. Service now runs as its own project type with one job per visit, but
almost nothing beyond that is settled.

**The UI work has started.** Five views exist as mocks: customer record, project workspace, proposal,
job and service plan. **Memo 7 adds fourteen more against S14**, ten drawn and four placeholdered.

---

## Threads

| Thread | Folder | Status |
|---|---|---|
| **Entity and object modelling** | `entity-modeling/` | Live. Has its own detailed handoff, `OVERVIEW.md`, which carries the model, the open questions and a file index |
| **Earlier model work** | `earlier/` | Superseded. The A against B comparison, the customer model proposal, the open decisions list and the convergence one-pager. Kept because the reasoning is still cited |
| **Claude Design handoff** | `design-handoff/` | History. The August prompt and the two memos that produced the standalone Pros Web screens. Superseded on structure |
| **Claude Design context** | `CLAUDE-DESIGN-CONTEXT.md` | **Current, version 3.0 of 14 Sep.** Rewritten after version 2.0 was wrong in three places. Opens with what changed since CD was last briefed |
| **Claude Design briefs** | `CD-PROMPT-s14-canvas.md` | Round one build brief: fourteen frames, two placeholders, the proposal excluded |
| **S14 round two** | `memo-8-s14-round-two.html` | **Current.** Six screens reworked from Andrew's review. Memo 7 is round one and is superseded in part |
| **Review responses** | `CD-REVIEW-01-responses.md` | Twenty five comments, verbatim, with routing. Four needed rulings; two have landed |
| **Origin financing page migration** | not started | Parked. Two of the pages were located, the third repository never was. See global sources |

## Registers beside this file

| File | What it holds |
|---|---|
| `WORKED-EXAMPLE.md` | The complete Thompson mock data, S15. Use it, invent nothing |
| `WORKED-EXAMPLE-S14.md` | **The Brenner mock data, S14.** A different org, a single trade and a first-time customer, so none of the Thompson data survives. Four flagged inconsistencies in the source script |
| `MODEL-SNAPSHOT.md` | What our model contains, on a date, and the diff against DRAFT v3 |
| `TEAM-POSITIONS.md` | **What the team currently holds, once, with dates.** The only place a team position is stated. Everything else points here |
| `MODEL-COMPARISON.md` | Every difference between our model and DRAFT v3, thirty seven of them, all ruled on 14 Sep. Stale in places, and it says where |
| `DRIFT-CHECK.md` | Everything we depend on that somebody else can change, and when we last looked |
| `DEVIATIONS.md` | Where a mock departs from the scenario it was built against |
| `OBJECT-REGISTER.md` | Things a screen needed that neither model has |
| `JOBS-TO-BE-DONE.md` | What people are trying to accomplish, for cross-referencing solutions against |
| `IDEAS-CATALOGUE.md` | Curated needs and moves |
| `components/` | Component records, moved out of CD because the library is repository-resident |
| `in-depth/` | **Documents that answer one question and then stop changing.** A register is never finished; these are. When one concludes, its settlements go to the decision log and the document stays as the reasoning |

---

## The canonical example

Every memo, diagram and mock uses the same scenario, and keeping it consistent is worth more than
variety. Contractor **Northgate Home Services**, customers **Robert and Sara Thompson**, 1428 Maple
Ave, Sacramento CA. Three leads, two sold, one deferred, one change order, one permit that sticks.

It is adopted in the team repository as scenario **S15**. **All of the data lives in
`WORKED-EXAMPLE.md` beside this file**, which carries the shared spine plus two tellings, cash and
financed, and records the eight refinements C made to S15 on 11 Sep 2026 to make it internally
consistent and bring it onto our model. **Do not invent a second example.**

---

## Where the other work lives

The team's record, the boards and the Confluence scenario scripts are all in `SOURCES.md` beside this
file, with notes on which of them can actually be reached and which of them are out of date.

One warning worth repeating here because it costs time: **only two of the seventeen team scenario
pages have been rewritten into the current vocabulary.** The rest still call the spine a Job and the
work a Workstream. Read a page's header before trusting its nouns.
