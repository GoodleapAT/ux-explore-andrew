# The worked example

**The Thompsons. One example, used by every memo, mockup and walkthrough in this project.**

> **Who may write to this file:** any surface that can write. Edit in place. **Do not invent a second
> example**, and do not invent a value that belongs here without adding it here as well, or the next
> artefact will invent a different one.
>
> **This is the mock data, and it is deliberately complete.** Every value a screen might need is
> below. If something is missing, say so and add it rather than filling the gap locally.

Keeping this consistent is worth more than variety. Nine columns of a grid drawn from three
different inventions of the same customer is unreadable, and the inconsistency is the first thing a
reviewer notices and the least interesting thing to fix.

---

## Provenance, and what C refined

The narrative is the team's scenario **S15, "Multi-trade expansion (project umbrella, cash)"**, in
Confluence. **The sequence and the numbers below were refined by C on 11 Sep 2026** to make the
scenario internally consistent and to bring it onto our model. **Ten changes.** Eight on 11 September, two added on 15 September, and **items 4, 5 and 9 were each amended on 15 September** as the model moved. The weekday correction is noted after the list:

1. **The final bill arithmetic.** S15 shows $23,920 in its narrative and $21,120 in its payment plan,
   and flags the mismatch itself. Resolved by tying the change order to the final bill: the third
   milestone is two fifths of the original at $21,120, plus the $2,800 change order, which is
   $23,920. The mismatch existed because the script kept the change order in a note.
2. **The change order moved onto the main line.** S15 parks the rot discovery in its notes as
   material for a future scenario, and its execution table describes a financed variant. Here it
   happens, on the cash line, and the financed language is gone.
3. **The work sequence.** S15 installs windows first. The canonical dates in the modelling handoff
   have siding first, because those were written for the financed telling. Split into two tellings
   below so neither is lost.
4. **When the project is created.** S15 records a 12 August decision to pursue all three trades as
   an internal decision with no record behind it, and mints its spine at the first proposal. Corrected
   on 11 Sep to that date. **Moved to 18 August and back again on 14 Sep**, as the team's position
   changed repeatedly. **Now 4 August**, changed on 15 Sep: qualification is automatic on expressed
   intent, the Home App form expresses it, and creating the lead creates the project. **T-2 did not
   move. The rule held and the date did.** **Start selling is now 10 August**, and it creates nothing.
   *The team's script says 12 August throughout; ours no longer does. See item 10.*
5. **Vocabulary.** S15 is one of the six pages still written as Sale, Workstream and Job-as-spine.
   Translated throughout to Lead, Project and Job. **Updated twice on 14 Sep:** a lead carries several
   interests, so this file says interest where it used to say lead, and demand now starts at an
   **inquiry** before any lead exists. **And twice more on 15 Sep**: first the opportunity was added,
   then **the interest was retired** and the opportunity took over its status and its history. This
   file now says opportunity throughout and never says interest except as history.
   Nouns per `VOCABULARY.md`, chain per T-3.
6. **The property's build year.** Andrew's earlier standalone screens say 1996. The scenarios need a
   1978 build for the original single-pane windows to make sense. **1978 is canonical**; the 1996 is
   an error in the older file.
7. **No permit.** S15 says plainly that no permit is required on this job. The windows permit stall in
   memo 6 was imported from S16 and does not belong in the cash telling.
8. **The subcontractor is named.** S15 assigns windows to a subcontractor and flags cross-org crew
   assignment as unmodelled. Named here so a screen has something to show; the gap stands.
