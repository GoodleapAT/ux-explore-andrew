# CD prompt: the S5 customer record, payments only

**21 September 2026. Build this from what you already have.**

---

## What you are receiving

**`memo-14-s5-customer-view.html`**, one screen with the argument under it. A customer record at the
payments-only tier, ten months after a single card payment, at the moment the homeowner asks for more
work.

**The memo is editorial. Do not put its prose on the canvas.** A canvas is read as a design, so
annotation on a frame is noise on the thing being judged. The mock in it is a sketch of the content
and the order, not of the visual detail.

---

## The most important instruction

**Rebuild it out of the components, objects and layouts already in this project. Do not reproduce the
memo's markup.** The memo was written outside Claude Design in a smaller, simpler kit, so its type
scale, its card composition and its spacing are all approximations. Where the memo and this project
disagree about how something is built, **this project wins**.

The clearest case, and the reason this instruction is first:

**Overview is one card, not two.** The memo draws an Overview card and a Projects and service plans
card side by side. In this project the S15 customer record already solves this: a single `M.Card`
holding a three column grid, `repeat(3, minmax(0,1fr))` with a 24px gap, each column after the first
separated by `padding-left:24px` and `border-left:1px solid var(--sol-borders-ui-subtle)`. Use that.

For S5 the three columns are:

| Column | Label | Contents |
|---|---|---|
| 1 | **1 contact** | Dana Whitfield, no role set. Phone icon button only, because there is no email address |
| 2 | **1 property** | 1806 Cedar Row. No city, no property detail, and **no photograph**, so omit the 104px raster rather than showing an empty one |
| 3 | **Projects and service plans** | One row: the fence, $2,400.00, Paid |

The same applies everywhere else. Reuse, do not rebuild:

- **Breadcrumb.** Underlined 14px secondary links with a `caret-right` icon between them, not a slash.
- **Title block.** `h3` at 700 32px/40px with `letter-spacing:-0.02em`, subtitle at 400 16px/24px
  secondary, 8px below. The memo's 26px title is wrong.
- **Group headings.** `h4` at 700 24px/32px, in a section with a 16px gap. The memo uses 18px.
- **Page frame.** `padding:32px 40px 40px`, `gap:32px`, inside the Merlin shell.
- **Money group.** The S15 customer record's money treatment, unchanged in structure: hero figure,
  one action, the derived facts, then the transaction rows and a footer line.
- **The overflow menu.** `PwOverflowMenu`, the one the payments pages share.
- **Buttons.** `M.Button` with its own variants and sizes. Outline for secondary, and whatever the
  project already uses for a primary.
- **Separators.** `M.Separator` rather than a hand-rolled rule.

**One thing the memo does that you should keep:** the money formatter. Your own list recreation already
renders currency with a two digit minimum, so every figure reads `$2,400.00` and `$0.00`. Keep that,
and keep US dates, `Jun 12, 2026`.

---

## The screen

**Org:** Caldwell Brothers Fence and Deck, two brothers, four in season. No CRM, no field service
software. They use us to take card payments and nothing else.

**Viewer:** Wes Caldwell, the brother who does the office side.

**Moment:** Tuesday, April 13, 2027. Dana Whitfield has called about a gate. Wes went to Customers,
searched Whitfield, and opened her record.

### Groups, in order

**Four groups in the same order as the S15 record: Overview, Active projects, Selling, Money.** At
this tier Active projects and Selling hold nothing, so **they disappear rather than render empty.**
That leaves:

1. **Overview**, the single three column card described above.
2. **Money**.
3. **Discover more Pros functionality to bolster your business**.

**Money is last, and it is the only group here with anything in it.** That is deliberate and it is the
open question in the memo. One order across all three tiers was judged worth more than a better order
at one of them. Do not reorder it without saying so.

### Header

- Breadcrumb: Customers, then Dana Whitfield.
- Title: **Dana Whitfield**. Subtitle: **Customer since June 2026 &middot; 1806 Cedar Row**.
- **No primary button in the header.** The S15 record has *Log a call*, which does not exist at this
  tier. Just the overflow menu.
