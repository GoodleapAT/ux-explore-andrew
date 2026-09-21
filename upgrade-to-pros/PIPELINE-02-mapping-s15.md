# The pipeline, mapped onto S15

**A sketch of how the five primitives might land on the Thompson scenario. 16 September 2026.**

> # Do not act on this. It is a sketch, not a specification
>
> **Nothing here has been agreed.** No screen should be drawn from it, no component should be built
> for it, and no value in it should be treated as canonical. **It exists so the shape of the problem
> can be looked at before anybody commits to it.**
>
> **Read `PIPELINE-01-structure.md` first.** This document assumes the five primitives and does not
> re-explain them.
>
> **The scenario's own data is in `S15-DATA.md`**, which is settled. Where this sketch and that pack
> disagree about a date or a value, **the pack wins** and this document is wrong.
>
> **Section 5A was added on 16 September, after a conversation that resolved most of section 5.**
> Read 5A first. **Sections 5 and 6 are kept exactly as written**, because the route to the answer is
> worth more than a tidy document, and because two of section 5's five problems are still live.

---

## 1. The two organisations are not alike

Dana's configuration was written for **a mid-size roofer doing mixed retail and insurance work**, one
trade, one job per sale. Northgate is **multi-trade home improvement**, HVAC plus roofing, siding and
windows, and S15 is specifically **one project carrying two jobs.**

| | Dana's Roofing | Northgate in S15 |
|---|---|---|
| Trades per sale | One | **Two** |
| Jobs per sale | One | **Two, under one project** |
| Funding | Cash, financed and insurance | **Cash only** |
| Insurance | A major path | **Absent** |
| HOA | Active on some properties | **Absent** |
| Permits | By jurisdiction and scope | **Required on both jobs** |
| Roles on a job | Office manager, sales rep, production manager | **CSR, sales consultant, production coordinator, two crew leads, office manager** |

**The one that breaks the configuration is the second row.** Every stage, gate and task in Dana's
configuration assumes one card moving through one pipeline. S15 has two jobs that must be scheduled,
permitted, installed and completed separately, under a project that is invoiced once. **Dana's
configuration has no concept of that and cannot be stretched to it by adding stages.**

---

## 2. Which sub-statuses S15 lights

**This is the part that maps cleanly, and it maps better than what the data pack currently says.**

| Sub-status | In S15 | Reading |
|---|---|---|
| **Permit** | **Lit, on both jobs.** Not required → **Applied** (7 Aug) → **Approved** (11 Aug) → *Final inspection passed, never reached* | **The only thing in the entire scenario anybody waits on.** A textbook sub-status: external, ordered, and the contractor cannot accelerate it |
| **Materials** | **Lit, on both jobs.** Not ordered → Ordered → Confirmed with date → **Delivered** (14 Aug) | Fits, though the scenario compresses it into one beat with no drama |
| **Financing** | **Lit and frozen at *Cash*.** It never moves | Worth drawing precisely because it never moves. A universal sub-status sitting at its first value for the whole run |
| **Insurance** | **Not activated.** The attribute rule does not match | **Eligibility, not gating.** Hidden or marked not applicable, never blocked or pending |
| **HOA** | **Not activated.** Same | Same |

**The data pack currently says "pending", "issued" and "deliveries received", which are inventions.**
The value sets above are canonical and should replace them, **and that is the one change in this
document I would make now rather than later.**

**Note what the permit's fourth value does.** *Final inspection passed* is in the value set and S15
never reaches it, because there is no inspection anywhere in the scenario. **So the sub-status ends
the run in its third value out of four**, which is a more honest and more interesting thing to draw
than a completed one.

---

## 3. Which gates would fire, and the answer is almost none

| Gate | In S15 |
|---|---|
| Leads & Sales → Production, on financing NTP or claim approved | **Never fires.** Funding path is cash, so the condition is not active |
| Ops intake → Orders & scheduling, on HOA approved | **Not activated.** No HOA |
| **Orders & scheduling → Final checks, on permit approved** | **This is the one.** Permits applied 7 August, approved 11 August, crews and dates confirmed 12 August. **The gate is satisfied the day before the work it gates.** |
| Final checks → Installing, on day-before checks complete | Would fire, and the scenario does not describe any day-before checks |
| Closeout → Invoiced, on permit final inspection passed | **Cannot be satisfied**, because S15 has no inspection. **Under Dana's configuration this scenario could never be invoiced** |

**Two findings sit in that table.**

**The scenario has exactly one live gate**, and it is satisfied without incident. Everything else is
either inactive by attribute rule or would be satisfied silently. **This is the same fact the script
states about itself**: nothing is ever blocked and the permits are the only dependency.

**And the last row is a genuine incompatibility.** Dana's configuration blocks invoicing until a
permit's final inspection has passed. S15 invoices on 24 August with no inspection in the story at
all. **Either Northgate's configuration has no such gate, or the scenario is missing a beat.** It is
worth knowing which.

---

## 4. Where the ten stages land, if they land at all

**Following section 7 of the structure document, the stages split across three records.** This is the
sketch, and every row is arguable.

