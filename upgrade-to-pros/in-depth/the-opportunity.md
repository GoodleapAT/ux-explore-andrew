# The Opportunity

**The durable record of a trade a customer might buy. 15 September 2026. Status: open.**

> **This document was written three times in one day** and the version below is the third. The first
> two are kept at the foot, because the route to this answer is more useful than either of them.
>
> **Its settlements are in `DECISIONS.md`** and its nouns and values are in `VOCABULARY.md`. If they
> disagree with this file, they win.

---

## What it is

**One record per customer, per property, per trade.** A thing this household might buy at this
address. It is created the first time anybody has a reason to think so, and **it outlives every sale,
every lead and every project**.

**Where the demand came from is an attribute of it, not a different kind of object.** A trade the
customer asked for through the app and a trade the system recommended are the same kind of record with
different origins. **That was the last piece to fall into place** and it is the part worth defending.

## The lifecycle

| Status | Means | Set by |
|---|---|---|
| **Open** | It exists and nobody is selling it. May carry a **worth raising** mark and a **revive date** | Created open. Returns here after a decline |
| **On a lead** | It is being sold, as part of one lead's selling episode | The lead picking it up |
| **Won** | It sold and became committed work. **The only terminal state** | The proposal being accepted |
| **Dismissed** | Nobody is going to sell it. **Requires a reason code and a note** | A person |

**Won is terminal and nothing else is.** A trade that was offered and declined goes **back to Open**,
carrying a revive date and a history entry saying what happened. **That is the whole point of the
object** and it is what Andrew asked for: a roofing opportunity that was once on a lead, was priced,
was declined, and is now free-standing with its story intact.

**Two kinds of no, and they are not the same.** *Dismissed* is us deciding it is not worth raising.
**A customer declining is not a dismissal**: it returns the opportunity to Open. **Where a customer's
final no lives is C's reading and wants confirming:** Dismissed with a reason code that says the
customer refused, as against a reason code that says we judged it not worth raising. The standing rule
already requires a reason on every unhappy state, so this costs nothing new.

## What the history holds

**This is the screen Andrew described.** Under the customer, roofing appears as an opportunity, and
opening it shows how it got here.

- Raised by the customer through the Home App, 4 August, in their own words.
- Immediately associated with a lead, the same morning, because the contact qualified itself.
- Put on the sale at Start selling, 10 August, alongside siding and windows.
- Priced at $38,900 as an option on the proposal, 13 August.
- Presented 18 August, and declined for this season. The customer said the roof is "not leaking yet".
- Free-standing again since 18 August, with a revive date of March 2027 and a note to lead with the
  August storm photographs.

**Nothing in that list is derived from anywhere else.** It is one record's own history, and it is the
first thing in either model that can answer "what has happened with the roof" in one place.

## The interest is gone

**Dropped, 15 September 2026.** It was the opportunity's participation in a lead, and once the
opportunity carries its own status and history there is nothing left for it to hold. **An opportunity
is on a lead or it is not**, and a proposal option prices the opportunity directly.

**Four demand grains instead of five**: opportunity, inquiry or prospect, lead, project. **The grain
count has been the biggest logged risk to a demand screen all week and this is the first time it has
gone down.**

**What it costs.** The word is in the team's own position on lead granularity, and it was in six of
our documents. **The behaviour their position describes is untouched**: a lead still carries several
trades and a CSR still discusses three of them in one conversation without changing views. **Only the
object is gone**, and that is a vocabulary difference to raise rather than a disagreement.

## What this answers

**Six open questions, and two blocking rows in the object register.** Recorded here because a change
that closes this much is worth being able to see the shape of.

