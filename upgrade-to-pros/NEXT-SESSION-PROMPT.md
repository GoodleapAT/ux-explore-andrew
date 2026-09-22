# Prompt for the next session

> **Written 21 September 2026, for Claude Code.** The previous version of this file, written
> 15 September for a chat session, has been replaced. It described a state four passes of the model
> ago and had already been marked used.

**Paste the short version below into Claude Code. Everything after it is here so you do not have to.**

---

## The short version, to paste

```
Continuing the Upgrade to Pros UX work. I am Andrew Thompson, UX and Product Design at GoodLeap.

Read CLAUDE.md, then ux-explore-andrew/START-HERE.md, then ux-explore-andrew/CHANGELOG.md, and tell me the date of
the newest changelog entry before anything else. My working memory is the ux-explore-andrew folder. The
UX-Explore folder beside it is a different repo and it is stale, so stay out of it.

Then read, in this order, all inside ux-explore-andrew:
  upgrade-to-pros/NEXT-SESSION-PROMPT.md   (this is the handover; it names what is live)
  upgrade-to-pros/OPEN-ITEMS.md            (everything unresolved, O-39 to O-47 are new)
  standards/INDEX.md                        then ui-copy.md, mockup-density.md, ui-composition.md
  upgrade-to-pros/S15-DATA.md               sections 1, 1A and 8
  upgrade-to-pros/components/ITERATION-6.md

Do not read every memo. The handover says which two are current and which are stale.

I am moving from Cowork to Claude Code for two reasons. I want to work in the repository directly,
including occasional pull and push against the team's repo, not just my own. And Claude Code supports
commenting inside artifacts, which I have not been able to get working in Cowork.

You can write. Follow the write-back protocol without asking. Read the repositories and write paths
section of the handover before you touch git.
```

---

## Repositories and write paths, read before touching git

Three folders at this level matter and two of them are traps.

| Folder | Repository | Org | What you may do |
|---|---|---|---|
| **`ux-explore-andrew/`** | `ux-explore-andrew` | GoodleapAT | **Andrew's own. Commit and push freely.** The folder was renamed from `ux-hosted` on 21 Sep 2026 so that it matches the repository; documents written before that date call it `ux-hosted` |
| **`u2p-project-planning/`** | `u2p-project-planning` | loanpal-engineering | **Read and edit locally. Never push to main.** Contributions go as a branch and a pull request for Joel. Andrew does want to pull from it and occasionally contribute, so it is in scope, but only that way |
| **`UX-Explore/`** | `UX-Explore` | loanpal-engineering | **Stale. An older copy of `standards/` with no changelog.** Do not read from it and do not write to it. **If the folder you have open has no `CHANGELOG.md` at its root, you are in the wrong one** |

**Do not commit to any repository in the `loanpal-engineering` organisation.** An organisation-level
ruleset forbids direct commits to main and requires a pull request with a code owner review. The
repository's own settings page does not show the rule.

**The state as of 21 September 2026: `ux-explore-andrew` has about thirty uncommitted files on `main` and
nothing from the last week has been pushed.** Everything in the live list below exists only on
Andrew's machine. **Offer to commit before doing anything else**, in coherent commits rather than one
lump, because the changelog rows already describe what changed and the commit messages should match
them.

---

## Where the work actually is

**Live and current:**

| File | What it is |
|---|---|
| `memo-13-refine-the-scope.html` | Five screens. The job at the hand-off, the refine overlay at three states, the job with everything booked. **The current job-page design** |
| `CD-CANVAS-job-and-refine-surface.html` | The same five screens with no annotation, for the Claude Design canvas |
| `memo-14-s5-customer-view.html` | One screen. The S5 customer record at the payments-only tier, built on Andrew's own Pros Web shell |
| `CD-PROMPT-s15-revised.md` | The S15 handover for CD, carrying the revised calendar and the refinement flow |
| `CD-PROMPT-s5-customer-view.md` | The S5 handover, which leads with an instruction to rebuild from existing CD components |
| `S15-ROOFING-SCOPE-AND-ITEMIZATION.md` | Scope of work text and the itemization, as sold and as refined, both at $38,900. **Every figure is ours** |
| `S15-DATA.md` | The only source of mock data. **Section 1A carries the 17 September calendar** |
| `components/ITERATION-6.md` | MoneyCard amended, plus RefineOverlay, WaitingOnLine and DiscoverRow |

**Stale, and do not copy dates or beats out of them:**

- `memo-11-project-two-moments.html`. Dates the post-sale inspection 10 August, three days after the
  refinement it is supposed to produce, and carries the old install week.
