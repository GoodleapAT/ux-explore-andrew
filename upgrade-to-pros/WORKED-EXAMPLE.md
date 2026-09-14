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
scenario internally consistent and to bring it onto our model. Eight changes, all deliberate:

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
4. **When the project is created.** S15 records the 12 August decision to pursue all three trades as
   an internal decision with no record behind it, and mints its spine at the first proposal. Corrected
   on 11 Sep to 12 August. **Moved to 18 August and back again on 14 Sep**, as the team's position
   changed repeatedly. **It is 12 August**, now because qualification creates the lead and the lead
   creates the project. The rule is T-2, not anything in this file.
5. **Vocabulary.** S15 is one of the six pages still written as Sale, Workstream and Job-as-spine.
   Translated throughout to Lead, Project and Job. **Updated twice on 14 Sep:** a lead carries several
   interests, so this file says interest where it used to say lead, and demand now starts at an
   **inquiry** before any lead exists. Nouns per `VOCABULARY.md`, chain per T-3.
6. **The property's build year.** Andrew's earlier standalone screens say 1996. The scenarios need a
   1978 build for the original single-pane windows to make sense. **1978 is canonical**; the 1996 is
   an error in the older file.
7. **No permit.** S15 says plainly that no permit is required on this job. The windows permit stall in
   memo 6 was imported from S16 and does not belong in the cash telling.
8. **The subcontractor is named.** S15 assigns windows to a subcontractor and flags cross-org crew
   assignment as unmodelled. Named here so a screen has something to show; the gap stands.

**Dates run past today on purpose.** This is a designed narrative that has to reach a close-out, not
a report of where a real job stands.

---

## The contractor

**Northgate Home Services.** Multi-trade home improvement, around forty staff. An HVAC division and
an exteriors division covering roofing, siding and windows, sharing one sales desk and one back
office. Sacramento.

**Product tier: full platform.** Payments, selling and operations. Useful when drawing the other two
tiers by subtraction, and a reminder that this example exercises the fullest case.

| Person | Role | Where they appear |
|---|---|---|
| **Priya Raman** | Sales consultant, exteriors | Qualifies the inquiries into the lead, and owns the lead and the project. Prices the proposal, presents it, captures the decision |
| **Marcus Ellery** | Production coordinator | Runs the hand-off, builds the work packages, books the crews, raises the change order |
| **Dwight Okafor** | Exterior crew lead | The siding job. Internal crew of four |
| **Hector Salas** | Lead installer, Valley Glass and Trim | The windows job. **A subcontractor's crew on Northgate's job**, which the model does not handle |
| **Danny Cho** | HVAC service technician | The 2025 heat pump install and both maintenance visits |
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
- Roof: asphalt shingle, near end of life. Storm damage July 2026
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
- **A maintenance plan was sold at closeout**: two visits a year, $29 a month, renewing 24 September.
  **Not in S15.** It comes from this file. Whether it joins the scenario is an open request to the
  team, recorded in the deviations register
- Visits so far: 14 October 2025, complete, no findings. 18 March 2026, complete, refrigerant topped
  up and the condenser fan motor noted as noisy. Both entitlements for year one used
- Year one billing: twelve charges of $29 collected on a Visa ending 6411. No closing balance, by
  design

---

## Demand: two inquiries, then one lead with three interests

**Restated 14 September 2026**, twice. The demand chain is Inquiry or Prospect, then Lead, per T-3,
and a lead creates a project, per T-2. This section previously ran on three leads, then on one
engagement.

**Two inquiries, 21 and 22 July.** Robert contacts Northgate about the roof through the Home App on
Tuesday 21 July. Sara telephones about the siding on Wednesday 22 July. **Two separate contacts, so
two inquiries.** Windows is suggested internally by DeDe on 21 July and is not a customer contact at
all, so it enters as neither: it rides along until there is a lead to attach it to.

**One lead, Wednesday 12 August.** Priya Raman qualifies the demand and **both inquiries resolve into
one lead** carrying three interests. **Creating the lead creates the project**, so the project's
birthday is 12 August.

**Note what that requires, because it is not a small thing.** Two inquiries becoming one lead means
qualification is already an act of **routing demand into a lead** rather than minting one lead per
inquiry. **So M-008, qualifying a new inquiry into an existing lead, is not a new mechanism.** The
canonical example needs it on day one. It is the same act applied later in time.

**And the windows interest has no inquiry behind it**, because nobody asked for it. That is lead
origin as a first-class attribute, in the object register as blocking, showing up in the data rather
than in the abstract.

Origin is set once per interest and never changes; status is what moves.

| Interest | Raised | Route and author | The detail, in the customer's words where there are any | Estimate |
|---|---|---|---|---|
| **Roofing** | Tue 21 Jul 2026 | Home App, by Robert | "Found shingles in the yard after the storm last night. Someone should look at it before winter." | $38,900 |
| **Windows** | Tue 21 Jul 2026 | Suggested by DeDe, same day | Original single-pane units on a 1978 build. Flagged as worth raising if exteriors work is already on the table. **A rationale, not evidence**, because nobody has said they want them | $18,600 |
| **Siding** | Wed 22 Jul 2026 | Intake call, by Sara | "The south side is looking really tired, it's cracking in places. What would a full wrap cost, and could you do it at the same time as the roof?" | $34,200 |

**Status through the scenario.** Both inquiries read Qualified on 12 August. All three interests read
Pursuing from the same date. The lead reads Active until the close. Siding and windows
become Won on 18 August. Roofing becomes **Deferred** on 18 August, reason "budget this season",
revive March 2027, estimate retained at $38,900.

