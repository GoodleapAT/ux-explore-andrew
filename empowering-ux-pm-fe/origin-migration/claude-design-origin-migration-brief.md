# Claude Design brief: translating Origin payments views into Pros Web

Paste this as project instructions. This project references the **Merlin design system
project**, which is already connected and is where Merlin's components and Sol token values
come from.

**Coming next, after this context:** the `pay-mfe`, `origin-shell` and `merlin` repos, plus
`site-map-data.json`. Read this brief first so you know what to look for when they arrive.

---

## The one rule

**Origin is read-only reference. Merlin is the only build target.**

Read `pay-mfe` to understand what a screen does, what data it shows, what states it has and
what a user can do. Then build that intent using Merlin components and Sol tokens.

Never emit Lumos code. Never copy an Origin class name. If an Origin screen needs something
Merlin does not have, stop and say so rather than inventing it.

---

## What you can and cannot see in `pay-mfe`

**You cannot see Lumos 2.** Origin's design system is `@goodleap/lumos2-mfe`, imported 251
times in this repo, and it is **not in `package.json`**. single-spa resolves it at runtime
from an import map, so no source is available. You will see imports for `Button`, `Card`,
`Table`, `InfiniteTable`, `Typography`, `FilterBar`, `Modal`, `DynamicForm` and about 35
others with no implementation behind them.

Treat a Lumos import as a statement of intent, not a specification. `<Table>` tells you
there is a table. It does not tell you its behaviour, and you must not guess at it.

**You cannot copy Origin's styling.** Origin is Tailwind **3.1.8 with a `twd-` class
prefix**. Merlin is Tailwind **4.2.4 unprefixed**. So `twd-bg-neutral-l5` has no Merlin
equivalent and cannot be translated mechanically. Read Origin's classes only as hints about
intent, for example spacing density or emphasis.

**Origin also runs React 18.3.1 and `react-router-dom` 6**, against Merlin's React 19 and
TanStack Router. No routing or hook code transfers.

---

## Read these first, before any component source

`pay-mfe/project-context/` is written for AI agents and will save you a great deal of
guessing:

| File | What it gives you |
|---|---|
| `capabilities.json` | 17 named capabilities with summaries and keywords. The product's own feature taxonomy |
| `historical-prd-summary.md` | Four development phases, seven business domains, and a terminology table mapping canonical terms to their aliases |
| `repository-inventory.md` | What lives where |
| `intent-catalog.json` | Concepts and intents |

`pay-mfe/packages/web/cypress/integration/*.feature` — **15 Cypress BDD files in
Given/When/Then prose.** These are the behavioural specification: states, transitions, empty
cases, and which role performs each action. They are executable, so unlike documentation they
cannot have drifted. Read the relevant `.feature` file before designing any screen.

---

## Six traps in this codebase

**1. Roughly a quarter of the payments surface is embedded Stripe, not GoodLeap UI.**
Disputed transactions is `ConnectPaymentDisputes`. Capital is `CapitalFinancing`. Payments
onboarding is embedded KYB, payout account and terms. Business details wraps
`AccountManagement`. **Do not redesign these.** Only the surrounding GoodLeap chrome is
design work. Say clearly when a screen is mostly a Stripe embed.

**2. "Payments" and "transactions" are the same thing, named four ways.** The tab labelled
*Transactions* renders `pages/payments/payments-list.tsx`, whose default export is
`GoodLeapPaymentDetailsComponent`, which renders `components/transactions/`. Do not infer a
product distinction from the directory names. Use *transactions* for the list and *payments*
for the umbrella.

**3. `pages/transactions/transactions-list.page.tsx` is dead code.** Never imported,
hardcodes `margin: '100px'`, contains a `// import and use TransactionsFilter here` comment.
Ignore it.

**4. The route table is not a complete inventory.** `PayoutsList.tsx` is a real page that
does not appear in `utils/routes.tsx`; it is mounted elsewhere. Do not assume that reading
the route file gives you every screen.

