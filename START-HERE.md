# Start here

**ux-explore-andrew. Andrew Thompson, UX / Product Design, GoodLeap.**

> **Who may write to this file:** any surface that can write. Edit in place. Keep it under two
> screens. If it grows past that, something below it is not being used.

This repository is the working memory for Andrew's design and modelling work. It is not any team's
record. It exists so that a conversation on any AI surface can start warm rather than cold, and so
that corrections compound instead of evaporating at the end of a session.

---

## The protocol

### 1. Every surface reads this file and the changelog first

Read this file, then `CHANGELOG.md`, and **say out loud the date of the newest changelog entry**
before doing anything else. That one sentence is how Andrew finds out that a surface is working from
a stale copy.

Then read whichever of the files below the task touches. `SOURCES.md` and the project's own sources
file are almost always among them, because they say where things are and which of them you can
actually reach.

### 2. Every session ends with a write-back

Two questions, always both, never one:

1. **What did we learn about the problem?** Goes into the project's overview, or into
   `IDEAS-INBOX.md` if it is a new thread rather than a development of an existing one.
2. **What did we learn about how to work on it?** Goes into `standards/`.

The second question is the one that gets skipped, and skipping it is why the same correction gets
made three times. **A session where Andrew corrected something and no standard changed is a session
that lost work.**

### 3. How you write back depends on what you can do

**If you can write to files** (Cowork, Claude Code): do it before the session ends. Do not ask
whether to write back. Ask only about the content, and only if it is ambiguous.

**If you can read but not write** (Claude Design, and Claude chat with repository access but no write
path): end the session by producing a **write-back block**, which Andrew carries to a surface that can
write. A write-back block names:

- the file
- the section or table
- the exact text to add or replace
- whether it is an append, an edit, or a new row

Make it paste-able as one message. Do not summarise what should change; write what should be written.

**If you can neither read nor write** these files: say so at the start rather than working from
memory, and ask for the relevant ones to be pasted in.

### 4. Prompt Andrew the moment something needs writing, not only at the end

Do not save it all up. When one of these happens, say so in one line: what needs writing, which file
it goes in, and whether you can write it yourself or need him to carry it.

| Trigger | Where it goes |
|---|---|
| **Andrew corrects you**, on anything, however small | A standard. This is the most important trigger and the easiest to miss |
| **Something gets settled** in conversation | A decision log. The project's for domain, the root's for how the work is done |
| **A new idea, problem or story appears** | `IDEAS-INBOX.md`, one line |
| **A source is wrong, moved, or unreachable** | The relevant sources file, changing the access note rather than deleting the row |
| **You diverge from a standard or a mock** | A standard if the rule was wrong, the changelog either way |
| **A tool or surface behaves unexpectedly** | The tooling quirks table in `SOURCES.md`, so the next session does not lose the same ten minutes |
| **Anything above actually gets written** | `CHANGELOG.md`, always |

Then do the two-question sweep at the end of the session regardless, because some of it only becomes
visible in hindsight.

### 5. What the surfaces are called

Use these short forms everywhere: in the changelog's **From** column, in decision rows, in
learned-from lines, and in conversation.

| Short | Surface |
|---|---|
| **C** | Claude Cowork |
| **CC** | Claude Code |
| **CD** | Claude Design |

Changelog rows written before 11 Sep 2026 say "Cowork" and "Claude Code" in full. They stay as they
are, because that file is append only.

### 6. Telling the other surfaces

**No surface can notify another.** It all routes through Andrew, so when you change something, tell
him which surfaces are now stale and what to do about each. Put the same thing in the changelog's
last column.

| Surface | How it picks up a change | What Andrew has to do |
|---|---|---|
| **C**, Cowork | Reads the repository fresh at the start of a session, and picks up the read-me-first file automatically | Nothing. A new session is current |
| **CC**, Claude Code | Same, and re-reads the instructions file on start | Nothing. A new session is current |
| **Claude chat with a project** | Project knowledge is a synced copy, not a live read | Re-sync the project knowledge, or paste the changed file in |
| **CD**, Claude Design | Reads the repository if access is granted, but its own project instructions are a stored copy | Point it at the repository again, and if a standard changed, refresh what is stored in the project |
| **Anything with no access** | It cannot | Paste the changed file in, and say what it replaces |

