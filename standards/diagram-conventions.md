# Diagram conventions

**Scope:** any diagram, on any surface, in any document. Not just design memos.

**Surfaces:** all.

**How hard to hold this.** Orthogonal connectors and the `[i]` marker are **Always**. Everything else here is **Default**. Markers mean: **Always**, breaking it is a defect and you say so first. **Default**, do it unless you have a reason and say the reason. **Prefer**, a leaning.

---

## The rules

- **Connectors are always orthogonal.** Right-angle corners, never curves. This holds everywhere.
- **A diagram is annotation throughout**, so it needs no `[i]` marker and no convention note. Only
  mockups need those, because in a mockup annotation could be mistaken for interface copy.
- **Label the relationship on the connector**, not only the boxes. A line with no verb on it is an
  assertion nobody can argue with.
- **Say which boxes are entity claims and which are not.** In the current model, Selling and Work are
  groupings in the experience rather than proposed entities, and a reader who is modelling data will
  otherwise take them as entities.
- **Leave out what attaches to several objects at once**, and say in the caption that it has been
  left out. Documents, notes, measurements, history, site assessments and insights all attach to more
  than one thing, and drawing them at a single level asserts an ownership the model is not claiming.
- **Do not draw the pipeline as belonging to one level.** Stages, statuses, tasks and gates are
  surfaced at the lead, project, selling, work and job levels alike.
- A diagram is **complete on structure and not exhaustive on contents**. Say so rather than letting a
  reader assume the gaps are oversights.

## Reading the boards

The team's Figma boards are the source of truth and any local copy is a copy. When they disagree,
the board wins and the local file gets updated.

**A practical note on reading them.** The Figma text extraction tool fails on large board nodes, so
read a board as a rendered screenshot instead. Request it at a high enough resolution to read the
small annotation, because the small annotation is usually where the argument is.

## Learned from

- **Standing instruction.** Orthogonal connectors, and the `[i]` marker being for mockups only, both
  carried from the Claude project instructions, now kept as a render.
- **10 Sep 2026.** Andrew flagged that Selling and Work are groupings rather than entities and are
  easy to misread, along with the two deliberate omissions: the pipeline, and the cross-cutting
  records. All three are now rules rather than things to be told each time.
- **10 Sep 2026.** The text extraction failure was hit on the Pros Entities board and worked around
  with screenshots. Recorded so the next session does not lose the same ten minutes.
