# Repository hygiene

**Scope:** any repository this work is kept in, on any surface. Not just this one.

**Surfaces:** those that can run git. Read-only surfaces can skip this file.

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
- **Never amend, rebase, force push, or touch a branch other than the one asked for.** A local commit
  that cannot be pushed is a question for Andrew, not a problem to solve by rewriting history.
- **Where a repository lives is a decision for the root decision log**, because it would still be true
  of a different project. Which organisation, which account, and why.

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
- **11 Sep 2026.** `.DS_Store` was sitting untracked in two folders with no `.gitignore` in the
  repository at all.
