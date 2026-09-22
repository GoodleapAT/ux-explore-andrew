# CD prompt: S6, the loan-only wedge

**22 September 2026. Fourteen frames, two of them optional. Upload `S6-DATA.md` alongside this file,
then paste the section headed "The prompt" as your message.**

---

## What you are receiving

**`S6-DATA.md`**, the data pack. Every name, figure, date and time the screens need, each carrying
its provenance. **There is no memo for S6 and there are no mockups to rebuild from.** This is the
first scenario in the series that goes straight from a script to a canvas.

**The scenario itself** is a beat script on Confluence in the ProsOperations space, authored by Joel
and last modified 15 September 2026. It is the team's record, not ours. **Andrew's own UX notes are
written into it on eight beats**, and those notes are the design direction; the data pack marks them
ANDREW so they are not confused with the narrative.

**The navigation** Andrew supplied on 22 September 2026 is the shell of record for these concepts. It
supersedes the seven-item nav in `memo-14-s5-customer-view.html`.

---

## The most important instruction

**Build this out of the components, objects and layouts already in this project.** Where this prompt
and the project disagree about how something is constructed, **the project wins**. Where they
disagree about what is on the screen, **this prompt wins**.

**And the thing that makes S6 different from everything before it: eleven of the fourteen frames are
not Pros Web.** Nine are Pros mobile, two are the homeowner's own computer, and only three are the
web shell this project has been building against. **There is no mobile shell in this project yet**,
so the first decision is the frame itself, and it is the one thing worth getting agreement on before
drawing nine screens inside it.

---

## The scenario, in six sentences

Mike Pruitt owns a six-person roofing outfit. He is at a kitchen table in a hail-damaged neighbourhood
with his own two-page paper contract: tear-off, synthetic underlayment, architectural shingle,
$19,000.00. The homeowner wants the roof and cannot pay cash, so **the only thing that ever touches
our product is the loan**: he prices it on his phone, shares the application, she fills it in on her
own computer and is approved in band with one outstanding condition. **He clears that condition
himself, through DeDe, on his phone**, and the notice to proceed renders the same evening. Two weeks
later his crew re-roofs the house, the county signs the final, and Mike taps a button to say so.
The money lands the next business day and he reconciles it at six in the morning from a list that
also holds his card payments.

**He sells, contracts, permits, schedules and builds entirely off our surfaces.** Application status,
cases, payouts and statements are the whole of the product he experiences, and **that thinness is the
scenario's argument**, not a limitation of it.

---

## The prompt

Build the fourteen frames in `S6-DATA.md` section 8, in that order, using this project's existing
components and this project's type scale and spacing. The data pack is the only source of values; do
not invent a name, a figure, a date or a time that is not in it. Say what is missing instead.

Nine frames are a phone, two are the homeowner's own laptop, three are the web shell. The mobile
frame does not exist in this project yet, so propose one and use it consistently rather than
adapting the web layouts to a narrow column.

The scenario is a contractor who uses us only for financing. Nothing about selling, scheduling,
crews, materials or permits happens on our surfaces, so those regions of the product are empty for
this customer and must not be drawn as if they are waiting to be filled in. The navigation as
supplied keeps every section visible and padlocks the two the org has not bought; follow that
pattern rather than shrinking the nav.

Read the hard rules and the open questions below before you start. The open questions are open; if
you find a better answer to one, say so rather than resolving it quietly on a frame.

---

## The elements the beats do not cover

**The script says what happens. These are the things a screen needs that no beat mentions, and they
are where most of the design work is.**

**The navigation itself.** Home, Customers, Engagements, then Sell, Work, Money, Analytics, Capital,
Banking, Settings. Cases and Payouts both live under Money, next to Invoices, Payments and Financing.
**Capital and Banking carry a padlock and are greyed**, which is the advertise position: a capability
that will exist advertises, a gap the model cannot answer is left out. **Engagements or Jobs will
probably become Projects**, so do not build anything that depends on either word.

**The cases queue as a surface.** Nothing in the script describes it. What a case row says, whose it
is to resolve, how an org with one open case looks as against one with forty. **For S6 there is
exactly one case.**

