# Pros Web: project context for Claude Design

**Version 2.0 · 11 September 2026 · Andrew Thompson, UX / Product Design**

> ## Read this before starting
>
> **This is context, not a build brief. Do not build anything yet.** Read what is listed below, tell
> me what you have understood and where you disagree, and wait to be told what to design.
>
> **This supersedes the August 2026 brief** and its two memos, which are in `design-handoff/` in this
> folder. That brief assumed a proposal was the parent of jobs and called the demand object an
> opportunity. Both are wrong now. What still holds from it is everything about the screens
> themselves: the customer list, the composition across product tiers, the sheet pattern, the money
> vocabulary, and the four-way distinction between stage, sub-status, task and gate.
>
> **You can read this repository but you cannot write to it.** That matters, and there is a protocol
> for it at the end of this document. Follow it.

---

## What to read, and in what order

| Order | File | Why |
|---|---|---|
| 1 | `../START-HERE.md` | The working protocol, and how this repository is organised |
| 2 | `../standards/mockup-density.md` and `../standards/ui-composition.md` | **Binding.** These govern every screen. Read them before you form any opinion about layout |
| 2b | `../standards/external-work.md` | How other people's parallel work is handled here: reference, never input |
| 2c | `../standards/component-library.md` | **Binding.** Where all of this is heading, and what to record every time you create or adapt a component |
| 3 | `OVERVIEW.md` | Project state of play |
| 4 | `VOCABULARY.md` | The settled nouns. Getting these wrong is the most common error |
| 5 | `DECISIONS.md` | What is settled and must not be reopened |
| 6 | `entity-modeling/memo-6-five-views.html` | **The current UI position.** Five views at the agreed density |
| 7 | `../prototypes/` | Two standalone screens built before the modelling started. **The composition reference** |
| 8 | `entity-modeling/OVERVIEW.md` | The detailed modelling handoff, including the open questions |
| 9 | `SOURCES.md` | Boards, the team repository, the Confluence scenarios, and which you can reach |
| 10 | `../reference/merlin-sol-tokens.css` | The real design tokens. Use these rather than inventing a palette, but read the caveat under Design system below: this file is incomplete |

Everything in `earlier/` and `design-handoff/` is history. Read it for reasoning, not for structure.

---

## Where the effort has landed

Pros Web needs two things Merlin does not have: something to represent work that **might** be sold,
and something to hold work **sold together**.

Four people have been modelling the same territory. As of DRAFT v3 on the shared board, and Andrew's
Model C, the two have converged:

- **Project is the spine.** It models one customer journey and is the container.
- **Job is the work entity.** One job executes one committed scope component.
- **Lead is the demand object**, carrying an origin and surviving being declined.
- **Selling and Work are groupings in the experience, not entities.** DRAFT v3 agrees: it has no
  selling lifecycle anchor at all, and selling states live on the lead, the proposal and the contract.
- **Money attaches at the project.** One master invoice for the whole project, with each job's
  evidence releasing its own milestone. Costs land per job.
- **Everything is anchored to a customer and a property**, so a project is one customer at one
  address.

That is the agreement. What follows is where it is still an argument.

---

## Differences that remain

Five. The first is live and the rest are open rather than contested.

**1. What mints the project.** DRAFT v3 mints it at the **first proposal**. Andrew's position, now
recorded as a decision, is that it mints **when someone starts pursuing a lead with the intention of
writing a proposal**, so it exists before anything is priced. In the team's own multi-trade scenario
there is a beat where the contractor decides to pursue three trades together and the script records
"no writes, the bundling decision leaves no trace". That is the moment the container exists for. The
gap is one beat wide. **Design as though the project exists before pricing.**

**2. Whether demand is an object or an attribute.** DRAFT v3 has **one lead carrying several
interests**, three authors and three arrival moments. Andrew has **one lead per trade**. This decides
whether a deferred trade is a thing with its own status, reason and revive condition, or an attribute
inside a lead that was otherwise won. **Design per-trade leads**, and expect this one to move if the
group pushes back.

