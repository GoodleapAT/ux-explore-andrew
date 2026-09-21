# S15, the data

**Every value any S15 screen might need, for all twenty four beats including the ones the script marks
no screen. Rebuilt 16 September 2026 on the revised calendar, and revised again 17 September 2026 to
add the post-sale inspection, the day-before checks and the scope refinement. See section 1A.**

> **How to use this file.** It is the only source of mock data for S15. **Do not invent a value that
> is not here.** If something is missing, say so and it gets added here, so the next screen uses the
> same one.
>
> **Every value carries its provenance**, and there are three kinds:
>
> - **SCRIPT** — stated in the S15 beat script. Not negotiable without changing the script.
> - **CANON** — from the project's worked example. Reusable and correct for the Thompsons.
> - **OURS** — invented for this pack because a screen needs it and neither source has it.
>   **Change these freely.** They are marked so nobody mistakes them for settled, and they are listed
>   together in section 12.
>
> **The dates in this file are newer than the Confluence script.** The calendar was revised on 16
> September at Andrew's instruction and **the script has not yet been updated to match**. Where they
> disagree, this file wins, and section 1 lists every difference.
>
> **The worked example file is stale for S15.** It describes three trades, a change order and three
> milestones. Take anchor data from here, not from there.

---

## 1. What changed in the calendar, and what it breaks

**Revised 16 Sep 2026. Three problems in the original were being worked around.** Permits were applied
for and issued on the same beat, one beat had no date at all, and the gap between signing and
installation was five weeks with nothing happening in it.

| Beat | Was | Now | Why |
|---|---|---|---|
| 5 | Sales visit booked for **Thursday** | Booked for **Wednesday**, the next day | So the sale can complete on a weekday and beat 11 does not land on a Saturday |
| 6, 7 | Thu 6 Aug | **Wed 5 Aug** | Same |
| 8, 9, 10 | Fri 7 Aug | **Thu 6 Aug** | Same |
| 11 | **No date.** "A day after" a Friday signing, which is a Saturday | **Fri 7 Aug** | The whole reason for the shift |
| 14 | Thu 13 Aug, applied **and** issued | **Fri 7 Aug, applied only.** Same day as beat 11 | Permits are filed in the same sitting that builds the work orders |
| 15 | Thu 20 Aug, "both permits issued", contradicting beat 14 | **Tue 11 Aug, issued.** Two working days later | Resolves the contradiction and creates a real waiting period |
| 16 | Mon 24 Aug | **Wed 12 Aug** | Dates get confirmed once the permits are in |
| 17 | Fri 4 Sep | **Fri 14 Aug** | |
| 18 | Mon 7 to Fri 11 Sep | **Mon 17 to Fri 21 Aug** | Install within a week of the permits issuing |
| 19 | Fri 11 Sep | **Fri 21 Aug** | |
| 20 | Mon 14 Sep | **Mon 24 Aug** | |
| 21 | Mon 21 Sep | **Wed 26 Aug** | Two days after the invoice rather than seven |

**Four consequences, all of which want a decision or a note.**

**The script's six-weeks sentence is now wrong.** It says Northgate funds $72,600 of materials and two
crews on trust **for six weeks**, and calls that deliberate and commercially unusual. **It is now
twenty days.** Still unusual, quieter. **The script needs that line changed.**

**Beat 15's UX instruction is now wrong, and that is a gain.** It says "merge into previous step",
which was right when both events shared a beat. **With a real gap there are two useful states:
applied and not yet issued, then both issued.** The permits are the only thing anybody ever waits on
in this entire scenario, so **this is the demo's only pending state**. Do not merge them.

**The two jobs are staggered and do not overlap**, settled 16 Sep at Andrew's instruction.
**The dates in this paragraph were superseded on 17 September. See section 1A.** Roofing
Monday 17 to Tuesday 18, siding Wednesday 19 to Friday 21. **An earlier draft of this pack had them
overlapping on Wednesday 19**, and that one day of overlap made beat 18's instruction impossible to
satisfy: it asks for one job complete and one merely scheduled, and with an overlap that state never
occurs. **With the stagger, Tuesday 18 August is exactly that screen**: roofing complete, siding
scheduled to start tomorrow. Beat 18's own text, two crews at one address, stays true of the week.

