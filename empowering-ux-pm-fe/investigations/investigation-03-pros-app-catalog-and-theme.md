# The Pros App component catalog has nothing keeping it current, and Sol already ships a Flutter build

**From:** Andrew Thompson (UX / Product Design)
**For:** Pros App / Flutter team
**Status:** Needs Flutter expertise to confirm feasibility

**One of four investigations.** Each stands alone; none blocks another.

| # | Doc | Team | Size |
|---|---|---|---|
| 1 | Make Sol's token values readable from the Merlin repo | Merlin / Pros Web | Half a day |
| 2 | Fix contradictory AI styling guidance files | Merlin / Pros Web | ~2 hours |
| 3 | **This doc.** Catalog trust, and Sol's Flutter output | Pros App / Flutter | ~1-2 days, guessing |
| 4 | Colour palette defect in the design tokens package | `goodleap/design-system` | upstream |

Note that investigation 04 reports a defect in the design tokens package which affects Part C below.

---

## Context

I am working on cross-platform convergence between Pros Web and the Pros App. Near term I
want a catalog where a designer or engineer can see a web component and its mobile
counterpart side by side, with a note on whether the difference is deliberate or
accidental.

Widgetbook is the obvious foundation for the mobile half and it is in better shape than I
expected. Before building on it I want to be confident it reflects reality.

Nothing below is a criticism of how it was set up. The issues are all "nothing keeps this
current," which is normal to only notice once someone starts depending on it.

---

## Part A: Widgetbook has no mechanism keeping it current

### A1. It is not part of any engineering guidance

`CLAUDE.md` mentions Widgetbook exactly once, and only as an aside about codegen:

> `# If :all fails due to an unrelated package (e.g. widgetbook), use the scoped variant:`

`.claude/PROJECT_GUIDELINES.md` does not mention it at all, including in the section that
catalogues shared widgets and opens with "Before building any new UI element, search
`app/lib/shared/widgets/`... Creating a custom widget that duplicates shared functionality
is a PR rejection point."

The only place the expectation is written down is `docs/widgetbook-github-pages.md:317`:

> **Keeping current:** Add Widgetbook use cases when creating new shared widgets.
> Periodically review `app/lib/shared/widgets/` for uncataloged widgets.

A line in a deployment doc will not hold. For comparison, the web repo puts this in its
contributing guidance with a stated reason: "always update the demo page... Design review
has a single source of truth."

**Ask:** move the expectation into `CLAUDE.md` and `PROJECT_GUIDELINES.md` alongside the
other UI conventions, so it is visible to engineers and AI tools at the point of work.

### A2. Two use cases appear to exist but were never registered

`widgetbook/lib/directories.dart` is a hand-maintained list of everything in the catalog.
Two use case files do not appear to be referenced in it:

- `use_cases/feedback/pipeline_error_widget.dart`
- `use_cases/feature_widgets/timeline_section_widget.dart`

Flagging as worth confirming rather than asserting, since my detection was a filename match
against the directory list. If correct, these are components that exist, have use cases
written, and do not appear in the catalog.

### A3. The generator is installed but unused

`widgetbook/pubspec.yaml` declares `widgetbook_annotation: ^3.11.0` and
`widgetbook_generator: ^3.22.0`. Use case files carry the annotations:

```dart
@widgetbook.UseCase(name: 'Default', type: PrimaryButton)
Widget buildPrimaryButtonDefaultUseCase(BuildContext context) {
```

But there is no generated output. `find widgetbook -name "*.g.dart"` returns nothing, and
there is no `build.yaml` in the package. So the annotations do nothing, and the same
registration is written by hand in `directories.dart`, which is 720 lines.

Every component is registered twice, once decoratively and once for real, and the real one
is manual. That is a reasonable explanation for A2.

**Ask:** either turn the generator on, or remove the annotations and dev dependency so it
is clear the manual list is authoritative. Either is fine. The halfway state is the
problem, because it looks automated to anyone reading it, including AI tools that might
assume adding an annotation is sufficient.