**3. Stored or derived.** DRAFT v3 writes nothing on the project; its state is derived from the
proposal and the jobs, and the board says plainly that the project points at nothing. Andrew's
diagram draws roll-ups on it. **Not yet ruled on.** Assume derived, and assume a derived status has
to be able to show what produced it.

**4. Where declined-but-still-wanted work lives.** DRAFT v3 splits it: the option stays on the
proposal with its price, and the interest stays open on the lead. Their own note says the reporting
need has lost its home. Andrew keeps it as one lead with a status, a required reason, a free-text
note and a revive condition, **and** keeps the priced option. Take both halves: the demand survives
on the lead and the number survives on the proposal.

**5. Services and memberships.** The least settled part of the model and the most likely to change
under you. DRAFT v3 puts a **Service Agreement beside the project**, anchored to the customer and the
property, outliving every journey beneath it, and mints a project per entitlement cycle. Andrew runs
**service as its own project type**, one job per visit, cadence from the plan terms. Their own
scenario flags the defect that a subscription invoice belongs to neither a job nor a project.
Andrew's review comments on those pages argued for service sitting **under** a project, which
contradicts the agreement-outlives-journeys finding and is unadjudicated. **Treat any service screen
as provisional.**

---

## The scenarios

Seventeen beat scripts in Confluence, in the ProsOperations space under a page called "Scenarios".
Each walks a journey beat by beat. They are the best test of whether a screen survives contact with a
real sequence, and **they are authoritative on the experience rather than on the model.**

**How to read a scenario page.** Each has a table with three columns, and they are not equally
reliable.

| Column | What it is | How much to trust it |
|---|---|---|
| **What happens** | The plain language account of the journey, written by the team | **The important one.** Read this. If a screen contradicts it, the screen is wrong |
| **Notes** | The team's own questions: open points about the experience or the model, detail still needed, future considerations, permutations not walked | Genuine signal about what is unresolved. Not decisions |
| **Entities** | Generated, not authored. An inference about where each beat touches DRAFT v3 | **Treat as a reading, not a specification.** Useful for orientation, wrong in places, and it maps to DRAFT v3 rather than to the model in this document |

So: build from **What happens**, mine **Notes** for what is unsettled, and check **Entities** against
`VOCABULARY.md` rather than the other way round.

**Review status is marked on the page itself**, in Confluence, not recorded here. A tick means the
team has reviewed it. A construction marker means review is in progress. No marker means it has not
been reviewed. **Not all of them have been reviewed.** Check the marker before you lean on a
scenario, and check it on the page rather than trusting any snapshot of it, including this document.

**One more warning before you read any of them.** Six are still written in the old nouns, where the
spine is called a Job and the work is called a Workstream. A coordinated rename was deferred on
5 September. The column below tells you which.

The one-line summaries below are mine, and in places they lean on the generated Entities column
rather than on the team's own words. Use them to choose which scenario to open, not as a substitute
for opening it.

| ID | What it stresses | Entry | Nouns |
|---|---|---|---|
| **S1** | One invoice settled by two financing milestones eleven weeks apart. Money at its furthest from work | Lead | Current |
| **S2** | Progress billing as several invoices per job, each issued by work evidence rather than one invoice paid in parts | Lead | Current |
| **S3** | Two rails, a card deposit and a loan draw, settling one receivable. Proves a funding source cannot own its invoice | Lead | Current |
| **S4** | Selling only, with production and money entirely off-system. Forces a signed-suffices policy and a manual close | Lead | **Old** |
| **S5** | The thinnest card wedge. The accepted commercial artefact is a text message, and a charge is what witnesses it | A charge | **Old** |
| **S6** | A funding source landing with no selling and no work lane, forcing a synthetic invoice so mixed funding can converge | Financing app | Current |
| **S7** | The amendment path. An upgrade has to clear two orthogonal tests: the approved ceiling, and the underwritten category | An option | Current |
| **S8** | The membership flywheel across a year of cycles. Twelve invoices spanning three journeys and outliving all of them | Service agreement | Current |
| **S9** | A service quoted and booked on the phone, invoice authorised before the work, and a plan sold at the end | Lead | Current |
| **S10** | The payer is not the signer. Four payments from two payers on one invoice, with scope written by a carrier's adjuster | Lead | Current |
| **S11** | The floor. A solo handyman, a payment with no rail behind it, and an invoice created after both the work and the money | An invoice | Current |
| **S12** | Financing declined, card fallback. The hand-off pulled visibly apart: contract signed at beat 5, job created at beat 8 | Tender plan | Current |
| **S13** | Reactive repair. A diagnostic fee credited against the repair that follows it | Lead | **Old** |
| **S14** | The only work-lit, money-dark path. No invoice ever exists, so visit-close fires with nothing subscribed to it | Lead | **Old** |
| **S14B** | The same org with payments on. A three-milestone invoice mixing card and check, each request issued by a work event | Lead | **Old** |
| **S15** | Multi-trade, cash. **The canonical scenario.** Three trades in, two out, one deferred, and the counts differ at every line | Lead | **Old** |
| **S16** | Multi-trade, financed. Two lanes on one loan that never re-converge, held 26 days apart by a city permit desk | Lead | Current |
| **S17** | A stranger calls to buy a service plan. A project minted at quote that may never commit any scope | Lead | Current |

