# The team's positions

**What the team currently holds, on a date, in one place. Everything else points here.**

> **Who may write to this file:** any surface that can write. **One row per position.** When a position
> changes, add the new row and move the old one to the history table at the foot. Never delete one,
> because knowing a position moved is usually more useful than the position itself.
>
> **These are not our decisions.** Our decisions are in `DECISIONS.md`. A position here binds the
> design work because Andrew has said it does, not because the team can decide for him.

## Why this file exists

**On 14 September 2026 the team changed its mind about when a project is created, twice in one day.**
Each change meant rewriting the same external fact into seven of our documents: the decision log, the
comparison, the model snapshot, the overview, the worked example, the beats document and the Claude
Design context. Two sweeps in an afternoon, and the third would have cost the same again.

**So the position is recorded once and pointed at.** The same rule the standards already apply to
renders: a copy goes stale, and a stale copy that looks authoritative is worse than none. A team
position restated in seven documents is seven copies.

**The test for whether something belongs here:** could the team change it without asking Andrew? If
yes, it goes here and nothing else states it. If no, it is ours and it goes in the decision log.

---

## Current positions

| # | Position | As at | Source | Supersedes |
|---|---|---|---|---|
| **T-1** | **A lead is an engagement**, carrying several interests or trades. Not one lead per trade | 14 Sep 2026 | Conversation. **Not on the board and not in their repository** | Our one-lead-per-trade decision of 10 Sep |
| **T-2** | **A lead creates a project.** One lead, one project, at the moment the lead is created. The lead is itself the qualified object, so this is the qualification moment | 14 Sep 2026, latest board revision | Board, demand lane, edge reads "Creates" | Their own intent-to-sell wording, their project-at-won position, and DRAFT v3's project-at-proposal-creation. **Four earlier positions, all the same day** |
| **T-3** | **Demand starts before the lead.** **Inquiry**, a customer has contacted the contractor in some way. **Prospect**, an unverified customer or unverified expression of interest. Either becomes a **Lead** when qualified, on an edge reading "qualified, not disqualified" | 14 Sep 2026, latest board revision | Board, demand lane | The Qualified Lead entity of the earlier v4, which is collapsed: **the Lead now is the qualified thing** |
| **T-4** | **A satellite record is data that hangs off a step but is never a step itself.** Estimate, Crew Assignment, Purchase Order, Photos and Docs, Forms and Checklists, Scope Component, Job Financials, Commission | 14 Sep 2026 | v4 visual language | The reading of these as flow entities, which is how our comparison recorded four of them |
| **T-5** | **Jobs run uniform outer states**: review, in progress, completed, plus exception branches. **Trade-specific steps are sub-states inside in progress.** Only the outer states derive the project's label | 14 Sep 2026 | v4 | Nothing stated before |
| **T-6** | **Checkpoints are per-org policy, not structure**: none, deposit paid, financing NTP, approvals, customer sign-off. Composed onto each workflow's transitions | 14 Sep 2026 | v4 | Nothing stated before |
| **T-7** | **The project's state is derived and one-way.** Every lane's record carries a project reference back to it. The project is outside every lane and models one customer journey | 14 Sep 2026 | v4 | Nothing. Consistent with v3 |
| **T-8** | **Every entity is anchored to both Customer and Property.** Those edges are omitted from the drawing for legibility | 14 Sep 2026 | v4 visual language note | The reading that dual anchoring was a project-level question, which is how D-04 framed it |
| **T-9** | **A service agreement mints a service plan instead of a project**, and Service Plan sits beside Project rather than being a kind of it | 8 Sep 2026, unchanged in v4 | Board, v3 and v4 | Nothing. **This is the one live disagreement with us** |
| **T-10** | **Permit and Rebate Application are gaps**, with no incumbent model behind them | 14 Sep 2026 | v4, marked in yellow | Nothing |
| **T-11** | **Project merging may be needed. Withdrawn 15 Sep 2026.** It followed from one lead creating one project, and the join rule removed the case: later demand joins the open lead, and a contact arriving after one closes starts a fresh lead and project which is a different sale. **Never the team's position; Andrew's, and now retracted** | 14 Sep 2026, withdrawn 15 Sep | **Andrew, not the team** | Nothing. New, and now dead |

