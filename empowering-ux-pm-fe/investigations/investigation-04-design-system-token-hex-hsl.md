# `@loanpal/design-tokens` ships two disagreeing colour palettes, and web and Flutter each read a different one

**From:** Andrew Thompson (UX / Product Design, Merlin / Pros)
**For:** maintainers of `goodleap/design-system` (`packages/design-tokens`)
**Package version examined:** `@loanpal/design-tokens@0.5.5`, token files generated `2026-05-27T18:47:08Z`
**Severity:** high. Causes guaranteed, silent colour divergence between platforms.

**Two related investigations**, both downstream of this one, neither blocking:

| # | Doc | Team |
|---|---|---|
| 1 | Commit resolved token values into the Merlin repo | Merlin / Pros Web |
| 3 | Adopt Sol's Flutter output in the Pros App | Pros App / Flutter |

I found this while trying to make Sol's values readable to design tooling. Investigation 03 asks
the mobile team to adopt the Flutter build, and I do not want to send them into this.

---

## Summary

`build/sol/tokens.json` states a `hex` and an `hsl` value for the same token, side by side,
as if they were the same colour. **In 309 of 403 paired entries they are not the same
colour.** 95 differ by more than 8 in a single channel, which is visible. The worst case
differs by 40.

The two published builds then read different columns:

| Consumer | Reads | Renders `actions.button` as |
|---|---|---|
| Web, via `./sol/tailwind/v4` → `build/sol/tailwind/theme.css:26` | `hsl(246 68% 19%)` | **`#161051`** |
| Flutter, via `build/sol/flutter/primitives.dart:36` | `Color(0xFF200F51)` | **`#200F51`** |
| `build/sol/tokens.json` | `"hex": "#200f51"` | `#200F51` |

So a team can use the correct semantic token name on both platforms, do everything right,
and still ship two different colours.

---

## Why this is urgent for us specifically

The Pros App is currently hand-writing its Material 3 theme:

```dart
static const _primary = Color(0xFF42289A);   // app/lib/shared/theme/app_theme.dart
```

I have been encouraging that team to replace it with `SolMaterialTheme().light()` from your
Flutter build, which is exactly what it is for and is a genuinely good piece of work. But if
they adopt it, mobile will render `#200F51` while Pros Web renders `#161051`, from the same
token, in the same package version. Adopting Sol would *introduce* a cross-platform
inconsistency rather than remove one.

We already have measurable colour drift between our two surfaces. I had assumed it was
caused by our own hand-maintained values. Some of it is upstream of us.

---

## Reproduction

Self-contained, no repo access needed. From any project with the package installed:

```python
import json, colorsys
d = json.load(open('node_modules/@loanpal/design-tokens/build/sol/tokens.json'))

rows = []
def walk(o, p=''):
    if isinstance(o, dict):
        if isinstance(o.get('hex'), str) and isinstance(o.get('hsl'), str):
            rows.append((p, o['hex'], o['hsl']))
        for k, v in o.items():
            walk(v, f'{p}.{k}' if p else k)
walk(d)

def hsl2hex(s):
    h, sa, l = s.split()
    r, g, b = colorsys.hls_to_rgb(float(h)/360,
                                  float(l.rstrip('%'))/100,
                                  float(sa.rstrip('%'))/100)
    return '#%02x%02x%02x' % (round(r*255), round(g*255), round(b*255))

bad = [(p, hx, hsl, hsl2hex(hsl)) for p, hx, hsl in rows
       if hsl2hex(hsl).lower() != hx.lower()]

print(f'{len(rows)} paired entries, {len(bad)} inconsistent')
```

Output against 0.5.5: `403 paired entries, 309 inconsistent`

---

## Evidence

### Worst offenders

| Token | `hex` | `hsl` | `hsl` resolves to | Max channel delta |
|---|---|---|---|---|
| `color.blue.700` | `#0e3276` | `219 61% 19%` | `#13284e` | 40 |
| `color.blue.800` | `#122d5f` | `219 65% 15%` | `#0d1f3f` | 32 |
| `color.purple.200` | `#dbdbfc` | `240 91% 87%` | `#c0c0fc` | 27 |
| `color.blue.900` | `#13284e` | `219 70% 12%` | `#091834` | 26 |
| `color.purple.500` | `#654cd1` | `246 58% 61%` | `#6d62d5` | 22 |
| `color.blue.200` | `#cce2fc` | `219 90% 85%` | `#b6cefb` | 22 |
| `color.teal.500` | `#13a2ae` | `180 79% 39%` | `#15b2b2` | 16 |
| `color.purple.700` | `#200f51` | `246 68% 19%` | `#161051` | 10 |

