# Kickoff prompt (superseded)

> **Superseded on 11 Sep 2026.** A kickoff prompt is no longer needed. The repository root carries
> a start-here protocol that every surface reads first, and the enclosing folder carries a
> read-me-first file that Cowork and Claude Code pick up without being asked. Paths and folder
> names below are from before the move and are no longer correct.
>
> Kept as a record of how a session was opened before the protocol existed.

---

# Kickoff prompt for the next chat

Paste the block below as the first message. Connect the folder
`Documents/GitHub/entity-modeling-andrew` before sending. Connecting `Documents/GitHub` as well is
useful but not required.

---

I'm continuing entity-modelling work for Pros Web. Start by reading `OVERVIEW.md` in the
entity-modeling-andrew folder — it's the handoff and it carries the model, the canonical Thompson
scenario, the open questions and where everything lives. Don't read anything else yet.

Three things I want to do in this session, in order.

**1. Compare DRAFT v3 against my Model C.**
DRAFT v3 is the revised model the four of us — Daidipya, Joel, John Gaquin and me — built while
walking scenarios:
https://www.figma.com/board/pNgQNZTXaNC8CFK2yFTItu/Pros-Entities?node-id=498-4910

The scenarios we worked through are in Confluence:
https://goodleap.atlassian.net/wiki/x/KQCsTQE
(The Atlassian connector may need authorising before you can read these. Tell me if so.)

My current model is `diagram-model-c-structure-v3.html` in the folder. The three-model comparison in
`pros-web-three-models-snapshot.md` predates DRAFT v3, so treat it as background rather than
current.

I already know DRAFT v3 added a Spine lane with "Project — The Spine, models one customer journey"
and narrowed Job to "execution of one committed scope component". What I don't know is how it
answers the four questions in the handoff: thin container versus financial roll-up, minted versus
declared, per-property versus per-customer, and where declined-but-still-wanted demand lives. Read
the board and tell me.

Also check how DRAFT v3 handles **services and memberships**, for example annual HVAC maintenance.
It has Service Plan in the Spine lane beside Project, and Joel's earlier map had a flywheel of
service agreements and recurring service events. These express jobs and money differently from
one-off project work, and my model doesn't really handle them yet.

My model also sits on that same board as "Andrew's Model v3":
https://www.figma.com/board/pNgQNZTXaNC8CFK2yFTItu/Pros-Entities?node-id=498-5293
Treat the board as the source of truth and the local HTML as its copy. Note that **Selling and Work
are groupings in the experience, not proposed entities** — everything else in that diagram is an
entity claim, but those two exist because the product needs a clear line between what is being sold
and what is being delivered. Two further things are intentional and easy to misread as gaps: the pipeline is not drawn, because stages, statuses, tasks
and checklists are surfaced at the project, selling, work and job levels alike rather than owned by
one of them; and documents, notes, measurements, history, site assessments and insights are left
out, because they attach to several objects at once. Deciding where each of those actually surfaces
is part of the UI work in step 3.

**2. Settle on a final model.**
Based on that comparison, help me decide what to carry from Model C into DRAFT v3 and what to drop.
I care most about the container existing before pricing and about opportunities surviving a decline,
so push back if DRAFT v3 handles those better than I think.

**3. Start the UX and UI.**
Once the model is settled, I want to design screens that fully address it and the scenario set. Use
the design memo format specified in `merlin-ux-design-project-instructions.md` in the GitHub root:
mockup on the left, argument on the right, numbered open questions, editorial rather than
interactive.

Working agreements are at the end of the handoff. The ones that matter most: ask before building or
rebuilding any artifact, save work to the entity-modeling-andrew folder unless I say otherwise, keep
replies short and free of file paths, orthogonal connectors only, and no em dashes.

Read the handoff and tell me what you make of DRAFT v3 against my model. Don't build anything yet.
