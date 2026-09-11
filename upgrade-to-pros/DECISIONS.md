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

| Date | Decision | Why | Supersedes | Applies to |
|---|---|---|---|---|
| 2026-09-10 | **Project is the spine and Job is the work entity.** Job means the execution of one committed scope component | The team's DRAFT v3 resolved the collision the same way Model C already had. Two vocabularies converged and the level disagreement is gone | The neutral naming used while the container was contested | The whole model |
| 2026-09-10 | **The project mints when someone starts pursuing a lead with the intention of writing a proposal.** It exists before anything is priced | DRAFT v3 mints it at the first proposal, which leaves the moment a contractor decides to pursue several trades together with no trace at all. That decision is most of why the container exists | DRAFT v3's proposal-mints rule, for Andrew's model | Lead and project |
| 2026-09-10 | **One lead per trade.** Three trades on one house are three leads, and several leads can be pursued into one project | The alternative, one lead carrying several interests, is what DRAFT v3 does and leaves a deferred trade as an attribute rather than a thing with its own status. Flagged as possibly needing to adapt if it collides with the group's position | | Lead |
| 2026-09-10 | **The demand object is called Lead**, not Opportunity | Matches the group's vocabulary, and the argument was never about the name | Model C's use of Opportunity | Lead |
| 2026-09-10 | **A declined proposal and the project holding it are retained**, with the right statuses rather than being deleted or archived away | A declined trade that keeps its priced option can be revived without requoting, which is the cheapest thing that makes a next-season conversation possible | | Proposal, project, lead |
| 2026-09-10 | **Every unhappy state requires a reason code and a free-text note.** Deferred, lost, blocked, cancelled, suspended | The code drives reporting and the note drives the next conversation with the homeowner. Both have to be captured at the moment the answer exists, which is usually in the room | | All entities |
| 2026-09-10 | **A proposal carries two statuses, a lifecycle one and a delivery one.** Revised is not a lifecycle state; changes not sent sits on the delivery axis | A proposal can be presented and then edited without being resent. One status list cannot hold both facts without duplicating every combination | The single proposal status list proposed earlier the same day | Proposal |
| 2026-09-10 | **The container is called Project.** Merlin's existing Project object, a design artefact carrying a bill of materials and an electricity profile, is set aside | The group has adopted Project, and arguing the name costs more than the collision does | The open naming question | Naming |
| 2026-09-10 | **Service runs as its own project type**, with one job per visit and the cadence taken from the plan terms. Past, current and upcoming visits all exist as jobs | A membership is recurring, has no closing balance, and its work is produced by a term rather than by a signed scope. Stretching the ordinary work stream to cover it was a placeholder, not an answer | Model C's note that periodic maintenance could be stored in the work stream | Service plans |
| 2026-09-10 | **A house sale is recorded as a status or attribute on the property** | The group treats transfer as unsolved. It is not a structural problem, it is a missing attribute | | Property |