- **Overflow menu**, and its first item is the reason it is there: **Take a payment**, then Add a
  note, Edit name and address, Merge customers. Draw it open in at least one frame so the item is
  visible.

### Money

- Hero: **Outstanding $0.00**, status **Nothing due**.
- One action beside the hero: **Take a payment**.
- Derived facts: **Collected, all time $2,400.00** and **Last payment Jun 12, 2026**.
- Three transaction rows, dimmed, newest first:
  - Paid out to your bank, Jun 15, 2026, $2,400.00
  - Credit card, approved, Jun 12, 2026 at 4:35 pm PDT, $2,400.00
  - Credit card, declined, Jun 12, 2026 at 4:34 pm PDT, status **Retried and approved**
- Footer: **One payment since June 2026**, with a See all activity link.

### Discover

**Three columns, not three rows.** Three cards across, each with a heading, one sentence, and a
**Learn more** link. **No footer line under the row.**

| Heading | Sentence |
|---|---|
| Proposals and pricing | Send a quote and get it accepted here instead of by text, with your own prices behind it. |
| Jobs and scheduling | Book a crew, track the work day by day, and keep the photos with the job they belong to. |
| Costs and profit | Put materials and labor against a job and see what it earned once the work is done. |

---

## The data, so nothing gets invented

| Field | Value |
|---|---|
| Homeowner | **Dana Whitfield** |
| Address | **1806 Cedar Row.** No city on record, no property detail, no photograph |
| Phone | **(916) 555-0143**, and it came off the card receipt, not from a contact form |
| Email | **None.** Nobody ever asked |
| Customer since | **June 2026** |
| The payment | **$2,400.00**, credit card, Friday Jun 12, 2026 at 4:35 pm PDT |
| The decline before it | Same card, 4:34 pm PDT, retried and approved one minute later |
| Payout | **$2,400.00** to the bank, Mon Jun 15, 2026 |
| The memo on the payment | **`fence - balance`**, typed as shown, lower case, no tidying |
| Outstanding now | **$0.00** |
| What it was really worth | **$4,800.00.** Half moved by check before anyone opened the app |

**Two provenance lines matter and should read as prose in the sub line, not as labels.** The phone
number is *From the card receipt, Jun 12, 2026*. The address is *Typed with the payment, Jun 12,
2026*. The project row's sub line is *From the payment memo, Jun 12, 2026. One job, no scope.*

---

## Hard rules

- **No reference codes.** No customer number, no payment number, no invoice number.
- **No scope, no line items, no estimate anywhere.** The charge was amount-only. The four word memo is
  the only description of the work that has ever existed, which is the point of the screen.
- **No cost and no profit figures.** Not greyed, not labelled unavailable. Absent.
- **No explanatory copy inside the screen.** If a message seems necessary, list it outside the frame
  as a suggestion.
- **Colour only where somebody has to act, at most one coloured region.** Nothing on this screen is
  amber. The ten month old decline is resolved and must not read as a live problem.
- **A group that is not needed disappears from where it was.** It does not render as an empty card.
- **Verb first on buttons and CTAs**, sentence case, per the UX writing guide.

---

## Four things nobody has decided. Do not resolve them quietly

1. **The phone number is rail metadata, not a contact.** It is surfaced in the contacts column with
   its provenance, which is a claim the model does not support. If you find a better treatment, say
   so rather than changing it silently.
2. **The nav does not shrink at this tier.** The shell ships one fixed list of seven sections and
   varies only the customer list's columns by tier. Wes has something in two of the seven. Reproduce
   the nav as it is; do not invent a smaller one.
3. **The project row's status is Paid**, which is a money fact standing in for a work fact. Nothing in
   the record knows whether the fence was ever finished.
4. **Take a payment may mint a second project.** The S5 flow map has the gate as a second spine on
   the same anchors, so the action quietly creates a record and nothing on the screen says so.

Also worth knowing, and not a question for this screen: in the S15 record the Overview **group** and
the Overview **card** share a name, which reads as a repetition once the group is down to one card.
If that is being fixed, fix it in both places.
