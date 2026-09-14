# Decisions, Upgrade to Pros

**Domain decisions for this project, so they stop being re-litigated.**

> **Who may write to this file:** any surface that can write. **Append only.** Add to the bottom.
> Never edit or delete an existing row. A reversal is a **new row** naming the row it supersedes, for
> the same reason a change order keeps the original contract value.
>
> **Only log what was actually decided.** A recommendation nobody accepted is not a decision. Open
> questions live in `OVERVIEW.md` and in the entity modelling handoff, not here.
>
> **Scope.** These are Andrew's decisions for his own model and design work. They are not the team's
> decisions. The team keeps its own decision log in its own repository.

## Standing

**Every row says how much weight it carries.** Without this, a direction Andrew is exploring and a
thing the group has settled look identical, and somebody quotes the first as though it were the
second.

| Standing | Means | To change it |
|---|---|---|
| **Working** | Andrew's call. The path being designed against | He changes his mind. No ceremony |
| **Raised** | Put to the group, waiting on them | They answer |
| **Agreed** | The group settled it | Takes the group. Do not quietly reverse it |

**A Working decision still binds the design work.** What changes is how hard it is to reverse, not
how much it should be followed. Anything building screens should treat Working and Agreed the same
and only care about the difference when somebody asks whether it can be argued with.

---

## Principles

**A principle is a rule that generates answers, not a decision about one thing.** There should never
be many. When a new question is asked, check these first: if a principle already answers it, the
answer is not a new decision, it is an application.

### P-1 · Money is stored where it occurs, and higher levels derive

Costs occur on the job. Revenue occurs at the project, because that is where the receivable is. The
customer shows a roll-up of both. Nothing is stored twice.

**Settled 14 Sep 2026**, by Andrew, while ruling on the comparison. It replaces a question that had
been running as "does the project store the money or derive it", which was the wrong question: the
answer is neither, it is that each level stores what happens at it.

**What it already explains, without further argument:**

- **Per-job margin is unavailable**, because revenue and cost never occur at the same level. Not an
  oversight anybody can fix by adding a field. A consequence of the rule.
- **The master invoice sits at the project**, since that is where the receivable occurs.
- **The customer's financial figures are derived**, never authored.
- **Per-customer profit needs an allocation**, for the same reason per-job margin does, one level up.
- **A subscription invoice has no parent**, because it occurs against an agreement and the rule has
  no level for that. This is where the principle runs out, and it is the same defect their own
  scenarios flag.

### P-2 · A project is one workspace that transforms, not a sequence of screens

It opens focused on what is needed to sell. It transforms as the work arrives, especially once jobs
exist. The same object, showing different things, rather than a handover between two places.

**Stated 14 Sep 2026**, by Andrew, while working through when a project is created. The decision of
13 September, that templates flex by lifecycle stage as well as by product tier, is an **instance of
this principle** rather than a separate idea.

---

## Carried in

Settled during the modelling work before this log existed, so no precise dates. All are recorded in
the entity modelling handoff, and several are settled only there rather than with the wider group.

| Decision | Why |
|---|---|
| The container is mandatory | Not created only when there is something to bundle, because most of what it holds happens before anything is bundled |
| Lead, proposal and job are associated, not nested | Nesting would make the simple case harder than it is today |
| The simple case stays simple | One lead, one proposal, one job looks like today's product |
| A customer is a person, above the address | One customer may hold several properties |
| Financing is presented at the proposal but modelled below it | The customer decides once, for the whole sale |
| A change order attaches to one scope and shows both the scope value and the contract total | Both numbers move and both matter |
| Notes and history are one event stream, filtered twice | They are the same store read two ways, not two logs |
| Three product tiers per organisation | Payments only; payments and selling; payments, selling and operations |
| Selling and Work are groupings in the experience, not entities | The product needs a clear line between what is being sold and what is being delivered. Everything else in the model is an entity claim; these two are a UI claim |
| The pipeline is not drawn at any single level | Stages, statuses, tasks and gates are surfaced at the lead, project, selling, work and job levels alike. Boxing them at one level would understate where they appear |
| Change orders run three grades | No price change is a task. A price change within financing headroom is a sub-status. A price change beyond headroom is its own object, with a cash-split path |

---

## Log

