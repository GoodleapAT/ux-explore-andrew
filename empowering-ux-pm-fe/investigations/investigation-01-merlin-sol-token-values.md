# Sol's token values are not readable from the Merlin repo

**From:** Andrew Thompson (UX / Product Design)
**For:** Merlin / Pros Web frontend team
**Status:** Needs frontend expertise to confirm the approach
**Package version examined:** `@loanpal/design-tokens@0.5.5`, token files generated `2026-05-27`

**One of four investigations.** Each stands alone; none blocks another.

| # | Doc | Team | Size |
|---|---|---|---|
| 1 | **This doc.** Make Sol's token values readable from the repo | Merlin / Pros Web | Half a day, guessing |
| 2 | Fix contradictory AI styling guidance files | Merlin / Pros Web | ~2 hours |
| 3 | Mobile catalog trust, and adopt Sol's Flutter output | Pros App / Flutter | ~1-2 days, guessing |
| 4 | Colour palette defect in the design tokens package | `goodleap/design-system` | upstream |

Investigation 04 is a defect report against the design tokens package itself, and is the upstream cause of some of what is described here.

---

## TL;DR

Sol already publishes its values in machine-readable form. The problem is purely that
reading them requires an npm credential, so nothing outside an authenticated install can
resolve a `sol-*` class to a value.

**Ask:** commit a resolved snapshot of the token values into the repo, refreshed
automatically so it cannot go stale.

**Not asking:** to change any token value, add tokens, build a generator, or change how
components consume tokens. Components keep using `bg-sol-*` classes exactly as they do now.

---

## The values are already published in machine-readable form

Worth establishing up front, because it makes this a much smaller ask than it might sound.
`@loanpal/design-tokens@0.5.5` already exposes all of the following as public package
exports:

```
./sol/tokens.json                    (47KB, structured)
./tokens/sol/semantic-light.json
./tokens/sol/semantic-dark.json
./tokens/sol/colors.json
./tokens/shared/primitives.json
```

`tokens.json` is organised by category: `color`, `typography`, `spacing`, `radius`,
`border`, `shadow`, `breakpoint`, `font`, `animation`, `zIndex`, `outline`, `icon`,
`container`, `blur`.

So the machine-readable source exists and is already exported. This is only about
making it reachable without a credential.

---

## The problem

`frontend/src/index.css:13` is the only place Sol enters the app:

```css
@import '@loanpal/design-tokens/sol/tailwind/v4';
```

The package is pinned at `^0.5.5` (`frontend/package.json:57`) and is a private registry
package requiring `NODE_AUTH_TOKEN` (`frontend/README.md:16`). Nothing resolved is
committed anywhere in the repo. Around 65 distinct `sol-*` tokens are referenced across
`frontend/src`, and none can be resolved from the repo alone.

### Consequence 1: the registry's token dependency ships no values

`frontend/README.md` promises downstream consumers:

> The consumer needs Tailwind CSS installed for the components to render correctly; Sol
> design tokens are bundled via the `sol-tokens` registry item.

Every published UI item declares `sol-tokens` as a `registryDependency`, so any consumer
running `shadcn add @merlin/button` pulls it in. But
`frontend/registry/sol-tokens/sol-tokens.css` contains no values. It is a 10-line
re-export that documents its own limitation:

```css
/* This file is a placeholder to satisfy the registry file requirement.
 * The actual tokens are provided by the @loanpal/design-tokens package. */
@import '@loanpal/design-tokens/sol/tailwind/v4';
```

A downstream team installs a Merlin component, receives a CSS file importing a private
package they may not have credentials for, and the component renders unstyled.

### Consequence 2: tools cannot match our styling, and fail silently

This is what surfaced it for me. When any tool outside an authenticated install reads
`className="bg-sol-actions-button"`, it has nothing to resolve that name against. It does
not error. It substitutes something plausible.

Here is the actual gap, using the real values (converted from the HSL triplets the package
ships in `build/sol/css/index.css`, light mode):

| | Primary button background |
|---|---|
| **Real Sol value** (`sol-actions-button`) | `#161051` |
| A design-system doc we had been using | `#432c9e` |
| The Flutter app's primary | `#42289A` |

