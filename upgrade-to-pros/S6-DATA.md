# S6, the data

**Every value the S6 concept screens need. Built 22 September 2026 from the beat script and Andrew's
own UX notes inside it.**

> **How to use this file.** It is the only source of mock data for S6. **Do not invent a value that
> is not here.** If something is missing, say so and it gets added here, so the next screen uses the
> same one.
>
> **Every value carries its provenance**, and there are four kinds:
>
> - **SCRIPT** — stated in the S6 beat script on Confluence, in the ProsOperations space, authored by
>   Joel and last modified 15 September 2026. **Not negotiable without changing the script.**
> - **ANDREW** — from Andrew's own UX notes written into that page, on beats 2, 3, 4, 5, 7, 8, 10 and
>   17. These are design decisions already taken and they outrank anything derived.
> - **SHELL** — from the navigation Andrew supplied on 22 September 2026, which is the shell of record
>   for these concepts.
> - **OURS** — invented for this pack because a screen needs it and no source has it. **Change these
>   freely.** They are listed together in section 11.
>
> **The script is not saved in this repository**, the same gap already logged for S15. Every SCRIPT
> value below was read from the live page on 22 September 2026 and is quoted rather than paraphrased
> where a screen will render it.
>
> **Two deliberate departures from the script**, both Andrew's, both recorded here so nobody
> reconciles them away: **Mike clears the stip himself through DeDe on his phone**, where the script
> has the homeowner photograph her own paystub from the couch; and **the notice to proceed is shown
> without the e-signature or the scope entry beats being drawn**, which are its two preconditions in
> the script.

---

## 1. The organisation

| Field | Value | Provenance |
|---|---|---|
| Trade | **Roofing.** Tear-off and re-roof | SCRIPT |
| Size | **Six people** | SCRIPT |
| Name | **Pruitt Roofing** | **OURS** |
| Owner, and the only person in the app | **Mike Pruitt** | Mike is SCRIPT, the surname is **OURS** |
| How they found us | Financing only. They sell, contract and build entirely off our surfaces | SCRIPT |
| Financing enablement | **One installation category only: Roofing.** Full category name *Roofing / Windows / Doors / Siding / Geothermal / Restoration* | SCRIPT, category detail from Joel's comment on the page |
| What that settles | The rate card and the offers the calculator prices against are **fixed before any application exists** | SCRIPT |
| Contractor tier | **Level 2**, which is why the homeowner has nothing to do at completion | SCRIPT |
| Surfaces they touch | Application status, cases, payouts, statements. **That is the entire product Mike experiences** | SCRIPT |

**The shell's footer must read Pruitt Roofing and Mike Pruitt, Owner.** The navigation as supplied
reads Redhawk Home Services and Dana Ruiz, Owner / GM, which is the shell's own demo org and would
contradict every screen in this scenario.

---

## 2. The cast

| Name | Role | In S6 they | Provenance |
|---|---|---|---|
| **Mike Pruitt** | Owner, six-person roofing outfit | Runs the calculator, shares the application, sees the loan, clears the stip through DeDe, types the scope, marks the install complete, reconciles the payout | Mike SCRIPT, surname **OURS** |
| **Nadia Brandt** | Homeowner | Wants the roof, cannot pay cash, fills the application on her own computer, e-signs the agreement | Role SCRIPT, name **OURS** |
| **DeDe** | Assistant | Explains the open stip, offers to capture the paystub, confirms it cleared | SHELL, and Daidipya's note on beat 8 |
| **The county inspector** | Not named, never on screen | Signs the final that Friday | SCRIPT |
| **The crew** | Four, not named | Tears off and re-roofs over two days | Crew size **OURS** |

**Nobody else exists.** No CSR, no sales consultant, no coordinator, no office manager. **That absence
is the scenario**, and a screen that implies a second person in the org is wrong.

---

## 3. The customer, the contact and the property

| Field | Value | Provenance |
|---|---|---|
| Customer | **Nadia Brandt** | **OURS** |
| Property | **4417 Meadowlark Lane, Aurora, CO 80013** | **OURS** |
| Phone | **(303) 555-0172** | **OURS** |
| Email | **n.brandt@example.com.** Required, because the share is by email and email only | Requirement SCRIPT and ANDREW, address **OURS** |
| How the anchors arrived | **She typed them herself**, into the application on her own computer | SCRIPT |
| What Mike typed first | Name and email at the new financing step, the rest optional and filled later by the application | ANDREW, beat 2 |
| Neighbourhood | Hail damaged, canvassed after a storm | SCRIPT |
| Property detail on record | **None.** No photograph, no roof measurement of ours, no site assessment. Nobody from our side has been there | SCRIPT |

