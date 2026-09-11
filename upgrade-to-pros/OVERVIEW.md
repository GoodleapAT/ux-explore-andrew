# Upgrade to Pros

**Project overview. Read this before doing anything in this folder.**

> **Who may write to this file:** any surface that can write. Edit in place. Keep the state of play
> current; that is most of what this file is for.

Taking GoodLeap's contractor tooling from payments only into selling and operations. Pros Web needs
entities Merlin does not have: something to represent work that might be sold, and something to hold
work sold together.

The root of this repository carries how the work is done. This file carries what the work is.

---

## State of play, September 2026

**The model has converged.** A team model called DRAFT v3 and Andrew's Model C arrived at the same
shape from different directions: a container called **Project** is the spine, and **Job** is the work
entity beneath it, meaning the execution of one committed scope component. That resolves the collision
John Gaquin spotted, where Job was being used for two different things.

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
job and service plan.

---

## Threads

| Thread | Folder | Status |
|---|---|---|
| **Entity and object modelling** | `entity-modeling/` | Live. Has its own detailed handoff, `OVERVIEW.md`, which carries the model, the open questions and a file index |
| **Earlier model work** | `earlier/` | Superseded. The A against B comparison, the customer model proposal, the open decisions list and the convergence one-pager. Kept because the reasoning is still cited |
| **Claude Design handoff** | `design-handoff/` | History. The August prompt and the two memos that produced the standalone Pros Web screens. Superseded on structure |
| **Claude Design context** | `CLAUDE-DESIGN-CONTEXT.md` | Current. The context document for the Claude Design project: where the model landed, the differences remaining, all seventeen scenarios, the UI exploration so far, and the write-back protocol for a surface that can read but not write |
| **Origin financing page migration** | not started | Parked. Two of the pages were located, the third repository never was. See global sources |

---

## The canonical example

Every memo, diagram and mock uses the same scenario, and keeping it consistent is worth more than
variety. Contractor **Northgate Home Services**, customers **Robert and Sara Thompson**, 1428 Maple
Ave, Sacramento CA. Three leads, two sold, one deferred, one change order, one permit that sticks.

It is adopted in the team repository as scenario **S15**. The full telling is in the entity modelling
handoff. **Do not invent a second example.**

---

## Where the other work lives

The team's record, the boards and the Confluence scenario scripts are all in `SOURCES.md` beside this
file, with notes on which of them can actually be reached and which of them are out of date.

One warning worth repeating here because it costs time: **only two of the seventeen team scenario
pages have been rewritten into the current vocabulary.** The rest still call the spine a Job and the
work a Workstream. Read a page's header before trusting its nouns.