**Beats 11 and 14 now share Friday 7 August**, with two empty beats numbered between them. Harmless,
and the script already puts beats 8, 9 and 10 on one day. **Do not renumber**, because the UX column
and every memo cite beats by number.

---

## 1A. Revised again, 17 September 2026

**Two problems remained.** The refinement at beat 11 had no cause, because nothing in the scenario
sent anybody to the property between signing and building the work orders. And Dana's configuration
has a **Final checks** stage with a day-before gate that the script never demonstrated, so every
mockup drawing that stage had to invent a date for it.

**Three beats go in and one moves.** Lettered insertions, because four memos and the team's
Confluence script cite beats by number.

| Beat | Status | When | What it does |
|---|---|---|---|
| **10a** | **New** | Booked **Thu 6 Aug** late afternoon, carried out **Fri 7 Aug, 8:05 to 9:40am** | **The post-sale inspection.** One visit, both trades, Marcus Ellery. It is what produces the refinement at beat 11 |
| **11** | **Same date, rewritten** | Fri 7 Aug, from about 11:20 | Now explicitly the scope refinement, with the inspection findings as its input. See section 8 |
| **17a** | **New** | **Mon 17 Aug** | **Day-before checks on the roofing job.** Weather, materials on site, dumpster on site, customer check-in |
| **18** | **Moved** | Roofing **Tue 18 to Wed 19**, siding **Thu 20 to Fri 21** | Final checks take the Monday, so the install starts on the Tuesday |
| **18a** | **New** | **Wed 19 Aug** | **Day-before checks on the siding job**, carried out while the roofing crew finishes |

**Beats 19, 20 and 21 do not move.** Both jobs still complete Friday 21 August, the invoice is still
Monday 24 August and payment is still Wednesday 26 August. **The three day amber window between
completion and invoicing survives**, which matters because it is the only amber in the scenario.

**Four consequences.**

**Siding drops from three days to two.** The install week is five weekdays and Final checks now takes
one of them, so Monday is checks, Tuesday and Wednesday are roofing, Thursday and Friday are siding.
The siding duration was **OURS** rather than the script's, so nothing canonical breaks, but **two days
for 2,140 square feet of fibre cement with a crew of three is tight** and anybody who builds for a
living will say so.

**Beat 18's canonical screen day moves from Tuesday 18 to Wednesday 19 August.** That is still the
only day where one job is complete and the other is merely scheduled, which is what the beat asks for.

**Each job gets its own day-before check, not the project.** Roofing is checked on Monday, siding on
Wednesday. This is the first thing in the scenario that is deliberately per job rather than shared,
and it is the right reading: the gate is on the job's own transition into Installing.

**The post-sale inspection is one visit and two refinements.** It stays a single task held at the
project for tracking. From each job's side it is a thing the job cannot perform itself, so **it
surfaces on a job as a wait rather than as a task**, which keeps each job's checklist count honest.

**Still outstanding:** the Confluence script's "six weeks" sentence now reads twenty days and has not
been changed.

---

## 2. The organisation

| | | |
|---|---|---|
| **Northgate** | Multi-trade home improvement | SCRIPT |
| **Divisions** | HVAC, and exteriors covering roofing, siding and windows | SCRIPT |
| **Size** | Roughly 25 to 60 people | CANON |
| **Structure** | One sales desk and one back office serving both divisions | CANON |
| **Adoption** | Selling, work and money all on platform. **No financing on this job** | SCRIPT |

## 3. The cast

| Name | Role | In S15 they | Provenance |
|---|---|---|---|
| **Sara Thompson** | Homeowner, decision maker | Telephones about the roof, raises siding on the same call, accepts the proposal, signs, takes both walkthroughs | SCRIPT |
| **Robert Thompson** | Homeowner, billing contact | **Does not appear in any beat.** Exists on the record | CANON |
| **Renata Silva** | CSR, front desk | Takes the call, captures both trades, books the sales visit, hands to Priya | SCRIPT |
| **Priya Raman** | Sales consultant, exteriors | Site assessment and presentation on one visit, prices both trades | SCRIPT |
| **Marcus Ellery** | Production coordinator | Builds both work orders and materials lists, refines both scopes, files permits, books crews and dates | SCRIPT |
| **Dwight Okafor** | Exterior crew lead | Runs the **roofing** job. Crew of four | CANON, reassigned from siding **OURS** |
| **Luis Ferrara** | Siding crew lead | Runs the **siding** job. Crew of three | **OURS.** Two trades in one week need two leads |
| **Alicia Moss** | Office manager | Raises the final invoice, records the card payment | CANON |
| **Danny Cho** | HVAC service technician | Does not appear. Installed the 2025 heat pump | CANON |