9. **How the three trades arrive. Changed 15 Sep 2026, and it is the largest departure in this list.**
   S15 has the customer raise the roof and the siding as two separate contacts. Here the roof is the
   only contact, and **windows and siding are opportunities recommended by DeDe on evidence**, marked
   worth raising by Renata Silva, and raised by her on the intake call. **Two reasons.** The old
   version had the windows record homeless for the whole gap before any lead existed. And the story
   tested three trades captured at once, which is the cheap case, while never showing where
   cross-sell demand lives. The reasoning is in `in-depth/the-opportunity.md` and the departure is in
   `DEVIATIONS.md`.
   **The homelessness disappeared hours later**, when item 4 moved the lead to the first contact, and
   the interest was retired later still. **The change stands on what is left of its second reason**: a
   trade that might sell and a trade being sold are different states of one durable record, and a
   customer with no demand at all can still carry opportunities. **All three trades are now
   opportunities**, including the one the customer asked for, so the story no longer has two kinds of
   demand in it.
10. **The front of the story is compressed, and a CSR is added. 15 Sep 2026, both at Andrew's
   instruction.** S15 runs its demand from 21 July to 12 August, twenty two days. **Ours runs 4 to
   10 August, six days**, and everything from 13 August onward is untouched, so the proposal, the
   presentation, the contract, the work and the money all keep their dates. **The storm moves to
   early August with it.** And **Renata Silva, a CSR on the front desk, takes the intake call and
   hands the lead to Priya**, where previously Priya did both. **What this costs is in
   `DEVIATIONS.md`**: the gap that made S15 test Start selling as a separate act is much shorter, and
   Northgate is now organised more like Brightline, which removes one axis of difference between the
   two scenarios.

**Dates run past today on purpose.** This is a designed narrative that has to reach a close-out, not
a report of where a real job stands.

**Weekdays corrected, 15 Sep 2026.** Eight rows of the sequence table carried the wrong weekday and
had done since 11 September. **Correcting them put the final bill on a Saturday and the final payment
on a Saturday**, so the close-out moved to Monday 28 September and Monday 5 October. Everything before
the close-out keeps its original date. **The arithmetic is untouched**: the three payments still total
$55,600 and the final bill is still $23,920.

---

## The contractor

**Northgate Home Services.** Multi-trade home improvement, around forty staff. An HVAC division and
an exteriors division covering roofing, siding and windows, sharing one sales desk and one back
office. Sacramento.

**Product tier: full platform.** Payments, selling and operations. Useful when drawing the other two
tiers by subtraction, and a reminder that this example exercises the fullest case.

| Person | Role | Where they appear |
|---|---|---|
| **Priya Raman** | Sales consultant, exteriors | **Takes the lead from Renata after the intake call.** Runs Start selling, prices the proposal, presents it, captures the decision, and owns the lead and the project. **She does not qualify anything; the contact qualified itself** |
| **Marcus Ellery** | Production coordinator | Runs the hand-off, builds the work packages, books the crews, raises the change order |
| **Dwight Okafor** | Exterior crew lead | The siding job. Internal crew of four |
| **Hector Salas** | Lead installer, Valley Glass and Trim | The windows job. **A subcontractor's crew on Northgate's job**, which the model does not handle |
| **Danny Cho** | HVAC service technician | The 2025 heat pump install and both maintenance visits |
| **Renata Silva** | CSR, front desk | Takes the 5 August intake call, works the exteriors template across all three trades, and hands the lead to Priya. **Added 15 Sep 2026** |
| **Alicia Moss** | Office manager | Intake in 2025, invoicing, payment recording |

**Suppliers.** Sierra Exterior Supply for the siding boards and trim. Delta Glazing Supply for the
window units. Valley Glass and Trim is the installing subcontractor, not a supplier.

---

## The customer

**Robert and Sara Thompson.** Customer since August 2025.

| Contact | Role | Detail | Note |
|---|---|---|---|
| **Sara Thompson** | Decision maker | sara.t@email.com, (916) 555-0188 | Prefers text. Signs the paperwork |
| **Robert Thompson** | Billing | r.thompson@email.com, (916) 555-0142 | Defers to Sara on cost. Raised the roofing himself through the Home App |

## The property

**1428 Maple Ave, Sacramento CA 95818.** One property; the Thompsons hold no others.