**Gaps the scenarios flag repeatedly.** These will bite any screen you design, so know them now.

- **Readiness gating.** Nothing connects a permit's status to the visit that depends on it. A job can
  be blocked for a month with nothing in its own record saying so.
- **Lead attribution.** No entity records which surface or which system raised a lead, so a homeowner
  app request, a referral and a suggestion engine all look the same.
- **Duplicate households.** Dedupe and merge is an unresolved residual across four scenarios.
- **Communications and follow-up.** Calls, notifications, debriefs and review requests have no
  entity anywhere.
- **Per-job revenue.** Revenue lands on the project and costs land on the jobs, so per-job margin
  needs an allocation nobody has specified.

---

## The UI exploration so far

Four rounds, and only the last two are current.

| Artefact | Status |
|---|---|
| `../prototypes/` two standalone screens | **The composition reference.** A customer record and a job view built before the modelling started. Every layout rule in `../standards/ui-composition.md` is read out of these two files |
| `entity-modeling/memo-4-model-c-screens.html` | History. Eight screens, 31 August, drawn before the convergence. Uses opportunity and proposal-as-parent |
| `entity-modeling/memo-5-statuses-on-screen.html` | Superseded on layout and density. Useful only for the status sets in its argument columns |
| `entity-modeling/memo-5b-project-workspace.html` | Superseded on density. Notable because it is where the memo layout changed to a full-width mockup |
| `entity-modeling/memo-6-five-views.html` | **Current.** Five views: customer record, project workspace, proposal, job, service plan |

**What the five current views establish**

- The customer record shows **leads and projects** where opportunities and proposals used to be,
  because under this model a proposal lives inside a project.
- The project workspace has **no status rail**. It was drawn and then removed as a diagram of the
  model rather than something anyone needs on a Tuesday.
- The job view **keeps** its stage rail, because those are the contractor's own configured stages
  rather than the model's derived states.
- The service plan **has no balance**. No total, no balance due, no closing figure. The absence is how
  the page says it is not a project.
- Under each view is a list of what was taken out and what still needs a home. **Read those lists.**
  They are where the unresolved parts are named.

**Two rules you must not relax.** They are in the standards and they are the result of a correction,
not a preference.

- **No badges, pills or chips.** Status is plain text, optionally with an icon, in the second line of
  the right-hand column. Colour appears **once per page** and only where somebody has to act.
- **No explanatory copy inside a screen.** No information boxes, no footnotes explaining the model.
  If a message seems necessary, propose it separately rather than placing it.

---

## Somebody else's UX effort, which does not apply here

> **None of this section is a requirement.** It is not Andrew's work, he is not involved in it, and
> nothing in it constrains anything you design. It is here so you recognise it if you come across it,
> and so you do not mistake it for a specification. **Treat every claim below as "what they are
> doing", never as "what we do".** If a screen seems to need one of their positions, that is a
> question for Andrew, not a licence to adopt it.

Joel added a skill to the team repository on 10 September that takes a scenario's beat script and
generates a clickable beat-by-beat walkthrough. One scenario exists so far. Three things to
recognise.

