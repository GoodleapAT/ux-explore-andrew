# Every rule, on one screen

**Read this when you cannot remember which rule applies or how hard to hold it.** The individual
standards carry the reasoning and the worked examples; this is the whole set at a glance.

| Marker | Meaning | What to do if you break it |
|---|---|---|
| **Always** | Breaking it is a defect | Say so **before** you do it, not after |
| **Default** | Do it unless you have a reason | Do the other thing, and say the reason |
| **Prefer** | A leaning | Nothing. Use judgement |

**If two rules collide, say so and pick one.** It has happened once already and the fix was a new
rule, not a silent choice. A collision you resolve quietly is a collision nobody else can learn from.

---

## Building a screen

*From `mockup-density.md` and `ui-composition.md`.*

| | Rule |
|---|---|
| **Always** | No reference codes or record identifiers. Call the thing by its name |
| **Always** | No explanatory copy inside a screen. Suggested messages go in a list underneath |
| **Always** | Placeholder what the current question does not touch, and label it |
| **Always** | Bundle content into cards, in pairs, under a group heading. Not full-width blocks down a column |
| **Always** | A group may contain one card, and it keeps its heading. A lone card takes the full width |
| **Default** | Status in the second line of the right-hand column, in secondary text |
| **Default** | Provenance and history read as prose in the sub line |
| **Default** | Colour only where somebody has to act. At most one coloured region per screen |
| **Default** | A gap the model cannot answer is left out, not drawn as unavailable |
| **Default** | Badges only where they carry a state the row cannot say in words. New, blocked, deferred, yes. Won, paid, active, no. Three or four a page, not twelve |
| **Default** | Two cards abreast is unconditional. Cards shrink rather than stacking |
| **Default** | Pair cards that answer the same kind of question |
| **Default** | Segmented control in the card header to collapse several lists into one card |
| **Default** | Detail that does not fit goes sideways into a sheet, not down into an accordion. **One declared exception**: capture during a live call, where collapsible sections win, with counts on the headers and one section open |
| **Default** | Small peer lists become links in the page header, not sections |
| **Default** | Facts about the thing go in a card, not in a subtitle |
| **Default** | Parked content goes in one full-width list at the bottom, each item labelled not drawn |
| **Prefer** | An icon may pair with text where it earns its place. Not one per row |
| **Prefer** | Group headings get no rule above them |

**When a state cannot use colour and cannot use a badge**, reach in this order and stop when one
works: the status word, weight, a leading glyph, position, a badge, colour. **Do not invent a
seventh.** If none works, the screen carries too many states.

## Components

*From `component-library.md`.*

| | Rule |
|---|---|
| **Always** | Record a component the moment you create or adapt it. Never later |
| **Always** | Seven fields: name, level, states, when to use, when not to, what it does when its subject is absent, what variation it absorbs |
| **Always** | Page templates are components too |
| **Default** | Declare a position for each product tier where the subject may not exist: absent, empty and self-advertising, or replaced |
| **Default** | One component with declared states, not three near-identical siblings |
| **Default** | The library is repository-resident. CD designs components, it does not keep them |
| **Default** | A template declares, per lifecycle stage, which groups are prominent, collapsed, or absent |
| **Prefer** | Do not stop designing to build the library. Leave the trail |

**The absence boundary:** a capability that will exist **advertises**; a gap the model cannot answer
is **left out**. The test is whether somebody could make it appear by doing something.

**Why the library is held this tightly:** global principle G-1, in the root decision log. The aim is a
library complete enough to compose a scenario's screens rather than each being drawn by hand. It is a
belief, not a demonstration, and **nothing may be justified on the grounds that it requires this**
until a scenario has actually been composed.

## Before a round starts

*From `walk-the-data-first.md`.*

| | Rule |
|---|---|
| **Always** | Walk the scenario's data in date order before drawing. Ask of every record: does this have somewhere to live at the moment it appears? |
| **Always** | A record with nowhere to live is a model defect and is reported as one, not given a plausible parent |
| **Default** | Check the narrative against the nouns. A story tolerates a record appearing from nowhere; a screen cannot |
| **Default** | Read the dates as gaps, not just as events |
| **Default** | Ask where every fact came from. Evidence predating its record means the record hangs off something else |

## After a ruling

*From `after-a-ruling.md`.*

| | Rule |
|---|---|
| **Always** | Separate the principle from the mechanism, and attribute each. A test that implements a ruling is somebody's reading |
| **Always** | Sweep for what the ruling breaks, in the same session |
| **Always** | Sweep for what it creates. One answer usually opens two questions |
| **Always** | Check that a superseded decision was superseded in writing, by name |
| **Default** | Name the second-order consequence in the reply, not only in the document |
| **Default** | Check whether the ruling dissolved the problem that prompted it. If so, find the other reason or withdraw the thing |
| **Default** | Re-read the other scenario. Nobody is looking at it |

## Working a review queue

*From `review-queue.md`.*