- Two storey, 2,140 square feet, **built 1978**
- Siding: original wood lap on all elevations. South and west are faded and cracking
- Windows: fourteen original single-pane units. Two on the south elevation are out of square
- Roof: asphalt shingle, near end of life. Storm damage August 2026
- Access: dumpster goes on the north driveway. Ladder work needed on the south elevation
- **HOA controls exterior colour.** Approval needed before any exterior work
- Gate code 4417. Dog in the back yard, friendly but loud

## History, before this scenario

**HVAC, central air and a heat pump conversion. Closed 24 September 2025.**

A phone enquiry in August 2025, when the old system failed in the August heat. One lead, one
proposal, one scope, one job. $14,800 on a ten-year loan. Installed by Danny Cho. **Proof that the
simple case still looks like today's product.**

- Installed equipment: a Carrier heat pump, registered against the property, ten years parts to
  September 2035
- **Site photographs from the install, September 2025**, taken for the equipment record. Several show
  the south and west elevations in the background, with the wood lap faded and cracking
- **Two opportunities recommended on 26 September 2025**, two days after the HVAC project closed, off
  those photographs and off the property record. **Siding**, from the faded and cracking wood lap.
  **Windows**, from the 1978 build and its original single-pane glazing. **Both sit Open and unmarked
  for eleven months**, and neither is mentioned to the Thompsons until 5 August 2026. **Changed 15 Sep
  2026**, at Andrew's instruction: they used to be recommended on the morning of the roofing contact
- **A maintenance plan was sold at closeout**: two visits a year, $29 a month, renewing 24 September.
  **Not in S15.** It comes from this file. Whether it joins the scenario is an open request to the
  team, recorded in the deviations register
- Visits so far: 14 October 2025, complete, no findings. 18 March 2026, complete, refrigerant topped
  up and the condenser fan motor noted as noisy. Both entitlements for year one used
- Year one billing: twelve charges of $29 collected on a Visa ending 6411. No closing balance, by
  design

---

## Demand: one inquiry, three opportunities, one lead that closes in August

**Restated four times on 15 September 2026**, which is a cost worth seeing rather than hiding. The
demand chain is Inquiry or Prospect, then Lead, per T-3, and a lead creates a project, per T-2.
**The Opportunity is ours and is new on 15 September**; its reasoning is in
`in-depth/the-opportunity.md` and its values are in `VOCABULARY.md`. **The Interest no longer exists.**

**Three opportunities, and two of them are nearly a year old.** All three are the same kind of record
and they differ only in where they came from and when.

**Siding and windows have been Open since 26 September 2025**, recommended two days after the heat
pump project closed, off the install photographs and the property record. **Nobody has marked them
and nobody has mentioned them to the Thompsons.** They sit under the customer with no demand beside
them, which is the state the customer record spends most of its life in.

**Roofing arrives on Tuesday 4 August 2026** and is a different thing entirely: the customer asked
for it.

| Opportunity | Origin | The evidence, or the customer's words |
|---|---|---|
| **Roofing** | **The customer.** Home App, by Robert, the morning after the storm | "Found shingles in the yard after the storm last night. Someone should look at it before winter." |
| **Windows** | **Recommended by DeDe, 26 Sep 2025.** Eleven months old and never mentioned | Fourteen original single-pane units on a 1978 build, still the ones the house was built with |
| **Siding** | **Recommended by DeDe, 26 Sep 2025.** Eleven months old and never mentioned | Photographs taken on the heat pump install two days earlier show the south and west wood lap faded and cracking. **Northgate's own crew took them**, on Northgate's own job |

**The inquiry, and it qualifies itself.** Robert's contact names a trade and a property, so intent is
expressed and the contact is qualified without anybody marking it. **The lead is created that
morning, and creating the lead creates the project. Nobody at Northgate is present for either.**

**Roofing goes on the lead immediately**, because it is what the contact was about. **Windows and
siding stay Open**, and Renata Silva marks both as worth raising when she opens the lead later that
morning. **That is the first time anybody has looked at either of them in eleven months.** Nobody has
committed to selling anything.

