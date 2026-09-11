# Changelog

**What changed, when, and who else needs to know. This is the only file that answers "has anything
changed since I last looked".**

> **Who may write to this file:** any surface that can write, and it **must**, every time it changes
> anything in this repository. **Append only.** Newest at the bottom. Never edit or delete a row.
>
> **Every surface reads this file at the start of a session and says out loud the date of the newest
> entry.** That one sentence is the whole sync mechanism. If a Claude Design session says 9 September
> and a Cowork session says 11 September, Design is stale and needs re-pointing.
>
> **Surfaces that cannot write** must include a row for this file in their write-back block.
>
> One row per meaningful change. A typo fix is not a meaningful change. A changed rule, a new
> decision, a moved file, a source that turned out to be wrong, or a new document all are.

## The columns

| Column | What goes in it |
|---|---|
| **Date** | The date of the change |
| **What changed** | One sentence, in plain language. Enough that somebody can tell whether it affects them |
| **Files** | Which files. Name them, because that is how a reader decides whether to re-read |
| **From** | Which surface made the change: Cowork, Claude Code, Claude chat, Claude Design via a write-back |
| **Who else needs to know** | Which other surfaces are now stale, and what to do. `None` is a valid answer and usually the right one |

---

| Date | What changed | Files | From | Who else needs to know |
|---|---|---|---|---|
| 2026-09-11 | Working memory created: start-here protocol, global sources, idea inbox, process decision log, five standards | Root files and `standards/` | Cowork | None, first version |
| 2026-09-11 | Restructured to multi-project: global at the root, project folders below. Vocabulary moved into the project, idea catalogue moved with it | `START-HERE.md`, `upgrade-to-pros/` | Cowork | None, nothing was pointing at it yet |
| 2026-09-11 | Repository hygiene standard added, after an organisation ruleset blocked commits to main. A gitignore was added | `standards/repository-hygiene.md`, `.gitignore` | Claude Code | None |
| 2026-09-11 | Repository moved from `loanpal-engineering/UX-Explore` to `GoodleapAT/ux-explore-andrew`, which also absorbed the hosted prototypes | Everything, plus the read-me-first file outside the repository | Cowork | Any surface pointed at the old repository, which is all of them. The old one can be deleted |
| 2026-09-11 | Claude Design context written: where the model landed, the five differences from DRAFT v3, all eighteen scenario rows, the UI history, and the read-only write-back protocol | `upgrade-to-pros/CLAUDE-DESIGN-CONTEXT.md` | Cowork | Claude Design. Point it at the repository and have it read this document first |
| 2026-09-11 | Scenario pages: recorded that the Entities column is generated rather than authored, so the scenarios are authoritative on the experience and not on the model. Review status is a marker on the page | `upgrade-to-pros/SOURCES.md`, `upgrade-to-pros/CLAUDE-DESIGN-CONTEXT.md` | Cowork | Any surface that has already read a scenario and treated the Entities column as a specification |
| 2026-09-11 | This changelog created, with prompting triggers and a per-surface staleness table added to the protocol | `CHANGELOG.md`, `START-HERE.md`, both read-me-first files | Cowork | All surfaces, at the start of their next session |
| 2026-09-11 | Claude Design re-pointed at the moved repository and told what changed. First live use of the sync mechanism | None, an action rather than a change | Cowork | None |
| 2026-09-11 | Joel's ux-factory recorded: what it is, what is worth borrowing, what does not transfer, the board's nav contract and the two read-only boundaries. Three new idea records and a need | `upgrade-to-pros/SOURCES.md`, `upgrade-to-pros/IDEAS-CATALOGUE.md`, `IDEAS-INBOX.md` | Cowork | Claude Design, if it has been asked about page structure. The board has a UX DRAFT section with nine archetypes and a nav contract that the context document does not yet mention |
| 2026-09-11 | **Token correction.** Joel's team reports the Merlin file is a mirror of Sol carrying only the 113 semantic tokens, with no radius, spacing or font scale. Our extracted stylesheet is that mirror | `SOURCES.md` | Cowork | Claude Design and any surface building mockups. The token file is incomplete, not wrong. Re-extract from Sol before the next round |
| 2026-09-11 | The nav contract, the parallel UX effort and the token caveat added to the Claude Design context, so Design reads them from the repository rather than from a message. Working voice gained a rule: writing a changelog row is not the same as telling Andrew | `upgrade-to-pros/CLAUDE-DESIGN-CONTEXT.md`, `standards/working-voice.md` | Cowork | **Claude Design.** Have it re-read the context document, which now carries the nav contract and the token caveat |
| 2026-09-11 | **Reframed Joel's UX factory as external reference rather than an input.** New standard on handling other people's parallel work: reference never input, say whose it is, nothing crosses over until Andrew says so, do not manufacture urgency from it. The nav contract is recorded as their position and explicitly not binding. N-004 recast as M-005, a move Andrew may take rather than a gap he must fill | `standards/external-work.md`, `upgrade-to-pros/SOURCES.md`, `upgrade-to-pros/CLAUDE-DESIGN-CONTEXT.md`, `upgrade-to-pros/IDEAS-CATALOGUE.md`, `IDEAS-INBOX.md` | Cowork | **Claude Design.** Re-read the context document. Its section on the other effort now says plainly that none of it is a requirement |
| 2026-09-11 | Mockup density gained a rule: **no reference codes or record identifiers**. Call the thing by its name. They cost row space, buy nothing on a structural question, and make a screen look drawn against a system of record that exists | `standards/mockup-density.md` | Cowork | **Claude Design.** Applies to anything already built. The five views in memo 6 still carry codes and are now out of step with the standard |
| 2026-09-11 | **Component library standard added.** Atomic design principles, six fields recorded at creation, a declared position per product tier for when a component's subject is absent, one component with states rather than near-identical siblings, and the library repository-resident rather than living in CD. Surface short forms defined: C, CC, CD | `standards/component-library.md`, `START-HERE.md`, `DECISIONS.md` | C | **CD.** It changes how every component is recorded from now on, and it should know the destination before it builds more screens |
