# Upgrade to Pros

**Project overview. Read this before doing anything in this folder.**

> **Who may write to this file:** any surface that can write. Edit in place. Keep the state of play
> current; that is most of what this file is for.

Taking GoodLeap's contractor tooling from payments only into selling and operations. Pros Web needs
entities Merlin does not have: something to represent work that might be sold, and something to hold
work sold together.

The root of this repository carries how the work is done. This file carries what the work is.

---

## State of play, 15 September 2026, end of day

**The demand side was rebuilt. One object added, one retired, and the grain count went down for the
first time this week.** Everything below happened in one day, in four passes, and the route is worth
reading once in `in-depth/the-opportunity.md`.

### The Opportunity, and it is ours rather than the team's

**One record per customer, per property, per trade.** A thing this household might buy at this
address, created the first time anybody has a reason to think so, and **it outlives every lead and
every project.**

**Where the demand came from is an attribute of it, not a different kind of object.** A trade the
customer asked for through the app and a trade the system recommended are the same record with
different origins. **That is the part worth defending**, and it answers lead origin as a first-class
attribute, which had been blocking in the object register all week.

**Statuses are Open, On a lead, Won and Dismissed, and Won is the only terminal one.** A trade that is
offered and declined **goes back to Open** with a revive date and a history entry. That is the whole
point: roofing appears under the customer, free-standing, and opening it shows that the customer
raised it in July, it went on a sale, it was priced at $38,900, and they declined for the season.

### The Interest is retired

**Once the opportunity carried its own status and history, the interest had nothing left to hold.** An
opportunity is on a lead or it is not, and a proposal option prices the opportunity directly.

**Four demand grains instead of five**: opportunity, inquiry or prospect, lead, project. **This is the
first time that count has gone down.** Every previous move added one, and it has been the biggest
logged risk to a demand screen all week. **The four are now genuinely different jobs** rather than
different gradings of the same idea.

**The word survives in the team's own position on lead granularity**, and the behaviour that position
describes is untouched. **Only the object is gone**, which is a vocabulary difference to raise rather
than a disagreement.

### Qualification is automatic, and the lead is a selling episode

**Qualification tests expressed intent**, which means a contact naming a trade and a property. The
Home App always qualifies; a phone call qualifies when somebody writes both down. **The discrete mark
survives as the exception path.** *The definition of the test is C's reading rather than Andrew's
ruling and wants confirming.*

**A new contact joins the open lead** for that customer and property. **And the lead closes when
everything on it is resolved, which is the hand-off.** So the join rule applies only while a lead is
open, and a contact during delivery starts a new lead with its own project, which is correct because
it is a different sale.

**Project merging is dead.** One lead has one project, later demand joins the open lead, so there is
never a second project. Later demand that sells lands in the existing project as another proposal and
another job.

### What the canonical example looks like now

**The lead and the project are born 4 August**, when Robert's app contact qualifies itself, with nobody
at Northgate present. **Roofing goes on the lead at once; windows and siding stay Open until Start
selling on 10 August.** Roofing returns to Open on 18 August when it is declined. **The lead closes on
24 August at the hand-off**, and the project delivers until 5 October with no lead behind it.

**One state nothing has ever drawn.** A project delivering for six weeks with its lead already
closed. **A second one was removed rather than solved**: the lead and project used to sit for
twenty two days holding one opportunity, and Andrew compressed the front of the story to six days so
that state stops being a problem worth a screen.

**Every figure, date and outcome is unchanged through all four rewrites.**

### Open

**Four things, and none of them blocks a first pass at a memo.** Where a customer's final no lives,
whether Start selling is what attaches an opportunity or qualification is, whether the container's
name may shrink when a trade is declined, and confirmation of the qualification test.

**Two defects logged earlier the same day went away without being fixed**: the lead's status hole and
the project never reaching a final state, both answered by the lead closing at the hand-off.