**A render is a copy, so it goes stale.** Anything in `renders/` is generated from the standards. When
a standard changes, the render is wrong until it is regenerated, and a wrong render is worse than a
missing one because it looks authoritative. Regenerate it in the same session, and say so.

### 7. Rules are never changed silently

A standard that turns out to be wrong gets replaced, and the replacement records what it replaced and
why. A decision that gets reversed becomes a new row in a decision log, never an edit to the old one.
Same reason a change order keeps the original contract value.

---

## Global or project? One test

**If it would still be true on a different project, it is global.**

| Global | Project |
|---|---|
| How a mockup should be laid out | What the nouns mean |
| The design memo format | Which board is the source of truth |
| How to talk to Andrew | Whether the container mints before pricing |
| Where the Merlin design system lives | Where the scenario scripts live |
| Diagram conventions | The canonical worked example |

When it is genuinely both, it is global, and the project file notes the exception.

---

## What is at the root

| File or folder | What it is | How it is written |
|---|---|---|
| `START-HERE.md` | This file. Protocol, the global test, the project index | Edited in place |
| `SOURCES.md` | Sources that outlive any one project: the design system, product repositories, people, tooling quirks | Edited in place, one row per source |
| `IDEAS-INBOX.md` | Raw capture, **for every project**. One line per idea | **Append only.** Never edit, reorder or delete |
| `CHANGELOG.md` | What changed, when, from which surface, and who else is now stale. **The only file that answers whether anything has moved since you last looked** | **Append only.** Newest at the bottom |
| `DECISIONS.md` | Decisions about **how the work is done and where things live**. Not domain decisions | **Append only.** A reversal is a new row |
| `GLOSSARY.md` | **Every controlled vocabulary in one place.** Standing, rigidity, criticality, intent, hold, access, appetite and the rest, plus the collisions between them. Read it before filling in any status column, and **add to it in the session you invent a vocabulary**, not later | Edited in place, one section per vocabulary |
| `standards/` | How to work. One short file per topic, each rule marked **Always**, **Default** or **Prefer**. **Start with `standards/INDEX.md`**, which is every rule on one screen | New files and in-place edits, each recording what it learned from |
| `reference/` | Extracted material used across projects, such as the Merlin token stylesheet | Regenerated, not hand edited |
| `renders/` | The standards rendered for a surface that cannot read this repository, such as the Claude project instructions | Regenerated when a standard changes |
| `prototypes/` | Standalone hosted prototypes, whole-page exports. Outputs rather than working memory | Added when one is built |

**Why the inbox is global.** Capture has to cost nothing. Deciding which project an idea belongs to is
a routing decision, and a routing decision at capture time is friction, and friction stops capture.
Routing happens when an idea is promoted into a project's catalogue.

**Why there is no global domain decision log.** Process decisions are already recorded as rules in
`standards/`, each with a learned-from line that serves as its log. The root decision log is narrow:
which repository, which format, where things live.

---

## Projects

| Project | Folder | Status | What it is |
|---|---|---|---|
| **Upgrade to Pros** | `upgrade-to-pros/` | Live | Taking GoodLeap's contractor tooling from payments only into selling and operations. Current thread is entity and object modelling, moving into UI |
| **Atlas** | not yet created | Dormant | Earlier work, currently still loose in the enclosing folder. Becomes a project folder when it is next picked up |

Each project folder carries its own overview, sources, decisions, idea catalogue and vocabulary, then
a folder per thread. **Read a project's overview before doing anything in it.**

---

## Things this repository is deliberately not

- **Not any team's record.** Contributions to a team repository go as a branch and a pull request for
  its owner to review. Nothing here is authoritative for anyone but Andrew.
- **Not a backlog.** The idea catalogues carry an appetite and a revive condition precisely so they do
  not become one. An idea with no appetite is a note, not a plan.
- **Not a team's publishing target.** Standalone prototypes do live here, in `prototypes/`, because
  this repository is also where they are hosted from. They are outputs, not working memory, and they
  move into a project folder once they clearly belong to one.