I lean toward turning it on since it makes A2 structurally impossible, but you will know
whether the generator handles your folder taxonomy. The manual list currently carries
information the annotations do not: folder grouping, and comments naming the Dart class
behind each display name (`name: 'Primary Button', // PrimaryButton`). If that would be
lost, the manual list may genuinely be better and A3 becomes "remove the unused generator."

### A4. Widgetbook is excluded from tests

`melos.yaml` excludes it from test runs in three places via `ignore: ["*widgetbook*"]`.
That may be entirely correct. Raising it only because, combined with A1 through A3, there
is currently nothing at all that would catch the catalog going out of date.

### A5. One coverage gap

The Widgetbook config has four addons: theme, viewport, a provider wrapper, and alignment.
There is no text scale addon, so a designer browsing the catalog cannot see behaviour at
large text sizes. Golden tests do cover scales 1.0 and 2.0, so the risk is covered in
testing. Low priority, cheap if you are in the file anyway.

`MaterialThemeAddon` is also configured with a single theme named `'Light'`, so dark mode
is not browsable. See Part C, which may change that.

---

## Part B: two theme issues that are probably known

### B1. A debug value appears to have shipped

`app/lib/shared/extensions/palette.dart:337`:

```dart
outlinedBorderColor: Color(0xFFd71ef7),
```

Bright magenta, the only lowercase hex in the file, and your own theme migration notes
describe it as "Appears to be a debug/placeholder value." Worth confirming whether anything
renders it.

### B2. No interaction state colours

There are no hover, pressed, or focus colour tokens on the mobile side, where web has all
three. Genuine question rather than a request: intentional for touch, or a gap? It affects
whether I record it as a deliberate divergence or accidental drift. Note that Sol's Flutter
output does ship pressed and hover tokens, so Part C may resolve this for free.

---

## Part C: Sol already generates Flutter code, and it targets exactly what you hand-wrote

`@loanpal/design-tokens@0.5.5` ships a Flutter build at `build/sol/flutter/`, exposed as
public package exports `./sol/flutter`, `./sol/flutter/light`, and `./sol/flutter/dark`:

```
material_theme.dart      SolMaterialTheme().light() / .dark() -> ThemeData
semantic_tokens.dart     108 semantic Color tokens, theme-aware via SolSemantic.x(context)
primitives.dart          raw colour scales
sol_design_system.dart   barrel export
```

Generated `2026-05-27`, header says `Source: @goodleap/design-tokens`.

### It maps almost exactly onto what `origin/master` currently does by hand

`material_theme.dart`'s own usage doc:

```dart
MaterialApp(
  theme: SolMaterialTheme().light(),
  darkTheme: SolMaterialTheme().dark(),
  themeMode: ThemeMode.system,
)
```

That is what `theme_service.dart` and `app_theme.dart` build by hand today, including the
hand-written constants:

```dart
static const _primary = Color(0xFF42289A);
static const _primaryContainer = Color(0xFFEFEBFF);
```

And `semantic_tokens.dart` covers a good portion of what `goodleap_tokens.dart` holds as
"orphaned" brand colours: system success, warning, error, info (both tinted and solid
variants), chart colours, and the teal and pink accents.

Three things worth knowing:

**Dark mode may come for free.** `app_theme.dart` currently notes "Dark mode colors are not
yet designed — visually identical to light until Step 12," and `goodLeapLight` and
`goodLeapDark` in `palette.dart` are identical. Sol ships a real dark theme, and the
semantic tokens adapt to theme brightness automatically.

**The values differ from yours, materially.** Sol's `actions-button` resolves to `#161051`,
a near-black indigo. The mobile app's `_primary` is `#42289A`. This is not a rounding
difference, and adopting Sol would visibly change the app. That is a design decision, and
it is mine to make. I am not asking you to change colours, only to tell me whether the
mechanism is viable.