| Dana's stage | Carried by, in S15 | Beats | Notes |
|---|---|---|---|
| New lead | **Lead** | 3 | Minted by the call. Nobody creates it |
| Working | **Lead** | 4 to 7 | Second trade added, visit booked, assessed and presented. **Dana's collapses contacted, inspected and proposal-sent into one stage, and S15 does the same thing for the same reason**: assessment and presentation are one visit |
| Sold | **Lead**, and then it closes | 8 to 10 | Contract, deposit, hand-off. **The lead closes here**, which Dana's configuration has no equivalent for |
| Ops intake | **Job ×2** | 11, 14 | Work orders, materials lists, scopes refined, permits applied for |
| Orders & scheduling | **Job ×2** | 15 to 17 | Permits issued, crews and dates, materials delivered |
| Final checks | **Job ×2** | — | **No beat.** The scenario does not describe a day-before check |
| Installing | **Job ×2, staggered** | 18 | Roofing 17 to 18 Aug, siding 19 to 21 Aug |
| Closeout | **Job ×2** | 19 | Walkthroughs, warranties, review requested |
| Invoiced | **Project** | 20 | **One invoice for two jobs.** Not a job stage |
| Closed | **Project** | 21 | Paid, and the project closes |

**Three things this table makes visible.**

**The two jobs occupy the same stage at almost every point, then diverge for three days.** From beat
11 to beat 17 they move together. At beat 18 roofing reaches Installing two days before siding, and
**on 18 August roofing is in Closeout while siding has not started.** That is the only moment the two
cards are in different columns, and **it is exactly the screen the script asks for at beat 18.**

**The last two stages are not job stages and pretending they are breaks the money.** One invoice
covers two jobs. If Invoiced is a job stage, either both jobs sit in it against one invoice, or the
invoice belongs to neither.

**Final checks has no beat at all.** Either Northgate's configuration does not have that stage, or the
scenario skips a real step. Given the script says nothing is ever blocked, **the absence may be the
scenario being tidy rather than the configuration being wrong.**

---

## 5A. What changed on 16 September, after this document was first written

**Andrew's call, in conversation: multiple trades stay bundled under one lead card on the Leads &
Sales board, and they separate when the lead closes.** That one decision resolves most of section 5
and changes the shape of the answer. **The sections below it are kept as written**, because the
route to this is worth more than a tidy document, but read this first.

### It settles the sales card

**A salesperson works the customer, not the roof.** One call, one visit, one proposal covering both
trades. Two cards that always moved together would be noise on a board whose job is to show you what
to work on.

**And Dana's configuration already agreed.** It collapses contacted, inspected and proposal-sent into
one stage called Working, because its reps inspect and quote in a single appointment. **Selling has
fewer distinct positions than production because the work is one conversation**, and a bundled card is
the same instinct one level up.

### It removes the object we had been reaching for

The argument for a per-trade selling record was that **the sales board needed card-shaped things**.
If the lead is the card, it does not.

**The decline case is the test, and it passes.** Suppose the Thompsons took siding and declined
roofing. One lead card moves to Sold. One job is born. **The declined roof rolls up to the roof
asset**, which is the durable per-trade-element record on the property. **Nothing needs a separate
record to die in**, which is what the Opportunity was mostly for.

**So the shape is three objects, but not the three we started with:**

| Object | What it is | Lifespan | Card on |
|---|---|---|---|
| **Asset** | One trade-specific element of the property: the roof, the siding, the HVAC | **Permanent.** Implied by the property | No board. It is a record, not work |
| **Lead** | One selling episode, carrying any number of trades | **Bounded.** Opens on contact, closes at the hand-off | **Leads & Sales** |
| **Job** | Execution of one committed trade | **Bounded.** Born at the hand-off, ends at close-out | **Production** |

**Naming is unsettled.** *Asset* is free across the glossary, the vocabulary and the object register.
*Category*, which is the word Andrew used, **collides with installation category**, a financing
concept in the team's own open items with values like ROOF_1. *Element* is already defined in our
vocabulary as one element of work someone might buy.

### And it resolves the board problem, which stops being a problem

**Section 5 listed "boards are stage ranges and three records now carry the stages" as the second
failure. Under this call it is not a failure, it is the design.**

| Board | Shows | Owned by |
|---|---|---|
| **Leads & Sales** | **Lead** cards | The sales desk |
| **Production** | **Job** cards | The production coordinator and the crews |
| **Closeout & Payment** | **Project** cards | The back office |

**Three boards, three record types, each aligned to the team that owns it**, which is what a board was
always defined to be: a filtered view usually aligned to a team. **The stage-range definition was the
accident, not the three-board structure.**

**It also fixes the first failure in section 5.** The project was going to be invisible, because leads
were on one board and jobs on another and the container had nowhere to sit. **It now surfaces on the
third board exactly when it becomes interesting**: complete-but-unbilled, then billed-but-unpaid. That
is an office manager's queue, precisely, and in S15 the project enters it at beat 19 and leaves at
beat 21.

### Walked against S15

