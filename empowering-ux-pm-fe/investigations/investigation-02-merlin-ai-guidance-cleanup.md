# The styling guidance files in the Merlin repo contradict each other and the code

**From:** Andrew Thompson (UX / Product Design)
**For:** Merlin / Pros Web frontend team
**Status:** Needs frontend expertise to confirm the approach. Small and self-contained.

**One of four investigations.** Each stands alone; none blocks another.

| # | Doc | Team | Size |
|---|---|---|---|
| 1 | Make Sol's token values readable from the repo | Merlin / Pros Web | Half a day |
| 2 | **This doc.** Fix contradictory AI styling guidance files | Merlin / Pros Web | ~2 hours |
| 3 | Mobile catalog trust, and adopt Sol's Flutter output | Pros App / Flutter | ~1-2 days, guessing |
| 4 | Colour palette defect in the design tokens package | `goodleap/design-system` | upstream |

This is the smallest of the four and could be resolved this week.

Worth noting the relationship between this doc and investigation 01, because they look similar
and are not. Investigation 01 is an *access* problem: tools outside an authenticated install
cannot resolve `sol-*` names to values. This doc is a *correctness* problem: the written
guidance is wrong, which affects tools that have full repo access too. Fixing one does not
fix the other.

---

## TL;DR

Five files in the repo instruct AI coding tools on how to style UI. They contradict each
other and, in three places, document component APIs that do not exist in the code. Every AI
tool used against this repo reads these files first, so they are actively teaching the
wrong thing.

**Ask:** correct or delete the stale ones, and pick one file as the source of truth for
component variant names.

---

## The core problem: three different sets of Typography variant names, none correct

`Typography` is the component every piece of text in the app is supposed to go through. Its
real variants are defined at
`frontend/src/shared/components/ui/typography/typography-types.ts:16-35`:

```ts
export type TypographyVariant =
  | 'd1' | 'd2' | 'd3'
  | 'h1' | 'h2' | 'h3' | 'h4' | 'h5' | 'h6'
  | 'l1' | 'l2' | 'l3' | 'l4'
  | 'p1' | 'p2' | 'p3' | 'p4';
```

Three files document something else.

**1. `frontend/CLAUDE.md:46`**

> Variants: `t1` (title), `b1`, `b2` (body), `label`, `caption`.

Its worked examples use them, at lines 26, 30, 42, and 43:

```tsx
<Typography variant="t1" tKey="some.title.key" />
<Typography variant="b2" className="text-sol-text-secondary" tKey="some.body.key" />
```

**2. `frontend/src/shared/components/ui/CLAUDE.md:41`**

> Variants: `t1` (title), `b1`, `b2` (body), `label`, `caption`

Same wrong set, same wrong examples at lines 37 and 38.

**3. `.cursor/rules/typography-and-class-management.mdc`** documents a third set:

> - **Display**: `d1` (largest headings)
> - **Titles**: `t1`, `t2`, `t3`, `t4` (section headings)
> - **Subtitles**: `s1`, `s2` (emphasized text)
> - **Body**: `b1`, `b2` (paragraph text)
> - **Caption**: `c1` (small text, labels)

Across those three files, only `d1` exists. `t1`, `t2`, `t3`, `t4`, `s1`, `s2`, `b1`, `b2`,
`c1`, `label`, and `caption` do not. Every documented example would fail type-check.

That third file also has `alwaysApply: true` in its frontmatter, so unlike the others it is
injected into every session regardless of what's being worked on.

These all look like accurate descriptions of the pre-Sol type scale that didn't get updated
when the code moved. Understandable that it happened; worth fixing now that AI tools read
them as authoritative.

---

## Three more stale rules

**`.cursor/rules/design-system-colors-only.mdc`** documents a pre-Sol color palette in
full:

> ONLY use colors from the design system defined in frontend/src/index.css. The available
> colors include: primary-dark, secondary-dark, link, primary-white, secondary-white,
> success, info, progress, error, action-primary, action-secondary, action-error,
> interaction-* variants, surface-* variants, and accent-* variants.

Of those, only `primary-dark`, `accent-very-strong`, and `interaction-secondary-*` still
exist in `index.css`. The rule never mentions Sol. A tool following it will correctly avoid
raw Tailwind colors and then reach for names that don't resolve, which is worse than having
no rule, because the failure looks deliberate.