**Not in S15:** Hector Salas, the windows subcontractor. Windows are out of this script.

## 4. The customer, the contacts, the property

| Field | Value | Provenance |
|---|---|---|
| Customer | Sara Thompson | SCRIPT |
| Customer since | August 2025 | CANON |
| Contact, decision maker | **Sara Thompson**, (916) 555-0188, sara.t@email.com. Prefers text. Signs the paperwork | CANON |
| Contact, billing | **Robert Thompson**, (916) 555-0142, r.thompson@email.com. Defers to Sara on cost | CANON |
| **The matching number** | **(916) 555-0188.** Beat 2 matches on this, and it is stored **against Sara's contact record**, not against the customer | SCRIPT |
| Property | **1428 Maple Ave, Sacramento CA 95818.** One property; the Thompsons hold no others | CANON |
| Property detail | Two storey, 2,140 square feet, **built 1978** | CANON |
| Access | **Gate code 4417.** Dog in the back yard, friendly but loud | CANON |

## 5. What happened before the scenario

**The 2025 heat pump project. Beat 1 is entirely about this.**

| Field | Value | Provenance |
|---|---|---|
| What | Central air failed in the August heat, replaced and converted to a heat pump | SCRIPT |
| Structure | One project, one job | CANON |
| Value | **$14,800**, financed over ten years | SCRIPT |
| Closed | **Wed 24 September 2025** | SCRIPT |
| Installed by | Danny Cho | CANON |
| Installed equipment | **A Carrier heat pump**, registered against the property, ten years parts | CANON |
| Money position | **Settled by the lender. It was never Northgate's receivable**, so it is not a balance on this record. **This is why beat 1 reads $0** | CANON |

**The maintenance plan, sold at closeout.**

| Field | Value | Provenance |
|---|---|---|
| What | Two visits a year | SCRIPT |
| Price | **$29 a month** | SCRIPT |
| Renews | **24 September**, annually | CANON |
| Card | **Visa ending 6411** | CANON |
| Billing day | The 24th of each month, first charge 24 Sep 2025 | CANON |
| **Charges by 4 Aug 2026** | **11 charges, $319 collected** | Derived |
| **Charges by 26 Aug 2026** | **12 charges, $348 collected.** The twelfth lands 24 Aug | Derived |
| Visits used | Two, both by Danny Cho | CANON |

**Two streams, never totalled.** The plan has collected **$348 lifetime**. The project collects
**$73,100**. A previous memo showed "13 charges, $73,448" by adding them together. **Any transactions
list keeps recurring plan billing apart from project payments.**

**A useful coincidence.** The 24 August plan charge of $29 lands **on the same day as the $72,600
invoice**. Two money events on one day, one recurring and one one-off. It is the cheapest available
test of the separation rule.

## 6. The two trades

### Roofing

| Field | Value | Provenance |
|---|---|---|
| Price | **$38,900** | SCRIPT |
| Why it came in | Overnight storm, shingles in the yard, wants it looked at before winter | SCRIPT |
| Roof age | About 19 years | **OURS** |
| Area | 2,410 square feet | **OURS** |
| Layers to remove | 1 | **OURS** |
| Material | Architectural shingle, underlayment, ridge vent, flashing | **OURS** |
| Condition at assessment | Near end of life. Storm lifted shingles on the south slope. Decking sound where visible | **OURS** |
| Access | Ladder on the south elevation, dumpster on the north driveway | **OURS** |
| Crew | Dwight Okafor, four | **OURS** |
| Day-before checks | **Mon 17 August** | **OURS.** Beat 17a |
| Install | **Tue 18 to Wed 19 August** | **OURS.** The script gives the week, not the split |

**No roofing line items existed anywhere** when this pack was written, because the roof was declined
in the story the worked example describes. **A full breakdown has since been constructed and flagged**
in `S15-ROOFING-SCOPE-AND-ITEMIZATION.md`: six sold lines and twenty two refined lines, both totalling
$38,900. **Every figure in it is OURS.** Use that file rather than inventing a second one.

