# Repository hygiene

**Scope:** any repository this work is kept in, on any surface. Not just this one.

**Surfaces:** those that can run git. Read-only surfaces can skip this file.

**How hard to hold this.** The first three rules are **Always**. The rest are **Default**. Markers mean: **Always**, breaking it is a defect and you say so first. **Default**, do it unless you have a reason and say the reason. **Prefer**, a leaning.

---

## The rules

- **Check the write path before doing the work, not after.** A repository you can read and commit to
  locally is not necessarily one you can push to. Confirm it early, because finding out at push time
  means a pile of finished work and nowhere to put it.
- **Repositories in `loanpal-engineering` forbid direct commits to main.** An organisation-level
  ruleset requires a pull request with one approving review and a code owner review, and blocks force
  pushes and branch deletion. This is not per-repository branch protection, so the repository's own
  settings page shows nothing. Admin on the repository does not exempt you.
- **A greyed-out commit button in GitHub Desktop usually means a repository rule**, not a broken
  setup. GitHub Desktop reads the rules and disables the button, but fails to name the reason when the
  rule comes from an organisation ruleset rather than the repository. Check the rules from the command
  line rather than guessing at identity or permissions.
- **Every repository carries a `.gitignore` from the first commit.** macOS and editor noise, at
  minimum `.DS_Store`. Committing `.DS_Store` once means fighting it in every diff afterwards.
- **Read git state with `git --no-optional-locks`, always, from any sandboxed shell.** `git status`
  and `git diff` refresh the index as a convenience, which writes `.git/index.lock`. **The sandbox can
  create that file and cannot unlink it**, so an ordinary status check leaves a lock behind that blocks
  the next real commit. `git --no-optional-locks status --porcelain` returns exactly the same answer
  and leaves nothing. `GIT_OPTIONAL_LOCKS=0` does the same for a whole session.
- **Never amend, rebase, force push, or touch a branch other than the one asked for.** A local commit
  that cannot be pushed is a question for Andrew, not a problem to solve by rewriting history.
- **Where a repository lives is a decision for the root decision log**, because it would still be true
  of a different project. Which organisation, which account, and why.

## Parallel sessions on one repository

When one piece of work is split across several sessions, each opening its own pull request. **All
Default.**

- **Give each session different files.** When the work is split, the session doing the splitting
  names the files each piece will touch and says where two overlap. Overlapping pieces run one after
  the other, or the second starts from the first one's branch. Two sessions editing the same file at
  once is where every conflict so far has come from.
- **New code goes in a new file where it can.** A new rule, check or helper gets its own file rather
  than a block added to an existing one. **Tests especially**: a block added to the end of the same
  long test function by two sessions is a guaranteed conflict, and one test file per feature is not.
- **Merge small pull requests quickly, and bring the branch up to date right before opening one.**
  The less time two branches are open together, the fewer collisions.
- **Check the pull request is still clean after opening it**, and clear a conflict straight away by
  **merging main into the branch**, not by rebasing. Merging rewrites nothing, so it stays inside the
  Always rule above against rebasing and force pushing. Most of these conflicts are trivial; found
  late, they look like a problem.

## Diagnosing a blocked commit or push

In order, because each step rules out the cheaper cause first:

1. Is the git identity set, globally or locally
2. Is HEAD on a branch, and is there an unfinished merge, rebase or cherry-pick
3. Is commit signing required, and is there a custom hooks path or a non-sample hook
4. Do organisation or enterprise rulesets apply to the branch, which the repository's own protection
   settings will not show

## Learned from

- **11 Sep 2026.** Forty-nine files were finished and committed before anyone checked whether main
  could be pushed to. The organisation ruleset rejected it. The work was not lost, but the order was
  wrong, and the rule now says to check first.
- **11 Sep 2026.** GitHub Desktop's commit button was disabled with no reason given, which sent the
  diagnosis towards git identity and permissions when the cause was an organisation ruleset. Recorded
  so the next session starts at the right end.
- **15 Sep 2026.** A plain `git status` from the sandbox left a zero-byte `index.lock` that neither
  git nor `rm` could remove, because **the mount permits creating a file in `.git` and not unlinking
  one.** Andrew found it. **The cause is the index refresh, not the repository**, and
  `--no-optional-locks` avoids it entirely. **Two sessions had already lost time to this**: the quirks
  table already carried a row on how to diagnose the lock, which is the wrong half of the problem.
  **Knowing how to clean up after a tool is worth less than knowing how not to trigger it.**
- **14 Nov 2026.** Field Copilot's homeowner scanner work was split across four sessions, and three
  of their pull requests (#60, #61, #62) edited the same two files. #61 merged while #62 was being
  built, and #62 conflicted, in new tests added to the end of the same test function. **The session
  cleared it by rebasing and force pushing its own branch, which broke the Always rule above** and
  was only said afterwards. Andrew asked how to prevent it; the parallel sessions section is the
  answer, and it resolves conflicts by merging so the Always rule holds.
- **11 Sep 2026.** `.DS_Store` was sitting untracked in two folders with no `.gitignore` in the
  repository at all.
