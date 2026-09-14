# Deviations

**Where a mock departs from the scenario it was built against, and why.**

> **Who may write to this file:** any surface that can write. **Append a row when you build.** Edit
> the Resolution column when one is settled.
>
> **Every mock records the scenario version it was built against.** Scenario pages change, so a
> deviation is only meaningful against a date. Take it from the Confluence page's last modified
> date and put it on the mock itself as well as in this file.

## Why this exists

The scenarios are the team's, they are being revised, and some of them will be revised **because** a
mock showed the flow was wrong. So a deviation is not automatically an error. It is one of two
things, and the difference matters:

- **A proposal.** The mock is right and the scenario should change. These are the valuable ones, and
  they should reach Joel.
- **A local simplification.** The mock departs for its own reasons: fitting a grid, avoiding an
  undrawn surface, keeping one example consistent. These should not reach Joel and should not quietly
  become model claims.

When a scenario is next updated, this file says which mocks need rechecking and which deviations may
have just been resolved.

**When was drift last looked for?** The drift check register beside this file holds the date every
source was last checked, and the routine for checking. A deviation recorded against a scenario that
has since moved is a deviation against history.

## The fields

| Field | What it means |
|---|---|
| **Mock** | Which artefact, and its date |
| **Scenario** | Which scenario, and **the date of the version it was built against** |
| **What deviates** | The departure, in one sentence |
| **Why** | The reason |
| **Kind** | **Proposal** or **Simplification** |
| **Resolution** | Open, taken to the team, accepted, or withdrawn |

---

## S15 cash grid, 11 Sep 2026, built against S15 as at 4 Sep 2026

**Scenario last checked for drift: 13 Sep 2026, unmoved.**

| What deviates | Why | Kind | Resolution |
|---|---|---|---|
| **The change order happens on the main line.** S15 parks the rot discovery in a note as material for a future scenario, and its execution table describes a financed variant | Without it the final bill does not reconcile. The scenario shows $23,920 in its narrative and $21,120 in its plan and flags the mismatch itself. It only resolves if the third part is two fifths of the original plus the change order | **Proposal** | Open. Should reach the team, because it fixes an inconsistency the page already admits to |
| **The project is created on 12 August, at the decision to pursue.** S15 records that beat as an internal decision with no writes, and mints its spine at the first proposal | It is the sharpest claim in our model and the moment the container exists for. The gap is one beat wide | **Proposal** | Open. This is the live disagreement with DRAFT v3 and is already recorded as a decision |
| **Vocabulary translated throughout.** S15 says Sale, Workstream and Job as the spine | S15 is one of six pages still in the old nouns. The team deferred a coordinated rename on 5 September | **Simplification** | Resolves itself when the team renames |
| **Nine steps, not eighteen beats.** Beats collapsed to the points where one of the three views changes | A grid with eighteen columns is unreadable and most beats change nothing on these three views | **Simplification** | Open |
| **Work and close-out compressed into one column** | A consequence of the nine-step collapse, and a mistake. It removed the only moment in the scenario where anybody has to act, so nothing in the grid is amber and the blocked task state is never exercised | **Simplification** | **To fix.** Splitting step 9 into work and close-out is the first item of the next round |
| **The maintenance plan appears on the customer record.** S15 never mentions it | It comes from the worked example, sold at the closeout of the prior HVAC project. It makes the customer record honest about a returning household | **Proposal** | Open. Ask the team to add it to the scenario, or take it off the mocks |
| **The subcontractor is named** | S15 assigns windows to a subcontractor without naming one, so a screen has nothing to show | **Simplification** | Open. The underlying gap, cross-organisation crew assignment, is in the object register |
| **Costs split $25,530 siding and $12,834 windows** | S15 gives no cost figures. Memo 6's were wrong, implying a 58% margin against a stated 31% | **Simplification** | Settled. These are now the canonical figures in the worked example |
| **The windows scope's last line is delivery and handling, not a permit** | S15 says no permit is required on this job. The permit line belongs to the financed telling | **Simplification** | Settled |

## Standing divergences from the scenario set

Not tied to one mock. True of anything built from these scenarios.

| What deviates | Why | Kind |
|---|---|---|
| **The Entities column is ignored** | It is generated rather than written by the team, and it maps to DRAFT v3 rather than to our model | **Simplification**, and a permanent one |
| **Six scenarios are read in translation** | S4, S5, S13, S14, S14B and S15 are still in the old nouns | **Simplification** |
| **Reference codes are absent everywhere** | The scenarios use them throughout. The density standard bans them because they buy nothing on a structural question | **Simplification** |

---

## Memo 7, S14 end to end · built 14 Sep 2026 · against S14 as modified 14 Sep 2026

**Three faults in the scenario itself, found while building the data set.** These are the valuable
kind and should reach Joel.

| What deviates | Why | Kind |
|---|---|---|
| **The rebate does not match the option they bought.** Beat 15 files a heat-pump rebate; beat 7 sells Better, a two-stage condenser. The heat pump is Best, which they declined | Resolved in the data as a **high-efficiency air-conditioning rebate**, because the alternative is changing which option was bought and that breaks beats 4, 5 and 7 and the whole money promise | **Proposal.** The script probably has the wrong rebate name |
| **The tender promise differs from its own twin.** S14 beat 5 is half at the start and half at completion. The S14B header describes $500 deposit, half on install day, and the balance at inspection | S14's own wording used. **Two pages describing the same tender two ways** is a problem for the controlled pair, which is the whole point of S14B | **Proposal** |
| **Three unsigned contracts, one per option, generated ahead of selection.** Flagged as an assumption on the page itself | Our vocabulary says one contract per bundled sale. Drawn as a single row reading "Agreement, three versions", which dodges the question | **Proposal.** Needs a model ruling, not a layout choice |

