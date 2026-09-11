# Pros Web / Pros App design convergence

**Findings, decisions, and next steps** · Andrew Thompson, UX / Product Design · August 2026

**Method note:** everything below was read directly from the `merlin` and `gl-pros-flutter`
repos. Confluence material was reviewed but is treated as a source of questions rather than
answers; several relevant pages are 4 to 10 months old and contradict the code.

---

## Findings

**1. Merlin's design token values are not readable from its own repo.** The code refers to
Sol tokens by name only (`bg-sol-backgrounds-ui-high`); the values live in a private npm
package requiring a credential. Any tool without that package installed cannot determine
what color or type size Merlin uses, and does not error. It guesses. This is the root cause
of AI-generated designs never quite matching production.

**2. The two platforms have drifted, with no way to detect it.** Exactly three color values
match across the repos. Most visibly, the roof measurement edge colors are defined
independently in each and **all eight differ**; three differ enough to read as different
colors to a contractor comparing the same job on both surfaces. This is a shipped
inconsistency, not a design system question.

**3. No component-level web-to-app mapping exists anywhere.** Nothing maps a web component
to its mobile counterpart. Feature-level material exists in Confluence, but it was authored
as a Flutter implementation spec, treats web as the spec and mobile as the implementation,
and is not designer-owned.

**4. A 1:1 mapping would be wrong.** Of 54 web primitives, roughly 10 have no mobile
counterpart (data tables, sidebar, rich text editor, tooltips, breadcrumbs, charts) and
roughly 8 are structurally incompatible rather than differently named. Web's Button has two
variant axes; mobile's has one fixed state list. Web's Select opens in place; mobile's spans
four widgets and navigates to a new screen. Some of this is correct platform behavior, some
is accidental drift, and nothing currently distinguishes the two.

**5. Two component catalogs already exist and neither knows about the other.** Web has a
demo page at `/dev/sink` (~65 components, reachable without auth, backed by a metadata
file). Mobile has Widgetbook (~63 components, deployed to a URL). The web one is required by
contributing guidance. The mobile one is required by nothing, and is already drifting.

**6. Merlin publishes a shadcn component registry, and it hands us a join key.** 53
components published, consumable by other apps and by AI assistants. Registry item names
are stable, already namespaced, and already how engineers refer to these components. Two
gaps: nine primitives aren't published yet, and the registry's Sol token dependency ships no
values, so downstream teams installing a Merlin component get something unstyled.

**7. Merlin's AI guidance files teach the wrong API.** Five files instruct AI tools on
styling. Three document Typography variant names that do not exist in the code, in three
different wrong versions. One documents a pre-Sol color palette. One mandates an import
pattern the linter blocks. Every AI tool reads these first.

**8. Origin migration hasn't started in any visible way.** No Origin components or patterns
appear in Merlin yet. The only relevant Confluence doc runs the opposite direction, is from
October 2025, and lists its owner as TBD. Treat as unverified.

---

## Decisions

| Decision | Reasoning |
|---|---|
| **Converge tokens first, then interaction semantics, then components** | Tokens are the only layer where cross-platform 1:1 is achievable. Component APIs are too structurally different to merge cheaply. |
| **The mapping records typed relationships, not equivalences** | Categories: same, different shape, deliberately different, missing on one side. The "deliberately different" flag is what makes convergence finite instead of infinite. |
| **Join key is the registry item name (web) plus the Widgetbook path (mobile)** | Two existing identifier systems. No new vocabulary to maintain. |
| **Build the visual catalog first; the mapping file falls out of it** | The catalog is the instrument for making the judgment calls, not a display of judgments already made. Structuring the data first would mean designing the schema before knowing what it holds. |
| **Catalog lives as a route in the Merlin repo, deployed at `/dev/parity`** | Renders real components, so it cannot drift from production. Deployed means it is available to every designer and engineer, not one laptop. Sits beside the existing `/dev/sink` page and inherits its maintenance expectation. |
| **Pilot on lead detail; proposal second** | Both platforms have substantial lead detail implementations, so judgments can be checked against reality. Mobile's proposal area is five files, so there is nothing to compare yet. |
| **Confluence is a source of questions, not answers** | Multiple pages contradict the code. Anything load-bearing gets verified against the repos. |
| **Retire the old Merlin design system skill** | Pre-dates Sol. Documents the wrong typeface, wrong type scale, and a brand color matching neither platform. |

