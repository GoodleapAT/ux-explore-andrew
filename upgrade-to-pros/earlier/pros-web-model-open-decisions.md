# Pros Web customer model: nine questions and my current guesses

**From:** Andrew Thompson (UX / Product Design)
**For:** frontend and backend engineers on Pros Web
**What I want:** tell me which of these guesses is wrong, and which is cheap now but expensive
later.

---

## Read this first

Everything below is a **preference or an informed guess, not a decision.** I have stated a lean on
most of them because a document full of open questions is harder to react to than one with
something to argue against. The lean is there to be knocked down, and on several of them I would
be relieved to be told I have it wrong.

Every option I considered is still written down, including the ones I did not pick. If my reasoning
for picking one over another is bad, the alternative is right there and I would rather we go back
to it now than discover the problem later.

**Nothing here is scoped, and none of it is a build request.**

Where I cite existing behaviour, I read it out of the repo rather than out of documentation.
Corrections welcome and expected, particularly on intent, since I can see field names and not
reasoning.

---

## Summary

| # | Question | My guess | How sure |
|---|---|---|---|
| 1 | Does the proposal get an additive subdivision layer? | Yes, additive parts | Fairly sure |
| 2 | What is that part called? | No preference | Deferred |
| 3 | Where does financing attach? | The part, presented at the proposal | Contingent, see below |
| 4 | Can parts be accepted individually? | Yes | Moderate |
| 5 | What is a change order scoped to? | The part | Moderate |
| 6 | Is a recurring service a job or its own object? | Its own object, sold via a proposal | Fairly sure |
| 7 | How are the associations stored? | No idea | Open |
| 8 | What is the authoritative contract value? | Probably the proposal total | Least sure of the nine |
| 9 | Are notes and history one thing or two? | One event stream | Moderate |

---

## The shape being tested

Three granularities, deliberately not a hierarchy:

```
Customer
  ├── Contact      ×N
  ├── Property     ×N
  │
  ├── Opportunity  ×N     a single piece of work someone might buy
  ├── Proposal     ×N     one priced, customer-facing document
  └── Job          ×N     one piece of work being delivered
```

Opportunity, Proposal and Job are **associated, not nested**. One proposal can answer several
opportunities and produce several jobs. One job can satisfy several opportunities. The reason is a
real scenario: a customer wants siding, windows, solar and a battery. The contractor wants to hand
them one document, because four documents is a bad sales experience. But siding and solar are
different crews, different timelines and different permits, so they are different jobs.

That is the whole source of the questions below.

---

## What already exists in Merlin, as far as I can tell

Four findings, stated first because they change which options are actually available.

**1. `projects` is a design artefact, not a commercial one.** On the proposal it is a version
pointer, and resolved it carries a bill of materials, an electricity profile and a design. So it is
closer to "the engineered system" than to "the priced chunk of scope". It is the nearest existing
thing to the additive part in question 1, but not the same thing. If it is closer than I think,
that changes question 1 from new work into an extension.

**2. Financing is proposal-level and singular in practice.** `financingBundles` is an array, but
each bundle is a set of quotes, quotes carry a `productType` of `CASH` or `LOAN`, and the code works
with a single `activeFinancingBundle` selected by `financingBundleId`. So the array reads as
alternatives offered, not several financings running at once.

**3. A change order today is a financing change, not a scope change.** It fires when the loan
amount, the offer id, the autopay election or the cash partner price differs from the active
bundle, and it resolves by updating the proposal's financing. It is blocked outright when the loan
status is `Conditional`, and bounded by minimum and maximum loan amounts from the category.
Proposal status includes `PENDING_FINANCING`.

So there is already machinery for "the money changed after the customer said yes", and it is
attached to the proposal. There is nothing attaching a change order to a piece of work.

**4. The proposal hangs off `leadId`, and a lead is an address.** Not a person. Everything below
assumes a person-level identity above the address, which is itself the largest structural change in
the model and is tracked separately.

---

## 1. Does the proposal get an additive subdivision layer?

When one proposal covers exterior work and renewables, is that one flat document with two jobs
loosely attached, or does the document have named parts with one job each?

| Option | What it means | Trade-off |
|---|---|---|
| **A. Flat proposal** | One scope of work, one total. Jobs reference the proposal directly | Cheapest now. But with two jobs on one proposal, nothing records which part of the scope belongs to which job, so cost attribution, materials and change orders become manual or conventional |
| **B. Additive parts** | Proposal contains N parts, each with its own scope, itemisation and total. Each part produces one job, or one service per question 6. Proposal total is the sum | New entity, more authoring UI, more surface. But most of the ambiguity in the rest of this document resolves |
| **C. One proposal per job** | Never bundle | Simplest data model of the three. Costs the single customer-facing document, which is the thing the contractor actually wanted |

**My guess is B.** The argument that moved me is not about data: B makes the one-to-one case free.
A proposal with a single part behaves exactly like today's proposal, so a contractor who prefers
one proposal per job never sees the concept and loses nothing. A permits bundling and then cannot
describe it. C forbids something people want.

