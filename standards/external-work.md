# Other people's work

**Scope:** any effort by someone else that touches the same territory. Another person's model, a
team's prototypes, a generated walkthrough, a skill somebody added to a shared repository, a board
section Andrew did not author.

**Surfaces:** all.

**How hard to hold this.** Every rule in this file is **Always**. This is the one standard with no soft edges, because the failure mode is silent. Markers mean: **Always**, breaking it is a defect and you say so first. **Default**, do it unless you have a reason and say the reason. **Prefer**, a leaning.

---

## The rules

- **Record it as reference, never as input.** It goes in a sources file, as a thing that exists and
  what it is good for. It does not go in a decision log, a vocabulary, a standard, or a brief as
  though it applied here.
- **Say whose it is, every time.** Not "the nav contract" but "the nav contract Joel's factory builds
  to". Ownership is part of the fact, and dropping it is how somebody else's position quietly becomes
  a constraint.
- **Nothing crosses over until Andrew says so.** Borrowing is an explicit act. When he does borrow
  something, it becomes a decision with a date, and from that point it is ours and gets cited as
  ours.
- **Do not manufacture urgency from it.** That another effort is moving is not a reason for Andrew to
  respond to it. "They are already building against X" is an observation, not a deadline, and
  presenting it as one makes somebody else's timetable his.
- **Do not soften our positions to fit theirs.** If their work assumes something our model rejects,
  say both plainly and leave the disagreement standing. A brief that hedges our own model to avoid a
  clash with an unadopted external one is worse than no brief.
- **Separate the mechanism from the content.** Usually the borrowable part is a technique rather than
  a conclusion: how a map stays in step with its data, how a gap is named rather than improvised.
  Those travel. The model underneath them usually does not.
- **A brief that mentions external work must say it is not binding.** Any surface reading about it
  will otherwise treat it as a requirement, because that is what everything else in a brief is.
- **An external position is recorded in exactly one file, with a date, and pointed at. Never
  restated.** Cite the row. Do not paraphrase it into a decision log, a memo, an overview or a brief,
  even accurately. **A restated external position is a copy, and copies go stale**, which is the same
  rule this repository already applies to renders. For Upgrade to Pros that file is
  `upgrade-to-pros/TEAM-POSITIONS.md`.
- **When an external position changes, change the row, not the documents.** If a document has to be
  edited because somebody else changed their mind, the position was restated somewhere it should not
  have been. That is the signal, and the fix is to replace the restatement with a pointer.
- **The test for what belongs in that file: could they change it without asking Andrew?** If yes it is
  theirs, and nothing of ours states it. If no it is ours, and it goes in a decision log.


## Before you recommend anything about it

**Added 15 Sep 2026, and all Always, because the failure repeated three times.**

- **Check the decision log before citing external work in a recommendation.** If it has already been
  ruled on, cite the row and stop. Do not re-argue a settled question because you found the artefact
  yourself and it looked impressive. **The review-queue standard already requires checking an incoming
  comment against the log; this is the same check applied to advice you are about to volunteer.**
- **A name collision is not evidence.** If Andrew describes wanting to build something and you find an
  existing thing with the same name, those are two things. **The name is not a reason to treat his
  idea as already solved**, and it is not a reason to make the external one the baseline. Say the
  collision exists, in one line, and carry on answering the question he asked.
- **Never recommend that Andrew position his work as an input to somebody else's system.** Describing
  how their thing consumes ours is a finding. Recommending that arrangement is adoption by another
  route, and it is the most expensive form of the assimilation this standard exists to prevent.
- **A declined framework is not a default.** When something has been declined, the absence of a
  finished alternative is not a reason to fall back on it. It is the reason the alternative is being
  built.

## Somebody else's work can now execute, not just be read

**Added 21 Sep 2026, and it is the most dangerous form this has taken yet.**

- **Never invoke one of Joel's skills. Andrew's instruction, 21 September 2026, and it stands until
  he says otherwise, in this session or any other.** Five of them are **live and invokable in any
  Claude Code session opened in the enclosing folder**, because the team repository sits beside this
  one and Claude Code loads the skills it finds there. They are `ux-factory`, `script-to-model`,
  `scenario-builder`, `scenario-digest` and `board-snapshot`, all authored by Joel Feyereisen.
- **A listed skill is not permission to run it.** Everything in this standard was written for
  documents that could only be read. A skill reads the team's board and Confluence, writes their
  files and commits. **Running one would make our work an input to their system in a single call**,
  which the rule above forbids as a recommendation and which this makes possible by accident.
- **Say it is there once, name whose it is, then leave it.** Its existence is worth a line the first
  time it becomes relevant, because the name collides with the factory Andrew is building. It is not
  worth a second line and it is not a fallback.

## Why

The failure is not that external work is bad. It is that describing it accurately and describing it
as applicable look almost identical in writing, and a reader cannot tell the difference. One extra
clause fixes it, and without that clause the default is assimilation: another group's assumptions
arrive as facts, and by the time anyone notices, they are being designed to.

## Learned from

- **14 Sep 2026.** The team changed when a project is created **twice in one afternoon**, and the
  position had been restated in seven of our documents, so each change cost a full sweep. The mint
  point held four positions in one day and finished close to where Andrew started. **The cost was not
  the changes, it was the copies.** Hence the one-file rule above, and the file it names.
- **11 Sep 2026.** A team skill and a board UX section were written up in a way that implied they
  constrained Andrew's work. The brief told a design surface not to harden a navigation model against
  a contract Andrew has never adopted, and the summary described an external effort's pace as a reason
  to act. Andrew's correction: this is not an effort he is involved in, he may want to borrow elements,
  and it should not inform his work unless he says so.
- **15 Sep 2026.** **The third instance of the same correction, and the second about the same
  artefact.** Asked how to build a factory of his own out of the last several weeks of thinking, C
  found an external folder with that name, made it the baseline, told Andrew the idea already existed
  and belonged to someone else, and recommended he become its supplier. **The decision declining it
  was already in the log, dated the day before.** Andrew: he did not want to adopt it, and he did want
  to eventually build a factory of his own based on this thinking. The rules above are what was
  missing: not a rule against assimilation, which existed, but a rule requiring the log to be read
  before advice is given, and a rule saying a shared name proves nothing.
- **21 Sep 2026.** **Andrew, on finding that Joel's UX factory is invokable rather than merely
  readable in a Claude Code session:** do not use it unless he says so explicitly. Recorded as a
  standing instruction rather than a session preference, because the skills reappear in every session
  opened in that folder and the previous three instances of this correction were all about the same
  artefact.