Worth noting that lead detail and proposal exercise the catalog differently. Lead detail is
**reconciliation**: two real implementations exist and the work is deciding which differences
are deliberate. Proposal is **specification**: mobile barely exists, so web defines what it
should become. Both matter; reconciliation goes first because the work is checkable.

---

## Investigations in flight

Four documents written, each carrying evidence and an ask, for delegation by the frontend leads.

| # | Investigation | Team | Size | Blocks |
|---|---|---|---|---|
| 1 | Commit resolved Sol token values, with a CI drift check | Merlin / Pros Web | ~1 day | AI parity, Figma Code Connect, cross-platform drift checks, investigation 03 part C |
| 2 | Fix the contradictory AI styling guidance files | Merlin / Pros Web | ~2 hours | Nothing. Can ship immediately. |
| 3 | Make the mobile catalog trustworthy; adopt Sol's Flutter output | Pros App / Flutter | ~1-2 days | The mobile half of the parity catalog |
| 4 | Colour palette defect in the design tokens package: hex and HSL disagree for 309 of 403 entries, and web and Flutter read different columns | `goodleap/design-system` | upstream | Any cross-platform token convergence |

Investigation 01 is the highest-leverage item for us. Investigation 04 is the highest severity
overall, and it is the one item on the list that isn't ours to fix.

---

## Next steps

**Now, no dependencies**

1. Send the four investigations to the frontend leads.
2. Build the `/dev/parity` scaffold plus six to ten real lead detail pairs, to pressure-test
   whether the four relationship categories are the right ones.
3. Decide which set of roof edge colors is correct, and whether mobile's values were a
   deliberate softening or drift.

**Once investigation 01 lands**

4. Point AI tooling at the committed token values instead of a hand-written snapshot.
5. Stand up an automated web-to-app token drift check, so finding 2 cannot recur silently.
6. Give the Flutter team a platform-neutral token source so their theme file becomes
   generated rather than hand-maintained. This is the single highest-leverage cross-platform
   change available.

**Once the pilot format holds**

7. Extend the catalog to the proposal flow, in specification mode.
8. Take the concrete Sol gap list to whoever owns it: 41 missing tokens on the mobile side,
   plus the documented web-side gaps. Ship in order of usage. Unglamorous asks are hard to
   stall.
9. Gate Origin feature migrations on a re-specification step that names which Merlin
   components the feature needs and which don't exist yet. Sequence shortest list first, so
   early migrations extend the design system rather than fork it.

---

## Open questions and risks

**Sol has no identified owner.** No scope document, no roadmap, no named team. If the token
package belongs to another group, investigation 01 may need to be routed upstream rather than
solved locally. That answer shapes several later steps.

**Mobile catalog completeness gates the parity view.** A relationship map pointing at an
incomplete catalog will read as though mobile is missing components it actually has. Request
3 exists to address this.

**Widgetbook embedding is unproven.** It is published on a private-repo URL, so viewers need
repo access, and whether it supports linking to one specific component by URL has not been
confirmed. If it does not, the mobile half starts as screenshots with a link out.

**Any mapping needs an automated check or it becomes the next stale document.** This
codebase already contains five contradictory guidance files and several out-of-date
Confluence pages. A cross-platform mapping is a strong candidate to become the sixth. The
mitigation is a check that fails when a referenced component is renamed or removed, which is
feasible because the mapping points at real code paths. Build it early rather than promising
it later.

**Multiple competing convergence targets may exist.** Older documents name at least two
other candidates for the eventual unified design system besides Sol. Unverified, and worth
confirming with the leads directly rather than from documentation.