**1. There is a UX DRAFT section on the board with nine page designs.** At node `137:2376` on the Pros
Entities board, titled "top-level pages, four lenses over one spine". Their skill treats those nine as
binding on itself and forbids inventing structure outside them. **Andrew did not author it, has not
read it, and has not adopted it.** The five current views owe nothing to it.

**2. The nav contract they build to.** Home, then four lenses over one spine: Pipeline for work rows,
Customers for the person anchor, Properties for the property anchor, Money for receivable rows, then
a secondary group for pricebook and settings. Three consequences they state outright:

- **Embed detail surfaces, never list surfaces.** Origin and GoodPay arrive as columns, filters and
  drill-ins, never as their own tabs with their own pipelines.
- **One row per thing, everywhere.** Finance accounts, invoices and card transactions are columns and
  chips on a row, never sibling rows.
- **Project is not a nav item.** You land on it from a row's umbrella chip.

The third one is interesting, because the five views treat the project workspace as a first-class page
and arriving from a row is still arriving. **But it is not a constraint on us and it is not a decision
waiting to be made.** Design the five views as they are. If a screen genuinely forces the question,
raise it with Andrew and leave it open.

**3. Their wedge-first rule, which Andrew may raid later.** Every capability is a standalone entry
point rather than a locked step, so a card-only contractor gets a working app with the selling columns
simply empty. The part worth borrowing is that **an entity a scenario does not light could render as
an empty panel advertising the adjacent capability rather than being absent.** Logged as an idea, not
adopted. Do not build to it unless Andrew says to.

**Why none of their screens are a reference for you.** They are generated from a serialised snapshot
of DRAFT v3, so they carry DRAFT v3's mint rule, its single lead with several interests, and Service
Plan beside Project. Their kit is an acknowledged stopgap with its own class names. Their fidelity is
deliberately wireframe. So they are not a reference for the model, the components, or the finish.

**One boundary worth knowing.** Their skill cannot write to this Claude Design project. It is enforced
by a hook and an allow-list rather than by instruction, because generated wireframes must not end up
where the canonical components live. Their gap list is a request to Andrew, never a commit.

---

## Where this is heading: a component library

**The library is the output. Screens are how it gets discovered.** The destination is a component
repository on atomic design principles, where every component carries its logic and not only its
markup. `../standards/component-library.md` is the rule; the short version is here so you do not miss
it.

**Record every component you create or adapt, at the moment you create it.** Six fields: name,
atomic level, states, when to use, when not to use, and what it does when its subject is absent.
Never later. The usage rule and the anti-rule only exist while the reasoning is in the room, and a
screen never shows what somebody decided not to do.

**Two requirements will break anything drawn too specifically.**

- **Three product tiers.** Payments only; payments and selling; payments, selling and operations.
  Every component needs a declared position for each tier where its subject may not exist: absent,
  empty and self-advertising, or replaced. Silence is not a position. The payments-only tier is a real
  product and a large part of the customer base, and a record where the balance is the page is a
  different design problem rather than a subset of the full one.
- **Seventeen scenarios, not one.** A component that fits this scenario and needs a near-identical
  sibling for the next was drawn too specifically. Prefer one component with declared states over
  three that look alike, and say so when you feel the pull to fork one.

**The library is repository-resident, and this project is where components get designed rather than
where they are kept.** Colleagues will consume it from CC and other programs and most will never open
CD, so write every component record so it makes sense to somebody who cannot see the canvas.

**Do not stop designing in order to build the library.** Keep working the scenario and leave the
trail.

### What the surfaces are called

**C** is Claude Cowork, **CC** is Claude Code, **CD** is Claude Design, which is you. Use the short
forms in write-back blocks and changelog rows.

---

## What must survive

Structural claims the whole thing rests on. If a layout decision breaks one of these, change the
layout, not the claim.

1. **The project is mandatory and exists before anything is priced.**
2. **Lead, proposal and job are associated, not nested.** Nothing indents under anything on the
   customer record. Three leads collapsing into two committed scopes must stay representable.
3. **The simple case stays simple.** One lead, one proposal, one job looks like today. No new concept
   appears until there is something to bundle.