*C's reading, not Andrew's ruling: that the trade named by the contact joins the lead at once and the
rest join at Start selling. It is what gives the six days something to be. Flagged in the
opportunity document.*

**The call, Wednesday 5 August.** Renata telephones Sara. The exteriors intake template runs with the
roofing questions, **and now also with the windows and siding questions, because both opportunities
are marked worth raising.** Sara engages on the siding and is lukewarm on the windows, and their words
are captured against each opportunity. All three trades are discussed in one conversation, which is
the case the team's lead-granularity position rests on.

- **Siding.** "The south side is looking really tired, it's cracking in places. What would a full
  wrap cost, and could you do it at the same time as the roof?"
- **Windows.** "They're original, but they still work. I've never really thought about them."

**Start selling, Monday 10 August.** **Renata hands the lead to Priya after the call**, and Priya puts windows and siding on the lead alongside roofing.
**This is not qualification and it creates nothing**; the lead and the project have existed for three
weeks. It is the act that says these three are the sale.

**The gap is six days, and it was twenty two until 15 September.** Qualification and Start selling
are still separated, with the lead alive throughout and a hand-off from the front desk to the sales
consultant inside the gap. **S14's two moments are two minutes apart**, so the contrast survives at
two orders of magnitude rather than three.

**Status through the scenario.**

| | 4 Aug | 5 Aug | 10 Aug | 18 Aug | 24 Aug |
|---|---|---|---|---|---|
| **The inquiry** | Qualified, automatically | | | | |
| **Roofing** | On a lead | Detail captured | | **Back to Open.** Declined for this season, revive March 2027, estimate retained at $38,900 | |
| **Windows** | Open, worth raising | Detail captured | **On a lead** | **Won** | |
| **Siding** | Open, worth raising | Detail captured | **On a lead** | **Won** | |
| **The lead** | Active | | | | **Closed.** Nothing left on it |
| **The project** | Created | | | Sold | Contract signed, two jobs |

**The roofing opportunity is the case this whole model exists for.** It was raised by the customer,
put on a sale, priced at $38,900 as an option, presented, and declined. **It is now free-standing
again with its whole history in one place**, a revive date of March 2027, and a note to lead with the
August storm photographs. **It never becomes a scope or a job**, and it does not need the lead kept
alive to survive.

**Note what the lead looks like for those six days**, because no mock has drawn it: a live lead with a
live project behind it, one opportunity on it, two more sitting Open against the customer, no
proposal, no money. **That is the state the project's thinnest form has to carry**, and it lasts
six days rather than the two minutes it lasts in S14, and there is a hand-off inside it.

**And note when the lead closes: 24 August, at the hand-off.** Not at the end. From then until
5 October the project delivers with no lead behind it at all, which is a shape nothing has drawn
either.

### What changed across the four restatements

So a screen built on any older version can be corrected. **All four were on 15 September.**

| Was | Now |
|---|---|
| Three lead records, one per trade | **One lead** |
| Two inquiries, roofing and siding, resolving into one lead | **One inquiry, roofing only** |
| Siding raised by Sara on a follow-up call she made | **Siding recommended by DeDe and raised by Priya**, with Sara's words now an answer rather than the reason for the call |
| Windows an interest from 4 August with no inquiry behind it and nowhere to live | **Windows an opportunity**, and so are the other two |
| The deferred trade a lead of its own, then an interest on a live lead | **A free-standing opportunity with a history**, needing no lead |
| **The lead and the project born 10 August**, at an act of qualification | **Born 4 August, automatically.** Nobody is present for it |
| **10 August was qualification** | **10 August is Start selling**, and it creates nothing |
| **The lead ran to the close** | **The lead closes 24 August**, at the hand-off |
| Three interests on a lead | **Three opportunities. The interest is retired** |