**5. Payment schedules is not a real feature yet.** Gated on a LaunchDarkly flag **and**
`STAGE === 'devint01'` **and** an allowlist of two test organisations, with a mock service
layer. It has UI and tests but no shipped backend. Flag it if asked to work on it.

**6. Origin's pricebook is an iframe of Merlin.** `pricebook-card.component.tsx` generates a
limited-use token and iframes `app.merlin-v12.com`. So that screen is already Pros. Do not
redesign it as if it were Origin's.

---

## `origin-shell` is small and it is the IA

Three near-identical files, `src/routes/{devint01,stage,prod}.html`, 87 lines each. They are
a single-spa router config mapping URLs to micro-frontends, and between them they are
Origin's entire top-level information architecture: **24 routes across 15 MFEs.**

Only five mount `pay-mfe`:

```
/payments          /payments/create          /capital
/admin/payments    /reports/payments
```

There is no UI in this repo. Use it to know where a payments screen sits in Origin's global
navigation, and nothing else.

---

## What to build with

**Merlin has 54 primitives** at `merlin/frontend/src/shared/components/ui/`. Search there
before proposing anything new. 53 are published to a `@merlin` shadcn registry.

**Sol token values come from the connected Merlin design system project.** Look them up
there rather than inferring them. Do not read values from the `merlin` repo itself: it refers
to tokens only by name (`bg-sol-actions-button`) and the values live in a credential-gated
package, so a name in that repo cannot be resolved to a colour.

**Typography variants are `d1`–`d3`, `h1`–`h6`, `l1`–`l4`, `p1`–`p4`.** Note that
`frontend/CLAUDE.md`, `ui/CLAUDE.md` and a Cursor rule all document a *different, wrong*
set including `t1`, `b1`, `b2`, `label` and `caption`. Those do not exist and will not
compile. Trust
`frontend/src/shared/components/ui/typography/typography-types.ts` over any prose in that
repo.

**Merlin's breakpoints are custom:** `xs` 400, `sm` 650, `md` 750, `lg` 1024, `xl` 1280.
The entire typography scale changes at `sm`.

---

## Five components Merlin does not have

Origin's payments surface is table-heavy and leans on Lumos components with no Merlin
equivalent:

`InfiniteTable` · `TableInsight` (with its own context provider) · `DynamicForm` ·
`FilterBar` · `PopConfirm` · `ConfirmationInput`

Merlin has `table` and `data-table`, but not infinite scroll, not an insight panel pattern,
and not a filter bar primitive.

**When a screen needs one of these, stop and flag it.** Name the Origin component, describe
what it does, and say what Merlin would need. That is a design system decision with real
cost, and I need to know before you design around it.

---

## One structural difference that will bite

**Origin organises by financial object. Pros organises by lead.**

Origin has a global `/payments` container with invoices, transactions, subscriptions and
schedules as sibling tabs. Pros puts invoices under `/leads/$leadId/invoices`, and **neither
Pros surface has a global invoice list at all.**

So do not assume Origin's URL structure carries across. When translating a screen, say
explicitly where you think it belongs in Pros: extending the existing lead tabs, or in a new
org-level financial area. Some Origin screens are genuinely per-lead and some are genuinely
not, and payouts, disputes, transaction history and exports fall into the second group.

`site-map-data.json` has the full node inventory for all three platforms, with content,
actions, states, gating and outbound links already extracted. Use it rather than
re-deriving.

---

## How to hand work back

For each screen, give me:

1. **What the Origin screen does** — content, actions, states, and which role performs them,
   sourced from the `.feature` file where one exists
2. **The Merlin build** — real component names, variants and sizes, with Sol token names
3. **Anything Merlin lacks** — named, with what it does and what would be needed
4. **Where it belongs in Pros** — per-lead or org-level, and why
5. **Anything you could not determine** — say so rather than filling the gap

That last one matters more than the rest. A confident guess costs more to unpick than an
acknowledged gap.