**Time zone is MDT, not PDT.** Aurora is Colorado and the scenario runs in October, so every time on
these screens reads `4:50 pm MDT`. S5 and S15 are both Pacific; this one is not.

---

## 4. The calendar

**Anchored to Thursday 1 October 2026. Every weekday below is verified.**

| When | What happens | Surface |
|---|---|---|
| **Thu Oct 1, 4:50 pm** | Kitchen table. $19,000 roof agreed in the world, nothing signed | Off app |
| **Thu Oct 1, 4:55 pm** | Mike starts a new financing application and prices it | Pros mobile |
| **Thu Oct 1, 4:57 pm** | He turns the phone round and presents two monthly figures. She picks the cheaper | Pros mobile |
| **Thu Oct 1, 4:58 pm** | He shares the application with her by email | Pros mobile |
| **Thu Oct 1, 5:20 pm** | She fills it in on her own computer, for autofill | Her own computer |
| **Thu Oct 1, 5:24 pm** | She submits it | Her own computer |
| **Thu Oct 1, 5:24 pm** | Approved in band, one open stip: her most recent paystub | Her own computer |
| **Thu Oct 1, 5:26 pm** | **Mike is notified of the approval** | Pros mobile |
| **Thu Oct 1, 6:00 pm** | He opens Cases, finds the paystub case, DeDe explains it and offers to capture the document | Pros mobile |
| **Thu Oct 1, 6:04 pm** | The paystub is captured in the DeDe chat and accepted. The stip clears | Pros mobile |
| **Thu Oct 1, 8:47 pm** | She takes her selfie and photographs her ID, then e-signs the agreement | **Not drawn** |
| **Thu Oct 1, 8:52 pm** | **Notice to proceed renders.** Mike is notified | Pros mobile |
| **Thu Oct 1, evening** | She signs Mike's own paper roofing contract | Off app, never ingested |
| **Fri Oct 2 to Mon Oct 12** | Permits, crew, material orders, all on Mike's whiteboard | Off app, never ingested |
| **Tue Oct 13 and Wed Oct 14** | Tear off and re-roof, two days, crew of four | Off app, never ingested |
| **Fri Oct 16** | The county inspector signs the final | Off app, never ingested |
| **Fri Oct 16, 4:10 pm** | Mike marks the installation complete | Pros web |
| **Fri Oct 16** | The Completed Project Certificate goes to the homeowner. Level 2, so she has nothing to do | No screen |
| **Mon Oct 19** | Money moves by ACH, the next business day | No screen |
| **Tue Oct 20, 6:05 am** | Mike reconciles from the payout statement | Pros web |

**The whole selling and approval sequence is one evening.** Four fifty in a driveway to a notice to
proceed before nine, which is the scenario's single strongest fact and the reason the times are on
the screens.

---

## 5. The money

| Field | Value | Provenance |
|---|---|---|
| The roof | **$19,000.00** | SCRIPT |
| Rate | **12.99%** | SCRIPT |
| Term taken | **180 months**, 15 years | SCRIPT |
| Monthly, taken | **$243.23** | SCRIPT |
| Monthly, the other option | **$287.77**, 120 months, same rate | SCRIPT |
| Dealer fee | **7.5%, $1,425.00** | **OURS** |
| Net to Mike's bank | **$17,575.00**, single draw | **OURS** |
| How it arrives | **ACH, next business day**, Mon Oct 19 | SCRIPT |
| The synthetic invoice | **$19,000.00**, settled by one Payment of $19,000.00 | SCRIPT, and see section 10 |
| Anything the homeowner owes Mike | **Nothing.** Her obligation is to the lender | SCRIPT |

**The two monthly figures are both about 1.3% above a plain amortisation at 12.99%**, which reads as
a fee-inclusive rate card rather than an error. They are consistent with each other. **Use them
exactly as written and do not recompute them.**

**The dealer fee is ours and it is the most likely figure to be challenged in the room.** It is here
because the payouts screen cannot show $19,000.00 landing in a bank account when $19,000.00 is what
the homeowner financed, and a contractor reading that screen would notice immediately.