**Every estimate, date, figure and outcome is unchanged through all four.** Sara's siding words are
unchanged and have moved from being the reason for a call to being an answer during one. Her windows
words are new, because the old file had nobody asking her about windows at all.

**One claim moved three times in one day, which is worth recording as a warning.** Routing a new
inquiry into an existing lead was: needed on day one, then unproven, then the universal rule, and now
**the rule but only while a lead is open.** Nothing was built on any of the first three, which was
luck rather than judgement.

**The roofing opportunity's note**, captured in the room on 18 August by Priya Raman and now part of
that opportunity's own history:

> Took siding and windows and asked to come back to the roof in spring. Sara said the roof is "not
> leaking yet". Worth leading with the August storm photos when we call back.

---

## The project

**Restated three times on 14 September 2026 and twice more on 15 September**, which is itself worth
knowing. **See T-2; this file does not state the rule, it only applies it.**

**What the two changes of 15 September did.** The first changed what feeds the project and left the
date alone. **The second moved the date, from 10 August to 4 August**, because qualification turned out
to be automatic on expressed intent. **T-2 never moved through any of it.** The rule has held since
14 September; what keeps changing is when a lead comes into being.

**"Siding and windows, Thompson."** Created **Tuesday 4 August 2026**, the moment Robert's Home App
contact qualified itself and the lead came into being. **Creating the lead created this, and nobody
at Northgate was present for it.** Nothing was priced for another nine days.

One customer. One property. One inquiry and three opportunities behind it. One lead carrying three
opportunities on it while it was selling. One proposal covering all three. Two committed scopes. **One
opportunity declined and now free-standing**, needing no lead to survive.

**Its name changes twice, and the second change is the interesting one.**

| Date | Contents | Name |
|---|---|---|
| 4 August | Roofing | "Roofing, Thompson" |
| 5 August | Roofing, siding, windows | "Roofing, siding and windows, Thompson" |
| 18 August | Siding and windows, roofing deferred | **"Siding and windows, Thompson"** |

**So the name grows and then shrinks.** The naming decision says growing is the advertisement and says
nothing about shrinking, and a name losing a trade reads as something being lost rather than something
being decided. **Open, and recorded in the beats document.** Anybody can rename it in place at any
point, which is the other half of the naming ruling of 15 September.

**Every position this date has held**, because six in two days is worth being able to see.

| The date | The reason given | When |
|---|---|---|
| 10 August | Pursuit. Somebody starts working the lead intending to write a proposal | 10 Sep, ours |
| At the first proposal | The team's DRAFT v3 | Superseded 14 Sep |
| 18 August | At the win, with contracts signed | 14 Sep, theirs, for a few hours |
| 10 August | Intent to sell expressed at qualification | 14 Sep, theirs |
| 10 August | Creating the lead creates the project | 14 Sep, theirs, the same moment renamed |
| **4 August** | **Same rule. Qualification turned out to be automatic on expressed intent, so the lead exists from the first contact** | **15 Sep, ours** |

**The last move is the only one that did not change the rule.** The five before it argued about what
creates the project. This one accepts the answer and changes when the thing that creates it comes into
being. **That is a different kind of move and it is worth distinguishing**, because a design built to
tolerate the trigger moving is not automatically built to tolerate the trigger firing at the first
contact instead of at an act somebody performs.

**The thing this example is now good for.** The lead and the project both exist from **4 August** to
the close, so the useful question is no longer whether the container is needed before a win. It is
**what each of them holds while both are live**, and that is a UX question rather than a modelling
one. **And for six days of it, neither holds much at all**, which was a twenty two day hole until
15 September and is now a short one with a hand-off in it.

**Roofing is the interesting case.** It went on the lead, it was priced as an option on the
proposal, it was declined, and it never becomes a scope or a job. **If the lead does not hold its
whole story in one piece, the split between lead and project is wrong.**

---

## The proposal

Prepared Thursday 13 August, three days before anyone saw it. One proposal, three options, one per
trade.

