# Pros Web customer model: overview

A short read. Covers the three granularities, the additive part inside a proposal, and how
financing and change orders behave once parts exist. Everything here is a working proposition, not
a decision.

---

## The problem

A customer wants siding, windows, solar and a battery. The contractor wants to hand them **one
document**, because four documents is a bad sales experience. But siding and solar are different
crews, different timelines and different permits, so they are **different pieces of work**.

Today those two facts pull in opposite directions. The model below is an attempt to let both be
true at once.

---

## Three granularities, deliberately not a hierarchy

```
Customer
  ├── Contact      ×N
  ├── Property     ×N
  │
  ├── Opportunity  ×N     a single piece of work someone might buy
  ├── Proposal     ×N     one priced, customer-facing document
  └── Job          ×N     one piece of work being delivered
```

| Entity | What it is | Why it is separate |
|---|---|---|
| **Opportunity** | One element of work a customer might buy. Siding is one, windows is another, even when they sell together | So that losing one and winning the other is representable |
| **Proposal** | One priced document the customer sees and signs | So that four things can be sold in one conversation |
| **Job** | One piece of work being delivered, with a crew and a schedule | So that scheduling and operations are not forced to treat siding and solar as one thing |

The important move: these are **associated, not nested**. One proposal can answer several
opportunities and produce several jobs. One job can satisfy several opportunities. Nothing owns
anything else.

---

## The additive part

The proposal gains an internal subdivision. Each part carries its own scope of work, itemisation
and total. Each part produces one job, or one recurring service.

```
Proposal  "Thompson residence, exterior + renewables"
│
├── Part 1  Siding and windows ........ $28,400  ──►  Job: exterior crew
├── Part 2  Solar and battery ......... $41,900  ──►  Job: solar crew
└── Part 3  Annual HVAC maintenance ... $39/mo   ──►  Service: recurring visits
                                        ───────
                          Proposal total  $70,300  plus $39/mo
```

**The key property is that the simple case stays simple.** A proposal with a single part behaves
exactly like today's proposal. A contractor who only ever sells one thing at a time never
encounters the concept.

This is not the same as the existing **tiers**, which are a good / better / best choice where the
customer picks one. Parts are additive: everything is in scope at once. Different concern, not
being changed here.

---

## How financing works with parts

Two things a contractor might want, and they are not the same:

**One financing for the whole proposal.** The common case, and how it works today. The customer
finances $70,300 across the lot.

**Different financing per part.** Exterior paid in cash, solar financed over twenty years. One
document, two arrangements. Today this needs two proposals, which works but costs the single
document.

The proposition is to **attach financing to the part but present it at the proposal**. A mode flag
says whether the proposal is in shared or per-part financing. In shared mode every part points at
the same financing and the customer sees one financing block, identical to today.

```
Shared mode (build this)          Per-part mode (do not build yet)

Part 1 ──┐                        Part 1 ──► Cash
Part 2 ──┼──► One financing       Part 2 ──► 20yr loan
Part 3 ──┘                        Part 3 ──► Monthly subscription
```

The intent is to build shared mode only, on a shape that does not need migrating if per-part is
ever wanted. Whether that caution is worth its cost is an open question for engineering, since it
turns on how expensive the alternative migration would be.

---

## How change orders work with parts

Worth knowing what a change order is today: **a financing change, not a scope change.** It fires
when the loan amount, the offer, the autopay election or the cash price moves away from what was
agreed, and it resolves by updating the proposal's financing. It is blocked outright when the loan
is in a conditional state.

So there is already machinery for "the money changed after they said yes", and it is attached to
the proposal. There is nothing attaching a change to a specific piece of work.

Once one proposal produces three jobs, that becomes a problem:

- "The scope changed" has to say **whose** scope.
- "The price changed" has to say **which job's** cost moved.

The proposition is that a change order becomes **part-scoped**, because the part is the only level
that touches both the money and the work. The part knows its own value, so the financing impact is
computable, and the part maps to a job, so operations know which crew is affected.

```
Homeowner adds a skylight to the exterior work

  Change order on Part 1
    ├── Part 1 value:  $28,400 → $31,200
    ├── Proposal total: $70,300 → $73,100
    ├── Financing:      recalculated, may need re-approval
    └── Affected work:  exterior crew job, unambiguously
```

**One caveat worth stating plainly.** While shared financing is the only mode built, any change to
one part still moves the whole financed amount. So part-scoped change orders make the *work* side
unambiguous immediately, and the *money* side only once per-part financing exists. That is a real
limitation, not a detail.

---

## What this buys

- One document for the customer, several jobs for operations, without either compromising.
- A record of what a customer wanted but did not buy, because opportunities survive independently
  of the proposal outcome.
- Partial acceptance becomes expressible. Take the siding, decline the windows, without voiding
  and reissuing.
- Cost, materials and change orders attributable to the right crew without reading an itemisation.
- Recurring services sold through the same document as everything else, rather than through a
  separate agreement flow.

## What is still open

Naming of the part, how the associations are physically stored, what counts as the authoritative
contract value, and how a recurring charge sits inside a proposal total. Those are covered in the
longer questions document.