**The deferred interest stays on the lead**, which is where next spring's conversation starts
from. It was priced as an option on the proposal and it never becomes a scope or a job, so the
lead is the only place its whole story is in one piece.

**What changed across both restatements**, so a screen built on either older version can be
corrected: three lead records became two inquiries resolving into one lead with three interests; the
assignment is of the lead rather than of three leads; and the deferred trade is an interest on a live
lead rather than a lead of its own. **Every estimate, date, quoted word and outcome is unchanged.**

**The deferred interest's note**, captured in the room on 18 August by Priya Raman:

> Took siding and windows and asked to come back to the roof in spring. Sara said the roof is "not
> leaking yet". Worth leading with the July storm photos when we call back.

---

## The project

**Restated three times on 14 September 2026**, which is itself worth knowing. **See T-2; this file
does not state the rule, it only applies it.**

**"Siding and windows, Thompson."** Created Wednesday 12 August 2026, when Priya Raman qualified the
two inquiries into one lead. **Creating the lead created this.** Nothing was priced at that point, and
it carried the working name "Thompson exteriors" until the proposal settled what was in it.

One customer. One property. One lead behind it, carrying three interests. One proposal covering all
three. Two committed scopes. One interest deferred and still sitting on the lead.

**What is different from the first telling of this file.** It used to open on 12 August as an act of
pursuit, which is where it is again. In between it was moved to 18 August at the win and then moved
back twice. **The date has returned to the original and the reason has been renamed three times**:
pursuit, then intent to sell, now the creation of the lead. Same moment, same date, three names.

**The thing this example is now good for.** The lead and the project both exist from 12 August to the
close, so the useful question is no longer whether the container is needed before a win. It is **what
each of them holds while both are live**, and that is a UX question rather than a modelling one.

**Roofing is the interesting case.** It is an interest on the lead, it was priced as an option on the
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

- **22 July, on the intake call.** An exteriors intake template worked over the phone. Grounding
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
| Milestone three, two fifths plus the change order | On both trades completing | **$23,920** | Issued 26 Sep, paid by check 3 Oct |

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
| Tue 2 Sep | Window units delivered from Delta Glazing Supply | Job |
| Tue 8 to Thu 10 Sep | **Windows installed** by Hector Salas and crew. Before, during and after photos. Units registered to the property | Job |
| Fri 11 Sep | Windows walkthrough with Sara, warranty registered, review requested. **Windows complete** | Job, project |
| Mon 15 Sep | Milestone two invoiced and paid by check. Siding boards delivered from Sierra Exterior Supply | Project, customer |
| Tue 16 Sep | **Siding tear-off starts** on the south and west elevations | Job |
| Wed 17 Sep | Pulling the old north-wall boards exposes rot nobody could have quoted. Forty square feet, photographed before anything is covered. **Change order raised, plus $2,800** | Job, project, customer |
| Thu 18 Sep | Sara signs the change order. Contract amended to $55,600. Rot repair proceeds | Project |
| Thu 25 Sep | **Siding complete.** Final photos, checklist closed, walkthrough with Sara | Job, project |
| Fri 26 Sep | Both trades complete. Final bill issued, $23,920. Margin reads 31% at the project | Project, customer |
| Fri 3 Oct | Final payment by check. Project closes. Job debrief captured, warranties filed, review requested | All three |

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

Same customer, same property, same lead and its three interests, same proposal, same deferred roof, same two jobs,
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
| 18 Aug | Decision | Roofing interest | Took siding and windows and asked to come back to the roof in spring. Sara said the roof is "not leaking yet". Worth leading with the July storm photos when we call back. | Priya Raman |
| 22 Jul | Intake | Customer | Sara raised the siding on the follow-up call and asked whether it could ride the same visit as the roof. Worked the exteriors intake template. Gauged interest in the windows, which she was lukewarm about. | Priya Raman |
| 18 Mar | Service visit | Maintenance plan | Condenser fan motor is noisy and the unit is a year old, so it is a warranty question rather than a repair. Flagged to watch at the autumn visit. | Danny Cho |
| 12 Aug 2025 | Intake | Customer | Came in from a phone enquiry, system failed in the heat. Sara decides, Robert handles billing. | Alicia Moss |

### History, newest first

| Date | Event |
|---|---|
| 3 Oct | Final payment received. Project closed |
| 26 Sep | Final bill issued, $23,920 |
| 25 Sep | Siding complete |
| 18 Sep | Change order signed. Contract amended to $55,600 |
| 17 Sep | Change order raised on the siding scope, plus $2,800 |
| 15 Sep | Milestone two paid, $21,120 |
| 11 Sep | Windows complete |
| 24 Aug | Contract signed, cash plan agreed, deposit received. Two jobs created |
| 21 Aug | Proposal revised after the site assessment |
| 18 Aug | Proposal accepted at $52,800. Roofing deferred to spring. Project renamed "Siding and windows, Thompson" once its contents settled |
| 13 Aug | Proposal prepared, three trades priced |
| 12 Aug | **Both inquiries qualified into one lead.** Three interests moved to Pursuing. **Creating the lead created the project**, working name "Thompson exteriors" |
| 22 Jul | **Second inquiry.** Sara telephones about the siding |
| 21 Jul | **First inquiry.** Robert raises the roof in the Home App. Windows suggested internally by DeDe, with no inquiry behind it |
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