| Option | Priced | Presentation | Outcome |
|---|---|---|---|
| **Roofing** | 13 Aug, $38,900 | Offered first | Declined for this season, 18 Aug. Price retained |
| **Siding** | 13 Aug, $34,200 | Offered first, alongside roofing | Selected |
| **Windows** | 13 Aug, $18,600 | **Priced and deliberately held back.** Raised second, after roofing and siding | Selected |

**Versions.** Version one on 13 August, never sent. Version two presented in person on 18 August at
the kitchen table. Version three reworked in the room to siding and windows, total $52,800, and
accepted the same evening. Revised again on 21 August from what the site assessment found, with the
customer's existing link resolving to the current version and a fresh link sent as well.

**The session, 18 August.** Roofing and siding presented first. Then windows raised. The customer
takes windows and siding and defers the roof. **The trade that was held back wins and the one that
was offered loses**, which is the whole reason priced and offered are different things.

## The site assessment

One record, two sittings.

- **5 August, on the intake call.** An exteriors intake template worked over the phone. Grounding
  questions, not measurement.
- **20 August, on site.** The full assessment. Fourteen window openings measured unit by unit. The
  south and west elevations walked and measured. Photos and notes tagged per trade. Roofing noted for
  the future, not measured.

Findings that changed the price: two south elevation window openings out of square, needing trim
work. Siding area confirmed at 2,140 square feet across two elevations.

## Scope detail

### Siding, $34,200 rising to $37,000

Full wrap of the south and west elevations in fibre cement lap siding: tear-off, house wrap, trim
and paint.

| Line | Quantity | Amount |
|---|---|---|
| Fibre cement lap siding, 8.25 inch, Cobble Stone | 2,140 sq ft | $18,690 |
| Tear-off and disposal, two layers | 2,140 sq ft | $4,280 |
| House wrap and flashing | 2,140 sq ft | $3,210 |
| Trim, corners and paint | 1 lot | $8,020 |
| **Sheathing repair**, added by the change order | 40 sq ft | $2,800 |
| | | **$37,000** |

### Windows, $18,600

Replacement of fourteen original single-pane units with double-glazed vinyl.

| Line | Quantity | Amount |
|---|---|---|
| Double-glazed vinyl units, low-E, argon, U-factor 0.28 | 14 | $11,760 |
| Removal and disposal | 14 | $1,680 |
| Interior and exterior trim | 14 | $3,220 |
| Out-of-square correction, two south elevation openings | 2 | $1,120 |
| Delivery and handling | 1 lot | $820 |
| | | **$18,600** |

*Note: in the financed telling this last line is a building permit. In the cash telling no permit is
required, so the value sits on delivery and handling instead. Same total.*

---

## Telling A: cash, windows first

**This is S15 and the one to build now.** The customer pays cash in three parts.

### Money

| | Trigger | Amount | Status |
|---|---|---|---|
| **Contract** | Signed 24 Aug | $52,800, rising to $55,600 | Amended 18 Sep |
| Milestone one, a fifth | At signing | $10,560 | Paid by check, 24 Aug |
| Milestone two, two fifths | On the first trade completing | $21,120 | Paid by check, 15 Sep |
| Milestone three, two fifths plus the change order | On both trades completing | **$23,920** | Issued 28 Sep, paid by check 5 Oct |

Collected before the final bill: **$31,680**. Master invoice total **$55,600**. Balance due after the
second payment: **$23,920**.

**Costs and margin.** Siding **$25,530**. Windows **$12,834**. Total $38,364. Project margin **31%**.
Per-job margin is not available, because revenue landed on the project and costs land on the jobs.

*Corrected 13 Sep 2026.* The first version of this file said $21,940 and $16,410, which also comes to
31% at the project but implies a 12% margin on windows and 41% on siding, a spread that would draw a
question in review having nothing to do with the design. CD's figures are canonical. Memo 6's figure
of $23,060 was simply wrong: it implies 58%.

### The sequence

