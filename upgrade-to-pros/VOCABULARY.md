# Vocabulary, Upgrade to Pros

**Scope:** the nouns. Use these in every document, diagram, mockup and conversation. Getting them
wrong in a document is worse than in conversation, because the document outlives the correction.

**Surfaces:** all.

---

## The settled nouns

| Word | What it means | Not to be confused with |
|---|---|---|
| **Customer** | A person, above the address. One customer may hold several properties | The property. A customer is not an address |
| **Property** | The site the work happens at. Referenced by the project, never owned by it | |
| **Inquiry** | **A customer has contacted the contractor in some way.** An event, not a party. Pre-qualification | A prospect, which is a person rather than a contact. A lead, which is qualified |
| **Prospect** | **An unverified customer, or an unverified expression of interest.** A party, not an event. Pre-qualification | An inquiry. See T-3 and the open question against it: these two may be one object with a type |
| **Lead** | **Qualified demand.** An inquiry or prospect the contractor has verified as worth selling to. **Creating one creates a project**, per T-2. Carries several interests, each with its own origin, detail and status, surviving being declined | Opportunity, retired and carrying two old meanings; see the decoder below. An inquiry or prospect, which are not yet qualified. An interest, which is one trade inside a lead |
| **Interest** | **One trade inside a lead.** The unit a customer says yes or no to, and the thing a proposal option is priced against | A lead, which holds several. A scope component, which only exists once something is committed |
| **Project** | The container and the spine. Models one customer journey. **Its creation point is set by T-2** and its state is derived and one-way, per T-7. Not stated here, because it moved five times in one day | Merlin's existing Project object, a design artefact carrying a bill of materials and an electricity profile. The collision is known and accepted |
| **Proposal** | What gets presented. Holds one or more options, each with a statement of work, an estimate and an itemisation, plus financing. Versioned | |
| **Option** | One priced choice inside a proposal, today one per trade. Carries a presentation state, because priced is not the same as offered | |
| **Scope component** | A trade-typed unit derived from the estimate lines. One becomes one job when committed | Scope, which collides with the insurance sub-status "Scope received" |
| **Contract** | One acceptance, one signature, one financing per bundled sale. Amended by change orders | |
| **Job** | The execution of one committed scope component. Carries its crew, schedule, material order, permits and checklists | The old use of Job as the spine, which six of the team's scenario pages still use. See the vocabulary warning in this project's `SOURCES.md` |
| **Service plan** | A recurring agreement, held against the customer and the property rather than inside a project. Runs as its own project type, one job per visit, cadence from the plan terms | A project. A plan has no closing balance and outlives the journeys under it |
| **Selling** and **Work** | Groupings in the experience, **not entities**. They exist because the product needs a clear line between what is being sold and what is being delivered | Everything else in the model, which is an entity claim |

---

## The states

**The status sets, gathered here 14 Sep 2026 from the statuses memo of 10 September**, which was the
only place they existed. A memo is an argument and it goes stale; a vocabulary file is where a value
list belongs.

**These are proposals, not decisions.** They were drawn to test whether they survive being put on
screen, and they did. Nothing in the decision log ratifies the lists themselves, so treat them as the
working set and say so when you use them.

| Set | Authored or derived | Values |
|---|---|---|
| **Inquiry** and **Prospect** | Authored | New · Qualifying · Qualified · Disqualified |
| **Interest** | Authored | New · Pursuing · Quoted · Won · Deferred · Lost |
| **Lead** | **Derived**, except the last | Active · Dormant · Closed *(authored)* |
| **Project** | **Derived**, except the first and the last | Pursuing *(authored)* · Quoting · Presented · Sold · In progress · Complete · Paid · Stalled · Lost · Cancelled *(authored)* |
| **Proposal, lifecycle axis** | Authored | Draft · Presented · Accepted · Declined · Expired · Superseded |
| **Proposal, delivery axis** | Authored | Never sent · Sent · Viewed · Presented in person · Changes not sent |
| **Option, decision state** | Authored | Priced, held back · Offered · Selected · Declined |
| **Job, outer state** | Authored, except Blocked | Review · Ready · In progress · Complete · Blocked *(derived)* · Cancelled |
| **Service plan** | Authored | Active · Renewing · Suspended · Not renewed · Cancelled. **Never Paid** |
| **Visit** | Authored | Upcoming · Scheduled · In progress · Complete · Missed · Skipped |

**A defect in the project set, found 14 Sep 2026 while walking S14.** The list contains **Paid** and
has no path that skips it. In S14 no invoice ever exists, so the job derives complete and the project
can never read paid. **There is no money-absent route through this vocabulary**, and the team's script
names the same hole in their own derivation table. **Unresolved.** The cheapest fix is that Complete
is terminal where no money lane is in use, which makes the final state depend on a capability being
switched on, and nothing else in the model works that way.

**Four things that hold across all of them.**

- **The job's outer states are fixed vocabulary and cannot be renamed by an organisation.** The
  project's derived status reads them. Everything an organisation wants to rename sits underneath
  them as configured steps.
