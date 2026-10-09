# Empowering UX, PM and FE

**Project overview. Read this before doing anything in this folder.**

> **Who may write to this file:** any surface that can write. Edit in place. Keep the state of play
> current; that is most of what this file is for.

**Design systems working together, and empowering non designers to design and non engineers to
build.**

Improving the stages of the software development lifecycle that design and implement UI and UX, so
that designers, PMs and frontend engineers can design and ship features with AI tools, across Pros
Web, the Pros App and the Origin migration, without the platforms drifting further apart.

The root of this repository carries how the work is done. This file carries what the work is.

---

## Objectives

From Section 1 of the Upgrade to Pros FigJam board, where this work started in August:

1. Use of AI platforms (Claude Design, Claude Code, Figma AI) in the UI and UX phases.
2. PMs and frontend and backend engineers designing and shipping features.
3. Pros Web and Pros App features designed in parallel, rather than App following.
4. Preventing silent drift between Pros Web and the Pros App.
5. Faster, more intelligent migration of Origin functionality to Pros.

**Implied by the August work**, read from the record on 9 Oct and confirmed by Andrew:

6. **A design system tools can trust.** Claude Design and other tools get real token values and
   components rather than plausible guesses. Investigations 01, 02 and 04 serve this.
7. **One findable cross-platform catalog.** Each web component paired with its mobile counterpart,
   with a note on whether any difference is deliberate. The `/dev/parity` plan, the mapping
   categories and investigation 03 serve this.
8. **Design review at the right moment, without gating everything.** CODEOWNERS paths, the two-axis
   routing model and the bulk lead upload case serve this.
9. **Named owners and a workgroup.** Progress depends on focused frontend help and an owner on each
   platform. Sol has no known owner.

**Added by Andrew, 9 Oct:**

10. **Local environments for PMs and UX designers.** Anyone designing or shipping UI can run each
    platform locally and work in its repository with Claude Code. This was already on the board as a
    next step ("give designers, and possibly PMs, capable local environments"), and is now a goal in
    its own right. Progress is under **Local environments** below.
11. **Designers and PMs can create their own internal repositories.** Internal, not public. Now that
    everyone works with AI tools, a repository is how working material gets shared and built on, so
    being able to create one without an engineer could be extremely beneficial for collaboration.
    Two routes found so far, both in `SOURCES.md`: a Slack workflow documented on Confluence, and a
    GitHub repo request in GoodLeap Watt. Neither has been tried and compared yet.

**Not the aim:** rebuilding Origin in place, since Origin is reference only and Merlin is the build
target; or a unified catalog for its own sake, since the site map was scoped to serve the migration.

**The pitch to frontend engineers:** "UI production got cheap. Coordination did not." Four buckets:
make the system findable; get design in at the right moment; let designers act on their own
feedback; keep pace with the tools.

---

## State of play, 9 October 2026

**The project folder was created today** from work done between 4 and 25 August, before attention
moved to the Upgrade to Pros data modelling. Nothing has moved on it since August.

**Open, carried from August:**

- **No response from the frontend leads** to any of the four investigations is recorded.
- **The `/dev/parity` catalog was never built.** The plan was a visual catalog first, piloted on lead
  detail, then a mapping file worked backward from it.
- **Sol's owner is still unknown.** Sol lives in `goodleap/design-system`; nobody has been found who
  maintains it.
- **The workgroup** on a unified component catalog was proposed, but its stakeholders were never named.
- **The Origin payments IA matrix** has an empty Target column, and whether Origin absorbs Pros or the
  reverse was never resolved.

### Local environments, 9 Oct

**Merlin (Pros Web): partly done.**

- **Andrew's setup guide** is on Confluence, "Setting up Claude Code and a full local environment for
  Merlin". It was written over time in a Claude chat called **Merlin environment setup**. Link in
  `SOURCES.md`.
- **Alexei Godfray added an `onboardsetup.zsh` script** to the Merlin repo to help onboard people.
  **Issues still to work out:** some steps are not descriptive enough, some are not relevant to
  people who are not engineers, and some are out of date, such as using Docker at all.
- **Open: Andrew can no longer push to the Merlin repo.** He used to have write access. Cause and fix
  are being investigated.

**Pros App: not yet assessed.** Next.

**Origin: not yet assessed.** Lower priority over time as features move to Pros, but still a
priority. **The bigger concern is Origin's multi-repo structure.** Interrogating it to learn Origin
or work on a feature costs a lot of time and tokens, because Claude Code struggles to find where a
given element comes from. Part of the reason is known: Lumos 2 is resolved at runtime and has no
source in `pay-mfe`, and the shell, micro-frontends and backends are separate repositories.

`earlier/EARLY-WORK-OVERVIEW.md` has the full record, including what was found in code and what was
left open in each thread. **Re-check anything it says was found in code before relying on it.**

---

## Threads

| Thread | Folder | Status |
|---|---|---|
| **Early work record** | `earlier/EARLY-WORK-OVERVIEW.md` | History. All seven August threads in one document. Moved here from `upgrade-to-pros/earlier/` on 9 Oct |
| **Investigations** | `investigations/` | Sent in August, no response recorded. Four asks of the frontend teams and the design-system maintainers, each standalone |
| **Origin migration** | `origin-migration/` | Paused since 25 Aug. The Claude Design brief and the three-platform site-map data |

**The four investigations:**

| File | Finding | For |
|---|---|---|
| `investigation-01-merlin-sol-token-values.md` | Sol's token values are not readable from the Merlin repo | Merlin frontend |
| `investigation-02-merlin-ai-guidance-cleanup.md` | The styling guidance files contradict each other and the code | Merlin frontend |
| `investigation-03-pros-app-catalog-and-theme.md` | The Pros App catalog has nothing keeping it current, and Sol already ships a Flutter build | Pros App / Flutter |
| `investigation-04-design-system-token-hex-hsl.md` | The token package ships two disagreeing colour palettes, and web and Flutter each read a different one. High severity | `goodleap/design-system` maintainers |

**The Origin migration files:**

| File | What it is |
|---|---|
| `claude-design-origin-migration-brief.md` | Project instructions for a Claude Design project translating Origin payments views into Pros Web. One rule: Origin is read-only reference, Merlin is the only build target |
| `site-map-data.json` | Node inventory for Pros Web, the Pros App and Origin payments, with content, actions, states, gating and links. Generated 12 Aug. Describes unreleased work |

---

## Where the other work lives

- **The FigJam board.** Section 1 of the Upgrade to Pros board, Page 1, holds the objectives, the
  two-axis guardrails, the bulk lead upload case and the payments IA. Links are in `SOURCES.md`.
- **The convergence one-pager**, from the opening strategy read, is in `upgrade-to-pros/earlier/`.
- **Two Confluence pages** in the Merlin space came out of this work. Links are in `SOURCES.md`.