**`.cursor/rules/ui-component-barrel-imports.mdc`** mandates the opposite of the enforced
rule:

> import them all with one import statement using the barrel export:
> `import { Button, Icon } from '@/shared/components';`

`frontend/CLAUDE.md` forbids barrel imports, `eslint.config.js:53-54` enforces the ban via
`barrel-files/avoid-barrel-files: 'error'` and `avoid-re-export-all: 'error'`, and
`frontend/src/shared/components/index.ts` does not exist. So the rule instructs tools to
write an import that cannot resolve and would be blocked by lint regardless.

**`.claude/skills/contributing/frontend-guidelines.md`** has a stale directory diagram
showing `frontend/src/components/`, `hooks/`, `utils/`, `types/`. The real layout is
`src/shared/components/`, `src/shared/hooks/`, and so on. Minor, but it sends tools looking
in the wrong place before they start.

---

## What is accurate, for contrast

I checked the other documented lists rather than assume they'd all drifted. The Button
variants in `ui/CLAUDE.md:45` are correct: `solid`, `outline`, `clear`, `link`,
`destructive`, `toolbar`, `icon` all match `button-variants.ts`. One small gap, the
documented size list omits `link`, which does exist as a size.

So this is specifically a Typography and color problem, not a general rot problem. That
should keep the fix small.

---

## Why this matters more than it used to

These files were presumably written as notes for humans, who would notice a wrong variant
name the moment the compiler complained and move on.

AI tools behave differently. They treat the guidance as authoritative, generate code using
the documented names, and produce output that is confidently wrong in a consistent way.
Because it's consistent, it reads as deliberate. On my side this shows up as prototypes and
generated components that don't match production and don't compile, plus review churn when
generated code has to be hand-corrected against rules that are written down incorrectly.

Both `frontend/CLAUDE.md` and `ui/CLAUDE.md` open by instructing tools to read them before
any UI work, so they're the highest-traffic documents in the repo for anything AI-assisted.

---

## Proposed fix

Ordered by value per unit of effort.

1. **Correct the Typography variants in `frontend/CLAUDE.md` and
   `frontend/src/shared/components/ui/CLAUDE.md`**, including the worked examples. Highest
   value line change in the repo for AI output quality.

2. **Delete or rewrite `.cursor/rules/typography-and-class-management.mdc`.** It duplicates
   `ui/CLAUDE.md` with older content, and `alwaysApply: true` means it's always in context.
   My suggestion is deletion. If it stays, it needs to match the type definition exactly.

3. **Delete or rewrite `.cursor/rules/design-system-colors-only.mdc`** to reference Sol
   token families instead of the pre-Sol palette.

4. **Delete `.cursor/rules/ui-component-barrel-imports.mdc`.** It contradicts an enforced
   lint rule and references a file that doesn't exist.

5. **Fix the directory diagram in `.claude/skills/contributing/frontend-guidelines.md`.**

6. **Add the missing `link` size to the documented Button size list.**

7. **Pick one source of truth for component variant names** and have the others link to it
   rather than restate it. `ui/CLAUDE.md` is the natural home, since `frontend/CLAUDE.md`
   already directs tools to read it in full. Restating variant lists in four places is what
   caused this.

### Optional

A test or lint rule asserting that variant names appearing in guidance files exist in the
corresponding TypeScript union. That makes this class of drift impossible rather than fixed
once. I don't know what it costs to build, so treat it as a suggestion. Worth noting these
files drifted once already, so without a check I'd expect recurrence.

### Acceptance criteria

- [ ] Every `Typography` variant name in `frontend/CLAUDE.md` and `ui/CLAUDE.md`, in prose
      and in examples, exists in `TypographyVariant`.
- [ ] No file in the repo documents a color palette that predates Sol.
- [ ] No file instructs tools to use barrel imports from `@/shared/components`.
- [ ] Component variant and size lists are stated in exactly one place.

---

## Open questions

1. Is `.cursor/rules/` still used by anyone on the team, or is it a leftover from before
   the `.claude/` setup? If nobody uses Cursor, deleting the directory may be simplest. I'd
   rather not assume.
2. Are there other guidance files I've missed? I found these by searching for styling and
   typography references, so this may not be exhaustive.