| What was open | How this answers it |
|---|---|
| **What closes a lead** | Everything on it resolves, because a declined trade goes back to being an opportunity rather than needing the lead kept alive. **The lead closes at the hand-off** |
| **The project can never reach a final state** | No new demand joins a closed lead, so the project stops accumulating and Paid can be terminal |
| **The lead's derived status had a hole** | The lead is already closed by the time work is in delivery, so the undefined state cannot occur |
| **Where several trades live** | As opportunities against the customer and the property, attached to a lead while being sold |
| **Does an unmarked opportunity expire** | It does not need to. It has a history rather than only a state, so a stale one is legible as stale |
| **A queue that surfaces a revive date** | The opportunity list under the customer, filtered by revive date. **Blocking in the object register since the Thompson work** |
| **Lead origin as a first-class attribute** | Origin is a property of the opportunity. **Also blocking, all week.** A trade the customer asked for and a trade we suggested stop being different kinds of thing |

## The lead is now a selling episode

**It opens when a contact arrives and there is no open lead for that customer and property. It closes
when everything on it is resolved**, which in the canonical example is 24 August, the hand-off.

**So the join rule only applies while a lead is open.** A contact during delivery finds none, and
starts a new lead with its own project. **That is correct rather than a problem**: it is a different
sale, and the customer record is what groups them.

**One consequence to be comfortable with.** Two projects can be live at one property, one delivering
and one selling. Nothing forbids it, the customer record already groups by project, and **it is
cheaper than either merging or a permanent lead.**

## Open

1. **Where a customer's final no lives.** Dismissed with a reason code is C's reading. See above.
2. **Does Start selling attach the opportunity, or does qualification?** C's reading is that the trade
   named by the contact goes on the lead immediately and the rest join at Start selling. **That is
   what gives the gap before Start selling something to be**, and it is a reading rather than a
   ruling.
3. **Who may mark an opportunity worth raising**, and does a dismissal suppress the recommendation
   coming back. Both carried over from the first version of this document.
4. **Does the name shrink?** A container named by its contents loses a trade when one is declined.
   Carried over.

---

## How this document got here, in one day

**Worth keeping, because the first two answers were both wrong in instructive ways and the defect that
started it turned out not to be the reason for anything.**

**Version one, morning.** The worked example had a system-suggested trade recorded as an interest
twenty two days before any lead existed for it to live inside, and the file admitted it in passing:
the record "rides along until there is a lead to attach it to". **A record with nowhere to live.** The
answer was a new object called Opportunity that converted to an interest when a lead was created, and
read Converted, terminal, one way.

**Version two, midday.** Automatic qualification moved the lead to the first contact, so nothing was
homeless any more. **The defect that prompted the object had dissolved.** The object survived on the
other finding: three facts had been sharing one record, and an interest with an origin could not tell
"the system thinks they might buy this" from "we have decided to raise it" from "the customer has
engaged on it".

**Version three, afternoon.** Andrew: opportunities should be tracked separately, connected to leads
but surviving them, so a declined trade becomes free-standing again with a history. **That inverted
the model.** The opportunity became the durable object and the interest the temporary one, and once
the opportunity carried its own history the interest had no work left to do.

**The pattern, and it is the reason this section exists.** Each version was a better answer to a
question the previous version had made askable. **The homelessness was a symptom, the collapsed record
was the defect, and the durable record was the fix**, and none of the three was visible from where the
previous one stood.

## Learned from

- **15 Sep 2026.** Andrew, reworking how three trades arrive, having spotted that the arrival story
  was the thing to settle before any screen. **The defect was found by asking about the narrative
  rather than about the model.**
- **15 Sep 2026.** The presenting defect dissolved within hours and the object stood on a different
  argument. **Do not retire a finding because the symptom that exposed it goes away.** Written into
  `../../standards/walk-the-data-first.md`.
- **15 Sep 2026.** C proposed a second sibling project for demand arriving after a contract; Andrew
  corrected it to one lead, one project, with jobs inside. **Flagged as a reading rather than logged
  as settled, so the correction cost one line.** Written into `../../standards/after-a-ruling.md`.
- **15 Sep 2026.** **Dropping an object reduced the grain count for the first time this week.** Every
  previous move added one. Worth noticing which direction a model change travels in.
