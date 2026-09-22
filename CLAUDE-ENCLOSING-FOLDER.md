# Read this first

**Andrew Thompson, UX / Product Design, GoodLeap.**

> **This file governs the enclosing folder, not this repository.** `CLAUDE.md` inside this repository
> is the one for the repository. **This is where it now lives, as of 21 Sep 2026**, and the path every
> surface actually reads, `CLAUDE.md` at the enclosing level, is a symbolic link to this file. **It is
> a link and not a copy on purpose**, so the two can never diverge. It was moved here because the
> enclosing folder is not a git work tree, so the first file every surface reads had no history and no
> backup.

Before doing anything in this folder, read **`ux-explore-andrew/START-HERE.md`**. It carries the
protocol, an index of the working memory, the rule for what is global and what belongs to a project,
and the project index.

**Then read `ux-explore-andrew/CHANGELOG.md` and say the date of its newest entry.** That one sentence
is how Andrew finds out whether a surface is working from a stale copy. Append to it whenever you
change anything, and name which other surfaces are now stale.

Then read whatever those files point you at for the task in hand. The sources registers, one global
and one per project, are almost always among them, because they say where things are and which of them
you can actually reach.

## The three things you must not skip

**Read `ux-explore-andrew/standards/` before building anything.** Short files, one per topic. They
exist because the same corrections were being made in session after session. If you build a mockup
without reading `ux-explore-andrew/standards/mockup-density.md` and `ux-explore-andrew/standards/ui-composition.md`, you will build it wrong.

**Prompt Andrew the moment something needs writing.** Do not save it up for the end. When he corrects
you, when something gets settled, when a new idea appears, when a source turns out to be wrong or
unreachable, or when you diverge from a standard, say so in one line: what needs writing, which file it
goes in, and whether you can write it yourself. The trigger table is in `START-HERE.md`.

**Write back before the session ends.** Two questions, always both:

1. What did we learn about the problem? Into the project's overview, or into
   `ux-explore-andrew/IDEAS-INBOX.md` if it is a new thread.
2. What did we learn about how to work on it? Into `ux-explore-andrew/standards/`.

If Andrew corrected something and no standard changed, the session lost work. Whatever gets written
also gets a changelog row. If you cannot write to files, end by producing a paste-able write-back block
instead; `START-HERE.md` says what one looks like.

## Quick orientation

- `ux-explore-andrew/` is Andrew's working memory, project material and hosted prototypes. **The folder
  and the repository now have the same name**, renamed on disk 21 Sep 2026; it was `ux-hosted/` until
  then, which is why documents written before that date use that word. Private, in the GoodleapAT
  organisation, and pushable by him. The root is global, and each project has a folder. The live
  project is `upgrade-to-pros/`
- **`UX-Explore/` at this level is a different repository and it is stale.** It is in
  `loanpal-engineering`, it holds an older copy of `standards/`, and it has no changelog.
  **The two names now differ by a suffix rather than completely**, which is the cost of the rename, so
  use the test rather than the name: **if the folder you have open has no `CHANGELOG.md` at its root,
  you are in the wrong one**
- `u2p-project-planning/` is the Upgrade to Pros team record, owned by Joel. Readable and editable
  here, **not pushable**. Contributions go as a branch and a pull request
- Everything else at this level is either a product repository or earlier cross-cutting work that has
  not been moved into a project yet. The global sources register tells you which

**Do not commit to any repository in the `loanpal-engineering` organisation.** An organisation-level
ruleset forbids direct commits to main there and requires a pull request with a code owner review.
This applies to every repository in that organisation, and the repository's own settings page does not
show the rule. See `ux-explore-andrew/standards/repository-hygiene.md`.

## House rules, in brief

No em dashes. Short replies. Plain language, no file paths in conversation. Lead with the decision and
the trade-off. **Ask before building or rebuilding any artifact, every time.** The full versions are
in `ux-explore-andrew/standards/working-voice.md`.