### Siding

| Field | Value | Provenance |
|---|---|---|
| Price | **$34,200** | SCRIPT |
| Why it came in | Sara raises it on the same call. South side faded and cracking. Asks what a full wrap costs and whether it can ride the same visit | SCRIPT |
| Elevations | **South and west** | SCRIPT |
| Area | **2,140 square feet across two elevations** | CANON |
| Current material | Wood lap, original to the 1978 build | CANON |
| New material | **Fibre cement lap, 8.25 inch, Cobble Stone** | CANON |
| Condition | Faded, cracking. Tear-off to sheathing | CANON |
| Crew | Luis Ferrara, three | **OURS** |
| Day-before checks | **Wed 19 August** | **OURS.** Beat 18a, while the roofing crew finishes |
| Install | **Thu 20 to Fri 21 August** | **OURS.** Two days, cut from three when Final checks took the Monday |

**The worked example's siding line items do not add up to $34,200.** Fibre cement lap $18,690,
tear-off and disposal $4,280, house wrap and flashing $3,210, which is **$26,180** against a script
price of $34,200, because they were priced for a different version of the story. **Do not show them
as a breakdown.**

**The two jobs are staggered and do not overlap.** Monday 17 is day-before checks on roofing, roofing
runs Tuesday 18 to Wednesday 19, siding is checked on Wednesday 19 and runs Thursday 20 to Friday 21.
**Two crews at one address across one week, never on the same day.** Beat 18's own text says two crews
at one address, which stays true of the week.

**This is what makes beat 18's screen possible.** Drawn on **Wednesday 19 August**, roofing is
complete and siding is scheduled to start tomorrow, which is exactly what the script asks for. With an
overlap that state never occurs on any day.

## 7. The money

| | Value | Provenance |
|---|---|---|
| Roofing | $38,900 | SCRIPT |
| Siding | $34,200 | SCRIPT |
| **Contract total** | **$73,100** | SCRIPT |
| Deposit | **$500, by cheque, Thu 6 August** | SCRIPT |
| Balance | **$72,600, due on completion** | SCRIPT |
| Milestones | **Two.** Deposit, and balance. **No progress milestones** | SCRIPT |
| Invoice | **One, project level, raised Mon 24 August for $72,600** | SCRIPT |
| Final payment | **Credit card, Wed 26 August** | SCRIPT |
| **Project margin** | **31%**, read at the project | SCRIPT |
| **Project cost, derived** | **$50,439**, being 69% of $73,100 | Derived |
| **Gross profit, derived** | **$22,661** | Derived |
| **Per-job cost** | **No split is given.** Costs sit per job, so a split must exist. Do not invent one on screen without flagging it | SCRIPT |
| **Per-job margin** | **Unavailable by rule.** Revenue occurs at the project, cost at the job. **Not drawn, not greyed, not labelled. Absent** | SCRIPT |

**Two tender instruments on one plan.** The deposit is a cheque and the balance a credit card, and
the plan reads cash throughout. **Nothing in the model resolves this**, and any badge saying cash is
inaccurate by beat 21.

**The trust window.** Twenty days between signing and final payment, during which Northgate funds
$72,600 of materials and two crews on a $500 deposit.

### The money state, beat by beat

| Beat | Date | Contract | Collected | Outstanding | Reads as |
|---|---|---|---|---|---|
| 1 | before | none | none | **$0** | Nothing owed. Plan billing $29 a month, 11 charges to date |
| 2 to 6 | 4 to 5 Aug | none | none | $0 | Unchanged. No price exists yet |
| 7 | 5 Aug, eve | **$73,100 proposed** | none | not yet a receivable | Accepted in the room. Not signed |
| 8 | 6 Aug | **$73,100** | **$500** | **$72,600** | Signed. Deposit taken by cheque |
| 9 to 18 | 6 to 21 Aug | $73,100 | $500 | $72,600 | **Not yet due.** Unchanged for two weeks |
| 19 | 21 Aug | $73,100 | $500 | $72,600 | **Due, and not yet invoiced.** Both jobs complete |
| 20 | 24 Aug | $73,100 | $500 | $72,600 | **Invoiced.** One project-level bill. Plan also charges $29 today |
| 21 | 26 Aug | $73,100 | **$73,100** | **$0** | **Paid by card. The project closes** |

