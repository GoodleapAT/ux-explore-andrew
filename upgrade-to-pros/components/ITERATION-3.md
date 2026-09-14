# Component records, iteration 3

**Created for memo 7, S14 end to end, 14 September 2026.**

> **Who may write to this file:** any surface that can write. **Record a component the moment you
> create or adapt it**, never later, because the usage rule and the anti-rule only exist while the
> reasoning is in the room.
>
> **Seven fields each**, per the standard as extended on 14 Sep: name, atomic level, states, when to
> use, when not to, what it does when its subject is absent, and **what variation it absorbs**.
> The last is new and is what lets a component change under a mock without anybody having to guess
> whether the change was legitimate.

**Atomic level is required and has never been enumerated.** The glossary records that as a gap, so
each record below says which level it means in words.

---

## TriageCard

**Level** organism, meaning a card with its own decision inside it rather than a row or a field.
**New** in memo 7, section A.

Where an inquiry goes: an advisor or a technician. Two rows, one selected, each with the reason for
the choice in the sub line.

**States** **asking**, where the routing question has been put and the destinations are drawn quiet
with no selection, which is what canvas frame 02 shows; undecided, where the destinations are
selectable and neither is selected and the primary action is unavailable; chosen, where one row
carries the selection and the other dims; and **derived**, where a rule picked from the answers and
the card reports rather than asks.

**Use it** at the first capture of demand, where a routing choice and a data capture happen in the
same ninety seconds and separating them would cost a sale.

**Do not use it** anywhere a routing decision can wait. A triage card on a screen nobody is under
time pressure on is a radio group with extra ceremony.

**When its subject is absent** at a contractor with one trade and one kind of visit, there is
nothing to triage, so the card is **absent** and the primary action becomes unconditional.

**Absorbs** more than two destinations, a reason code per destination, the derived state above, and
**a question above the destinations**, as RoutingQuestion, where the choice follows from an answer
rather than being made directly. **A new component instead** if the choice starts to carry a
scheduling consequence, because then it is a booking surface rather than a routing one.

**Amended 14 Sep 2026 from the canvas.** Without the absorption above, the system-age question on
frame 02 would have become a second triage component by the next round, which is exactly the failure
the seventh field was added to catch.

**Tiers** payments only: absent, no demand is captured. Selling: present. Operations: unchanged.

---

## MatchDismissalRow

**Level** molecule, a row inside a card.

A near-match on a customer or property that somebody has looked at and rejected, with what was
matched, why it is not the same, and when it was dismissed.

**States** unreviewed, one or more candidates awaiting a look; dismissed, shown with a reason and a
time; and **accepted**, at which point the row disappears because the record has been resolved
rather than created.

**Use it** wherever a record is about to be created that might already exist, and a person is under
enough pressure to create a duplicate by accident.

**Do not use it** as a search result. It is a record of a judgement, not a way of finding things.

**When its subject is absent**, which is most of the time, the row is **absent** and nothing marks
the fact that no candidates were found. A "no duplicates found" line would be explanatory copy.

**Absorbs** several candidates, a confidence ordering, and matches on different fields.
**A new component instead** if it ever has to merge two records, because a merge is an action with
consequences and this is a dismissal with none.

**Tiers** unchanged across all three; a payments-only contractor still has customers arriving.

---

## ReadinessCard

**Level** organism. **New**, and the most reusable thing in the memo.

What a dated commitment depends on, beside the date. Orders with promised dates, permits with
states, anything else a visit needs, with a segmented control whose label carries the count that
matters.

**States** clear, where the segment reads Blocking 0 and every row is quiet; **blocking**, where one
or more rows carry the count and the delayed row shows its previous date; and **unknown**, where a
dependency exists and nothing has promised a date for it.

**Use it** on any record whose date depends on something else arriving. Drawn for an install visit
and it would serve a permit-gated start or a financing notice to proceed unchanged.

**Do not use it** as a task list. Nothing on it is somebody's job to do; everything on it is a fact
derived from another record. The moment a row needs a checkbox it has become a TaskRow.

**When its subject is absent**, at an organisation that runs no orders and pulls no permits, the card
is **absent**, and the visit's date stands on its own.

**Absorbs** any number of dependency kinds, a previous-date history per row, and the blocking count
in the segment label. **A new component instead** if it has to gate the date rather than report on
it, because a gate needs an override and an override needs a reason.

**Tiers** payments only: absent. Selling: absent, nothing is scheduled. Operations: present.

**Note the two states are one component.** Sections I and J of memo 7 show the same card reading
Blocking 0 and then Blocking 1, and nothing else about it moves. That was the test.

---

## DerivationReceipt

**Level** organism. **New** in memo 7, section M, and it answers an object-register need that has
been open since the Thompson work.