Sol's primary action is a near-black indigo. Both approximations are mid purples. Nothing
guessing would land near the real value.

More real values, for reference:

| Token | Value |
|---|---|
| `sol-actions-button-hover` | `#050529` |
| `sol-actions-link` | `#382CA5` |
| `sol-text-primary` | `#14141A` |
| `sol-text-secondary` | `#4B4B58` |
| `sol-backgrounds-ui-medium` | `#F5F5F9` |
| `sol-borders-ui-subtle` | `#E3E3ED` |
| `sol-text-destructive` | `#8F0007` |
| `sol-states-focus` | `#144EB8` |

Practical effect: design explorations and prototypes never quite match production, and the
mismatch is subtle enough to survive review, because a plausible purple does not look
wrong.

### Consequence 3: the credential gate already causes developer friction

`.claude/skills/pendo/SKILL.md:141-152`:

> The `@loanpal/design-tokens` package is a private registry package that requires
> `NODE_AUTH_TOKEN` to install. If it is not installed locally,
> `prettier-plugin-tailwindcss` will sort Sol design token classes differently from CI.
> **Symptom:** `pnpm run format` passes locally but CI Prettier check fails on files that
> contain Sol token classes.

### Consequence 4: we cannot audit our own Sol gaps

`frontend/src/index.css:186-361` carries app-local `@theme` overrides annotated as Sol
gaps in our own words:

```css
/* Not yet in Sol tokens */
/* No 1:1 Sol equivalent — kept intentionally */
/* Small-device font sizes — temporary pending Sol responsive tokens */
```

There is an entire parallel `-mobile` type scale maintained by hand for this reason. With
resolved values committed, that becomes an auditable list to take upstream.

---

## Proposed solution

A build step that reads the installed package and emits a committed artifact. Given the
JSON already exists, this may be closer to a copy than a transform.

1. **Commit the resolved token values** in a machine-readable form, stamped with the
   source package version. `./sol/tokens.json` may be usable close to as-is.
2. **Replace the `registry/sol-tokens/sol-tokens.css` placeholder** with literal custom
   property values, so downstream MFEs work without the private package.
3. **Add a CI check** that regenerates and fails if the committed output has drifted from
   the installed package, in the same spirit as a lockfile check.

I would treat item 3 as non-optional. A snapshot without a drift check becomes another
out-of-date file, and investigation 02 is evidence this repo already has several.

### Acceptance criteria

- [ ] A committed file at a stable path contains resolved literal values for all `sol-*`
      tokens referenced in `frontend/src`, ideally everything Sol exports.
- [ ] Coverage includes colour, typography, spacing, radius, border, and shadow.
- [ ] Both light and dark values are preserved. The package ships both, and collapsing to
      light only would lose information.
- [ ] The app-local `@theme` additions at `index.css:186-361` are included and clearly
      marked as app-local rather than Sol.
- [ ] Output records the source package version.
- [ ] Generation is scripted and runs in CI; CI fails if the committed file has drifted.
- [ ] The file is committed, not gitignored. Note `public/r/` is gitignored
      (`frontend/.gitignore:64`), so please not there.
- [ ] `frontend/registry/sol-tokens/sol-tokens.css` ships literal values.

### Explicitly out of scope

- Changing any token value.
- Adding tokens or closing the Sol gaps noted in `index.css`. Mine to drive upstream.
- Changing how components consume tokens.
- Any change to the Flutter repo. That is investigation 03, and it is independent of this one.

---

## Open questions

1. Is there a licensing or security reason not to commit resolved values here? They are
   already in the shipped CSS bundle, so I assume not, but you would know.
2. Is a committed snapshot the right shape, or would you rather the registry item simply
   inline the values and leave the repo referencing the package as it does now?
3. Rough effort? My guess is half a day given the JSON already exists.

---

## Useful thing I found while digging

The package's own `package.json` gives its source repo:

```json
"repository": {
  "type": "git",
  "url": "https://github.com/goodleap/design-system.git",
  "directory": "packages/design-tokens"
}
```

So Sol lives in `goodleap/design-system`. If anyone knows who owns that repo, I would like
an introduction. Several things on my roadmap need a conversation with whoever maintains
it, and I have not been able to find an owner from documentation.