**The reading five screens rest on.** The payment plan lives at the project and carries both
milestones. **An invoice is raised per milestone when its trigger fires**, so beat 20 raises the
second invoice rather than the first thing money has ever lived in. If that is wrong, every money
screen from beat 11 is wrong.

**The state the model does not have.** Between beat 19 and beat 20, for **three days**, $72,600 is
owed and nothing has asked for it. Completion is the trigger, so the money is due the moment both
jobs close and the invoice is raised later. **It is the only amber in the scenario.**

---

## 8. The beats

**Twenty one numbered, plus three lettered insertions added 17 September 2026: 10a, 17a and 18a.**
See section 1A.

| # | When | Who | What happens | What exists after | Script's UX instruction |
|---|---|---|---|---|---|
| **1** | Closed **Wed 24 Sep 2025** | Nobody | The prior heat pump project, $14,800 financed, plan sold at closeout | Customer, 2 contacts, property, 1 closed project, 1 job, installed equipment, service plan | Customer view: contact, property, previous project and job summary. High-level money, $0 balance, nothing due, last few transactions |
| **2** | **Tue 4 Aug 2026, 8:05am** | Renata Silva | Sara telephones after an overnight storm. Shingles in the yard, wants the roof looked at before winter | A call in progress. Nothing minted yet | Call screen with an element that searches for a matching customer. **Match found on the phone number stored on the Thompson contact** |
| **3** | **8:07am**, same call | Renata Silva | The call names a trade and a property, so it qualifies itself. **A lead and a project exist and she creates neither** | **Lead** and **Project** minted. Lead named for one trade | Renata selects Roofing from a list of trades. Notes under a form and a free note field under Roofing |
| **4** | **8:11am**, same call | Renata Silva | Sara raises the south side. Faded, cracking. Asks about a full wrap and whether it can ride the same visit | Lead carries two trades. **Its name changes** | She selects siding and takes notes on a form provided for siding as well |
| **5** | **8:14am**, same call | Renata Silva | Books a sales visit for **Wednesday afternoon** and hands the lead to Priya | Appointment, sales. Lead assigned to Priya | CTA like Next step, options to book a sales visit or assign to a salesperson. She books. Sees availability over the next few days, selects a person and time. **We already have this screen** |
| **6** | **Wed 5 Aug, 4pm** | Priya Raman | Walks the roof and the south and west elevations, measures both, photographs. **Assessment and presentation are the same visit** | Site assessment with photos, measurements and notes for two trades | Priya opens the project, taps Begin site assessment, gathers required pictures, makes measurements, adds notes, saves |
| **7** | **Wed 5 Aug, evening** | Priya Raman, Sara | Presents a proposal covering both trades. Roofing $38,900, siding $34,200, **$73,100 together. Both accepted in the room** | **Proposal**, accepted | **No screen for demo.** She selects a CTA, Create proposal |
| **8** | **Thu 6 Aug** | Priya Raman, Sara | Cash chosen. **$500 deposit up front, $72,600 on completion.** Contract e-signed, deposit taken by cheque | **Contract** signed. **Payment plan**, two milestones. **Payment** $500 | **No screen needed for demo** |
| **9** | **Thu 6 Aug** | Marcus Ellery | Hand-off. **Two job containers created, one per committed trade.** Each carries the intake, the lead and the proposal behind it | **Job, roofing.** **Job, siding.** Both carry their provenance | **No screen needed for demo** |
| **10** | **Thu 6 Aug** | Nobody | **The lead closes.** Both trades sold, nothing left on it | Lead closed. **From here the project runs with no lead behind it** | **No screen needed for demo** |
| **10a** | Booked **Thu 6 Aug** late afternoon. Carried out **Fri 7 Aug, 8:05 to 9:40am** | Marcus Ellery | **The post-sale inspection. One visit, both trades.** He finds staining in the attic over the south slope, measures the main ridge at 48 feet, confirms one layer at the eave, and confirms the dumpster fits the north driveway. Six photographs | **Visit**, complete. Four findings and six photographs on the roofing job | **Job screen, Thu 6 Aug.** The only action is **Book the inspection**, because nothing can be refined until it has happened. The waiting-on line reads *post-sale inspection, not booked* |
| **11** | **Fri 7 Aug**, from about 11:20 | Marcus Ellery | **Refines the scope on each job, then builds the materials list from it.** On roofing: six signed lines become twenty two. The attic staining raises the decking allowance from 12 sheets to 16, **$260 over**, and site protection drops from three days to two, **$260 back**. **The total stays at $38,900.** Committing produces the materials list and makes the permit filing possible | Two refined scopes, two materials lists, materials ordered. **The signed itemization is untouched** | **The refine overlay, three states.** Opened with the findings at the top, part way through and temporarily over, and reopened read only after commit. **Full screen takeover, opening from the job's first checklist row** |
| **12** | — | — | **Empty row in the script.** Not a missing beat. Do not fill or renumber | — | — |
| **13** | — | — | **Empty row in the script.** Same | — | — |
| **14** | **Fri 7 Aug** | Marcus Ellery | **Permits applied for on both jobs**, in the same sitting that built the work orders | Two permit applications, pending | Task list items get checked. Visible at project level, where each job shows as an overview with a high level checklist, or at job level with a more detailed checklist |
| **15** | **Tue 11 Aug** | Marcus Ellery | **Both permits issued**, two working days later | Two permits, issued | **Its instruction to merge is now wrong.** Draw it: this is the scenario's only pending-then-resolved pair |
| **16** | **Wed 12 Aug** | Marcus Ellery, Sara by phone | Crews and dates confirmed in one conversation. **Both trades run in the same week**, two crews on different elevations. **The work order is issued to each crew here**, not at beat 11 | Two crew assignments, two install date ranges, two work orders issued | Project screen shows installation dates for each of the 2 jobs |
| **17** | **Fri 14 Aug** | Nobody on screen | **Materials delivered for both trades** | Two deliveries received | **No screen** |
| **17a** | **Mon 17 Aug** | Dwight Okafor, Marcus Ellery | **Day-before checks on the roofing job.** Weather checked, materials verified on site, dumpster verified on site, Sara texted | Roofing job clears its Final checks gate | **No screen needed for demo.** Drawn only if the rail's Final checks stage needs a real value rather than a derived one |
| **18** | **Tue 18 to Fri 21 Aug.** Roofing **18 to 19**, siding **20 to 21** | Dwight Okafor, then Luis Ferrara | **Both jobs run in the same week, staggered and not overlapping.** Roof torn off and replaced, then south and west elevations wrapped. Before, during and after photographs, checklist per trade | Photos on both jobs, checklists progressing | Project screen shows 1 job complete and 1 job with a scheduled date. **Draw Wed 19 Aug**, which is exactly that day: roofing complete, siding scheduled to start tomorrow |
| **18a** | **Wed 19 Aug** | Luis Ferrara, Marcus Ellery | **Day-before checks on the siding job**, carried out while the roofing crew finishes | Siding job clears its Final checks gate | **No screen.** Same treatment as 17a |
| **19** | **Fri 21 Aug** | Marcus Ellery, Sara | **Both jobs complete.** Two walkthroughs, warranties registered on the roofing materials and the siding, review requested | Both jobs complete. Warranties registered. **Balance becomes due** | Project screen shows complete installation on both jobs. Invoice shows updated balance |
| **20** | **Mon 24 Aug** | Alicia Moss | **One project-level final bill issued, $72,600.** Margin reads 31% at the project | **Invoice**, $72,600 | Project screen, contractor taps a CTA like Create invoice. The remaining balance is populated |
| **21** | **Wed 26 Aug** | Alicia Moss | **Final payment by credit card. The project closes** | Payment $72,600. Project paid and closed | Project screen shows invoice with milestones and the last milestone changes to paid |

