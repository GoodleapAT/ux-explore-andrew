# What a site assessment is

**Opened 14 September 2026. Status: open, and genuinely open.**

> **The question:** is a site assessment an object, a type of another object, or an experience?
>
> Promoted out of comparison row D-12, where Andrew ruled it undecided and said it needed its own
> thread rather than a classification. **Nothing here is settled.** This document exists so the
> question stops being re-asked from scratch.

**Andrew, 14 Sep 2026, in full**, because the whole shape of the problem is in it:

> We still do not have a solid idea of what a site assessment is. We know that when a tech is visiting
> a site they will assess certain parts of the property, especially whatever parts relate to their
> trades. We also know a lot of assessment detail will be taken by others dealing with a customer:
> CSR, sales, the installing team. So a site assessment may be a discrete object at the end of the day,
> or maybe a type of another object. It may also be an experience, geared towards the trade, that
> guides the tech or salesperson on what needs to be captured, and what needs capturing will likely be
> a preset or template from us, refined by the organisation over time. We also need to figure out how
> all these site details and notes are referenced to and by the property.

---

## What is actually known

- **Several different people capture site detail**, at different moments and for different reasons. A
  CSR during validation, a salesperson in the home, a tech on a visit, the installing crew on the day.
- **What gets captured depends on the trade.** A roofer and an HVAC tech assess different things about
  the same house.
- **The template is ours to seed and theirs to refine.** Whatever it turns out to be, the starting
  content comes from us and the organisation changes it over time.
- **DRAFT v3 has it as an entity**, with an edge reading `Site Assessment informs scope on the
  Proposal`. Our model deliberately left it out, as one of the things attaching to several objects at
  once.

## The three readings, and what each would cost

| Reading | What it means | What it costs |
|---|---|---|
| **A discrete object** | One record per assessment, with an author, a date, a trade and its findings. What DRAFT v3 has | Clean to model and to show. But it invites one assessment per visit, and then nobody knows which is current, or whether the salesperson's notes and the tech's notes are the same kind of thing |
| **A type of another object** | Not its own entity. A kind of note, or a kind of visit outcome, or a form instance | Cheapest, and it fits the fact that several roles capture the same sort of thing. But "informs scope" is then an edge from something generic, which loses the reason anybody cares about it |
| **An experience** | Not an entity at all. A guided capture flow, per trade, that writes its findings onto whatever object is appropriate | Matches what Andrew described most closely, and explains the template. But an experience with no object behind it has nowhere to store a partially finished assessment, and no way to show one later |

**These are not exclusive.** The likeliest answer is an experience that produces something, and the
open question is what that something is.

## The question underneath, which may be the real one

**How does site detail reference the property?** Registered separately as a blocking object, because it
is not the same question and it does not go away under any of the three readings. Notes,
measurements, photos and findings accumulate about an address across years, several projects and
several trades. Neither model says how any of that is reachable from the property.

If the answer to that is good, the assessment question may become easy. If it is not, none of the three
readings above will work.

## What would settle this

Not a modelling argument. **Watching who captures what, when.** The three readings differ mainly in
where the findings live, and that is decidable by looking at a real capture moment in a scenario rather
than by reasoning about entities.

**Nothing in this document is a decision.** When something here settles, it goes to the project
decision log and this document keeps the reasoning.
