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

## Type in a drawing

**Always: no monospace and no all caps in a diagram's labels.** The full rule and the reasoning are
in `ui-copy.md`, which stopped being about product UI only on 22 Sep 2026. **Diagrams were the worst
offender**, because caps and a monospace face read as precision and so attach themselves to axis
titles, legends and provenance notes. Sentence case in the display face, with weight and colour doing
the separating.

## Carrying a visual forward

**A visual made to diagnose a problem and a visual made to explain what you built are different
artifacts, and they look identical.** Added 22 Sep 2026.

- **Always: say what a drawing was made to do before reusing it.** Diagnosis and explanation are
  different jobs. A drawing that was made to work out why something kept going wrong carries the
  problem's framing inside it, **and the framing is invisible because the picture still looks
  correct.**
- **Always: when a drawing is carried into a document with a different audience, count the ink.**
  Anything given real space that is not part of the thing being explained is a candidate for a
  sentence instead. **A third of a drawing spent on something outside the subject is the tell.**
- **Default: the test for a mark is whether it would still be drawn if the problem had never
  happened.** A mark that exists to answer a worry belongs in the diagnosis and usually belongs in
  prose afterwards, not in the explanatory version.
- **Default: a boundary stated as a rule in text does not need a drawing arguing it in the
  negative.** Negative space, blocked arrows and does-not-reach markers are diagnostic moves. One
  positive sentence is stronger and it survives being quoted.
- **Prefer: spend the space you recover on the question the new audience actually has.** For anybody
  joining, that is usually who contributes what, not what went wrong before they arrived.

**Why this is a rule rather than a judgement call.** Prose gets rewritten when the argument moves on,
because a stale sentence reads as wrong. **A stale drawing reads as authoritative**, so it survives
rewrites that should have taken it out, and it keeps teaching the old framing to every new reader.

## Learned from

- **Standing instruction.** Orthogonal connectors, and the `[i]` marker being for mockups only, both
  carried from the Claude project instructions, now kept as a render.
- **10 Sep 2026.** Andrew flagged that Selling and Work are groupings rather than entities and are
  easy to misread, along with the two deliberate omissions: the pipeline, and the cross-cutting
  records. All three are now rules rather than things to be told each time.
- **10 Sep 2026.** The text extraction failure was hit on the Pros Entities board and worked around
  with screenshots. Recorded so the next session does not lose the same ten minutes.
- **22 Sep 2026.** **Andrew, on the composition drawing carried over from the design method render:**
  he asked whether it was overly focused on the entity model, because the material around it was made
  while he was working out why concept screens kept being invalidated by a moving model. **It was.**
  Three of its marks, roughly a third of its ink, were spent on the entity model, which is not part of
  the UX Kit at all, and the claim they made was defensive: they answered *will the model wreck my
  screens again* rather than *how does a surface get built*. **The boundary itself is load bearing and
  is kept as one positive sentence**, the rule that an object name may never appear in a core
  component. **The recovered space went to who contributes at each layer**, which is what the audience
  it is now being drawn for actually asks. The question was his; the rule is written from it.