## Open against these rows

**Against T-3: are Inquiry and Prospect one object or two?** Their definitions describe different
kinds of thing. An inquiry is an **event**, something that happened. A prospect is a **party**,
somebody who exists. Two entities of different categories, in one lane, with identical outgoing edges,
is usually one entity with a type, or two things at different levels that should not be peers.
**Unasked.**

**Against T-1: we have retired the word Interest. 15 September 2026.** Their row says a lead carries
several interests or trades. **The behaviour is untouched**: a lead still carries several trades and a
CSR still discusses three of them in one conversation without changing views, which is their whole
argument. **What changed is where the trade lives.** It is an **Opportunity**, durable, hanging off the
customer and the property, and it is on a lead while it is being sold rather than inside one.

**Why that is worth raising with them rather than assuming.** A declined trade survives the lead under
our reading and does not under theirs, and that is the case their scenarios handle in prose rather than
in the model. **It is a vocabulary difference with a behavioural consequence**, which is the kind that
looks small and is not.

**And where several trades live is answered, which used to be open against T-1 and T-2 together.**
Against the customer and the property, attached to a lead while being sold. **Merging is dead**: later
demand joins the open lead if there is one, and starts a fresh lead and project if there is not.

**Against T-11: merging is expensive wherever it lands.** Two projects each with a contract, an
invoice, jobs and money cannot be merged without deciding what happens to all four. Worth knowing
before it is treated as a small feature.

## What is not settled, in their record rather than ours

- **The mint edge label in v4 is clipped in the render** and reads only as far as "intent to sell to
  customer is ex". The exact wording is unread.
- **An Ownership versus Provenance panel is referenced** in v4's visual language note and is not in
  the node we looked at.
- **Work visits are marked Phase 2** in v4, so the appointment and crew assignment detail is theirs to
  stage rather than ours to design around yet.

## History, so a moved position is visible

| Position | Was | Until | Why it moved |
|---|---|---|---|
| **T-2** | The project is created when a proposal or proposals are won, with contracts signed where included. A proposal that never wins produces no project | 14 Sep 2026, same day | The team discussed it further and moved to intent-to-sell. **This lands close to Andrew's original pursuit rule**, which the win position had overturned a few hours earlier |
| **T-2** | DRAFT v3: creation of the proposal mints the project | 14 Sep 2026 | Superseded twice in one day, first by the win position, then by intent-to-sell |
| **T-2** | Created when intent to sell is expressed, at qualification or automatically on proposal creation. Two paths | 14 Sep 2026, same day | Collapsed to one path. **The lead became the qualified object**, so lead creation and qualification are the same moment and there is nothing left for a second path to trigger |
| **T-3** | Qualified Lead is an entity sitting between Lead and Proposal | 14 Sep 2026, same day | Collapsed. Demand now starts at Inquiry or Prospect and the Lead is the qualified thing, so a separate qualified-lead object is redundant |

**The mint point held five positions in one day**: ours at pursuit, the v3 snapshot at proposal
creation, the team at the win, the team at intent to sell, and the team at lead creation. **The last
two are the same moment described differently**, which is the first time a change has been a
restatement rather than a move.

**Anything designed against this should be designed so the trigger is cheap to move.** Five positions
in a day is the evidence, and the practical form of it is that no screen should depend on there being
a visible moment when a project appears.

---

## How to use this file

**Point at a row, do not restate it.** A document that needs the team's position on the mint point
says so and names T-2. It does not paraphrase T-2, because a paraphrase is a copy and copies go stale.

**When a position changes**, edit the row, add a history row, and the documents pointing at it are
correct without being touched. That is the whole point.

**When our position differs**, say so in the decision log and name the row it differs from. **T-9 is
the only one that currently applies.**

**A second divergence was recorded against T-2 on 15 September and withdrawn the same day.** C had
inferred that one lead may have several projects over time, and Andrew corrected it: **one lead, one
project, and the project contains multiple jobs.** We agree with T-2 completely. **Kept here as a
note because a withdrawn divergence is worth seeing once**, so nobody goes looking for a disagreement
that never existed.