**Every weekday above is verified.**

---

## 9. The containers, and their states

**Twenty one beats are not twenty one designs. They are six containers.**

| Container | States | Which beats |
|---|---|---|
| **Customer record** | 1, and more if you want them | 1 |
| **Inbound call** | **4** | 2 empty, 3 one trade, 4 two trades, 5 next step |
| **Site assessment** | 1 | 6 |
| **Project** | **7** | 11 after sale, 14 permits pending, 15 permits issued, 16 dates set, **18 roofing complete and siding scheduled**, 19 both complete and due, 21 paid |
| **Job** | 1 | 14 or 15, at job level rather than project level |
| **Create invoice** | 1 | 20 |

**A state is a variant of its container, never a new page.** If two states of one container come out
as two different designs, that is a finding and it should be reported rather than worked around.

**Surfaces.** Everything here is **Pros Web** except the site assessment at beat 6, which is field
capture on a tablet or phone, and is a different surface rather than a responsive desktop page.

---

## 10. What exists, and when

| Object | Exists from | Ends as |
|---|---|---|
| **Customer** | Aug 2025 | Open, two projects |
| **Contacts** | Aug 2025 | Two, unchanged |
| **Property** | Aug 2025 | Three pieces of installed work on it |
| **Service plan** | 24 Sep 2025 | Active. Renews 24 Sep 2026, a month after the project closes |
| **Prior project, heat pump** | Aug 2025 | Closed 24 Sep 2025, paid |
| **Lead** | **Beat 3**, 8:07am | **Closed at beat 10** |
| **Project** | **Beat 3**, 8:07am, minted by the lead | **Closed at beat 21** |
| **Site assessment** | Beat 6 | Complete |
| **Proposal** | Beat 7 | Accepted, frozen |
| **Contract** | Beat 8 | Signed |
| **Payment plan** | Beat 8 | Settled |
| **Job, roofing** | **Beat 9** | Complete |
| **Job, siding** | **Beat 9** | Complete |
| **Permits, two** | **Beat 14** applied, **beat 15** issued | Issued |
| **Invoice** | **Beat 20** | Paid |