- `memo-12-job-two-moments.html`. Carries the old install week.
- `CD-PROMPT-job-roofing-two-states.html` and its prompt. Superseded by memo 13's pair.
- Joel's `ux/s15-multi-trade-project/flow.md` in the team repository. **Describes the S15 that the
  rewrite replaced**: three trades with windows, the roof declined rather than sold, $52,800 by cheque
  outside our rails, no permits.

---

## What was settled in the last two sessions

**The refinement rule, which is the strongest thing here.** The signed itemization is frozen at
signature and the job gets a working copy. **The total is owned by the contract, not by the table**: a
coordinator may split lines, re-categorise them and move money between them, and may not change the
sum. Only a change order amending the proposal and the contract moves it. **Per-line variance is
normal and is not an error.**

**The materials list and the work order are views of the refined itemization**, not documents anybody
authors. Materials list is the Materials category with quantities; work order is the Services category
plus the scope text and access notes, **with prices stripped**. That is why beat 11 does three things
in one sitting. The category tag on each refined row is the sort key that makes it work.

**The work order is a view for an internal crew and a record for an external one**, because a
subcontract carries its own labour price and its own visibility boundary. One name over two things.

**S15 gained three lettered beats and one moved.** 10a, the post-sale inspection, Friday 7 August
8:05 to 9:40am. 17a and 18a, day-before checks, **one per job rather than one per project**. Beat 18
moved so Final checks takes the Monday: roofing Tuesday 18 to Wednesday 19, siding Thursday 20 to
Friday 21. **Nothing downstream moved**, so both jobs complete Friday 21, invoice Monday 24, paid
Wednesday 26, and the three day amber window survives.

**S5 is named.** Homeowner Dana Whitfield, 1806 Cedar Row. Contractor Caldwell Brothers Fence and
Deck, two brothers, four in season. **Wes Caldwell** is the one in the app. This Dana has nothing to
do with Dana's Roofing in the pipeline document.

**A takeover is now a declared exception** to the rule that detail goes sideways into a sheet, for one
named task that begins, ends and commits. Second exception after capture-during-a-call.

**Two copy rules were being broken by every mock**, and are now in `standards/ui-copy.md`. Dollar
values always show cents. Dates are US format and never day first.

---

## What to do next, in the order I would do it

1. **Fix the two stale memos.** Memo 11's inspection date and both memos' install week. Mechanical,
   and they are the files most likely to be read by somebody else.
2. **Pull the S15 script down from Confluence and save it verbatim with a date stamp.** O-39. The data
   pack cites it as authority and cannot reach it. Its six weeks sentence also needs changing to
   twenty days.
3. **Decide O-41**, whether the roofing price being roughly double market matters for a demo about
   workflow.
4. **The S5 screens Andrew has not yet asked for.** He named script rows 5 and 6, about three screens
   of taking a payment on a phone, much of which exists in the product today. Row 14 to 17's customer
   record is done.
5. **S6**, the loan-only wedge, which he named alongside S5 and has not started.

---

## Things to know before you build anything

**Ask before building or rebuilding a memo or an artifact. Every time.** This is an Always rule and it
has been broken before.

**No em dashes anywhere.** Short replies. Lead with the decision and the trade-off. No file paths,
code or identifiers in a reply unless asked, and write that detail into the documents instead.

**Never commit to any repository in the `loanpal-engineering` organisation.** An organisation-level
ruleset forbids it and the repository's own settings page does not show the rule. Contributions to
`u2p-project-planning` go as a branch and a pull request for Joel.

**Other people's work is reference, never input.** Say whose it is, every time. There is something
called a UX factory in the team repository, created by Joel. **Andrew declined to adopt it**, on
14 September, and wants to build his own from his own exploration. That correction has been made three
times; `standards/external-work.md` carries the Always rules about it.

**And five of Joel's skills are invokable in any Claude Code session opened in the enclosing folder**,
because the team repository sits beside this one: `ux-factory`, `script-to-model`, `scenario-builder`,
`scenario-digest` and `board-snapshot`. **Andrew's standing instruction, 21 September: do not use
them unless he says so explicitly.** A listed skill looks like an offer and is not one. Running one
would read their board, write their files and commit, which would make our work an input to their
system in a single call.

**Andrew's own equivalent is called the UX Kit**, renamed from the factory on 21 September and
provisional. Its reasoning is in `in-depth/the-ux-kit.md`, rewritten the same day, and it carries the
route, the ownership model, the exercises for other teams and the language workstream. **Its render
is deliberately stale and says so on its face.**

**The pipeline documents both open with "do not act on this".** Dana's Roofing's stages, tasks and
gates are a sketch. Every mock that draws a stage rail is using unagreed names and says so.

**Per-job cost and per-job margin are absent by rule.** Not greyed, not labelled unavailable, not
explained on screen. Revenue occurs at the project and cost at the job, and no allocation rule exists.