| Card | Born | Moves | Leaves |
|---|---|---|---|
| **Lead, "Roofing and siding, Thompson"** | Beat 3, 8:07am | New lead (3) → Working (4 to 7) → Sold (8) | **Closes at beat 10** and leaves the board |
| **Job, roofing** | Beat 9 | Ops intake (11, 14) → Orders & scheduling (15 to 17) → Installing (18) → Closeout (19) | Complete, 21 Aug |
| **Job, siding** | Beat 9 | Same, **two days behind from beat 18** | Complete, 21 Aug |
| **Project** | Exists from beat 3, **surfaces at beat 19** | Invoiced (20) → Closed (21) | Paid, 26 Aug |

**The only moment the two job cards are in different columns is 18 August**, where roofing is in
Closeout and siding has not started. **That is exactly the screen the script asks for at beat 18**,
and it is the payoff of staggering the trades.

### The uncomfortable consequence

**The moment one card becomes two is the hand-off, and that is beat 9, which the script marks "no
screen needed for demo".**

**The single beat where the product's structure changes shape is the one being skipped.** Everything
before it is one card carrying two trades; everything after it is two cards under a container. Nobody
has drawn that transition, and the scenario as written does not ask for it.

### Two things still open

**What the lead card shows when its trades disagree.** In S15 they never do, both sell together. A
lead where roofing is quoted and siding is still being measured has **two internal states and one card
position**, and something has to resolve them. Dana's Working stage absorbing three sub-steps may be
exactly how.

**Whether a lead where only some trades sold still moves to Sold.** Probably yes: **the episode is
over either way**, and the unsold trade now has somewhere to live.

---

## 5. What does not fit, and this is the useful part

**Five problems, in the order they would hurt.** **Two of these were resolved by section 5A** and are
marked. **Three are still live.**

**One card, two jobs, one project. RESOLVED by 5A**, the project surfaces on the third board. The whole primitive set is built around a card moving through
stages. S15 has **two cards under a container that itself has no stages**, because the project derives
its label and explicitly carries no configuration. **So what does a board show: two job cards, or one
project card?** If two, the project is invisible on the board that matters most. If one, the two jobs'
genuinely different stages have to be summarised into a single position and the summary rule does not
exist.

**Boards are stage ranges, and three records now carry the stages. RESOLVED by 5A**, the three boards become three record types. A board defined as "stages 1 to
3" was coherent when one card traversed all ten. **Now the Leads & Sales board is a view over Leads,
the Production board is a view over Jobs, and the Closeout & Payment board is a view over Projects.**
That is three different record types, not three ranges. **The reference itself flags filtering boards
by attribute as an unbuilt extension**, and this is a bigger change than that.

**A sub-status on which record?** The permit is per job in S15, two permits for two jobs. But the
reference's own open question asks about "a permit shared across sibling jobs", and a single permit
covering both trades is plausible in other jurisdictions. **The primitive assumes one card owns one
sub-status**, and a shared external dependency has nowhere to sit.

**Tasks attach to a stage, and the project has no stages.** Anything cross-job, such as the single
customer conversation at beat 16 that produced two schedules, **has nowhere to attach.** The team's
own material names this as an open cross-job question.

**The invoicing gate cannot be satisfied.** Section 3, last row.

---

## 6. What I would keep regardless of how this resolves

**Four things are sound and independent of every problem above.**

- **The four task states.** Complete, incomplete, **not applicable** which is system-set, and
  **skipped** which is person-set. Directly usable on S15's checklists at beats 14, 15 and 18, and the
  not-applicable-versus-skipped distinction is the sort of thing that is very hard to add later.
- **The sub-status definition**, and its test: **if the contractor can move it themselves it is a
  stage or a task, and if they can only wait on somebody else it is a sub-status.** S15's permit
  passes that test cleanly and nothing else in the scenario does.
- **Eligibility versus gating.** S15 has both: insurance and HOA are eligibility, the permit is
  gating, and **they should not look alike on screen.** One says ignore permanently, the other says
  work toward this.
- **The permit and materials value sets.** Canonical, and better than what the data pack currently
  invents.

---

## 7. The questions this raises, for later

**Not for CD to answer and not for this round.**

1. **What is on a board when a project has two jobs?** Two job cards, one project card, or a project
   card that expands.
2. **If boards are now views over record types rather than stage ranges, are they still boards?**
3. **Where does a cross-job task attach**, when the project carries no configuration by design.
4. **Can a sub-status belong to more than one card**, for a permit shared across sibling jobs.
5. **Does Northgate's configuration have Final checks and the final-inspection gate at all**, or is
   S15 simply a tidier story than a real job.
6. **Does the derived project label and a configured stage set coexist**, or does one of them have to
   give way.

---

## Learned from

- **16 Sep 2026.** Andrew asked whether the pipeline was written down anywhere. It was, twice, and
  **the fact that it no longer matched the entity model was recorded nowhere.** The structure document
  and this one exist so that CD can understand the shape before anybody decides how much of it to use.
- **16 Sep 2026.** Mapping it onto S15 was more useful than expected: **the scenario turns out to have
  exactly one live gate and one live external dependency**, which is the same thing the script says
  about itself in a section listing what it deliberately lacks. **Two independent readings agreeing is
  worth more than either.**
