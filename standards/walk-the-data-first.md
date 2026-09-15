# Walk the data before drawing the screens

**Scope:** the step before a round of mockups, memos or prototypes begins.

**Surfaces:** all.

---

## How hard to hold each rule

| Marker | Meaning |
|---|---|
| **Always** | Breaking it is a defect. If you must break it, say so before you do, not after |
| **Default** | Do this unless you have a reason. Having a reason is fine; not saying it is not |
| **Prefer** | A leaning. Use judgement and move on |

---

## The rules

### Always

- **Walk the scenario's own data before drawing anything from it**, in date order, and ask of every
  record: **does this have somewhere to live at the moment it appears?** Not later, when the thing
  that holds it exists. At the moment it appears.
- **When a record has nowhere to live, that is a model defect and it is reported as one.** Not worked
  around locally, not given a plausible parent, and not left for the screen to imply.

### Default

- **Check the narrative against the nouns.** A mock data file reads as a story, and a story tolerates
  a record appearing from nowhere because a reader supplies the missing context without noticing. A
  screen cannot. The same sentence that reads fine in a narrative is unbuildable.
- **Read the dates as gaps, not just as events.** A three-week interval with no beat in it is either
  a period where nothing happens, which is worth knowing, or a period where something happens that
  nobody has written down, which is usually the more interesting answer.
- **Ask where a fact came from, for every fact a screen shows.** Where evidence turns out to predate
  the record it supports, the record probably hangs off something other than what it appears to.

### Prefer

- Do this as a conversation rather than a document. It is quick, and the useful version of it is
  somebody saying "wait, where is that sitting?"

---

## Why

**A mock data file can carry a homeless record for days without anybody noticing**, and every artefact
built from it inherits the fault. The failure mode is not that the data is wrong; it is that the data
is narratively coherent and structurally impossible, and narrative coherence is what a reviewer
checks.

**The cost is asymmetric.** Walking the data takes minutes. Finding the same defect from a drawn
screen takes a round, and finding it from a built one takes longer than that.

**And it is often where the finding is.** A record with nowhere to live means the model is missing
something, and what it is missing is usually more interesting than the screen that exposed it.

## Worked example

The canonical scenario had a system-suggested trade recorded as an **interest** on 21 July. An
interest is defined as living inside a lead. The lead was created on 12 August.

**The data file admitted it in passing**, saying the interest "rides along until there is a lead to
attach it to". That sentence reads perfectly well and describes nothing.

**Twenty two days of homelessness**, and it had been in the file for four days across two restatements
of the same section, both of which read it and neither of which caught it.

**What walking it produced** was not a fix to the data but a new object, and a finding bigger than the
defect: three separate facts had been sharing one record, and no screen could have distinguished them.

**Then the defect dissolved, four hours later, and this is the part worth keeping.** An unrelated
ruling moved qualification earlier, so the lead now exists from the first day and nothing is homeless.
**The object survived on the other finding**, the one about three facts sharing a record, which the
ruling did not touch.

**So the thing walking the data found was not the thing it looked like it found.** The homelessness was
the symptom that made somebody look; the collapsed record was the defect. **Expect that, and do not
retire a finding because the symptom that exposed it goes away.**

## Learned from

- **15 Sep 2026.** Andrew asked whether the arrival story needed changing before any screens were
  drawn. **The question was about the narrative and the answer was a model defect**, which had
  survived two careful restatements of the same section because both were checking the nouns against
  the model rather than the records against the clock.
