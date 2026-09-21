# Words and numbers on a screen

**How copy inside a mockup is written and how values are formatted. 21 September 2026.**

> **Where this comes from.** GoodLeap's own UX Writing and Content Style Guide, in the Payments space
> on Confluence, last updated April 2026. **This file is not a second opinion**, it is the subset of
> that guide that our mocks keep getting wrong, plus the two places our work has to depart from it.
>
> The guide is for **product UI copy**. It is not the marketing voice guide, and it does not govern
> memo prose. **A memo may read in Andrew's register; a mockup reads in the product's.**

| Marker | Meaning |
|---|---|
| **Always** | Breaking it is a defect. Say so before you do it, not after |
| **Default** | Do it unless you have a reason. Having a reason is fine; not saying it is not |
| **Prefer** | A leaning |

---

## The two we were getting wrong everywhere

**Always: dollar values show cents, even for whole amounts.** `$2,400.00`, not `$2,400`. Commas at a
thousand and above, leading zero under a dollar, `$0.21` rather than `21c`.

This is not a preference. **Andrew's own Pros Web list recreation already formats money with a two
digit minimum**, so a real payments page renders `$2,400.00`. Memos 10 through 13, which read
`$38,900` and `$73,100`, are the ones out of step.

**Always: dates are US format and never day first.** `Jun 12, 2026` where space is tight,
`January 15, 2025` where it is not. Never `12 Jun`. Memos 10 through 13 read `6 Aug` and `Fri 7 Aug`
throughout, which is the one thing the guide names as forbidden.

Ranges use an en dash with no spaces, `January 10 to 15, 2025` written as `January 10–15, 2025`, and
repeat the year only when it changes. Times carry a zone and lowercase am or pm with no periods:
`4:35 pm PDT`.

---

## The rest, condensed

**Always: American English inside a mockup.** Color, labor, organize, canceled, catalog. **The memo
around it may be British**, which is the only place this file and `working-voice.md` appear to
disagree and do not: one governs the product, the other governs the writing about it.

**Always: no em dashes.** Already in `working-voice.md`, and the guide calls them a tell of
machine-written copy.

**Always: sentence case on buttons, links and headings.** Never all caps. No emoji, ever, in product
UI.

**Always: verb first on buttons and CTAs.** *Take a payment*, not *New payment*. *Download report*,
not *Report*. Never *Click here* and never *Submit*. **A menu item is a CTA for this purpose**, which
is where this rule bites most often, because a noun phrase reads naturally in a menu and still fails.

**Always: an error says what happened, then what to do.** *We couldn't process your payment. Check
your card details or try a different payment method.* Not *Payment failed*.

**Always: an empty state says why it is empty, then offers a next step.** *No invoices yet. Create one
to get started.* Not *Nothing to show*. **This is the rule our empty states break**, because a bare
*No crew assigned* is a dead end.

**Always: a destructive CTA names the real-world action** and its pair never shares a key term.
*Delete signed agreement* against *Keep agreement*, never *Cancel* against *Cancel*.

**Default: numbers one through nine spelled out, 10 and up as numerals.** Not in table cells, where
space wins.

**Default: second person.** *You can view your invoice*, not *The invoice can be viewed*.

**Default: no period on a single-sentence message** in a list, an inline error or a banner. Punctuate
everything if it runs to two.

**Default: spell an acronym out on first use in a screen, then shorten.** All caps, no periods.

**Prefer: cut the filler.** Really, very, just, simply, please note that.

---

## Who we are writing for, and what that changes

The rules above do not move. What moves is how much industry shorthand is safe.

| Audience | Shorthand |
|---|---|
| **Contractors and sales professionals** | Comfortable with NTP, M1, change order, milestone. Use them where they are faster, do not over-explain |
| **Back-office administrators** | Fluent in both industry and system terms. Use the precise label that matches their tools |
| **Homeowners** | Meeting financing language for the first time. Plain words, define any necessary term on first use |

**Pros Web is contractor and back-office.** So `Customers` in the nav is right, even though the guide
reserves *customer* for business-facing copy and prefers *homeowner* elsewhere: the contractor's
customers are the homeowners, and the surface is the contractor's.

## Terms that are already decided

Sign in, not log in. Autopay, one word. Payment method, not payment option. Bank account, not banking
details. Loan, not financing. Due date. Email, one word. GoodLeap, one word, two capitals.

**Never *user* in product UI.** It is an internal word.

---

## Learned from

- **21 Sep 2026.** Written after reading the guide against memo 14 and finding **two Always rules
  broken by every mock in the series**. Both are mechanical and neither changes a layout, which is
  exactly why nobody had noticed.
- **21 Sep 2026.** The cents rule was settled by evidence rather than argument: **Andrew's own
  recreation of the real Pros Web list already formats money the guide's way**, so the mocks were out
  of step with the product as well as with the guide.
- **21 Sep 2026.** The verb-first rule caught *New payment*, which Andrew had specified for an
  overflow menu. **Drawn as *Take a payment* with the alternatives listed under the mock** rather than
  silently changed, per the rule that suggested copy is judged on its own.