| | Rule |
|---|---|
| **Always** | Record the comment text verbatim before doing anything with it, typos included |
| **Always** | Check every comment against the decision log before acting on it |
| **Always** | Say when a comment is overtaken, name what overtook it, and do not act on it |
| **Always** | Say when a comment reverses a settled decision. Route it as a ruling, not a task |
| **Default** | Sort the queue into structural, visual, and cannot be acted on, before answering any of it |
| **Default** | Report the shape of the queue. Which comments are the same argument arriving twice |
| **Default** | Correct the count wherever it is recorded |
| **Prefer** | Group by the region a comment is about, not the frame it landed on. The cluster is the finding |

**A memo cannot carry a visual comment** and a build brief cannot carry a structural one. Half a
queue being visual is normal and means the structure is close enough to argue about details.

## Memos

*From `design-memo-format.md`.*

| | Rule |
|---|---|
| **Always** | Ask before building or rebuilding one |
| **Always** | The argument carries the thinking. Prose does not migrate into the mockup |
| **Always** | Editorial, not interactive, unless asked |
| **Always** | `[i]` marks annotation inside a mockup, and only inside a mockup |
| **Always** | Annotation belongs to a memo, not to a canvas. A canvas is judged as a design, so annotation competes with the reviewer's comments |
| **Default** | Mockup at full page width, argument in labelled blocks underneath, then numbered questions |
| **Default** | Eyebrow, title, narrow intro, settled card, to-decide card, lettered sections |
| **Default** | Mockups look like believable UI with real labels and values |
| **Default** | Where a layout choice is uncomfortable or costly, say so in the memo |
| **Always** | Ask before adding a closing four-card row or a closing note |

## Diagrams

*From `diagram-conventions.md`.*

| | Rule |
|---|---|
| **Always** | Connectors are orthogonal. Right angles, never curves. Everywhere |
| **Always** | A diagram is annotation throughout, so no `[i]` marker and no convention note |
| **Default** | Label the relationship on the connector, not only the boxes |
| **Default** | Say which boxes are entity claims and which are not |
| **Default** | Leave out what attaches to several objects at once, and say so in the caption |
| **Default** | Do not draw the pipeline as belonging to one level |

## Other people's work

*From `external-work.md`. All Always, because the failure mode is silent.*

| | Rule |
|---|---|
| **Always** | Record it as reference, never as input |
| **Always** | Say whose it is, every time |
| **Always** | Nothing crosses over until Andrew says so |
| **Always** | Do not manufacture urgency from it |
| **Always** | Do not soften our positions to fit theirs |
| **Always** | Separate the mechanism from the content. The technique travels; the model under it usually does not |
| **Always** | A brief that mentions external work says it is not binding |
| **Always** | An external position is recorded in one file with a date and pointed at, never restated. Cite the row |
| **Always** | When their position changes, change the row and not the documents. Having to edit a document means it was restated |

## Talking and writing

*From `working-voice.md`.*

| | Rule |
|---|---|
| **Always** | No em dashes. Anywhere |
| **Always** | Short replies. Answer the question, then stop |
| **Always** | Lead with the decision and the trade-off |
| **Always** | Plain language. No file paths, code or identifiers in a reply unless asked |
| **Always** | Ask before building or rebuilding any artefact. Every time |
| **Always** | Writing a changelog row is not the same as telling Andrew. Say it in the reply too |
| **Default** | Verify carefully, then report what you found rather than the evidence for it |
| **Default** | Markdown for anything durable. Bullets, tables and headings are wanted in documents |

## Repositories

*From `repository-hygiene.md`.*

| | Rule |
|---|---|
| **Always** | Check the write path before doing the work, not after |
| **Always** | Never commit to a repository in the `loanpal-engineering` organisation |
| **Always** | Never amend, rebase, force push, or touch a branch other than the one asked for |
| **Default** | Every repository carries a gitignore from the first commit |
| **Default** | Where a repository lives is a decision for the root decision log |

---

## The protocol, which is not in a standard

*From `START-HERE.md`. Listed here so this really is everything.*

| | Rule |
|---|---|
| **Always** | Read the start-here file and the changelog first, and say the date of the newest entry |
| **Always** | Prompt Andrew the moment something needs writing, not at the end |
| **Always** | Write back before the session ends. Two questions, both |
| **Always** | If you cannot write, produce a paste-able write-back block |
| **Always** | Rules are never changed silently. A replacement records what it replaced |
| **Always** | Append-only files are appended to. Never edited, never reordered |
| **Always** | A new controlled vocabulary goes in `GLOSSARY.md` in the session that invents it. Check there first for a value word that is already taken. **Exception, and the glossary states it itself: the nouns of the business and the domain status sets live in the project's own vocabulary file.** The glossary still records the collision |

---

## If you are still unsure

The order of authority, highest first:

1. **Andrew, in the conversation.** Everything here yields to that.
2. **An Always rule.**
3. **A decision in a decision log.**
4. **A Default rule.**
5. **The worked example**, for anything about data.
6. **A Prefer rule.**
7. **What a previous mock did.**

**Nothing that came from somebody else's effort appears on that list at all.**