- **Blocked is derived from a live blocker record and clears itself.** Nobody sets it and nobody has
  to remember to unset it.
- **Every unhappy state requires a reason code and a free-text note.** Deferred, lost, blocked,
  cancelled, suspended. The code drives reporting and the note drives the next conversation.
- **Deferred requires a revive date.** Without one, deferred and lost behave identically whatever the
  reporting says.

**Project status derives from the proposal and the jobs, never from the demand side.** Demand statuses
are about what a customer wants and the project's is about what they committed to, and the three are
allowed to disagree. In the worked example the project reads Sold, the lead reads Active, and the
roofing interest reads Deferred, all at the same time and all correct. **If this is wrong the model is
wrong rather than the layout**, so it is the first thing to revisit if project status starts
misbehaving.

**Four levels of demand status now.** Inquiry or prospect, interest, lead, project. That is two more
than the model had this morning, and it is the single biggest risk to a demand screen: four words that
all look like a status and mean things at different grains. **A demand surface has to make the level
obvious rather than just showing a word**, and if that turns out to be impossible the model is telling
us something.

**Corrected later the same day, after the board moved again.** The split into two sets was right and
it was one level too high. **Qualification now happens before the lead exists**, so New, Qualifying,
Qualified and Disqualified belong to the Inquiry and the Prospect. A lead is by definition already
qualified, so it cannot be in a qualifying state. What is left for the lead is whether it is being
worked: **Active, Dormant, Closed**.

**Their edge names the failure case: "qualified, not disqualified".** So Disqualified stays as the
word rather than becoming Rejected, and it sits at the level where the judgement is actually made.

**The original note follows, and its reasoning still holds one level down.**

**Two sets, settled 14 Sep 2026.** The interest carries the statuses that used to sit on the lead,
because won, deferred and lost are things a customer says about one trade. **The lead gets a set of
its own**, because a lead holding three interests cannot have one status that is true.

**Two values moved up while splitting them.** Qualifying and Disqualified were in the old lead set and
belong to the engagement rather than to a trade: you qualify a customer conversation, not a roof. That
matters beyond tidiness, because **qualification is the act T-2 hangs the project off**, so it has to
be a state of the thing that gets qualified.

**The lead set is mostly derived, which mirrors the project.** Active means at least one interest is
being pursued or quoted. Dormant means none are, but at least one is deferred with a revive date, so
the lead is worth surfacing again later rather than closed. Only New, Qualifying and Disqualified are
authored. **That the two levels came out with the same authored-and-derived shape is a point in
favour**, since the project set was drawn months earlier for different reasons.

**Still a proposal.** The values are drawn to be tested on screen and nothing ratifies them. Andrew's
position, 14 Sep: there is a lot of discussion still running across demand and selling, and this is a
stake in the sand rather than a settlement.

**The process vocabularies are somewhere else.** Standing, criticality, hold, rigidity and the rest
are in the root glossary. This section is only the domain.

---

## Reading the older material

**Opportunity has meant two different things in our own work**, and the superseded folders carry both
with no warning on them.

| Where you read it | What it meant there | What we call that now |
|---|---|---|
| **Model C**, and the board before 10 Sep | The demand object. The thing a customer might buy from | **Lead** |
| **The Model A against B comparison**, in `earlier/` | **One element of work someone might buy.** "Siding is one, windows is another" | An **interest** on the engagement. Not a lead, and not a scope component either |

**The second one is the trap.** A reader who knows Opportunity was retired in favour of Lead will
translate it that way throughout, and in the A against B material that is wrong: those opportunities
are per-trade units inside one piece of demand, which is a level below a lead. The diagrams in that
document show three opportunities feeding two scopes, and that only parses on the second reading.

**Added 14 Sep 2026.** Found while checking whether Opportunity was free to reuse. It is not, and the
reason is worth keeping whether or not anything is ever renamed.

## Words to avoid

- **Opportunity.** Retired in favour of Lead. **See the decoder above before reading it in older
  material**, where it sometimes means a per-trade unit rather than the demand object.
- **Sale** and **Workstream.** The previous team vocabulary, still live in six scenario pages. Do not
  introduce them into new work.
- **Sub-job.** An earlier name for what is now a Job.
- **Scope**, used alone, where **scope component** is meant.

## Learned from

- **10 Sep 2026.** Lead replaced Opportunity at Andrew's request, on the grounds that the argument was
  never about the name and matching the group's vocabulary is free.
- **10 Sep 2026.** Project confirmed as the container name, with Merlin's existing Project object set
  aside deliberately rather than worked around.
- **10 Sep 2026.** The spine and work split, Project over Job, confirmed as converged with the team's
  DRAFT v3.
- **14 Sep 2026.** Opportunity turns out to carry two retired meanings rather than one: the demand
  object in Model C, and a per-trade unit of work in the A against B comparison. A decoder was added
  above. **The lesson is that a retired word needs its meaning recorded, not just its retirement**,
  because "retired in favour of X" invites a reader to substitute X everywhere it appears.