Why a record reads the status it reads, when nobody set it. The list of evidence that produced a
derived state, each item with what it was and when it landed, and a line saying plainly that nobody
marked it.

**States** satisfied, every item present; **partial**, where some evidence has arrived and the
status has not changed yet; and **failed**, where an item came back negative, which is the red-tag
case and the reason this is a checklist rather than prose.

**Use it** beside any derived status a person might distrust or need to explain to a customer.

**Do not use it** for an authored status. A status somebody set needs an author and a time, not a
receipt, and showing evidence for a human decision implies the human was not trusted.

**When its subject is absent**, where a status is authored rather than derived, the card is
**replaced** by the author and timestamp.

**Absorbs** any number of evidence items, the failed state, and evidence arriving out of order.
**A new component instead** if it ever needs to show *why* an item is outstanding, because that is a
blocker explanation and it belongs with the blocker.

**Tiers** unchanged, wherever a lane is lit enough for a status to derive.

---

## OffSystemMoneyCard

**Level** organism. **Adapted** from MoneyCard in iteration 2, and it is the uncomfortable one.

What the customer agreed to pay, where the product does not collect it. What was agreed, in the
customer's own words, and a plain statement that money is handled elsewhere.

**States** agreed, where a tender promise exists; and **silent**, where none does.

**Use it** only where an organisation has the money capability and does not use it, which is not the
same as not having it. S14's contractor runs cash through QuickBooks by choice.

**Do not use it** at a payments-only contractor, where MoneyCard is the page. And **do not give it a
field**, ever. A field implies capture and there is nothing to capture into.

**When its subject is absent** the card is **absent** rather than empty, because a card saying
nothing about money on a screen where money changed hands is worse than no card.

**Absorbs** different tender words, a schedule in words rather than figures, and a third state where
a cheque is noted without being processed. **A new component instead** the moment anything on it
reconciles, because then it is MoneyCard.

**Tiers** payments only: replaced by MoneyCard. Selling and operations: present where the
organisation has switched money off.

**This record carries an admitted rule break.** The card's last line is explanatory copy inside a
screen, which the density standard forbids as an Always. It is there because a crew lead holding
$6,400 will not read a memo. **Recorded in the deviations register and withdrawable.**

---

## From the S14 canvas, 14 September 2026

**Written on the design surface and carried across in a write-back block.** Frames 03 to 14 needed no
new components: they are drawn on the five records above plus the iteration 2 set. **ReadinessCard
was used twice, frames 09 and 10, in its clear and blocking states, and nothing about it moved.**
That was the test and it passed.

---

## CandidateMatchList

**Level** organism, meaning a card that resolves a question rather than reporting an answer.
**New** on frame 01.

What the system already holds that might be the person on the phone. A typed query shown back, a
count, and the candidates it found, each with what it matched on and what is missing from it, and
two actions per row: open it, or say it is not the same.

**States** searching, where a query exists and candidates are still being counted; **candidates**,
one or more found and none resolved, which is the state drawn; **resolved to existing**, where a
candidate was opened and the create path closes; and **resolved to new**, where every candidate was
dismissed and the create action becomes available.

**Use it** immediately before any record that a person creates from something they were told, where
the same record might already exist. Demand capture is the case that produced it; a property at a
new address and a contact on an existing customer are the same shape.

**Do not use it** as a list view or a search results page. It exists to close a question with two
outcomes, and a screen where finding things is the whole job is a table with filters.

**When its subject is absent**, at an organisation with no existing customers on its first day, the
card is **empty and self-advertising**: the query reads back and the count reads none, because
somebody can make candidates appear by doing business. It does not say "no duplicates found", which
would be explanatory copy about a thing that did not happen.

**Absorbs** any number of candidates, matching on different fields, a confidence ordering, and the
create action moving from unavailable to primary as the last candidate is resolved.
**A new component instead** if it ever has to merge two records, or if a candidate can be resolved
into rather than opened, because both are actions with consequences and this one has none.

**Tiers** unchanged across all three. A payments-only contractor still has customers arriving twice.

**Note against MatchDismissalRow.** That record's anti-rule says it is not a way of finding things,
and it is right. The two components are the two halves of one act: this one finds and judges,
that one is the receipt for the judgement, and frames 01 and 03 show them in that order.

---

## RoutingQuestion

**Level** molecule, a question with its answers, sitting inside a card rather than being one.
**New** on frame 02, and it is the thing the brief called "whatever the system-age question turns
out to be".

One question whose answer decides where a record goes, drawn at heading scale with its answers as
choices and the consequence of each stated in the answer itself. It is not a field and must not look
like one.

**States** unasked, where the question stands alone and the destinations below it are quiet;
**answering**, drawn on frame 02, where the answer is arriving and no destination is selected yet;
and **answered**, where the destination resolves and the question collapses to a value in the record.
Frame 03 shows the answered state, as "System age, about 17 years" among the facts.