---

## 6. The loan, the stip and the notice to proceed

| Field | Value | Provenance |
|---|---|---|
| Product | A standard principal and interest loan | SCRIPT |
| Approved amount | **$19,000.00** | SCRIPT |
| Decision | **Approved in band**, on her screen, in the same session as submission | SCRIPT |
| Conditions | **One.** Her most recent paystub | SCRIPT |
| How the stip clears | **Mike captures it through DeDe on his phone**, and it clears automatically | ANDREW, departing from the script |
| Where the cleared state shows | The financing view, the customer view and the project view | SCRIPT and ANDREW, beat 10 |
| What we ever e-sign | **The Financing Agreement, and nothing else.** Mike's roofing contract stays paper | SCRIPT |
| Notice to proceed | Renders after the agreement is signed and the scope is known | SCRIPT |
| Notification behaviour | Mike is notified, and **the deep link lands him on the customer view** | ANDREW, beat 10 |

**The stip is the only pending state in the entire scenario.** Nothing else waits on anybody.

---

## 7. The scope, which arrives after the commitment

| Field | Value | Provenance |
|---|---|---|
| What Mike types | **26 squares**, manufacturer **GAF** | Squares **OURS**, GAF SCRIPT |
| Product | **Timberline HDZ**, architectural shingle | **OURS** |
| The rest of the scope | Tear-off, synthetic underlayment, architectural shingle | SCRIPT |
| Where it came from | Mike's own two-page paper contract, possibly parsable later | ANDREW, beat 8 |
| What it is not | **Not a line-item estimate and not a proposal.** It is a coverage description, so the loan knows what it is funding | SCRIPT |
| When | **After** the approval, not before | SCRIPT |

**26 squares against $19,000.00 is about $730 a square**, which is inside the market range for a
tear-off with architectural shingle. **It is ours and it is the figure to change if anybody objects.**

---

## 8. The twelve screens, and what each has to make true

**Andrew's seven experiences, expanded to the frames they actually need. Beat numbers are from the
script as it stands, 21 beats for profile (a).**

| # | Screen | Surface | Beat | What it has to make true |
|---|---|---|---|---|
| **1** | **New financing** | Pros mobile | 2 | Mike is starting an application, not opening a calculator. Name and email required, address and phone optional and fillable later. He enters $19,000.00 and picks which offers to present |
| **2** | **Present to customer** | Pros mobile | 3 | The same record stripped to what she needs to choose: two monthly figures, `$243.23` and `$287.77`. **Optional frame.** Andrew's note describes it and his screen list does not include it |
| **3** | **The application** | Her own computer | 5, 6 | A page or two of the real application, or a placeholder with thumbnails. **She chose her computer for autofill**, which is why this is not a phone |
| **4** | **Approved, one stip** | Her own computer | 7 | Approved for $19,000.00 at 12.99% over 180 months, with one outstanding item. **Optional frame**, and the only one that shows the decision where it actually lands |
| **5** | **Approval notification** | Pros mobile | **No beat** | Mike learns a loan exists on a record he did not create. **The script has no beat for this and it is being shown anyway** |
| **6** | **Cases** | Pros mobile | 8 | Money, then Cases. One open case, the paystub, marked as the customer's to resolve. A six-person org has **one** case, not twelve |
| **7** | **DeDe explains the case** | Pros mobile | 8 | What a stip is, what happens if it is not cleared, and an offer to capture the document now |
| **8** | **DeDe accepts the paystub** | Pros mobile | 9, 10 | Captured on Mike's phone, verified, cleared. **This is the departure from the script** |
| **9** | **Notice to proceed** | Pros mobile | 15 | A notification, deep linking to the customer view |
| **10** | **NTP on the financing view** | Pros mobile | 15 | Approved, signed, stip cleared, NTP rendered, the scope it covers, the monthly figure |
| **11** | **NTP on the customer view** | Pros mobile | 15 | The same fact from the customer's side, with the property and the one project on it |
| **12** | **NTP on the project view** | Pros mobile | 15 | The same fact from the project's side. **See section 10 on how empty this one is** |
| **13** | **Mark installation complete** | Pros web | 18 | An attestation and not a derivation. Andrew's open question: an ellipsis menu always present, plus a CTA once completion is plausible |
| **14** | **Payouts** | Pros web | 20, 21 | $17,575.00 deposited, in a combined list where loan draws and card payments sit together |

