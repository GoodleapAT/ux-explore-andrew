# Two models for bundled work

> **Superseded, 28 August 2026.** Model C, in which a **project** is the container and
> opportunities, proposals and jobs are peers inside it, dissolved the question this document was
> asking. The A versus B argument turned on which level is independent, and that only mattered while
> the proposal was assumed to be the container. It is not. Kept for the reasoning trail, in
> particular why the proposal cannot be the parent of jobs. Do not build from it.

Two ways to let one customer buy several things at once. Each introduces exactly one new object.
Everything else below already exists or is already agreed.

**Model A — Three granularities, deliberately not a hierarchy.**
One proposal contains additive scopes. Each scope has its own work, itemisation and value, and
produces one job or one service. Financing and the signature sit on the proposal.

> **The scope** (new object). A named chunk of work inside a proposal. It has its own statement of
> work, its own itemisation and its own price, and it is sized to what one crew turns up and does. A
> proposal with three scopes is one document describing three chunks of work. A proposal with one
> scope is just a proposal.

- *A roof replacement.* One proposal, one scope, one job. Nothing new is visible and it behaves
  exactly like a proposal does today.
- *Siding, windows and a roof.* One proposal with two scopes: siding and windows together for the
  exterior crew, roofing on its own. One document, one total, one financing arrangement, two jobs.

**Model B — Whole proposals, tied together by a folio.**
Each piece of work gets its own complete proposal. A folio ties several of them together so the
customer receives one thing. Financing sits on the folio when a single arrangement covers everything
being bought, and stays on the proposal when it does not. Either way the proposals underneath remain
independent and each feeds its own job.

> **The folio** (new object). The single thing a customer receives, assembled when sales is ready to
> present. It has two lives. **Before signing** it is a wrapper: a view over several finished
> proposals with summaries laid over the top, still open to having another proposal added. **On
> signing and financing application** it becomes the document of record, containing only the
> proposals the homeowner went forward with. The proposals inside keep their own statement of work,
> itemisation and price throughout, and remain separate objects.

- *A roof replacement.* One proposal, one job, and no folio at all. Nothing new is visible and it
  behaves exactly like a proposal does today.
- *Siding, windows and a roof.* Two proposals, each written and priced on its own, gathered into a
  folio so the customer receives one thing. Two jobs.

---

## How the pieces fit together

An **opportunity is one element of work someone might buy**. Siding is one, windows is another, even
when they sell together. It is created before anything is priced, it carries provenance (the
customer asked, a contractor spotted it, DeDe surfaced it), and it is won or lost.

Both models run the same chain: **opportunity, then the priced unit, then the delivered work.** What
differs is only what the priced unit is called and whether it can stand on its own.

**The simple case, which is most sales.** One thing wanted, one thing quoted, one thing built:

```
Model A    Opportunity ──►  Proposal ──► Scope ──► Job
                            one scope, so the proposal is a single chunk of work

Model B    Opportunity ──►  Proposal ─────────────► Job
                            no folio involved at all
```

Both of these are exactly how Pros works today. Neither new object appears until it is needed.

**The bundled case.** Several things wanted, sold together, built by different crews:

```
Model A                                     ┌─ one Proposal ─────────────────┐
   Opportunity siding  ┐                    │                                │
   Opportunity windows ┴──►  Scope 1  ──►  Job (exterior crew)             │
   Opportunity roofing ────►  Scope 2  ──►  Job (roofing crew)             │
                                            └─ holds financing + signature ──┘

Model B                                     ┌─ one Folio ────────────────────┐
   Opportunity siding  ┐                    │                                │
   Opportunity windows ┴──►  Proposal 1 ──►  Job (exterior crew)             │
   Opportunity roofing ────►  Proposal 2 ──►  Job (roofing crew)             │
                                            └─ presentation, and financing   │
                                               when it is shared ───────────-┘
```

Both models therefore support the full range: one opportunity through to one job, or many
opportunities through to many jobs, all under a single thing the customer sees and signs. Neither
forces you into the complicated version. **The difference is which object grows to accommodate the
bundle** — in A the proposal gains scopes, in B a folio gathers several proposals.

Two things hold in both. **The opportunity survives the sale**, so losing windows while winning
siding is representable either way. And **an opportunity is never the thing that gets delivered** —
it is the thing that justifies delivering something. A job traces back through the priced unit to
one or more opportunities, never straight to an opportunity.

