# S6, the loan-only wedge: the scenario, for Claude Design

**22 September 2026. Written to convey the scenario and the elements the concept screens will need.**

> **This is not a build brief.** It says what the scenario is, what Andrew intends to show, what the
> screens will need that the beats do not mention, and what is still undecided. **Nothing here asks
> for anything to be drawn**, and the frame list is his intent rather than a specification.
>
> **Where the scenario comes from.** A beat script on Confluence, in the ProsOperations space,
> authored by Joel and last modified 15 September 2026. It is the team's record. **Andrew's own UX
> notes are written into it on eight beats**, and the data pack marks those ANDREW so they are not
> read as narrative. The team also has a screen flow file for S6; it is numbered against a
> fifteen-beat version of a script that now has twenty one, and Andrew's instruction is to ignore it.
>
> **The data pack is `S6-DATA.md`**, in the same folder. Every name, figure, date and time, each
> carrying its provenance.

---

## The scenario, in six sentences

Mike Pruitt owns a six-person roofing outfit. He is at a kitchen table in a hail-damaged neighbourhood
with his own two-page paper contract: tear-off, synthetic underlayment, architectural shingle,
$19,000.00. The homeowner wants the roof and cannot pay cash, so **the only thing that ever touches
our product is the loan**: he prices it on his phone, shares the application, and she fills it in on
her own computer and is approved in band with one outstanding condition. **He clears that condition
himself, through DeDe, on his phone**, and the notice to proceed renders the same evening. Two weeks
later his crew re-roofs the house, the county signs the final, and Mike taps a button to say so. The
money lands the next business day and he reconciles it at six in the morning, from a list that also
holds his card payments.

**He sells, contracts, permits, schedules and builds entirely off our surfaces.** Application status,
cases, payouts and statements are the whole of the product he experiences, and **that thinness is the
scenario's argument** rather than a limitation of it.

---

## What Andrew intends to show

**Seven experiences, which imply about fourteen frames.** Section 8 of the data pack lists them with
the values each one needs.

| His words | Surface | Script beats |
|---|---|---|
| New finance in app, the calculator | Mobile | 2 |
| Customer completes application | Her own computer | 5, 6 |
| Notification for approval | Mobile | **No beat exists** |
| Cases in the left nav, the open paystub case, DeDe explains it and offers to take the picture | Mobile | 8 |
| In the DeDe chat the paystub is accepted, then the notice to proceed in the financing, customer and project views | Mobile | 9, 10, 15 |
| Contractor marks installation complete from a customer view | Web | 18 |
| Payouts in the left nav, the deposit in a list with loans and card payments together | Web | 20, 21 |

**Eleven of the fourteen frames are not Pros Web.** Nine are a phone, two are the homeowner's own
computer, three are the web shell.

**Two departures from the script, both his, both deliberate.** Mike clears the condition rather than
the homeowner, who in the script photographs her own paystub hours later from her couch. And the
notice to proceed appears without the e-signature or the scope entry, which are its two
preconditions in the script, so four of the frames carry a state whose causes are not shown.

---

## The elements the beats do not cover

**The script says what happens. These are the things the screens will need that no beat mentions.**

**The navigation.** Home, Customers, Engagements, then Sell, Work, Money, Analytics, Capital, Banking,
Settings. **Cases and Payouts both sit under Money**, next to Invoices, Payments and Financing, which
is what gives two of the seven experiences a home. **Capital and Banking carry a padlock and are
greyed**: the advertise position rather than the left-out one. It supersedes the seven-item nav in
memo 14. **Engagements or Jobs will probably become Projects.**

**The cases queue as a surface.** What a case row says, whose it is to resolve, and how an org with
one open case looks. For S6 there is exactly one.

**DeDe as a working surface rather than a provenance line.** Three of the frames need it explaining
the condition, offering to capture the document, and confirming it cleared. The library holds DeDe
only as words in a sub line, never as a conversation and never as something that takes a photograph
and verifies it.

**The notification pattern on mobile.** Three of them, for the approval, the cleared condition and
the notice to proceed. Andrew's note on beat 10 pairs a notification with its destination: the deep
link lands on the customer view.

**One fact on three surfaces.** The notice to proceed seen from financing, from the customer and from
the project. **The differences between those three are the point of showing all three.**

**The mark-complete affordance.** In his words: maybe every project needs an ellipsis menu at all
times, plus a CTA reading Mark as complete once it becomes clear the project is likely or almost
complete. Nothing in the model computes likely.

**A combined payouts list**, loan draws and card payments together with their own fee treatments,
which is Daidipya's request on the last beat. The pack carries five rows for it.

**A nearly empty project.** It holds a property, one job, the financing and the notice to proceed,
and nothing else will ever attach to it.

---

## How the values are written

**From the data pack and the copy standard, so nothing has to be looked up.**

Money always shows cents: `$19,000.00`, `$243.23`, `$17,575.00`. Dates are US format and never day
first: `Oct 1, 2026`. **Times are Mountain, not Pacific**, because the scenario is set in Aurora,
Colorado: `4:50 pm MDT`. No reference codes exist anywhere in this scenario. **The footer reads
Pruitt Roofing and Mike Pruitt, Owner**, not the shell's demo org.

**Three things the model says must not appear**, with the reasons in section 10 of the pack: the
synthetic invoice, which the wedge mints at signature and which appears on none of Mike's surfaces;
any balance owed to Mike, because the homeowner's obligation is to the lender; and any cost, margin
or profit figure.

---

## What is undecided

1. **There is no mobile shell.** Nine frames would need one and nothing in the project has one.
2. **Whether the nav shrinks at this tier.** It does not in the shell as supplied, so a loan-only org
   sees Sell, Work and Analytics with nothing in them. The padlock is an available mechanism if those
   should be gated too.
3. **Who the condition belongs to.** The case is the customer's to resolve and Mike resolves it
   anyway.
4. **The mark-complete trigger**, as above.
5. **What a project view is for at this tier.** Andrew's note on beat 17: optional stage and checklist
   tracking may belong there, provided an unused one does not roll up under the customer as
   unfinished work.
6. **The nav's counts belong to the shell's demo org**, six invoices and twelve cases. For a
   six-person roofing outfit with one loan, Cases is one and Invoices is empty.