| Date | Standing | Decision | Why | Supersedes | Applies to |
|---|---|---|---|---|---|
| 2026-09-10 | Agreed | **Project is the spine and Job is the work entity.** Job means the execution of one committed scope component | The team's DRAFT v3 resolved the collision the same way Model C already had. Two vocabularies converged and the level disagreement is gone | The neutral naming used while the container was contested | The whole model |
| 2026-09-10 | Working | **The project mints when someone starts pursuing a lead with the intention of writing a proposal.** It exists before anything is priced | DRAFT v3 mints it at the first proposal, which leaves the moment a contractor decides to pursue several trades together with no trace at all. That decision is most of why the container exists | DRAFT v3's proposal-mints rule, for Andrew's model | Lead and project |
| 2026-09-10 | Working | **One lead per trade.** Three trades on one house are three leads, and several leads can be pursued into one project | The alternative, one lead carrying several interests, is what DRAFT v3 does and leaves a deferred trade as an attribute rather than a thing with its own status. Flagged as possibly needing to adapt if it collides with the group's position | | Lead |
| 2026-09-10 | Working | **The demand object is called Lead**, not Opportunity | Matches the group's vocabulary, and the argument was never about the name | Model C's use of Opportunity | Lead |
| 2026-09-10 | Working | **A declined proposal and the project holding it are retained**, with the right statuses rather than being deleted or archived away | A declined trade that keeps its priced option can be revived without requoting, which is the cheapest thing that makes a next-season conversation possible | | Proposal, project, lead |
| 2026-09-10 | Working | **Every unhappy state requires a reason code and a free-text note.** Deferred, lost, blocked, cancelled, suspended | The code drives reporting and the note drives the next conversation with the homeowner. Both have to be captured at the moment the answer exists, which is usually in the room | | All entities |
| 2026-09-10 | Working | **A proposal carries two statuses, a lifecycle one and a delivery one.** Revised is not a lifecycle state; changes not sent sits on the delivery axis | A proposal can be presented and then edited without being resent. One status list cannot hold both facts without duplicating every combination | The single proposal status list proposed earlier the same day | Proposal |
| 2026-09-10 | Working | **The container is called Project.** Merlin's existing Project object, a design artefact carrying a bill of materials and an electricity profile, is set aside | The group has adopted Project, and arguing the name costs more than the collision does | The open naming question | Naming |
| 2026-09-10 | Working | **Service runs as its own project type**, with one job per visit and the cadence taken from the plan terms. Past, current and upcoming visits all exist as jobs | A membership is recurring, has no closing balance, and its work is produced by a term rather than by a signed scope. Stretching the ordinary work stream to cover it was a placeholder, not an answer | Model C's note that periodic maintenance could be stored in the work stream | Service plans |
| 2026-09-10 | Working | **A house sale is recorded as a status or attribute on the property** | The group treats transfer as unsolved. It is not a structural problem, it is a missing attribute | | Property |
| 2026-09-13 | Working | **Treatments B and C both stand for the pursuit moment. A is retired.** B pursues from a single lead's sheet and asks about other open leads after the call to action. C opens a project as a deliberate object and attaches leads into it | Either fits depending on the situation and the user's mental model. A, multi-select on the customer record, is the one nobody wants | | The pursuit moment |
| 2026-09-13 | Working | **The customer record regroups into Sales and Operations, with jobs listed flat under an Active projects heading, each row naming its project** | The regrouping reads better. Nesting jobs inside projects would contradict the claim that nothing indents on the customer record, which exists so three leads collapsing into two committed scopes stays representable. **Provisional:** more exploration needed, and a project changing section when a contract is signed means two places to look | | The customer record |
| 2026-09-13 | Working | **Sections flex by lifecycle stage as well as by product tier.** A project still selling has little or no operations section; a job in install needs almost no selling information | Tier flex answers what happens when a capability does not exist for this organisation. Stage flex answers what happens when it exists but does not matter yet. Different questions | | Every template |
| 2026-09-13 | Working | **Job costs are $25,530 siding and $12,834 windows** | Both splits give 31% at the project. The earlier one implied 12% on windows and 41% on siding, a spread that would draw a question having nothing to do with the design | The figures written into the worked example on 11 Sep | The worked example |
| 2026-09-13 | Working | **Memo 6 is superseded as the current UI position** by the S15 grid | Four faults: a costs figure implying 58% not 31%, a near-black in none of the 113 tokens, tender facts in the project fact sheet which is what makes the financed swap expensive, and reference codes on every row | Memo 6 as the current position | The UI |
| 2026-09-14 | Working | **Sales can see unvalidated leads.** In a larger organisation the sales view hides them **by default**, as a filter rather than a permission | Plenty of contractors have nobody separate to validate. One queue with a default, not two queues, and no handover is required for the small case | | The lead queue |
| 2026-09-14 | Working | **Assignment or claim creates the project.** No separate act is needed. Which of the two a contractor uses depends on how they run their desk, and the model does not pick | Both acts already exist and both already carry the intent to sell. A further confirm step would ask somebody to confirm what they have already done, and would be both skipped and over-used | | Lead and project |
| 2026-09-14 | Working | **The container is named by its contents, not by a person.** "Siding and windows, Thompson". It can be renamed later | No naming act at the moment somebody wants to get on with it, and it says exactly what is in it. When a second lead is attached **the name grows**, which teaches that the container exists by showing it rather than explaining it | | The project |
| 2026-09-14 | Working | **The word Project need not appear in the interface.** The entity is Project in the model; the screen calls it by its contents | Removes the Merlin naming collision from the product while leaving it in the model, where it is harmless | The open naming worry about Merlin's existing Project | Naming, UI only |
| 2026-09-14 | Working | **The project escalates through three forms**: implied, then a module or side pane, then its own page with sub-navigation. Each step happens when something arrives that needs the room | Whether the container is a place is a function of what is in it. The escalation is also the advertisement, so nobody has to be taught what a project is | | The project, every template |
| 2026-09-14 | Working | **No first-run introduction for Start selling.** One moment-of-need prompt instead, the first time a customer has another open lead while one is being sold | If the call to action needs explaining, the wording is wrong. What is not obvious is that a second lead can join, and that is worth saying at the moment it becomes true | | Onboarding |
| 2026-09-14 | Working | **Our model adopts DRAFT v3 wherever ours was the coarser one.** Twenty two of the thirty seven comparison rows. Our model stops being a rival model and becomes theirs plus three disagreements and six open questions | "This is just an artifact of my less detailed, broken-down model. We should use the v3 entities here", said of row after row. Ours was scoped to the container question and was never trying to be a full model, so where theirs is more detailed there is nothing to defend. **The entities gained are listed at the foot of the comparison** | The framing of ours as an alternative model | The whole model |
| 2026-09-14 | Working | **One scope equals one job** | Settles our side of the question their board answers both ways. Theirs says scope produces job **and** job decomposes into scopes; ours now says only the first | | Scope and job |
| 2026-09-14 | Working | **Forms, checklists, documents and photos are elements stored by the job, not entities**, and the list is not exhaustive | We want them in the experience and will keep drawing them, without claiming them in the model. **The only place we decline to adopt theirs**, since DRAFT v3 has both as entities. Anything else the job turns out to store joins this category rather than getting its own record | | The job |
| 2026-09-14 | Working | **Where a service agreement sits is deferred.** Preference at this time is service as a type of project, with visits denoted as jobs, past, current and upcoming | Either model might work and nothing forces the choice yet. **Deferring it keeps the subscription invoice defect contingent rather than settled**, because whether an agreement has a valid parent depends on this | | Services |
| 2026-09-14 | Working | **A lead surviving decline uses ours.** Reason, note and revive condition on the lead | Theirs carries the behaviour in its scenarios rather than in the model, which is a weaker place for it | | Lead |
| 2026-09-14 | Agreed | **A lead is an engagement, and it carries several interests or trades.** Not one lead per trade | **The team's decision, not Andrew's**, and it goes against his position. Their argument is a UX one: a CSR talking to a customer about several trades would otherwise have to work across several tabs or views to update what is being discussed in one conversation. **Andrew is designing against this and the implications will be understood through the UX work** | The one-lead-per-trade decision of 10 Sep 2026 | Lead, and every screen that lists demand |
| 2026-09-14 | Agreed | **The project is created when a proposal or proposals are won**, and the accompanying contracts are signed where contracts are included. **A project can hold one proposal or several** | **The team's decision, not Andrew's.** It supersedes his pursuit-mints rule and it also supersedes DRAFT v3's proposal-mints rule, so it is a third position rather than a choice between the two on the table | The pursuit-mints decision of 10 Sep 2026, and the assignment-or-claim decision of 14 Sep 2026 | Lead, project, and the whole selling experience |
| 2026-09-14 | Working | **The lead is the selling workspace.** Everything previously designed for the project during selling belongs to the engagement: holding several interests, showing where the customer stands on each, and carrying a deferred one | A consequence of the two rows above rather than a separate choice. If the project only exists after a win, nothing else can hold the selling work, and the engagement is the only object present for the whole of it | The project's role during selling, as designed on 13 and 14 Sep | The lead, and every selling screen |
| 2026-09-14 | Working | **The container's three escalating forms are retained but start later.** The project arrives at the win, so it never has an implied form and probably never a side-pane form. It begins at or near its own page | The escalation was designed across beats the project no longer spans. The reasoning holds, the starting point moves | The three-forms decision of 14 Sep 2026, as to where it begins | The project, every template |
| 2026-09-14 | Working | **Bundling now happens at the win, not at pursuit**, and a decision to pursue several trades together leaves no trace unless it succeeds | Follows from project-at-won. **This does not answer Andrew's original argument for the container**, which was precisely that the bundling decision should leave a trace. The argument is deferred to the UX work rather than resolved | | Lead and project |