**Twelve required, two optional.** Frames 2 and 4 are the ones Andrew's list does not call for.

---

## 9. The payouts list, which needs more than this scenario has

**Frame 14 shows a combined list, so it needs rows that are not S6's.** All **OURS**, all for Pruitt
Roofing, all small-job plausible for a six-person roofing outfit.

| Date | Customer | Kind | Gross | Fee | Deposited |
|---|---|---|---|---|---|
| **Mon Oct 19, 2026** | **Nadia Brandt** | **Loan draw** | $19,000.00 | $1,425.00 | **$17,575.00** |
| Fri Oct 16, 2026 | Owen Marsh | Card payment | $1,850.00 | $53.65 | $1,796.35 |
| Wed Oct 14, 2026 | Priscilla Vance | Card payment | $640.00 | $18.56 | $621.44 |
| Tue Oct 6, 2026 | Hollis Reyna | Loan draw | $8,400.00 | $630.00 | $7,770.00 |
| Fri Oct 2, 2026 | Owen Marsh | Card payment | $2,300.00 | $66.70 | $2,233.30 |

**Card fees run at 2.9%** and **loan dealer fees at 7.5%**, which is why the two kinds of row look so
different in the fee column. **That contrast is the argument for the combined list**, so do not
harmonise it.

---

## 10. Values that must not be invented, and things that must not appear

**Do not put on any S6 screen:**

- **No reference codes.** No loan number, no application number, no case number, no invoice number.
- **The synthetic invoice, anywhere.** The model mints an Invoice at signature so the wedge does not
  write to a second money spine, and the script is explicit that it appears on none of Mike's
  surfaces. **If the Invoices count in the nav includes it, the nav is surfacing the one object that
  is supposed to be invisible.** For S6 that count should read zero or be absent.
- **No balance due.** Her obligation is to the lender, so a due figure on Mike's screen is a lie.
- **No cost, no margin, no profit figures.** None of the fourteen frames has any.
- **No proposal, no estimate, no contract of ours.** The only document we ever hold is the Financing
  Agreement.
- **No site assessment, no measurement of ours, no property photograph.** Nobody from our side has
  been to the house.
- **No crew, no schedule, no material orders on our surfaces.** All of it is off app.
- **No second person in the org.**

**Two counts in the supplied nav belong to the shell's demo org and not to Mike.** Invoices reads six
in amber and Cases reads twelve. **For S6, Cases is one and Invoices is empty.**

**The project view is nearly empty and that is the point.** It holds the property, the one job, the
financing and the notice to proceed. **Andrew's own note on beat 17 is the open question**: whether a
loan-only contractor may optionally keep a stage and a checklist on it, and if they do not use it,
that it must not roll up under the customer as unfinished work.

---

## 11. Everything marked OURS, in one list

**Change any of these freely. Nothing downstream depends on them.**

Pruitt Roofing. Mike's surname. Nadia Brandt. 4417 Meadowlark Lane, Aurora, CO 80013. Her phone and
email. The crew of four. The dealer fee of 7.5% and therefore the $17,575.00 net. 26 squares.
Timberline HDZ. The four other payout rows and their customers, Owen Marsh, Priscilla Vance and
Hollis Reyna. The 2.9% card fee. Every clock time except 4:50 pm, 4:55 pm, 4:58 pm, 5:20 pm, 5:24 pm
and 8:47 pm, which are the script's. The October anchoring, which the script constrains only to a
Thursday start and a Tuesday and Wednesday re-roof in October.

---

## 12. Learned from

- **22 Sep 2026.** Built from the live Confluence page rather than from any local derivation, after
  finding that the team's own screen flow for S6 is numbered against a 15-beat version of a script
  that now has 21 beats. **The script's own change note also claims a notification beat that the
  table does not contain**, which is why frame 5 is marked as having no beat.
- **22 Sep 2026.** **Andrew's UX notes were already inside the script on eight beats** and they are
  the strongest material in it. They are recorded here as ANDREW rather than folded into SCRIPT,
  because the script is the team's record and those notes are his.
- **22 Sep 2026.** The dealer fee had to be invented before the payouts screen could exist at all.
  **A wedge that only moves money cannot have a money screen without a fee**, and no source carries
  one.