**And five places the memo added a surface the scenario assumes without describing.**

| What deviates | Why | Kind |
|---|---|---|
| **A triage choice on the intake screen**, between an advisor and a technician | The narrative has the CSR asking the system's age, which is a qualifying question rather than a field. It is the fork between S14 and S13 and the script does not name it | **Proposal** |
| **A near-match row the CSR dismisses** | The customer is new, but the screen cannot know that until somebody looks. Without the row, a duplicate gets created silently | **Proposal** |
| **Advisor availability with travel time** | Beat 2 books a 4pm visit from a 7:54am call and says nothing about how the CSR knows the advisor is free. The script has him arriving ten minutes late, which is what happens when nobody can see the previous job | **Simplification.** Drawn thinly; a scheduling surface is its own memo |
| **A readiness card** putting the order and the permits beside the date that depends on them | Readiness gating is named as unmodelled in the script's own findings. Everything on the card derives from records that already exist | **Proposal** |
| **A "telling the customer" row with no record behind it** | Beat 11 has Rosa phoning the homeowner and nothing holds it. Drawn as an obligation next to three modelled ones, deliberately uncomfortable | **Proposal** |

**One rule broken knowingly.** The close screen in section L carries one line of explanatory copy
inside the mock, which is an Always violation. It says where cheques go, and it is there because a
crew lead standing in a driveway with $6,400 will not read a memo. **Flagged in the memo itself and
here; withdraw it if the rule should hold.**

| What deviates | Why | Kind |
|---|---|---|
| **Explanatory copy inside the close screen** | The alternative is silence about money changing hands | **Simplification**, and an admitted rule break rather than a defensible one |

**One known deviation between the memo and the canvas, before the canvas is built.** Memo 7 section
A shows the near-match as a row that has been dismissed, which implies the system matched in the
background and reported afterwards. **Canvas frames 01 and 02 make the match a search Dana runs**, so
the dismissal is discovered by looking rather than reported. Section A is therefore slightly out of
step with the canvas from the moment it is drawn.

| What deviates | Why | Kind |
|---|---|---|
| **Memo 7 section A implies background matching; the canvas makes it a search** | Andrew chose search-then-create for the two new frames, which is the better answer and post-dates the memo | **Simplification**, and the memo is the thing that should change rather than the canvas |

---

## S14 canvas · built 14 Sep 2026 on CD · against `WORKED-EXAMPLE-S14.md` and memo 7, both as at 14 Sep 2026

**Carried across from CD's write-back block.** No value on any frame is outside the worked example.

| What deviates | Why | Kind |
|---|---|---|
| **Frames 01 and 02 make the near-match a search; memo 7 section A implies background matching** | Already recorded before the canvas existed and now confirmed by it. The canvas makes the match something Dana finds, and the dismissal an act with a reason captured at the time | **Memo 7 is the thing that should change.** Section A's dismissed row is correct as a receipt; its argument should say the match was searched for |
| **Memo 7's own introduction is wrong about itself.** It says ten drawn and four placeholdered. The file has **three** placeholders, sections D, F and K, so eleven are drawn | Found by CD while building the frame table. **Our error, not the scenario's** | **Corrected** in the memo, 14 Sep |
| **Memo sections F and G are absent from the canvas** | Andrew excluded the proposal screens from this round | Drawn as a labelled block in the strip at frame height, saying what is missing and that frame 08 opens with the work already sold. **The gap is visible rather than silent**, which is the right treatment and worth reusing |

---

## Checked on

Every time somebody runs the drift check, record it here as well, because a deviation register nobody
has revalidated is a list of claims about the past.

| Date | By | Scenarios checked | Anything moved |
|---|---|---|---|
| 13 Sep 2026 | C | S15, and every other scenario we have used | No. All unmoved since they were read |
| 14 Sep 2026 | C | S14, read fresh from Confluence | **Yes.** S14 was modified about three hours before it was read, and the modification is the 12 Sep elaboration of the assessment beats. Built against that version |
| 14 Sep 2026 | CD | S14, via the canvas build | No. Built against the worked example and memo 7 as they stood, and both were hours old |

---

## One repointing, recorded because it will recur

**The canvas was carried from the design surface into `prototypes/s14-canvas/` on 14 Sep 2026.** It
linked two stylesheets: its own kit, which came with it, and the **bound Merlin Design System project
on the design surface**, which does not exist here.

**Repointed to our extracted mirror** at `reference/merlin-sol-tokens.css`. Verified: the canvas uses
26 Sol tokens and all 26 are defined in the mirror, so nothing broke. **The mirror is still missing
the radius, spacing and font scales**, which the canvas does not use because the kit carries its own.

**Every canvas carried across will need the same one-line change.** Worth doing at the point of
carrying rather than discovering it when somebody opens the file months later and the page renders
unstyled.