---

## The 14 September reset, and what survived it

**The team settled lead granularity and the mint point, both against Andrew's positions.** Five rows
above record it. This section exists because a reader scanning the log cannot otherwise tell which of
the earlier rows still stand, and guessing wrong is expensive.

**Dead, superseded above:**

- The project mints on pursuit.
- One lead per trade.
- Assignment or claim creates the project.
- The container is mandatory for anything proposed or delivered. **A proposal that never wins now has
  no project at all.**

**Moot rather than wrong.** The pursuit-moment treatments, B and C, were about an act that no longer
creates anything. The reasoning about claiming from a pool may return as the way an engagement is
taken on, so the row stays readable, but nothing should be built from it as written. The same goes for
the moment-of-need prompt for Start selling: there is no longer a call to action at that point.

**Alive, and unaffected:**

- **Sales can see unvalidated leads**, hidden by a default filter rather than a permission.
- **The container is named by its contents**, not by a person. The moment it is named moves to the
  win, and the name still grows when a second proposal joins.
- **The word Project need not appear in the interface.** Arguably stronger now, since the object
  arrives late and quietly.
- **Lead, proposal and job are associated, not nested.**
- **Both principles.** P-1 on money is untouched. P-2, one workspace that transforms, still holds, but
  what transforms during selling is the engagement and the project is what it becomes.

