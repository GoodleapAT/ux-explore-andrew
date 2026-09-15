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
| **Opportunity** | **A trade this customer might buy at this property. One record per customer, per property, per trade.** The durable demand object: it is created the first time anybody has a reason to think so, and **it outlives every lead and every project**. **Where the demand came from is an attribute**, so a trade the customer asked for and a trade the system recommended are the same kind of record. It goes on a lead while it is being sold and **returns to Open if it is declined**, carrying its history and a revive date. **Un-retired 15 Sep 2026** and **widened the same day**; see the decoder below | An inquiry, which is one contact event. A lead, which is one selling episode. **The Interest, which this replaced and which is retired** |
| **Inquiry** | **A customer has contacted the contractor in some way.** An event, not a party. Pre-qualification | A prospect, which is a person rather than a contact. A lead, which is qualified. An opportunity, which nobody contacted anybody about |
| **Prospect** | **An unverified customer, or an unverified expression of interest.** A party, not an event. Pre-qualification | An inquiry. See T-3 and the open question against it: these two may be one object with a type |
| **Lead** | **Qualified demand, and one selling episode.** **One open lead per customer and property**, which every new contact joins rather than multiplying. **Qualification is automatic where intent is expressed**, meaning a trade and a property are named, so most leads are created without anybody marking anything. **Creating one creates a project**, per T-2, and **one lead has one project**. It carries the opportunities being sold, and **it closes when everything on it is resolved**, which is the hand-off. A customer may have many leads over time, one at a time per property | Opportunity, which from 15 Sep 2026 is the durable per-trade record and **no longer means this**; see the decoder below. An inquiry or prospect, which are not yet qualified |
| **Interest** | **Retired 15 Sep 2026.** It was one trade inside a lead, the unit a customer says yes or no to. **Once the opportunity carried its own status and history there was nothing left for it to hold**, so an opportunity is now on a lead or it is not, and a proposal option prices the opportunity directly | **Use Opportunity.** The word survives in the team's own position on lead granularity, and the behaviour that position describes is untouched: a lead still carries several trades |
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
| **Opportunity** | **Mixed.** On a lead and Won are derived; Dismissed is authored; Open is where it starts and where it returns | Open · On a lead · Won *(terminal)* · Dismissed *(reason required)*. **Open carries two optional attributes: a worth-raising mark and a revive date** |
| **Inquiry** and **Prospect** | **Mostly derived from 15 Sep.** Qualified is set automatically where a trade and a property are named | New · Qualifying · Qualified · Disqualified. **Most contacts go straight to Qualified**, so New and Qualifying now describe the contact that named neither |
| **Interest** | **Retired 15 Sep 2026** | Was New · Pursuing · Quoted · Won · Deferred · Lost. **Where each value went is in the mapping below** |
| **Lead** | **Derived**, except the last | Active · Dormant · Closed *(authored)* |
| **Project** | **Derived**, except the first and the last | Pursuing *(authored)* · Quoting · Presented · Sold · In progress · Complete · Paid · Stalled · Lost · Cancelled *(authored)* |
| **Proposal, lifecycle axis** | Authored | Draft · Presented · Accepted · Declined · Expired · Superseded |
| **Proposal, delivery axis** | Authored | Never sent · Sent · Viewed · Presented in person · Changes not sent |
| **Option, decision state** | Authored | Priced, held back · Offered · Selected · Declined |
| **Job, outer state** | Authored, except Blocked | Review · Ready · In progress · Complete · Blocked *(derived)* · Cancelled |
| **Service plan** | Authored | Active · Renewing · Suspended · Not renewed · Cancelled. **Never Paid** |
| **Visit** | Authored | Upcoming · Scheduled · In progress · Complete · Missed · Skipped |

### Where the interest's six values went

**Retired 15 Sep 2026.** Nothing was lost, and two of the six turn out to have been derived all along.

| Interest value | Now |
|---|---|
| **New** | Opportunity **Open** |
| **Pursuing** | Opportunity **On a lead** |
| **Quoted** | **Derived.** A priced option exists on the proposal. It was never a state of the demand |
| **Won** | Opportunity **Won**, and terminal |
| **Deferred** | Opportunity **Open**, with a revive date. **This is the case the whole change exists for** |
| **Lost** | Opportunity **Dismissed**, with a reason code saying the customer refused. **C's reading, wants confirming** |

**Two defects in the lead and project sets were found on 15 Sep and both are answered by this change.**
The lead had no value for work in delivery with nothing being sold, and the project could never reach a
final state once demand could keep joining it. **Neither can now occur**: the lead closes at the
hand-off, and a closed lead takes no new demand, so the project stops accumulating and Paid is
reachable. **Recorded because both were real and both went away without being fixed directly.**

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
roofing opportunity reads Open with a revive date, all at the same time and all correct. **If this is
wrong the model is wrong rather than the layout**, so it is the first thing to revisit if project
status starts misbehaving.