4. **One job per committed scope component.** Siblings run independently and meet at the final bill.
5. **One acceptance, one signature, one financing per bundled sale.** Financing is presented at the
   proposal and modelled below it. A job shows financing it does not own, and must say so.
6. **Deferred is not lost.** A declined trade keeps its lead open with a reason, a note and a revive
   condition, and keeps its priced option on the proposal.
7. **A change order attaches to one scope** and shows both the scope value and the contract total,
   because the contract figure is what triggers re-underwriting.
8. **Stage, sub-status, task and gate are four different things.** Stage is position. Sub-status is an
   external process nobody on the crew can accelerate. Task is work the team controls. Gate blocks a
   transition. Never let "waiting on the city" and "someone needs to make a call" look the same.
9. **Not applicable and not yet must look different**, without reading.
10. **Notes and history are one event stream, filtered twice.** Not two stores.
11. **A customer is a person, above the address.** One customer, several properties.
12. **A job never owns an invoice.** The master invoice is the total owed, held at the project.
13. **Three product tiers per organisation:** payments only; payments and selling; payments, selling
    and operations. Tier is set per organisation, so no screen handles mixed permissions in one
    account. The payments tier is a real product and a large part of the customer base, not a stub.

---

## Where it is undecided

Make a call, build it, and say which call you made. Do not fill these silently.

**The pipeline.** Stages, tasks, sub-statuses and gates are cross-cutting, and the model deliberately
does not draw them at any one level. A contractor configures ten stages describing first contact to
closeout, and that run crosses the lead, the project and the jobs. Whoever configures it thinks of it
as one pipeline; the model has it as four. Every current mock leaves a labelled placeholder where it
would go.

**Documents, notes, measurements, history, site assessments and insights.** They attach to the
customer, the project, the proposal, the jobs and the money at once. The awkward case is one site
assessment, findings tagged per trade, later read by two jobs that never run in step.

**Whether a deferred lead holds its project back.** The Thompsons commit two trades and defer one, so
a lead reads deferred inside a project that reads sold. Two statuses that appear to disagree and both
are correct. If project status derived from its leads instead of from the proposal and the jobs, a
deferred sibling could stop a project ever reading sold.

**Blocked as a state or a flag.** Drawn as an outer state, which loses the fact that the job was
ready before it was blocked. The reporting differs.

**Good, better, best within one trade.** The model allows several options per proposal and the
current mock reads one option per trade. Three tiers of siding would need a second axis.

**Whether option toggles freeze on acceptance.** Leaving them live on a signed proposal implies the
sale can still be edited.

---

## The worked example

Every screen uses the same scenario, and keeping it consistent is worth more than variety. **Do not
invent a second example.**

Contractor **Northgate Home Services**, a multi-trade home improvement company with an HVAC division
and an exteriors division sharing one sales desk. Customers **Robert and Sara Thompson**, 1428 Maple
Ave, Sacramento CA, built 1978. Two contacts: Sara decides, Robert handles billing. Customer since
August 2025.

- **Prior project, closed 24 Sep 2025.** HVAC, central air and a heat pump conversion, $14,800 on a
  ten-year loan. Proof the simple case still looks like today. A **heat pump maintenance plan** was
  sold at its closeout, two visits a year at $29 a month.
- **Three leads, one per trade.** Roofing, raised by the homeowner in the Home App on 21 July after a
  storm. Siding, raised by Sara on the intake call on 22 July. Windows, suggested by DeDe on 21 July.
- **Project "Exterior refresh for the Thompsons"**, opened 12 August when the contractor decided to
  pursue all three together.
- **Proposal P-1051**, prepared 13 August with all three trades priced. Roofing $38,900 and siding
  $34,200 offered; windows $18,600 priced and deliberately held back. Presented in person on 18
  August. The customer takes **siding and windows** and defers the roof to spring. Total $52,800,
  financed over 15 years at 6.99%, $474 a month. Contract signed the same evening.
