# Build brief for Claude Design: S15B end to end

> # SUPERSEDED. Do not run this. 15 September 2026.
>
> **Replaced by `CD-PROMPT-s15-script-walk.md`**, which builds fourteen frames from memo 10.
>
> **This brief builds a story that no longer exists.** It was written against memo 9 and the S15B
> page, both of which describe three trades arriving through the Home App, a change order for rot
> behind the siding, and a final payment taken off system. **S15 was rewritten the same evening**:
> two trades, an inbound phone call, permits on both jobs, no change order, and a final payment by
> credit card.
>
> **Three specific traps if it is run anyway:**
>
> - **The letters collide.** Frames A to L here mean different screens from sections A to N in memo
>   10. Both use letters and neither is wrong on its own.
> - **It names S15B as the scenario**, which was marked superseded three hours after it was created.
> - **It asks for four money states.** There are five, and the fifth is the one the model cannot
>   represent: due and uninvoiced.
>
> **Kept because its five repo-prep items are still the right list** and because the reversal of the
> letter convention is recorded in it.

**Written 15 September 2026. Paste the section headed "The prompt" into CD. Everything above it is
for Andrew.**

---

## Before you run this, do these five things

**1. Regenerate the CD pack and upload that, not a reading list.** The pack at `CD-PACK.md` is
**marked do not upload** and says so at the top. It was generated on 14 September and four things in
it are false. **Regenerating it is the single most important item here**, because last time CD could
not read five of the seven files a brief named, and one file beats seven uploads.

**2. Re-extract the Sol tokens.** What is in `reference/merlin-sol-tokens.css` is the Merlin mirror:
113 semantic tokens and **no radius, spacing or font scale**. That has been flagged since 11
September with "re-extract before the next round", and this is that round. **The brief below asks CD
to match existing styles, and it cannot match a scale it does not have.** If the re-extraction is not
possible today, say so in the prompt rather than letting CD invent values.

**3. Check the S15 page for drift.** It was **rewritten into the v4 model on 14 September** and our
drift register still says 4 September. Two things in that rewrite matter and are in the note below.

**4. Decide whether CD gets the S15B page.** It exists now and it is the script the letters run
against. **Recommend yes**, because the brief cites beats by number.

**5. The memo grew to twelve screens after this brief was first written.** Frames A and B are the
customer record before and after the roofing contact arrives, and the two recommendations on them are
**eleven months old**, made two days after the heat pump job closed. **That changed the worked
example**, so anything generated from it before this evening is out of date.

## What changed in their S15, found while writing the S15B page

**Their script already mints the project at the lead.** Beat 2 reads "Project, a new Project, minted
by the Lead". **That is T-2 and we agree with it.** It had been drifting out of date in our register.

**And their script already has the system suggesting a trade.** Beat 4: "the system points out that
the Thompsons are due for new Windows". **So the recommendation is theirs, not ours.** What is ours
is making it a durable record rather than an interest inside a lead.

**They still use Interest as a live object throughout**, which we retired today. The vocabulary
difference is real, it is recorded against T-1, and the S15B page states it plainly.

**They carry two open items our Opportunity answers.** Reporting must distinguish deferred from lost,
and telling an interest on an existing lead apart from a genuinely new lead when the arrivals are not
in the same thread. **Both are in their own words on their own page**, which is the strongest
argument we have and it should be the one that goes to Joel.

---

## The prompt

**Copy from here.**

---

You are building a canvas of twelve screens for Pros Web, from an existing memo.

## What you are working from

**`memo-9-s15-end-to-end.html` in the repository is the specification.** It carries twelve lettered
sections, each with a mockup, the argument for it, and its open questions. **Build what it shows.**
Where you disagree, say so and wait: the last two rounds produced their best findings from you
disagreeing, and one of them saved a page a brief had told you to delete.

**The scenario is S15B**, not S15. It is a new Confluence page under Scenarios, and it is our variant
with four named differences. **The memo cites its beats by number and so should you.**

**Read, in this order:** the CD pack, then the memo, then `components/ITERATION-2.md`, `ITERATION-3.md`
and `ITERATION-4.md`. The pack carries the team's positions, the state of play, every rule and the
mock data, so you should not need to go looking.

## The three things this round is actually for

**1. Merge the memo's layout with the components you already have.** The memo is drawn in a local
mock kit. **You have real components from the S14 rounds and from the design system.** Rebuild these
twelve screens with those. **Where the memo's layout and your component disagree, the component wins and
you say so.** That is the point of the round.

**2. The Opportunity has never been drawn in a real component.** It appears on six of the twelve
screens and it opens the whole strip: **frames A and B are the same customer record a day apart, and
two of the opportunities on them have been sitting untouched for eleven months.** **If it reads as clutter, or a person cannot tell an
opportunity from a lead at a glance, the object is wrong and not the page**, and that is a finding
worth more than the canvas.

**3. The money is on.** S14 runs this story with money switched off and S15B runs it with money on.
**That comparison decides whether MoneyCard and OffSystemMoneyCard should be one component with a
state or two components**, which is the clearest near-identical sibling in the library. Four money
states appear: no tender chosen, cash part paid, cash read-only at a job, settled.

## Frame labels, and this is a change from last time

**Frames are lettered A to L to match the memo's sections.** This reverses the convention of this
morning, where canvas frames were numbered and memo sections lettered so the two never shared a
symbol. **The reason it is safe here: one memo, one canvas, in lockstep.**

**Every frame label carries four things, in this order:**