| Date | What happens | Which view changes |
|---|---|---|
| Mon 24 Aug | Customer chooses cash. Payment plan agreed, contract e-signed, deposit taken by check. Hand-off. **Two jobs created**, siding to the internal exterior crew, windows to Valley Glass and Trim | Project, job |
| Tue 25 Aug | Two work packages built: work order, materials list and task list for each | Job |
| Wed 26 Aug | One coordinated post-sale inspection visit. Scope confirmed per trade, photos tagged to each. Both material orders placed | Job |
| Thu 27 Aug | Permitting reviewed. **None required on this job.** HOA colour approval already held from the proposal stage | Job |
| Fri 28 Aug | Crews assigned. Two dates committed with Sara in one conversation: windows 8 to 10 Sep, siding from 15 Sep | Job |
| Wed 2 Sep | Window units delivered from Delta Glazing Supply | Job |
| Tue 8 to Thu 10 Sep | **Windows installed** by Hector Salas and crew. Before, during and after photos. Units registered to the property | Job |
| Fri 11 Sep | Windows walkthrough with Sara, warranty registered, review requested. **Windows complete** | Job, project |
| Tue 15 Sep | Milestone two invoiced and paid by check. Siding boards delivered from Sierra Exterior Supply | Project, customer |
| Wed 16 Sep | **Siding tear-off starts** on the south and west elevations | Job |
| Thu 17 Sep | Pulling the old north-wall boards exposes rot nobody could have quoted. Forty square feet, photographed before anything is covered. **Change order raised, plus $2,800** | Job, project, customer |
| Fri 18 Sep | Sara signs the change order. Contract amended to $55,600. Rot repair proceeds | Project |
| Fri 25 Sep | **Siding complete.** Final photos, checklist closed, walkthrough with Sara | Job, project |
| Mon 28 Sep | Both trades complete. Final bill issued, $23,920. Margin reads 31% at the project | Project, customer |
| Mon 5 Oct | Final payment by check. Project closes. Job debrief captured, warranties filed, review requested | All three |

### Task lists, for the work packages

**Windows**, eight steps: work package built, units ordered, delivery confirmed, crew and date
confirmed, pre-work photos, install, walkthrough and warranty, closeout. Complete by 11 September.

**Siding**, eight steps: work package built, materials ordered, delivery confirmed, crew and date
confirmed, tear-off, sheathing repair (added by the change order), install and paint, walkthrough and
closeout.

### Waiting on, for the sub-status block

| Register | Value | Reads as |
|---|---|---|
| HOA colour approval | Approved, 14 Aug | Settled |
| Permit | Not required | Not applicable |
| Window units | Delivered 2 Sep | Settled |
| Siding materials | Delivered 15 Sep | Settled |
| Subcontractor insurance certificate | On file, expires Jan 2027 | Settled |

**Nothing in this telling is ever blocked.** That is worth knowing when drawing it: the cash,
no-permit telling has no amber anywhere, and a grid with no attention state in it is a fair test of
whether the screens work without one.

---

## Telling B: financed, siding first

**Not for now. This is the next run, and it is the team's S16.** Recorded here so the two do not
drift apart.

Same customer, same property, same lead and its three opportunities, same proposal, same declined roof, same two jobs,
same trade values. Everything up to 21 August is identical. The differences:

- **Tender.** One GoodLeap application from the proposal, approved for the full $52,800 at fifteen
  years and 6.99%, around $474 a month. Financing agreement and contract e-signed in the same
  sitting. No deposit.
- **Money mechanics.** Funding releases per job against that job's own work evidence, so the two
  lanes draw on one shared account at different times. A notice to proceed gates whether work can
  start at all.
- **Sequence.** Siding first, starting 2 September. Windows second, because **a building permit is
  required in that telling** and plan review holds it for twenty six days.
- **The change order.** Lands on a financed account and needs re-approval on the same account rather
  than only a signature. No new credit pull, because the amount sits inside the approved envelope and
  the added scope inside the underwritten category.