**The open question the reset created**, and the one the UX work is meant to answer: **does an
engagement do everything the project was going to do during selling?** Holding several interests,
showing where the customer stands on each, keeping a deferred one alive, and carrying the material
that accrues during validation. If it does, the project was never needed before the win. If it does
not, the gap will show up as something a screen cannot say.
| 2026-09-14 | Agreed | **The project is created when intent to sell is expressed**, at qualification or automatically when a proposal is created from the qualified lead. Backend first, possibly in the experience too. **See T-2** | The team's third position on this in one day, and **it lands close to Andrew's original pursuit rule**. Their v4 also adds Qualified Lead as an entity, which marks the end of validation, the exact thing Andrew said their model failed to mark | The project-at-won rows logged earlier the same day, and the pursuit-mints row of 10 Sep, which is superseded by agreement rather than by disagreement | Lead, project, the selling experience |
| 2026-09-14 | Working | **Adopt Qualified Lead as an entity.** See T-3 | It is the object our model needed and did not have. Validation ends somewhere, and until v4 nothing in either model said where | The claim that neither model marks the end of validation | Lead |
| 2026-09-14 | Working | **Adopt the satellite record distinction.** Data that hangs off a step but is never a step itself. See T-4 | **It generalises the ruling Andrew already made** about forms, checklists, documents and photos, and gives it a name that covers eight things rather than four. It also corrects four of our own adopt-theirs rows, which said entity where v4 says satellite | Our wording on D-10, D-16, D-25 and D-26, which described Estimate, Scope Component, Job Financials and Commission as becoming entities | The whole model, and every component record |
| 2026-09-14 | Working | **Adopt uniform job outer states with trade-specific sub-states, and checkpoints as per-org policy rather than structure.** See T-5 and T-6 | It answers a question our statuses work had open: whether a trade changes the shape of a job's lifecycle or only what happens inside it. v4 says only the inside | Any reading in which trades produce different job lifecycles | The job, and every status display |
| 2026-09-14 | Working | **The team's positions live in one file and are pointed at, never restated.** See `TEAM-POSITIONS.md` | The mint point moved twice in one afternoon and each move meant rewriting the same external fact into seven documents. **A restated external position is a copy, and copies go stale**, which is the rule the standards already apply to renders | Restating team positions inside our own documents | Every document that mentions what the team holds |