- **Money.** Master invoice MI-4471. Milestones 20, 40 and 40 per cent. Two drawn, $31,680.
- **Jobs.** JOB-3101 Siding, $37,000 after a change order, exterior crew, installing, five of eight
  steps. JOB-3102 Windows, $18,600, install crew, **blocked 14 days** on Permit P-22841 after plan
  review asked for missing U-factor documentation.
- **Change order CO-01**, 9 September, rot behind the siding on the north elevation, plus $2,800.
  Scope $34,200 to $37,000, contract $52,800 to $55,600, within financing headroom and re-signed with
  no new credit pull.
- **Balance due $23,920.** Project margin 31%. Per-job margin unavailable.
- **Roofing stays a live deferred lead**, estimate retained at $38,900, revive March 2027.

---

## Design system

There is a design system in this project already, and Merlin's real tokens are in this repository.

- **Use existing components wherever one fits.** Adapt content to the component rather than bending
  the component to a mockup.
- **Use the extracted tokens**, at `../reference/merlin-sol-tokens.css`. 113 Sol tokens taken from
  Merlin's compiled production stylesheet, plus the Pros Web page utility classes. Inter and Fira
  Code. Do not invent a palette.
- **That file is incomplete, and we found out on 11 September.** It is a *mirror* of Sol and carries
  only the semantic tokens, with **no radius, spacing or font scale**. Sol itself should be read
  directly. Use the file for colour, and where you need a radius, a spacing step or a type role, say
  you had to choose one rather than letting the choice pass silently.
- **Badge variant colours are not in that file**, because the design system bundle ships them
  minified. This does not matter while badges are forbidden.
- **The mockups argue a structure, not a specification.** They are not drawn to specify spacing, type
  or component choice. If the argument survives a different arrangement, use the better arrangement.
- **Create new components only where nothing suitable exists**, and say what you tried first.
- If a layout is impossible or ugly in the real system, say so plainly and propose the alternative.
  Do not silently approximate.

The Figma files and the live component sink are listed in `../SOURCES.md`.

---

## Because you cannot write to this repository

Everything above compounds only if what we learn gets written down. You can read this repository and
you cannot write to it, so the write-back has to come back through Andrew.

**Start by reading `../CHANGELOG.md` and saying the date of its newest entry.** If that date is older
than the last one Andrew mentioned, you are working from a stale copy and should say so rather than
carry on.

**Prompt him the moment something needs writing, not only at the end.** If he corrects you, if
something gets settled, if an idea appears, if a scenario turns out to say something different from
this document, say so in one line and offer the write-back there and then. Saving it all for the end
means most of it is lost.

**End every working session with a write-back block.** One paste-able message, naming:

- the file
- the section or table
- the exact text to add or replace
- whether it is an append, an edit, or a new row

Do not summarise what should change. Write what should be written. Andrew carries it to a surface that
can write.

**What to write back, always two things:**

1. **What we learned about the problem.** A new idea goes to `../IDEAS-INBOX.md` as one line with a
   date and where it came from. A development of something known goes to `OVERVIEW.md`. A settled
   argument goes to `DECISIONS.md` as a new row, never an edit to an old one.
2. **What we learned about how to work.** A rule worth keeping goes to `../standards/`, with a
   learned-from line recording the date and what prompted it.

Also write back when you **diverge**: a layout you changed, a component you invented, a call you made
on something this document leaves open, or a place where the model made a screen impossible. Name what
you changed, why, and which claim above it contradicts. Those are the most valuable entries.

**Every write-back block ends with a changelog row**, in the format that file specifies, including
which other surfaces are now stale. And tell Andrew plainly if a change means this document itself is
out of date, because a stale context document is worse than none.

**One caution about your own stored context.** Anything saved into this Claude Design project is a
copy, and copies go stale. The repository is the source of truth. If what you have stored disagrees
with what you read here, the repository wins and you should say so rather than reconciling it
silently.

---

## How to start

1. Read the ten files in the order listed at the top. The two standards first, before you form a view.
2. Tell me what you understood, in your own words, and specifically **where you disagree** with the
   five current views or with the claims under "what must survive".
3. Inventory the design system against the five views: what maps to something existing, what needs
   adapting, and what is genuinely new.
4. Then stop and ask what to design. **Do not build yet.**