### The grain count, and the day it finally went down

**Four levels of demand status: opportunity, inquiry or prospect, lead, project.** As of the end of
15 September 2026.

**It went four, five, four in one day.** Four in the morning, when inquiry, interest, lead and project
were the set. Five at midday, when the opportunity was added above the interest. **Four again in the
afternoon, when the interest was retired**, because the opportunity had taken over its status and its
history and there was nothing left for it to hold.

**This is the first time this count has gone down.** Every previous move added one, and the risk of a
demand screen showing several words that all look like a status at different grains has been the
biggest logged risk all week. **Worth noticing which direction a model change travels in**, because a
change that removes an object is usually worth more than one that adds a better object.

**The four are now genuinely different jobs rather than different gradings.** An opportunity is a
trade that might sell, an inquiry is one contact, a lead is one selling episode, a project is the
delivery container. **That is the real mitigation**, and it is stronger than the one recorded at
midday, which was that two of the five were never alive at once.

**The worth-raising mark was called To discuss while it was a status.** It is now an attribute on an
Open opportunity, so the collision that named it, against Pursue and Pursuing, no longer applies. The
word can be reconsidered when the mark is drawn.

**Corrected later the same day, after the board moved again.** The split into two sets was right and
it was one level too high. **Qualification now happens before the lead exists**, so New, Qualifying,
Qualified and Disqualified belong to the Inquiry and the Prospect. A lead is by definition already
qualified, so it cannot be in a qualifying state. What is left for the lead is whether it is being
worked: **Active, Dormant, Closed**.

**Their edge names the failure case: "qualified, not disqualified".** So Disqualified stays as the
word rather than becoming Rejected, and it sits at the level where the judgement is actually made.

**The two notes that follow are history. Read them for the reasoning, not the model.** They describe
the Interest carrying a status set and the lead's status being derived from interests. **The Interest
was retired on 15 September 2026** and the lead's set is Active, Dormant and Closed, all three read
from the opportunities on it. **The reasoning about splitting a status across levels is what survives**,
and it is why the opportunity carries its own set now.

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

**Opportunity has now meant three different things in our own work**, two of them retired and one
live. The superseded folders carry the retired two with no warning on them.

| Where you read it | What it meant there | What we call that now |
|---|---|---|
| **Model C**, and the board before 10 Sep | The demand object. The thing a customer might buy from | **Lead** |
| **The Model A against B comparison**, in `earlier/` | **One element of work someone might buy.** "Siding is one, windows is another" | An **opportunity**. See the note below: this reading has come back |
| **Anything from 15 Sep 2026 onward** | **A trade this customer might buy at this property.** One durable record per customer, per property, per trade, with origin as an attribute. **Widened later the same day** from cross-sell only, so it now covers a trade the customer asked for as well | **Opportunity.** This is the live meaning |

**The second one is the trap, and it got worse on 15 September.** A reader who knows Opportunity was
retired in favour of Lead will translate it that way throughout, and in the A against B material that
is wrong: those opportunities are per-trade units inside one piece of demand, which is a level below a
lead. The diagrams in that document show three opportunities feeding two scopes, and that only parses
on the second reading. **Now there is a third reading available**, and it is adjacent to the second
without being the same: the A against B sense is what we call an interest, and the live sense is the
stage before an interest.

**And then, by the end of the same day, the collision closed itself.** The interest was retired and
the opportunity took over its work. **So the A against B meaning and the live meaning have converged**:
"one element of work someone might buy, siding is one, windows is another" is now a fair description
of an opportunity. The decoder is down from three readings to two, and **the one that was going to
bite has stopped biting.**

**The remaining trap is only the Model C sense**, where Opportunity meant the demand object that is
now the Lead. That one is a level up and still misreads badly.

**The rule for reading it:** in anything dated before 15 September 2026, Opportunity is never the
live meaning. In anything after, it always is. **And the A against B sense turns out to be close to
the live one**, for the reason set out below, so that reading misleads less than it did.

**Added 14 Sep 2026**, when Opportunity turned out not to be free to reuse. **Un-retired anyway on
15 Sep 2026**, by Andrew, knowing the cost: it is the word the business uses for cross-sell and no
invented alternative carries that. The collision is recorded in the root glossary.

## Words to avoid

- **Opportunity**, in either of its retired senses. **The word is live again from 15 Sep 2026 with a
  third, narrow meaning.** See the decoder above before reading it in older material, and do not use
  it for the demand object or for a per-trade unit of work.
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
- **15 Sep 2026.** Opportunity un-retired by Andrew for cross-sell demand, and the new object needed
  it. **The decoder written the day before is what made the reversal safe to take**, because the cost
  was already written down and could be weighed rather than discovered. An argument for recording a
  retirement properly even when nobody expects to revisit it.