**Where I could be wrong.** If most bundled proposals in practice are one crew doing two things
rather than two crews, A is adequate and B is overhead for a rare case. I do not have the data to
say. If you do, it would settle this.

**What I need from you.** Whether this is an extension of something that already exists, per
finding 1, or genuinely new.

---

## 2. What is the additive part called?

**No preference, and not blocking.** I would rather name it once we agree what it does.

Noting only that three of the obvious words are taken. **Project** already has a design meaning,
**package** is the pricebook's word for a bundle of line items, and **scope** collides with "scope
of work". **Work package** is the construction industry's own term for exactly this concept.
**Segment** is unclaimed in either codebase but nobody in the field says it. I would rather inherit
an existing word correctly than introduce a fifth one.

---

## 3. Where does financing attach?

The scenario is one proposal covering exterior work paid in cash and solar financed over twenty
years. One document, two financing arrangements. Today you would do that with two proposals, which
works and costs the customer-facing document.

| Option | Shape | Adding per-part financing later |
|---|---|---|
| **A. Proposal-level** | Financing hangs off the proposal, as today | Schema migration |
| **B. Part-level with a mode flag** | Financing hangs off the part. A flag on the proposal says `shared` or `per-part`. In shared mode all parts point at one financing object and the UI shows a single financing block, as today | No migration. Build shared mode only |
| **C. Proposal-level now, accept the migration** | As A, deliberately and with eyes open | Honest, if per-part financing is unlikely to ever ship |

**My guess is B**, on the general principle of modelling at the finer grain and presenting at the
coarser one. To be clear, this is not a request to build multiple financing. It is a request to
build shared mode on a shape that does not need migrating later.

**Where I could be wrong, and this is the important one.** B is only worth it if the migration in A
is genuinely expensive. You know that and I do not. If financing is a thin join and adding the
per-part column later is a small job, then **C is the right answer** and I would rather be told so
than accommodated. I have picked B out of caution, not out of knowledge.

**What I need from you.** Is finding 2 correct, that the bundle array is alternative offers with
one active? And can a single bundle already contain both a cash component and a loan component
covering different parts of the work, or are its quotes strictly alternatives to each other? If the
latter is already possible, some of this question dissolves.

---

## 4. Can parts be accepted individually?

Customer takes the siding, declines the windows. Is that one proposal partly accepted, or a new
proposal?

| Option | Consequence |
|---|---|
| **A. Parts accepted individually** | Partial wins are representable. Opportunity state derives from whether its own part was accepted rather than whether the whole document was. Acceptance state has to live on the part, and the proposal's own status becomes derived rather than set |
| **B. Whole document only** | Simpler. Declining anything means reissuing, so the sales conversation is "here is a new proposal" rather than "we dropped that line". Loses the record that the customer ever wanted the windows |

**My guess is A.** This is the case that most tempted me away from bundling in the first place, and
the part layer is what makes it expressible rather than a workaround.

**The honest caveat.** Question 3 models financing at the part but builds shared mode first, so in
the near term declining a part still changes the financed amount. Given finding 3 that means a
change order, possibly re-underwriting, and possibly blocked outright when the loan status is
`Conditional`. **Part-level acceptance does not by itself make partial acceptance cheap while
shared financing is the only mode implemented.** Worth naming so nobody expects otherwise.

**What I need from you.** What happens today when a customer accepts a proposal and then the scope
shrinks? I can see the change order path for an amount changing. I cannot tell whether shrinking
scope is a supported flow or something people work around by voiding and reissuing. If it is the
latter, I would rather know before designing on top of it.

---

## 5. What is a change order scoped to?

Today it is proposal-scoped because it is about money, per finding 3. Once one proposal produces
two jobs, "the scope changed" needs to say whose scope, and "the price changed" needs to say which
job's cost moved.

| Option | Consequence |
|---|---|
| **A. Stays proposal-scoped** | Consistent with today, no new work. But operations cannot tell which crew's work changed without reading the itemisation |
| **B. Part-scoped** | The part maps to a job, so the affected work is unambiguous, and the part is the only thing that touches both the money and the work | 
| **C. Job-scoped** | Matches how the field talks about it. But financing sits above the job, so a job-scoped change order still has to reach upward to move the money |

**My guess is B**, for the reason in the table: it is the only level where the money and the work
meet.

**Where I could be wrong.** If change orders in practice are almost always about the money and
almost never about which crew is affected, A is fine and B is ceremony. Finding 3 suggests today's
change orders are purely financial, which is weak evidence for A.

---

## 6. Is a recurring service a job, or its own object?

The scenario is annual HVAC maintenance. It broke my job model, which is why this is here. A job
has a terminal state: scheduled, worked, completed. A maintenance agreement never completes. It
recurs until somebody cancels it.

| Option | Shape | Trade-off |
|---|---|---|
| **A. A type of job** | Reuses the job entity entirely | Cheapest. Requires either a job permanently in progress or a new job fabricated annually with no record of the agreement above them |
| **B. Its own object** | A Service, recurring and cancellable with no end state, containing N Visits, each individually schedulable and completable | Correct lifecycle. New entity |