Reduced to the levels alone, the two are the same shape:

```
Model A     Proposal  ──►  Scope     ──►  Job
            financing      work            delivery
            signature      itemisation
                           value

Model B     Folio     ──►  Proposal  ──►  Job
            financing?     work            delivery
            signature      itemisation
                           value
```

Model B is Model A with the middle level promoted. This is not a choice between two data shapes.
**It is a choice about which level is the independent one**, and everything else on this page
follows from that.

One thing worth noticing before the differences: **both models need a shared-or-separate financing
switch.** Model A already assumes one, with financing modelled on the scope and presented at the
proposal. Model B needs the same switch a level up. So financing mode is not a reason to prefer
either model. It is work both of them owe.

In Model B, financing **stays on the proposal** in three situations: when only one proposal is being
offered, when only one proposal in a folio moves forward, and when the homeowner is financing each
accepted proposal separately. It moves to the folio only when one arrangement covers everything being
bought.

---

## Where they actually differ

| | Model A | Model B |
|---|---|---|
| Unit of work and price | Scope | Proposal |
| Opportunities attach to | A scope | A proposal |
| Can that unit exist alone | No | Yes |
| When bundling is decided | At authoring time | Any time, up to the financing application |
| Unbundling later | Split a document already sent | Remove it from the folio |
| Financing sits on | The proposal | The proposal, or the folio when shared |
| What the customer signs | The proposal | The folio |
| A job points at | A scope | A proposal |
| Change order attaches to | A scope | A proposal |
| Numbers on screen | Scope values, one total | Proposal values, folio total |

---

## What each one buys

**Model A makes the document simple.** One thing is sent, one thing is signed, one total, one
financing arrangement. Nothing has to be reconciled and there is no ambiguity about what the
customer agreed to. Financing has an obvious home.

**Model B makes the sale simple.** Windows gets quoted, siding gets quoted, and only then does the
customer say they want both. In Model A that means re-authoring two documents into one with two
scopes. In Model B you gather what already exists. That sequence is how the conversation usually
goes, which is the strongest argument on this page.

---

## What each one costs

**Model A.** Bundling has to be decided before authoring. A scope cannot be sent, tracked or won on
its own, so a customer who wants only one of two things forces either a partial-acceptance mechanism
or a reissued document. The scope is a second-class object by construction.

**Model B.** The folio changes character partway through the sale. Before signing it is a
presentation view over several proposals; after signing it is the document of record. That is a
coherent lifecycle rather than an ambiguity, but it is still **two behaviours in one object**, and
the interface has to make the transition visible rather than let it happen quietly.

There are also three numbers on screen where Model A has two: each proposal's value and the folio
total. And because financing may sit on either level, the screen has to say which, since a
proposal's value is only the financed amount when financing has not moved up to the folio.

One further cost shows up once opportunities are in the picture. Siding and windows can be **either
one proposal covering both, or two proposals inside a folio**, and both are legitimate. That is two
ways to express the same sale, which means two ways to report on it and two ways for a contractor to
get it wrong. Model A has only one: the opportunities attach to a scope, and whether they share a
scope is a question about crews rather than about paperwork.

---

## Questions that exist only in one

**Only in A**

- Can a scope be accepted individually, and what does that do to shared financing?

**Only in B**

- Can a folio mix shared and separate financing, or is it one or the other for the whole folio?
- Can a proposal be pulled out of a folio after the financing application has gone in?
- Can one proposal sit in two folios?
- Does a folio have its own status, or is it derived from the proposals inside it?
- Is a win counted as one folio or as several proposals?
- What happens to a folio when every proposal in it is declined?

**Unchanged either way**

Person above address, how the associations are stored, notes and history as one stream, and the
service lifecycle. None of those move. Contract value has since been answered for Model B; see
below.

---

## What the answers were

Three questions were meant to settle this. Two have been answered, and both went Model B's way.

**1. When is bundling decided? After the quotes are ready.** Bundling is generally decided once both
quotes exist, and whether they share financing is decided at the same moment. A proposal can also be
added to a folio later, up until the financing application goes in.

This was the load-bearing question and it lands squarely on Model B. **Model A would require
re-authoring two finished quotes into one document with two scopes**, at exactly the point in the
sale where nobody wants to be redoing paperwork. Model B gathers what already exists.