**The review queue is forty nine comments across two rounds.** Half of the newest twenty four are
visual and routed to a build brief rather than a memo. **All five rulings that were blocking are
closed.** See `CD-REVIEW-02-routing.md`.


## State of play, 14 September 2026, end of day

> **History. Do not design from this section.** It says a lead carries several interests, that
> qualification is the boundary between an inquiry and a lead, and that two questions about where
> several trades live are open. **All three were overtaken on 15 September.** Kept because its
> reasoning about the team's position is still cited.

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
| **Claude Design briefs** | `CD-PROMPT-s14-canvas.md` | Round one build brief. History |
| | `CD-PROMPT-s14-round-two.md` | **Current.** Round two: eight frames drawn new, five carried, one redrawn with two moves |
| **S14 round two** | `memo-8-s14-round-two.html` | **Current for S14.** Six screens reworked from Andrew's review. **Its qualification frames are now wrong**: qualification became automatic on 15 Sep |
| **S15 end to end** | `memo-9-s15-end-to-end.html` | **Current. Eleven screens, 15 Sep.** The first pass at the run end to end, and **the first time a scenario has been composed from the library rather than drawn.** Money is placeholdered throughout |
| **Review responses** | `CD-REVIEW-01-responses.md` | Twenty five comments, verbatim, with routing. Four needed rulings; two have landed |
| **Origin financing page migration** | not started | Parked. Two of the pages were located, the third repository never was. See global sources |

## Registers beside this file

| File | What it holds |
|---|---|
| `WORKED-EXAMPLE.md` | The complete Thompson mock data, S15. Use it, invent nothing. **Demand section restated 15 Sep: one inquiry, two opportunities** |
| `CD-REVIEW-02-routing.md` | **Where the twenty four comments of 15 Sep go.** Structural, visual, or cannot be acted on. Read this before the two verbatim files beside it |
| `WORKED-EXAMPLE-S14.md` | **The Brenner mock data, S14.** A different org, a single trade and a first-time customer, so none of the Thompson data survives. Four flagged inconsistencies in the source script |
| `MODEL-SNAPSHOT.md` | What our model contains, on a date, and the diff against DRAFT v3 |
| `OPEN-ITEMS.md` | **One index of everything unresolved.** Read it first in a cold session. An index, not a store: each row points at where the thing lives |
| `TEAM-POSITIONS.md` | **What the team currently holds, once, with dates.** The only place a team position is stated. Everything else points here |
| `MODEL-COMPARISON.md` | Every difference between our model and DRAFT v3, thirty seven of them, all ruled on 14 Sep. Stale in places, and it says where |
| `DRIFT-CHECK.md` | Everything we depend on that somebody else can change, and when we last looked |
| `DEVIATIONS.md` | Where a mock departs from the scenario it was built against |
| `OBJECT-REGISTER.md` | Things a screen needed that neither model has |
| `JOBS-TO-BE-DONE.md` | What people are trying to accomplish, for cross-referencing solutions against |
| `IDEAS-CATALOGUE.md` | Curated needs and moves |
| `components/` | Component records, moved out of CD because the library is repository-resident. **`ITERATION-4.md` carries the G-1 finding**: nine components across both scenarios unchanged, one dead, one failing in the opposite direction to the one predicted |
| `in-depth/` | **Documents that answer one question and then stop changing.** A register is never finished; these are. When one concludes, its settlements go to the decision log and the document stays as the reasoning |

---

## The canonical example

Every memo, diagram and mock uses the same scenario, and keeping it consistent is worth more than
variety. Contractor **Northgate Home Services**, customers **Robert and Sara Thompson**, 1428 Maple
Ave, Sacramento CA. **One inquiry and three opportunities, one lead that closes at the hand-off.** Two sold,
one deferred, one change order, and **no permit**, which the cash telling is explicit about.

**Corrected 15 Sep 2026.** This paragraph said three leads, which the model stopped having on
14 September, and "one permit that sticks", which belongs to the financed telling and was contradicted
by the worked example's own refinement list and its waiting-on register.

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