**DeDe as a working surface, not a suggestion line.** Three frames need it: explaining the condition,
offering to capture the document, and confirming it cleared. The library has DeDe only as provenance
in a sub line, never as a conversation, and never as something that takes a photograph and verifies
it. **This is the newest pattern in the set.**

**The notification pattern on mobile.** Three notifications, for the approval, the cleared condition
and the notice to proceed. Andrew's note on beat 10 says the deep link lands on the customer view,
so the notification and its destination are a pair.

**The same fact on three surfaces.** Frames 10, 11 and 12 are the notice to proceed seen from
financing, from the customer and from the project. **They exist to show that one event reaches three
lenses**, so the differences between them are the content of those frames.

**The mark-complete affordance.** Andrew's open question, in his own words: maybe every project needs
an ellipsis menu at all times, plus a CTA reading Mark as complete once it becomes clear the project
is likely or almost complete. **Nothing in the model knows when that is**, which is why it is a
question.

**A combined payouts list.** Loan draws and card payments in one list with their own fee treatments,
which is Daidipya's request on the last beat. The data pack carries five rows for it.

**What a nearly empty project looks like.** The project holds a property, one job, the financing and
the notice to proceed, and nothing else will ever attach to it. Andrew's note on beat 17 asks whether
a loan-only contractor may optionally keep a stage and a checklist on it, and if they do not, that it
must not roll up under the customer as unfinished work.

---

## Hard rules

- **No reference codes.** No loan, application, case or invoice number anywhere.
- **Dollar values always show cents.** `$19,000.00`, `$243.23`, `$17,575.00`.
- **Dates are US format and never day first.** `Oct 1, 2026`. **Times carry a zone and this scenario
  is Mountain**: `4:50 pm MDT`, not PDT.
- **No explanatory copy inside a frame.** If a message seems necessary, list it outside the frame as
  a suggestion so it can be judged on its own.
- **Verb first on buttons, CTAs and menu items.** Sentence case. American English.
- **Colour only where somebody has to act**, at most one coloured region per frame. **The open
  condition is the only thing in this scenario that anybody has to act on**, so it is the only place
  colour is earned. Once it clears, nothing on these screens is coloured.
- **A gap the model cannot answer is left out**, not greyed and not labelled unavailable. The
  padlocked nav sections are the declared exception, because they advertise something buyable.
- **Badges only where they carry a state a row cannot say in words.** Three or four a screen, not
  twelve.
- **The synthetic invoice appears nowhere.** See the data pack, section 10, for why.
- **Nothing shows a balance owed to Mike.** Her obligation is to the lender.
- **No cost, margin or profit figures on any frame.**
- **The footer reads Pruitt Roofing, Mike Pruitt, Owner**, not the shell's demo org.

---

## Six things nobody has decided. Do not resolve them quietly

1. **The mobile shell does not exist.** Nine frames need it. Propose it as a proposal, and say what
   you took from the web shell and what you had to invent.
2. **Whether the nav shrinks at this tier.** It does not shrink in the shell as supplied. A loan-only
   org would see Sell, Work and Analytics with nothing in them, and the padlock is an available
   mechanism if we decide those should be gated too. **Reproduce the nav as supplied and flag the
   consequence rather than pre-empting it.**
3. **Who the stip belongs to.** The case says it is the customer's to resolve and Mike resolves it
   through DeDe anyway. Both are true and the row's wording has to carry both without reading as a
   contradiction.
4. **The notice to proceed is shown without its two preconditions.** The e-signature and the scope
   entry are not drawn, by decision. **So frames 9 through 12 assert a state whose causes are not on
   screen.** That is accepted, and it means those frames must not imply the signature happened
   somewhere the viewer can go and look.
5. **The mark-complete trigger.** See the elements section. An ellipsis always, or a CTA that appears
   on a condition nothing currently computes.
6. **What the project view is for, at this tier.** Optional tracking, or a record that exists only so
   the money has a parent.

---

## What good looks like

**A viewer with no context should be able to say, after fourteen frames, that a contractor can use us
for one thing and get value from it.** Not that the product is missing nine of its ten parts.

**And the single moment the whole scenario turns on is one evening.** Four fifty in a driveway, a
notice to proceed before nine, and a signed paper contract in a truck that we will never see. **If
the times are legible on the frames, the scenario argues for itself.**