**Nothing is ever blocked.** No change order, no HOA step, no failed inspection, no decline. **The
permits are the only dependency**, and after the revision they are the only thing on any screen that
is pending rather than done.

---

## 11. Values that must not be invented on screen

**Each is a gap in the model, not a gap in this file.**

- **Per-job margin.** Absent by rule. Not drawn, not greyed, not labelled.
- **Per-job cost.** A split must exist and no number is given.
- **The lead's name at beat 3**, before siding is added. The container is named by its contents, so it
  changes at beat 4. **What it reads at 8:07 is a choice nobody has made.**
- **Communications.** The call, the scheduling conversation at beat 16 and the review request at beat
  19 have no entity anywhere. Left out.
- **What the scope was before it was refined** at beat 11. Nothing records the prior version, so a
  "what changed" link is a promise the model cannot keep.
- **Whether two crews at one address on one day matters.** Nothing in the model knows.

---

## 12. Everything marked OURS, in one list

| Value | Used where |
|---|---|
| Beat 11 dated **Fri 7 Aug**, and the whole revised calendar | Everywhere |
| **Luis Ferrara**, siding crew lead, crew of three | 16, 18 |
| **Dwight Okafor reassigned** to roofing, crew of four | 16, 18 |
| Roof **2,410 sq ft**, **19 years old**, **1 layer** | 6 onward |
| Roof materials: architectural shingle, underlayment, ridge vent, flashing | 6 onward |
| Roof access: ladder south, dumpster north driveway | 6 onward |
| **Roofing 18 to 19 Aug, siding 20 to 21 Aug**, staggered with no overlap | 16, 18 |
| **Siding cut from three days to two** to make room for Final checks | 18 |
| The **post-sale inspection**, beat 10a, and all four of its findings | 10a, 11 |
| **Day-before checks**, beats 17a and 18a, and their four tasks | 17a, 18a |
| The **roofing itemization**, six sold lines and twenty two refined, both at $38,900 | 11 onward |
| The **decking allowance moving 12 sheets to 16**, and site protection three days to two | 11 |
| Any siding line-item breakdown | 7 onward |

---

## Learned from

- **16 Sep 2026.** Built after a memo produced screens whose layout changed between states for no
  reason a reader could see. **The data was being re-decided per screen**, which is what made
  presentation look arbitrary. This file exists so no screen has to decide anything.
- **16 Sep 2026.** Reading the script closely found **a contradiction between beats 14 and 15 that a
  previous memo had quietly resolved** by picking a date. Quietly resolving a source contradiction is
  the failure.
- **16 Sep 2026.** Revising the calendar to fix that contradiction **produced the scenario's only
  pending state**, which it had been missing entirely. The script had said so itself, in a section
  listing what it deliberately does not have.
