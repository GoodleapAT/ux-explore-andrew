# Component records, iteration 5

**The first records written under the two-axis scheme. 16 September 2026.**

> **Two fields are new on every record here** and are not on iterations 2 to 4.
>
> - **Layer.** `core`, `recipe` or `snowflake`. Who owns it and whether a product may change it.
> - **Composes.** For a recipe or a snowflake, the core components it is built from.
>
> **Level stays.** It is the size axis, atom through template, and it is a different question from
> layer. Both are recorded. See `in-depth/three-layers.md`.
>
> **Records 2 to 4 do not have these fields yet.** They get them when each is next touched, not in a
> sweep, per the standard's own rule about not stopping to build the library.

---

## MoneyCard

**Level** organism. **Layer** **recipe**. **Adapted**, and this record supersedes the two separate
records in iteration 2 and iteration 4.

**Composes** Card, Badge, Button, and a divider. No table.

The money on a record, in four tiers of decreasing weight. **The tiers are the component**, and the
reason it works is that they cannot be confused with one another.

| Tier | What it holds | Example |
|---|---|---|
| **Hero** | One label, one figure, one status line, one colour | Balance · $72,600 · Due on completion |
| **Action** | At most one button, and only when somebody must act | Create invoice |
| **Blocks** | The figures the hero is derived from | Contract $73,100 · Collected $500, paid |
| **Transactions** | Individual movements, dimmed | Three plan charges at $29 |
| **Footer** | A roll-up of the transactions tier, never of the blocks | Plan billing. 11 charges, $319 to date |

**States** at rest, where the hero is $0 and nothing is due; **not yet due**, where a balance exists
and its trigger has not fired; **due**, where the hero takes the warning colour and the action
appears; **invoiced**, where the hero keeps its figure and the status names the invoice; and
**settled**, where the hero is $0 and the blocks read paid.

**Use it** for the money on any record that holds a balance: a customer, a project, and an invoice.

**Do not use it** for cost and margin. That is a second card under the same group heading, and the
two are a pair rather than one card with more rows.

**When its subject is absent** the card is replaced by a single sentence naming why there is no money
yet, for example *no price yet* before a proposal is priced. **It does not render empty.**

**Tiers, per product tier.** Payments only: hero, blocks and transactions, no action. Selling: adds
the contract to the blocks. Operations: unchanged.

**What it absorbs.** A second money stream, by keeping it in the transactions tier with its own
footer. A change in what the hero is derived from. An extra block. **A new component instead** if the
hero has to carry two figures at once, because that is two cards.

### Why the tiers matter more than the styling

**A recurring charge and a project payment must never be totalled.** They are separate streams that
happen to belong to the same customer. A previous memo showed "13 charges, $73,448" by adding a
service plan's monthly billing to a project's payments, and the arithmetic was not wrong so much as
meaningless.

**The tiers make that mistake unavailable.** Contract and collected are blocks; plan charges are
transactions; the footer rolls up the transactions tier only. Nothing in the component offers a place
to put a number that spans both, so nobody puts one there.

### The four-signals question, answered

A due balance carries four things: a label, a coloured figure, a status, and a button. That looked
like the same fact four times and it is not.

**Due now and not invoiced are two different facts**, and a person who sees the first without the
second will go looking for an invoice that does not exist. **The colour is emphasis, not information,
and the button is the only thing anybody can act on.** One component, one hierarchy, four jobs.

---

## RevenueCard

**Level** organism. **Layer** **recipe**. **New**, 16 September 2026.

**Composes** Card, and a divider. No badge and no button.

The money the organisation earned, as opposed to the money the customer owes. **It is always the
second card in a Money group and never appears alone.**

**Three tiers.** A **roll-up** of two or four figures, gross profit and margin, and where a forecast
exists, gross profit and margin to date alongside them. Then one **block per revenue stream**, each
carrying its own cost, gross profit and margin as a small grid. No total row.

**States** to date only, where every stream is closed; **to date and forecast**, where at least one
stream is signed and unfinished; and **earned, not collected**, where work is complete and the money
has not arrived.

**Use it** beside MoneyCard on a customer or a project.

**Do not use it** where cost is unknown. **The card is absent rather than empty**, because a revenue
figure with no cost beside it invites somebody to read revenue as profit.

**When its subject is absent** the Money group holds one card and keeps its heading.

**What it absorbs** any number of streams, a stream with no cost, and a forecast alongside an actual.
**A new component instead** if a stream needs its own breakdown below the stat grid, because that is
a table and this is a card.

### The rule it has to hold on a project

**Per-job margin is unavailable**, because revenue occurs at the project and cost at the job, and no
allocation rule exists. **So on a project this card shows one block where a reader expects two.**
That is correct and it should not be explained on screen. The absence is the design.

---

## Learned from

- **16 Sep 2026.** Both records come from Andrew's own customer-record work, built one state at a
  time. **The four-tier shape was designed before it was described**, which is the order the library
  is supposed to work in: extract from a real screen rather than specify in advance.
- **16 Sep 2026.** Writing MoneyCard as one record **retired two**, and the merge was recommended in
  iteration 4 on the grounds that they were near-identical siblings. **The tier scheme is why they are
  one**: an off-system payment is a transaction with a different source, not a different card.
