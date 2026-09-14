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

**States** undecided, where neither row is selected and the primary action is unavailable; chosen,
where one row carries the selection and the other dims; and **derived**, where a rule picked from
the answers and the card reports rather than asks.

**Use it** at the first capture of demand, where a routing choice and a data capture happen in the
same ninety seconds and separating them would cost a sale.

**Do not use it** anywhere a routing decision can wait. A triage card on a screen nobody is under
time pressure on is a radio group with extra ceremony.

**When its subject is absent** at a contractor with one trade and one kind of visit, there is
nothing to triage, so the card is **absent** and the primary action becomes unconditional.

**Absorbs** more than two destinations, a reason code per destination, and the derived state above.
**A new component instead** if the choice starts to carry a scheduling consequence, because then it
is a booking surface rather than a routing one.

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

## Learned from

- **14 Sep 2026.** Built while drawing memo 7. **Five records, and the seventh field earned itself
  immediately**: ReadinessCard exists in two states across two sections of one memo, and without a
  declared absorption it would have been two components by the next round.
- **14 Sep 2026.** ReadinessCard is the only component here whose data already exists. Everything it
  shows is derived from an order, a permit and a visit, so **the gap it fills is a link rather than a
  record**, which makes it the cheapest thing in the object register to build.