**Use it** where a single answer changes the route a record takes and a person is capturing data at
the same time. The whole point is the visual break from the fields beside it.

**Do not use it** for a fact that is merely useful. If the answer does not change where the record
goes, it is a field and it belongs in the field group.

**When its subject is absent**, at a contractor with one destination, the question is **absent** and
whatever it asked becomes an ordinary field.

**Absorbs** more than three answers, an answer that routes nowhere, and a free-text answer that a
person interprets. **A new component instead** if it ever asks two questions, because two questions
with a combined consequence is a rule and belongs to TriageCard's derived state, not here.

**Tiers** payments only: absent. Selling: present. Operations: unchanged.

---

## CaptureFieldSet

**Level** molecule, a group of fields inside a card.

What is being taken down, mid flight, with what has not been asked for written out rather than left
blank. Filled values read as values, and the ones nobody asked for read as their own answer.

**States** empty; **partial**, drawn on frame 02, some values present and the rest labelled as not
asked for; and **complete**, where every field a record needs is present.

**Use it** where a person is typing while somebody talks and the screen has to show what is missing
without accusing them of missing it.

**Do not use it** to display a finished record. A record that is no longer being typed into is a
fact list, which is what frames 03 and 07 use.

**When its subject is absent** the whole card is absent, because a field set with nothing to capture
is a form nobody opened.

**Absorbs** any number of fields, a field that cannot be asked for on this route, and the not-asked
wording. **A new component instead** the moment a field can be invalid, because validation needs
messages and messages are a different argument.

**Tiers** unchanged.

---

## Learned from

- **14 Sep 2026.** Built while drawing memo 7. **Five records, and the seventh field earned itself
  immediately**: ReadinessCard exists in two states across two sections of one memo, and without a
  declared absorption it would have been two components by the next round.
- **14 Sep 2026.** ReadinessCard is the only component here whose data already exists. Everything it
  shows is derived from an order, a permit and a visit, so **the gap it fills is a link rather than a
  record**, which makes it the cheapest thing in the object register to build.
- **14 Sep 2026, from the canvas.** The seventh field caught its second case within a day, and this
  time **it stopped a component rather than describing one**. The build brief predicted that frames 01
  and 02 would produce at least two new components and expected the system-age question to be one. It
  is not: the card that holds it already existed and only the question inside it is new. Recording the
  widening took two sentences; the alternative was two triage cards with one difference between them.
- **14 Sep 2026, from the canvas.** **The anti-rule did more work than the usage rule.**
  MatchDismissalRow says plainly that it is not a way of finding things. Reading that before drawing
  frame 01 is what produced CandidateMatchList rather than stretching the row into a search result.
  An argument for writing the anti-rule as carefully as the rule.

---

## Amendments from memo 8, 14 September 2026

**CaptureFieldSet becomes a form.** Andrew, on screens A and B: "Who is calling should be a form."
The record described a field set that displays what is being taken down. **It is now fields somebody
types into**, with labels above bordered inputs, a read-back treatment for values that arrived from
elsewhere, and helper text under those. **States** gain **empty with one prefilled**, which is the
opening state of every inbound call: the number came with the call and nothing else exists.
**Absorbs** gains a value arriving from outside the form, shown as filled with its provenance
underneath rather than as something typed.

**CandidateMatchList becomes nested rather than peer.** Andrew: "The matches should be a nested
element and called out as 'Potential matches'." It was drawn as its own card beside the capture. **It
is now a tinted block inside the form**, with its own small heading and count. **Use it** inside the
thing that produces it. **Do not use it** as a card of its own: a card implies a peer question, and
this is a consequence of what was typed two seconds ago.

**MatchDismissalRow loses its reason block and keeps its reason.** Andrew: the why-not-the-same block
"can be removed or added as a tooltip". **Drawn as a tooltip on the dismissal itself.** The judgement
is still captured, because it is knowable for ninety seconds and never again, but it no longer takes
a row on a screen somebody is typing into. **A new component instead** if the reason ever needs to be
searchable, because a tooltip is not a place you can find things in.

**TriageCard is not used on the inquiry screen at all.** Andrew: "I don't want to see any of this yet"
about advisor against technician. The card stands as a record and **the inquiry no longer shows a
destination.** The routing either happens later or is derived without being seen, and neither is
decided. **That is a flow question rather than a component one**, and it is open in memo 8 section C.

**A new nested block, and it is the same shape twice.** Potential matches inside a capture, and
Coming up inside a project card. Both are a tinted block with a small heading inside a card, holding
rows that belong to the card rather than beside it. **Worth naming as one component before it is
drawn a third time**, which is the thing the seventh field exists to catch.