- **Canonical dates for this telling**, from the modelling handoff: signed 18 August, early production
  21 August, install day 2 September, closeout 24 September.

The rest of this telling gets filled in when it is run.

---

## Record text

For notes, history and activity cards, so every screen quotes the same words.

### Pinned notes, on the customer

- Gate code 4417. Dog in the back yard, friendly but loud.
- HOA requires colour approval before any exterior work.

### Notes

| Date | Type | On | Text | By |
|---|---|---|---|---|
| 17 Sep | Site note | Siding job | Rot behind the siding on the north elevation, about forty square feet, worse than the walk suggested. Photographed before anything was covered and raised a change order. Sara approved by phone. | Marcus Ellery |
| 20 Aug | Site assessment | Site assessment | Fourteen window openings measured unit by unit. Two on the south elevation are out of square and will need trim work. Siding confirmed at 2,140 square feet across two elevations. | Priya Raman |
| 18 Aug | Decision | Roofing opportunity | Took siding and windows and asked to come back to the roof in spring. Sara said the roof is "not leaking yet". Worth leading with the August storm photos when we call back. | Priya Raman |
| 5 Aug | Intake | Customer | Worked the exteriors intake template. Raised the siding and the windows from DeDe's recommendations. Sara was keen on the siding once she heard we had photos of it from the heat pump job, and asked whether it could ride the same visit as the roof. Lukewarm on the windows. Handing to Priya. | Renata Silva |
| 18 Mar | Service visit | Maintenance plan | Condenser fan motor is noisy and the unit is a year old, so it is a warranty question rather than a repair. Flagged to watch at the autumn visit. | Danny Cho |
| 10 Aug 2025 | Intake | Customer | Came in from a phone enquiry, system failed in the heat. Sara decides, Robert handles billing. | Alicia Moss |

### History, newest first

| Date | Event |
|---|---|
| 5 Oct | Final payment received. Project closed |
| 28 Sep | Final bill issued, $23,920 |
| 25 Sep | Siding complete |
| 18 Sep | Change order signed. Contract amended to $55,600 |
| 17 Sep | Change order raised on the siding scope, plus $2,800 |
| 15 Sep | Milestone two paid, $21,120 |
| 11 Sep | Windows complete |
| 24 Aug | Contract signed, cash plan agreed, deposit received. Two jobs created. **The lead closed**, having nothing left on it |
| 21 Aug | Proposal revised after the site assessment |
| 18 Aug | Proposal accepted at $52,800. Roofing deferred to spring. Project renamed "Siding and windows, Thompson" once its contents settled |
| 13 Aug | Proposal prepared, three trades priced |
| 10 Aug | **Start selling.** Windows and siding put on the lead alongside roofing. **Nothing was created**; the lead and the project were three weeks old |
| 5 Aug | **Intake call.** Renata works the exteriors template with Sara and raises all three trades, then hands the lead to Priya. Siding answered warmly, windows lukewarm. **Detail captured against each opportunity.** Both stay Open until Start selling |
| 4 Aug | **The inquiry, and it qualified itself.** Robert raises the roof in the Home App, which names a trade and a property, so **the lead and the project were created that morning with nobody present.** **Two opportunities recommended by DeDe the same day**, windows on the build year and siding on the heat pump install photographs. Both marked worth raising by Renata |
| 24 Sep 2025 | HVAC project closed and paid. Maintenance plan sold |

---

## What is deliberately not specified

Do not invent these, and say so if a screen needs one.

- **Photo and document contents.** Counts and captions only.
- **Task-level assignees** beyond the crew lead named per job.
- **Time entries and labour hours.** Costs are given as totals per job.
- **Anything about the roofing scope beyond its estimate.** It was priced and never assessed.
- **The subcontractor's own paperwork** beyond the insurance certificate.
- **Any second property or second customer.** The Thompsons hold one property and there is no
  co-signer.
