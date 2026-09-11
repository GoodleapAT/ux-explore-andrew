# Decisions, global

**How the work is done and where things live. Not domain decisions.**

> **Who may write to this file:** any surface that can write. **Append only.** Add to the bottom.
> Never edit or delete an existing row. A reversal is a **new row** that names the row it supersedes.
>
> **What belongs here.** Anything that would still be true on a different project: which repository,
> which format, where a kind of file lives, how a surface should behave. Domain decisions go in the
> project's own decision log.
>
> **What does not belong here.** Rules. A rule lives in `standards/`, and the learned-from line inside
> it is its log. This file is for decisions that do not become a rule.
>
> **Only log what was actually decided.** A recommendation nobody accepted is not a decision.

---

| Date | Decision | Why | Supersedes | Applies to |
|---|---|---|---|---|
| 2026-09-11 | **A working memory exists**, with a start-here protocol, a sources register, a two-file idea store, decision logs and a standards set | Corrections to how the work is done were evaporating at the end of every session. Domain learning was compounding and process learning was not | | Everything |
| 2026-09-11 | **The write-back is two questions, not one.** What did we learn about the problem, and what did we learn about how to work on it | The second question is the one that gets skipped, and skipping it is the whole failure mode | | Every session |
| 2026-09-11 | **Surfaces that cannot write must produce a paste-able write-back block**, naming the file, the section, the exact text and whether it is an append or an edit | Claude Design can read a repository if given access but cannot write to one. Without this the compounding stops at whichever surface is read only | | Claude Design, and chat without a write path |
| 2026-09-11 | **The substrate is markdown in a repository, not a tool** | Claude chat, Cowork and Claude Design have almost nothing in common except that all three can be handed text, and a repository is the only form all three can reach. A tool would give better capture and be invisible to Claude Design | | Everything |
| 2026-09-11 | **The repository is UX-Explore, private.** Not a folder inside the team repository | The team repository needs a fork, a branch and a pull request for its owner to review. A pull request per session will stop happening inside a fortnight, and compounding dies on friction. Also, working voice and raw capture are not team-reviewable material | An earlier suggestion to keep the working memory as a loose folder | Where everything lives |
| 2026-09-11 | **The structure is global at the root, project-specific in project folders.** The test is: if it would still be true on a different project, it is global | The working memory has to serve more than one project. Without the test, every file becomes a judgement call | The single-project layout built the same morning | Structure |
| 2026-09-11 | **One global idea inbox, one catalogue per project** | Capture must not require deciding which project an idea belongs to, because that is a routing decision and routing at capture time is friction. Routing happens at promotion instead | | Ideas |
| 2026-09-11 | **No global domain decision log.** The global log is narrow and process decisions live as rules in the standards | Two logs with a fuzzy boundary is worse than two logs with a sharp one. Rules already carry their own learned-from line | | Decisions |
| 2026-09-11 | **A read-me-first file sits at the top of the enclosing folder**, outside this repository, pointing into it | That enclosing folder is what Cowork opens, so it is the only place a hook is picked up without being asked for | | How a session starts |
| 2026-09-11 | **The standards are rendered for surfaces that cannot read the repository**, and the renders are regenerated rather than edited | One source, several outputs. A render edited in place becomes a second source of truth | | Standards |
| 2026-09-11 | **The repository is `ux-explore-andrew` in the GoodleapAT organisation, private.** Formerly `ux-hosted`, renamed and repurposed to hold the working memory alongside the prototypes it already carried | An organisation ruleset on `loanpal-engineering` forbids direct commits to main on every repository in it, requiring a pull request with an approving review and a code owner review. Admin on the repository does not exempt you, and the repository's own settings page does not show the rule. A pull request per session is exactly the friction that stops a write-back happening | The row above, which put it in `loanpal-engineering` | Where everything lives |
| 2026-09-11 | **Standalone prototypes live at the root in `prototypes/`**, not in a project folder | Neither existing prototype is clearly tied to one project. They move into a project folder when they are | | Prototypes |
| 2026-09-11 | **The move did not preserve the two unpushed commits.** Files were copied and committed fresh | The old and new repositories have unrelated histories, so pushing one into the other means merging unrelated roots. One day of history is not worth that | | History |
| 2026-09-11 | **A changelog is the cross-surface sync mechanism.** Every surface reads it at the start of a session and says the date of the newest entry, and appends to it whenever it changes anything | No surface can notify another, so staleness has to be visible to Andrew instead. Saying the date out loud is the cheapest possible check, and it costs one sentence | | Every surface |
| 2026-09-11 | **Prompt Andrew the moment something needs writing, not only at the end of a session** | Saving it up means most of it is lost, and a correction is the easiest thing to forget because it happens mid-task rather than at a boundary | | Every surface |
| 2026-09-11 | **A render carries the date of the standards it was generated from**, and says so at the top | A render is a copy and copies go stale. A stale render is worse than a missing one, because it looks authoritative | | Renders |
| 2026-09-11 | **A changelog row names which other surfaces are now stale and what to do about each** | Knowing something changed is useless without knowing who is affected. The agent that made the change is the only thing that knows | | Every surface |
| 2026-09-11 | **The eventual output is a component repository on atomic design principles**, where each component carries its logic: level, states, when to use, when not to, and what it does when its subject is absent. Recorded at creation, never later | The usage rule and the anti-rule only exist while the reasoning is in the room. Afterwards they have to be re-derived from markup, and the anti-rules are lost entirely because a screen never shows what somebody decided not to do | | Every component and page template |
| 2026-09-11 | **The component library is repository-resident. CD is where components are designed, not where they are kept** | Colleagues will consume it from CC and other programs and most will never open CD. A library that exists only as canvas artefacts cannot be read by the people who need it | | The library |
| 2026-09-11 | **Surfaces are abbreviated C for Claude Cowork, CC for Claude Code, CD for Claude Design.** Used in the changelog's From column, decision rows, learned-from lines and conversation | Shorter, and it makes the From column scannable. Rows written before this date stay in full, because the changelog is append only | | Every surface |