### It originates in the primitives and cascades

| Group | Inconsistent / total |
|---|---|
| `color.*` (primitives) | 90 / 101 |
| `sol-light.*` | 83 / 106 |
| `sol-dark.*` | 87 / 106 |
| `m3-light.*` | 20 / 45 |
| `m3-dark.*` | 29 / 45 |

Semantic tokens alias the primitives, so `color.blue.700` alone propagates to
`sol-light.chart.blue-medium` and others. Fixing the primitive layer should fix most of the
rest.

### Diagnosis: this looks like two palettes, not a conversion bug

The obvious hypothesis is a broken hex-to-HSL conversion. The purple ramp argues against it:

| Token | True HSL computed from `hex` | Stated `hsl` |
|---|---|---|
| `color.purple.200` | `240.0  84.6%  92.4%` | `240 91% 87%` |
| `color.purple.500` | `251.3  59.1%  55.9%` | `246 58% 61%` |
| `color.purple.600` | `253.9  58.5%  40.6%` | `246 58% 41%` |
| `color.purple.700` | `255.5  68.7%  18.8%` | `246 68% 19%` |

The stated hue is **pinned at 246 across the whole family**. The true hue derived from the
hex values **drifts from 240 to 255.5 as the ramp darkens**. Blue shows the same pattern
pinned at 219, teal at 180.

That reads like two independently produced ramps: one algorithmic with constant hue, one
hand-tuned or perceptually adjusted with hue drift. Lightness and saturation are close but
not equal either, so neither column appears derived from the other.

If that is right, the real question is not "fix the maths" but **which ramp is current**,
and the answer determines whether web or Flutter is currently wrong.

### Why nobody caught it

94 of 403 entries are consistent, including `color.gray.900` (`#14141a` both ways). Spot
check a few greys and everything looks correct.

---

## What I am asking for

1. **Decide which column is canonical.** External signals point to `hex`: it matches what
   our Figma-derived design tooling reports, and `#200F51` appears in Merlin application
   code in a comment citing a Figma node. But you would know.
2. **Regenerate so both columns derive from that single source**, and republish.
3. **Add a consistency assertion to the build.** The reproduction above is five lines and
   would have failed this release. This is the fix that matters most, because it prevents
   recurrence rather than correcting one version.
4. **Tell us the blast radius.** If `hex` is canonical, every web surface consuming
   `./sol/tailwind/*` has been rendering the wrong palette, and we would want to coordinate
   the visual change rather than have it land silently in a patch bump.

---

## Questions

1. Is this already fixed in a version after 0.5.5? I could not check the registry from
   where I was working, so this may be stale. If so, please point me at the version and
   ignore the rest.
2. Are the `hsl` and `hex` fields generated by the same pipeline step, or maintained
   separately? The hue pattern suggests separately.
3. Is the constant-hue ramp intentional design intent that the hex values have drifted away
   from, or the reverse?
4. Does the same split affect non-colour tokens? I only checked colour, because that is
   where both formats appear.

---

## What we are doing meanwhile

Nothing that assumes an answer. On the web side we are vendoring a resolved snapshot of the
values the app actually renders, which today means the `hsl`-derived ones, so that design
tooling stops guessing. On mobile we have paused the recommendation to adopt
`SolMaterialTheme()` until this is resolved, since adopting it now would create divergence
rather than remove it.

Happy to re-run any of the above against a newer version, or to hand over the full
309-entry diff.

---

## Appendix: consumption paths, for verification

```
Web
  merlin/frontend/src/index.css:13
    @import '@loanpal/design-tokens/sol/tailwind/v4';
  package.json exports: "./sol/tailwind/v4" -> "./build/sol/tailwind/theme.css"
  build/sol/tailwind/theme.css:26
    --sol-actions-button: hsl(246 68% 19%);        -> #161051

Flutter
  build/sol/flutter/primitives.dart:36
    static const purple700 = Color(0xFF200F51);    -> #200F51
  build/sol/flutter/primitives.dart:49
    static const brand700  = Color(0xFF200F51);

JSON
  build/sol/tokens.json
    color.purple.700         = {"hex": "#200f51", "hsl": "246 68% 19%"}
    sol-light.actions.button = {"hex": "#200f51", "hsl": "246 68% 19%"}
```