**Sol does not cover everything.** I checked `semantic_tokens.dart` for your
domain-specific tokens. Not present: the solar product colours, the roofing measurement
colours, and `inProgress`. Those stay local, and they become the genuine list of what Sol
is missing, which is useful to me as an upstream ask.

### The actual blocker is distribution, not generation

The Dart files ship inside an **npm** package. Flutter cannot consume npm. So the question
is how the generated code reaches your `pubspec.yaml`.

Options I can see, and I do not know which is sane in your toolchain:

1. Vendor the generated `.dart` files into the repo with a refresh script.
2. Ask the design-system repo to publish a pub package or expose a git-based pub dependency.
3. Something else entirely.

**Nothing is being asked of you yet.** What would help is a feasibility read:

1. Is any of the above reasonable in your build setup, or does it fight the toolchain?
2. Would you rather vendor, or consume a published Dart package if one existed?
3. If the mechanism works, roughly what would adoption cost? I am mostly trying to
   understand whether this is a week or a quarter before I take the colour change to
   stakeholders.

---

## One cross-platform bug, ownership unclear

The roof measurement edge colours are defined independently in each repo and all eight
differ:

| Edge type | Web (`frontend/src/shared/cfg/edge-colors.ts`) | Mobile (`goodleap_tokens.dart`) |
|---|---|---|
| Ridge | `#E1302B` | `#CE4335` |
| Hip | `#2B6EE1` | `#7191E3` |
| Valley | `#EF8A33` | `#E08F47` |
| Rake | `#9B58FF` | `#955FF6` |
| Eave | `#1EBEDA` | `#5DBBD7` |
| Wall flashing | `#E1CE26` | `#DDCE4F` |
| Step flashing | `#D526CA` | `#C43EC3` |
| Parapet | `#27D742` | `#67D35A` |

Mobile's are consistently softer and lighter. Hip, eave, and parapet differ enough to read
as different colours to a contractor comparing the two surfaces on the same job.

I checked whether Sol arbitrates this. It does not, these colours are not in Sol at all. So
deciding which set is correct is mine, and I will come back with an answer. Two things that
would help: whether the mobile values were a deliberate choice, for example softened for
small screens, or drift. And whether the two key sets even align one to one, since web keys
these off API enum values while mobile names them as display concepts.

---

## Summary of what I am asking for

| Item | Ask | Depends on |
|---|---|---|
| A1 | Move the Widgetbook expectation into `CLAUDE.md` / `PROJECT_GUIDELINES.md` | Nothing |
| A2 | Confirm and register the two apparently missing use cases | Nothing |
| A3 | Resolve the generator situation, turn it on or remove it | Nothing |
| A4 | Confirm the test exclusion is intentional | Nothing |
| A5 | Optional: add a text scale addon | Nothing |
| B1 | Confirm whether the magenta placeholder renders anywhere | Nothing |
| B2 | Answer whether missing interaction states are intentional | Nothing |
| C | Feasibility read on consuming Sol's Flutter output. No work yet | Nothing |
| Edge colours | Context on whether mobile's values were deliberate | Nothing |

A1 through A3 matter most to me, because they are what make the catalog something I can
build on. C is the one with the largest long-term payoff.

---

## Notes on my sources

Everything about Widgetbook and the theme files was read from the repo. My local checkout
is behind `origin/master`, so anything concerning `app/lib/shared/theme/` I read from
`origin/master` directly, since those files do not exist locally yet. If any of it is
already fixed on a branch I have not seen, tell me and I will drop it.

Everything about Sol's Flutter output was read from the installed
`@loanpal/design-tokens@0.5.5` package in the Merlin repo. Its `package.json` gives the
source as `github.com/goodleap/design-system`, directory `packages/design-tokens`. If
anyone on your side knows who owns that repo, I would like an introduction.