**My guess is B**, and the lifecycle argument is the whole of it: a thing with no end state should
not be modelled as a thing with an end state.

**How it is sold is settled, and it does not need a new path.** A service is sold through a
proposal, exactly like everything else. A proposal part produces either a job or a service. So
"new HVAC plus a maintenance plan" is one proposal, two parts, two different kinds of output. No
separate agreement flow, no second signing experience.

**The implication for the rest of this document.** The part's output becomes polymorphic. Anywhere
below that says a part maps to a job, read "maps to a job or a service". That mostly costs nothing,
with one exception worth attention, in question 8: a service has recurring revenue rather than a
one-time value, so a proposal containing a service part does not have a single meaningful total.
Flagged there rather than here.

Worth knowing: **the commercial half of this already exists in Origin as subscriptions**, with a
recurring charge and add-ons. The half that exists nowhere is the Visit, meaning a scheduled
occurrence with a technician and a checklist.

**What I need from you.** Can Origin's subscriptions be the billing engine behind a service, or are
they too coupled to the organisation-level payments context to hang off a customer record in Pros?

---

## 7. How are the associations stored?

**No preference. This one I genuinely do not know, and it is the answer I most want.**

Given the shape at the top, Opportunity to Job is many-to-many, mediated by the part:

```
Opportunity  →  Part  →  Job
```

An opportunity is deliberately **one element of work**. Siding is one opportunity, windows is
another, even when they sell together, so that losing one and winning the other is representable.

**What I need from you.** Is a join table between opportunities and parts acceptable, or is there
pressure to keep a single foreign key? I would rather know the constraint than design around one
that does not exist. And is there precedent in this codebase for many-to-many that I should follow
rather than invent?

---

## 8. What is the authoritative contract value?

A customer signs a proposal covering two jobs. Later, someone asks what the contract is worth.
Which number is that?

| Option | Authoritative | Everything else |
|---|---|---|
| **A. The proposal total** | What was signed | Job invoices and part values reconcile up to it |
| **B. The sum of job invoices** | What was actually billed | The proposal becomes a historical quote |
| **C. The part value** | What was signed for each piece of work | Proposal total and job invoices both derive from it |

**My guess is A, and this is the one I am least confident about.** "What was signed" is the answer
a contractor would give, and it is the number that appears on a document a customer has in their
hands.

**Where I could be wrong.** A and C are closer than the table makes them look. If the proposal
total is authoritative and also the sum of its parts, then either the total is stored and the parts
must reconcile to it, or the parts are stored and the total is derived. That is a real
implementation choice hiding inside "A", and I do not know which side of it is safer. B I am fairly
confident is wrong, because it makes the signed document non-authoritative, but it is the option
that best survives partial acceptance and scope changes, so it deserves a hearing.

**The service case does not fit any of the three.** Per question 6, a part can produce a service,
and a service has a recurring charge rather than a contract value. So a proposal containing a
maintenance plan has no single meaningful total: it has an up-front amount and a rate. Whatever we
pick here needs to either exclude recurring parts from the total or carry two numbers. I have no
view on which, and would rather raise it than let it surface during implementation.

**What I need from you.** Is there already an answer to this on the invoicing side that I should be
conforming to rather than proposing? This feels like a question that has been settled somewhere and
I simply have not found it.

---

## 9. Are notes and history one thing or two?

Smaller, and separable from everything above, but a data decision wearing a UI costume. Adding a
note *is* a history event. Both attach to a customer, an opportunity or a job, and both roll up to
the customer view.

| Option | Consequence |
|---|---|
| **A. One event stream, two filtered views** | Notes is the human-authored subset, history is everything including stage changes and payments. A note written on a job appears in customer history for free |
| **B. Two separate stores** | Simpler to build. Guarantees they drift, and the roll-up has to be assembled twice |

**My guess is A.** The cost of A is paid once, at the start, and only at the start.

---

## What I am not asking about

**Tiers are out of scope here.** The proposal's existing tiers, labelled "Options" in the UI, are a
good / better / best choice for the customer. They are a different concern from the additive part
in question 1 and I am not proposing to change or reuse them.

Not asking for estimates, not asking for a commitment, and not asking anyone to defend the current
model. Several of these things are the way they are because the product was solar first and roofing
second, and that is a reason rather than a fault.

## How to respond

Per question is ideal, even if the answer is "no opinion". In order of how much the answer would
change what I do:

1. **Question 7.** No guess of my own, and everything associative depends on it.
2. **Question 8.** My weakest guess of the nine, and it probably already has an answer I have not
   found.
3. **Question 3.** I have leaned one way purely out of caution. If the migration I am avoiding is
   cheap, tell me and I will drop it.
4. **Question 1.** Specifically whether it is new work or an extension of something that exists.

If any of the four findings above is wrong, that matters more than any of the guesses, since the
options I have drawn depend on them.