It also settles something previously listed as open: the folio is **mutable until the financing
application**, not fixed when it is assembled. Adding a proposal to an existing folio is a normal
move rather than an edge case.

**2. Does the customer need one document? Yes, with a way through to each proposal.** One thing is
sent and received, and the full individual proposals are reachable from inside it. The folio is not
a covering letter with attachments; it is the document, and the proposals are its detail.

**3. Can financing attach to something that is not the signed document?** Parked deliberately, and
now less pressing than it looked.

### Two things this resolved

**The folio has a lifecycle, which is why "is it a wrapper or the document" was a false choice.**
Before signing it is a presentation object, spun up when sales is ready to present, still open to
another proposal being added. On signing and financing application it becomes the document of
record, containing only the proposals the homeowner went forward with. Both descriptions were right;
they just apply at different moments.

**The financed amount follows what the homeowner actually buys.** Financing breakdown and totals
come from *which proposals go forward*, not from what was originally sent. So the proposal is the
authoritative number and the folio total is derived from the accepted ones. Financing stays on the
proposal when only one proposal is offered, when only one moves forward, or when the homeowner
finances each accepted proposal separately. It moves to the folio only when one arrangement covers
everything.

### Where that leaves the comparison

Model B's strongest argument is now confirmed rather than assumed. Model A's strongest argument, that
one document is simpler to reason about, is weakened rather than untouched: answer 2 means Model B
produces one document too, so A's advantage narrows to internal tidiness rather than customer
experience.

The remaining cost of Model B is the one that has not moved: **two proposals inside a folio and one
proposal covering both are both legal ways to express the same sale.** Answer 1 makes that less
likely to bite, since separate quoting is the normal path, but it does not remove it.

---

## Naming

**Chosen: scope and folio.** Earlier working names were "part" and "packet", then "section". Part
was vague, packet understated the object, and section read as document formatting rather than work.
The alternatives considered are kept below in case either choice needs revisiting.

**Words already taken, avoid all four.** *Offer* is used in the financing domain, where loan offers
carry an offer id. *Bundle* is taken by financing bundles. *Package* is the pricebook's word for a
set of line items. *Project* already exists in the proposal model as a design artefact.

### Candidates for the Model A object, now "scope"

A named chunk of work inside a proposal, with its own statement of work, itemisation and price,
sized to what one crew does.

| Candidate | For | Against |
|---|---|---|
| **Scope** | Field-native. Contractors say "the roofing scope" without being taught to | Collides with "scope of work", and the phrase "each scope has its own scope" has to be written around |
| **Section** | Document-native, and the proposal *is* a document | Sounds like formatting rather than work. A section of a contract is a clause |
| **Job line** | Names it by what it becomes, so "job line 1 of 2" maps straight to the job | "Line" pulls toward line items, which are a level below |
| **Work item** | Plain and unclaimed, works with a numeral | Sounds like a task, and tasks already exist in the project management model |
| **Work package** | The construction industry's own term for exactly this | Two words, and "package" is close enough to the pricebook's term to stumble on |

**Scope** was chosen for being the only candidate contractors already use for this exact idea. The
cost is real and shows up immediately in writing: the word cannot also be used generically, so
"scope of work" becomes "statement of work" wherever both appear. If that friction gets worse in the
interface than it is on paper, **job line** is the fallback.

### Candidates for the Model B object, now "folio"

The single thing a customer receives, gathering several complete proposals, optionally carrying one
financing arrangement, and becoming the document of record on signing.

| Candidate | For | Against |
|---|---|---|
| **Folio** | A bound collection of documents presented as one. Unclaimed, short, and exactly the right metaphor | Unfamiliar enough that it needs explaining once, and may read as precious |
| **Proposal set** | Plainly says what it is. No collisions, nothing to explain | Flat and administrative. Nobody will enjoy saying it |
| **Program** | Common in commercial construction for a set of related work | Less familiar residentially, and overlaps with software usage |
| **Plan** | The most human option. "The Thompson plan" is how a salesperson would actually say it | Vague, and plan already means several things in a solar context |
| **Combined proposal** | Self-explanatory, needs no glossary entry at all | Long, and defines itself by what it is made of rather than what it is |

**Folio** was chosen, and the answer that the customer receives one document supports it: the object
is document-shaped and becomes the document of record. **Plan** remains worth considering as a
customer-facing name if the internal and external names are allowed to differ.
