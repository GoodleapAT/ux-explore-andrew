# Prompt for the next session

> **This prompt has been used. 15 September 2026.** It is kept as the record of what the session was
> asked to do. **Two things in it are now out of date:** demand has **five** status grains, not four,
> and **the multi-trade inquiry is no longer taken twice on day one**, because siding and windows
> became opportunities rather than customer contacts. The multi-trade conversation happens on the
> intake call instead. **Do not use this prompt to start another session**; write a fresh one.

**Paste this into a new chat. 15 September 2026.**

---

Continuing the Upgrade to Pros UX work. I am Andrew Thompson, UX and Product Design at GoodLeap.

## Start by reading

1. The read-me-first file at the top of the enclosing folder, then `ux-explore-andrew/START-HERE.md`,
   then `CHANGELOG.md`. **Tell me the date of the newest changelog entry.**
2. `upgrade-to-pros/OPEN-ITEMS.md`. **New, 15 September.** One index of everything unresolved. Read it
   before you ask me anything, because most of what you would ask is already in it.
3. `upgrade-to-pros/TEAM-POSITIONS.md`. **The team's positions are cited by row, never restated.**
   They moved five times in one day and that file exists so a change costs one row rather than seven
   documents.
4. `upgrade-to-pros/OVERVIEW.md`, then `DECISIONS.md` including both reset sections and the note on
   why the no-indenting rule fell.
5. `standards/INDEX.md`, then `mockup-density.md` and `ui-composition.md` in full before building
   anything.
6. Both worked examples: `WORKED-EXAMPLE.md` for S15, the Thompsons, and `WORKED-EXAMPLE-S14.md` for
   S14, the Brenners.

**One warning that will cost you time if you skip it.** There is a stale copy of this working memory
in the enclosing folder, older, with no changelog and no glossary. If the folder you open has no
`CHANGELOG.md` at its root, you are in the wrong one.

## What I am uploading

- **The latest S14 canvas from Claude Design, with my new comments on it.** Note that **CD numbers its
  frames and the memos letter their sections**, deliberately, so the two never share a symbol. My
  comments cite frame numbers. The mapping is in the frame labels and in
  `upgrade-to-pros/CD-PROMPT-s14-round-two.md`.
- **The latest S15 mocks.** These were built against the team's DRAFT v3 model, with my own changes
  layered on top. **They predate DRAFT v4 and they predate everything settled on 14 September.**

## What I want to do

**Another iteration of S15, against DRAFT v4 rather than v3.**

**And the actual point is not the screens.** It is whether the components, including the page
templates, can carry both scenarios and the ones after them while still looking like one product.
S14 is a single-trade HVAC replacement with the money switched off. S15 is three trades on one
house, two sold and one deferred, with the money on. **If the same library cannot do both without
proliferating near-identical siblings, that is the finding.**

## Read these before you propose anything

**This is the first real test of global principle G-1**, in the root decision log: a library complete
enough that logic reacting to the entity model and the scenario can compose a scenario's screens
rather than each being drawn by hand. **It is a belief and nothing may be justified by it until a
scenario has actually been composed.** Two scenarios from one library is the nearest thing to
evidence we will get.

**Twenty three component records exist**, in `upgrade-to-pros/components/ITERATION-2.md` and
`ITERATION-3.md`, each with seven fields. **The seventh is what variation the component absorbs and
what would mean a new component instead**, and it has already stopped two components from being born
that should not have been. Use it: before you draw a variant, check whether an existing record
already absorbs it.

**Four things S14 could not test**, listed as O-13 to O-16 in the open items. All four are things S15
exercises: four status grains colliding, the container nesting with two jobs under it, the Start
selling act being separate from qualification, and a genuinely multi-trade inquiry. **S15 is where
these get answered, which is most of why it is next.**

## How to work with me

- **Ask before building or rebuilding any artefact. Every time, no exceptions.**
- No em dashes anywhere.
- Short replies. Answer the question, then stop. Lead with the decision I have to make and the
  trade-off, not the background.
- Plain language in conversation. No file paths, code or identifiers in a reply unless I ask. Put
  that detail in the documents you write instead.
- Verify carefully, then tell me what you found rather than showing me the evidence.
- Connectors in any diagram are orthogonal. Right angles, never curves.
- **When UI work comes up, the design memo format is the default.** Offer it, then wait, and settle
  scope with questions first: which screens, what fidelity, what is real rather than placeholder.
- **Prompt me the moment something needs writing**, not at the end. Say what needs writing, which
  file, and whether you can write it yourself.
- Writing a changelog row is not the same as telling me. Say it in the reply too.
- **Tell me when I am wrong.** Yesterday you caught a silent reversal of one of my own instructions
  and two errors in a brief, and that was worth more than the drawing.

## Two things I learned yesterday that you should not relearn

**A memo tight enough to be only rendered produces nothing.** The most useful findings from the last
two rounds came from the design surface disagreeing: a page a brief told it to delete was the only one
answering the memo's own open question, and a strip ran backwards in time. **Specify what and why, not
what it looks like.**

**An external position is recorded once and pointed at, never restated.** If you find yourself editing
a document because somebody else changed their mind, that document had restated something it should
have cited.

## The structure has a name

**The Product Thinking System.** Working memory, standards, registers, decision logs and the protocol
that ties them together.