---

## The second reset of 14 September, and why this one is cheaper

**The team moved again, hours later, and this time towards us.** The project is created when intent to
sell is expressed. That is the pursuit rule under another name, and v4's new Qualified Lead entity
supplies the thing Andrew said their model lacked: a marker for the end of validation.

**So most of what the first reset killed comes back.** The rows above supersede the project-at-won
rows rather than the pursuit rows. **The engagement survives unchanged**: lead-as-engagement was never
part of the reversal, so nothing about the worked example's engagement or job J-11 changes.

**What stays dead from the original position:** one lead per trade, and the claim that the project is
mandatory for anything proposed. Neither came back.

**What this cost, and the rule that came out of it.** Two full sweeps of seven documents in one
afternoon, because each of them restated the team's position instead of pointing at it. **The fifth
row above is the fix**, and it is the most durable thing learned today. A position that somebody else
controls is recorded once, with a date, and referenced.
| 2026-09-14 | Working | **Statuses split across two levels. The interest carries what used to be the lead's set; the lead gets its own.** Interest: new, pursuing, quoted, won, deferred, lost. Lead: new, qualifying, qualified, active, dormant, disqualified | A lead holding three interests cannot carry one status that is true. Won, deferred and lost are things a customer says about one trade. **Qualifying and Disqualified moved up to the lead**, because you qualify a conversation rather than a roof, and qualification is the act T-2 hangs the project off | The single lead status set in the vocabulary file, written when a lead was one trade | Lead, interest, and every screen that shows demand |
| 2026-09-14 | Working | **The lead's status is mostly derived, like the project's.** Active if any interest is being pursued or quoted, dormant if none are but one is deferred with a revive date. Only new, qualifying and disqualified are authored | Nobody should have to maintain a lead status by hand when its interests already say everything. **Dormant rather than closed** is what makes a revive date reachable, which is the open need about deferred work going quiet | | Lead |
| 2026-09-14 | Working | **The status split moves down one level.** New, Qualifying, Qualified and Disqualified belong to the Inquiry and the Prospect. The lead keeps only Active, Dormant and Closed. The interest set is unchanged | **Qualification now happens before the lead exists**, per T-3, so a lead cannot be in a qualifying state: it is qualified by definition. The split itself was right and was pitched one level too high. Their edge reads "qualified, not disqualified", so Disqualified keeps its word | The two-set split logged earlier the same day, which put those four values on the lead | Inquiry, prospect, lead, interest |
| 2026-09-14 | Working | **Four levels of demand status is accepted as a cost, not designed around yet.** Inquiry or prospect, interest, lead, project | Two more levels than this morning. **The risk is one screen showing four words that all look like a status at different grains**, so a demand surface has to make the level obvious. If that proves impossible the model is telling us something and this is where to look first | | Every demand screen |
| 2026-09-14 | Working | **Project merging is a need we have, not a feature we have chosen.** Recorded as N-004 and M-007, appetite deliberately unknown | A lead creates a project, so demand arriving later makes a second project that cannot join the first. **Merging is the cross-time case, not the multi-trade case**, because a lead already holds several interests. **And the cheaper alternative should be ruled out first**: qualifying a second inquiry into an existing lead means no merge is ever needed | | Project, lead |
| 2026-09-14 | Working | **A merge is prohibited once a project has a won proposal.** Before that it is allowed | It draws the line at the first irreversible thing rather than at the contract, which is later. A won proposal is the point at which the customer has committed and the project stops being a container for demand. **This makes M-007 shapeable**: the hard cases, merging signed contracts, invoices, jobs and payment plans, are all out of scope by definition | The open question of how late a merge is allowed | Project, and any merge affordance |
