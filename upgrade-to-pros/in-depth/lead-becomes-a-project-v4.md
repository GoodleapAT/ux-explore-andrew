# Beats: qualification opens the project

**Written, not drawn. 14 September 2026. Status: open.**

> **The question:** the project is now created when intent to sell is expressed, at qualification or
> automatically when a proposal is drafted from a qualified lead. **What does that look like, and what
> does the engagement hold that the project does not?**
>
> **The rule this is built on is T-2.** It is stated once, in `TEAM-POSITIONS.md`, and not restated
> here. If T-2 changes, this document is wrong and nothing else needs touching.
>
> **This replaces `lead-becomes-a-project.md`**, which was concluded when the premise moved. Its
> account of validation in beat 2 still stands and is not repeated here. Read it there.

**What is different from the previous document.** That one argued the trigger should be assignment or
a claim. The answer is **qualification**, which is later and better: assignment can happen before
anybody has decided the lead is worth selling, and qualification is an act with a state of its own.
The earlier reasoning was right about when and wrong about what.

---

## The new shape, in one line

**Engagement from the first interest. Project from qualification. Both live until the close.** That
is the thing to design, and it is a different problem from the one we had this morning, when the
project did not exist during selling at all.

## The beats

### 1. Arrival

The engagement exists. In the worked example it opens on 21 July when Robert raises roofing in the
Home App, and it gathers two more interests within a day: windows suggested by the system, siding
raised by Sara on a call.

**One engagement, three interests.** See T-1. This is the part the team changed against us, and their
reason is job J-11: a CSR discussing three trades in one conversation should not be switching views.

### 2. Validation

Unchanged, and the previous document covers it properly. Material accrues: notes, transcripts,
documents, investigation. It is a fortnight of accumulation rather than a status change.

**Still the biggest hole in both models.** v4 adds Qualified Lead as the thing validation ends at, per
T-3, but says nothing about what validation consists of.

### 3. Qualification, which now creates the project

**This is the beat that changed.** Somebody decides the engagement is worth selling to. In v4 that
produces a Qualified Lead, and the intent to sell expressed there creates the project.

**Two paths to it**, and T-2 allows both:

| | What happens | What it means for a screen |
|---|---|---|
| **Explicit** | Somebody qualifies the engagement. The project is created at that moment | There is an act to attach a call to action to, and a state change to show |
| **Implicit** | Nobody qualifies anything explicitly; a proposal gets drafted from the engagement and the project is created automatically | **There is no moment at all.** The project appears because somebody started pricing |

**The design has to work when the second path is the common one.** If most contractors never
explicitly qualify, then the project's creation is invisible in practice and every screen has to
tolerate a container that arrived without being asked for. That was true of the old assignment path
too, and it is the same lesson: **do not build the experience around the trigger.**

**Backend only, or in the experience too?** T-2 leaves this open, and it is the sharpest open
question here. A project created in the backend and not surfaced is free: nothing to teach, nothing to
name, no new concept on day one. A project surfaced at qualification has to justify itself immediately.

### 4. Both live, which is the real design problem

From qualification to the close, **the engagement and the project both exist**. That is new. The
previous two versions of this question each had only one of them alive at a time.

**So the question is what each holds.** A first attempt, and it is a proposal rather than a finding:

| | The engagement | The project |
|---|---|---|
| **Holds** | The interests, all of them, including ones never sold. The validation material. The customer's words. The origin of each interest | What is being sold and then delivered: proposals, contracts, scopes, jobs, money |
| **Survives** | Everything. A deferred interest outlives the project it was never part of | The journey it was created for |
| **Answers** | "Where does this customer stand on each thing they mentioned?" | "What did we sell, and how is it going?" |

**The test.** Roofing in the worked example. It is an interest on the engagement, it was priced as an
option on the proposal, it was declined, and it never becomes a scope or a job. **If the engagement
does not hold its whole story in one piece, the split is wrong.**

### 5. Sold, and the transformation

The contract signs, tender is secured, and the hand-off seeds one job per committed scope component.
The project's subject changes from selling to work.

**This is still principle P-2**, one workspace that transforms. What is new from v4 is that **the
project's state is derived and one-way**, per T-7, and that **jobs run uniform outer states** with
trade-specific steps as sub-states, per T-5. So the project's label is computed from its jobs rather
than set by anybody, and a screen must not offer to change it.

**Checkpoints are per-org policy rather than structure**, per T-6. That matters for a mockup: deposit
paid, financing NTP, approvals and customer sign-off are configuration, so a screen that hard-codes
them is drawing one contractor's setup as though it were the product.

### 6. Not sold

The proposal is declined and no scope is committed. **The project exists and has nothing in it.**

**This is the case worth drawing and the one nobody has drawn.** Under project-at-won it could not
happen. Under project-at-qualification it happens every time a deal is lost, which is often. The
project is marked lost, and the interests stay on the engagement with their reasons and revive
conditions.

**Open: is an empty lost project worth keeping?** It records that a sale was attempted, which is real
reporting value. It also means a busy contractor accumulates lost projects that hold nothing. Neither
model says.

---

## What this settles, and what it does not

**Settles nothing by itself.** T-2 settles the trigger; this document only works out what follows.

**The three open questions, in the order they matter:**

1. **Is the project surfaced at qualification, or backend only until there is something in it?** The
   escalation argument from the previous document applies here almost unchanged, and this is the one
   worth a mockup first.
2. **What does the engagement hold and what does the project hold**, while both are live? Beat 4 is a
   proposal, not an answer. The roofing case is the test.
3. **Does an empty lost project stay?** Beat 6.

**Carried over and still true.** The container is named by its contents. The word Project need not
appear in the interface. Sales can see unvalidated leads behind a default filter. None of those were
touched by any of the four changes to the trigger.

## Learned from

- **14 Sep 2026.** The trigger for this container held four positions in one day. **Anything built
  against a trigger should be built so the trigger is cheap to move**, which in practice means the
  design should not depend on there being a visible moment. Both surviving paths in beat 3 are
  invisible to the user, which is a hint that this was always the right conclusion.