1. **The memo name and letter.** "Memo 9 · A". The memo name is there so the letters cannot collide
   when there is a second S15B memo.
2. **The screen's name**, as the memo gives it.
3. **The S15B beats it covers.** "Beats 1 and 2".
4. **Who is on the screen.** "Renata Silva, front desk".

**The memo carries all four on every section**, in a strip under the section heading. Copy them.

**Annotation does not travel.** The memo's `[i]` lines are memo annotation and they stay in the memo.
**A canvas is judged as a design, so annotation on a frame competes with the reviewer's comments.**
Put anything you need to say in the frame label or in your write-back.

## The twelve frames

| | Screen | When | S15B beats | Who |
|---|---|---|---|---|
| **A** | The household on an ordinary Monday | Mon 3 Aug | 1 and 2 | **Nobody.** The record at rest |
| **B** | The same page, ninety seconds later | Tue 4 Aug, 7:12am | 3 | **Nobody.** Robert submits from the Home App |
| **C** | The lead nobody created, tapped from the record | Tue 4 Aug, 8:40am | 4 | Renata Silva, front desk |
| **D** | The intake call, with all three trades on the table | Wed 5 Aug, 2:15pm | 5 | Renata Silva, on the phone to Sara Thompson |
| **E** | The customer record, a returning household | Wed 5 Aug | 1, 5 and 6 | Renata Silva |
| **F** | Start selling, which creates nothing | Mon 10 Aug | 7 | Priya Raman, sales consultant |
| **G** | The kitchen table, and the trade that was held back | Tue 18 Aug | 8, 9 and 10 | Priya Raman with Sara Thompson |
| **H** | The hand-off, and the lead closes | Mon 24 Aug | 13 and 14 | Priya Raman hands to Marcus Ellery |
| **I** | Two jobs, no lead | Fri 11 Sep | 19 to 21 | Marcus Ellery, Hector Salas, Dwight Okafor |
| **J** | Rot behind the siding, and the only amber in the memo | Thu 17 Sep | 24 | Marcus Ellery, Dwight Okafor, Sara by phone |
| **K** | The close | Mon 5 Oct | 27 and 28 | Alicia Moss, Marcus Ellery |
| **L** | The customer record, and the roof that is still waiting | Mon 5 Oct | 28 and 29 | Priya Raman |

**Time order, left to right, one strip.** **A and B are the same page a day apart** and the whole
point is what changed between them without anybody doing anything, so **draw them adjacent and draw
them identically except where they differ.** The customer record then appears twice more, at E and L,
and E to L is nine weeks.

**C is reached by tapping the lead on B.** That transition is the one Andrew asked for and it is the
only place in the strip where one frame leads directly to the next by a click.

## What is new since you last worked

**The demand model was rebuilt on 15 September.** Four things, and all of them change screens.

- **The Opportunity is the durable demand object.** One record per customer, per property, per trade,
  with origin as an attribute, outliving every lead and every project. Statuses: Open, On a lead,
  Won, Dismissed. **A declined trade returns to Open** with a revive date and its history.
- **The Interest is retired.** An opportunity is on a lead or it is not. **Do not use the word.**
- **Qualification is automatic** where a contact names a trade and a property, so the lead and the
  project exist from the first contact and nobody creates them.
- **A lead is one selling episode and closes at the hand-off.** Five of these twelve frames are after
  that, so the project runs with no lead behind it and the only route back is a provenance row.

**And four smaller ones from the reviews:** the opportunities card splits into a lone card headed
**On this lead** above a pair headed **Other opportunities at this property**, which is deliberately
not "worth raising" because on that screen nothing has been marked yet; the capture screen uses
**collapsible sections**, which is a declared exception to the accordion rule with two conditions
attached; **a light grey pencil** sits beside every customer, lead, project and job title; and the
job cards carry **where it is, what is next, what it is waiting on**.

## The rules that will bite

**Read `standards/INDEX.md` and then `mockup-density.md` and `ui-composition.md` in full.** The three
that catch people on this memo:

- **One coloured region on one screen out of twelve.** Frame J is the only thing in this telling that
  anybody has to act on. **Do not colour the rest.**
- **Two cards abreast is unconditional**, and a group may contain one card which keeps its heading and
  takes the full width. Frame C uses both in one group.
- **No reference codes.** No job numbers, no invoice numbers, no proposal numbers.

## What to tell us afterwards

**A write-back block**, since you cannot write to the repository. Four things:

1. **Every component you used, and whether it needed changing.** This is the whole point of the
   round: nine components carried both scenarios unchanged last time and we want to know if that
   holds in real components rather than in a mock kit.
2. **Anything you had to invent**, with what it is and why nothing existing fitted.
3. **Where the memo's layout and your component disagreed**, and which you took.
4. **Your answer on the money**: one component with a state, or two. **You are better placed to
   answer that than the memo is**, because you have both scenarios in real components.

**Do not build the library while you build the canvas.** Leave the trail and we will record it.

---

**Copy to here.**

---

## Learned from

- **15 Sep 2026.** The letter convention reversed within a day of being settled. **Recorded as a
  reversal in the decision log naming the row it supersedes**, and made safe by putting the memo name
  in the frame label, so the collision the original rule prevented cannot return.
- **15 Sep 2026.** Writing the S15B page meant reading their S15 for the first time since 13
  September, **and it had been rewritten into v4 the day before**. Two of our positions turned out to
  be theirs already. **A drift check is cheap and this one was overdue.**
