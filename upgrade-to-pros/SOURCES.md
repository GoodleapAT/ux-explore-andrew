# Sources, Upgrade to Pros

**Specific to this project. Design system, product repositories, people and tooling quirks are in the
global sources file at the root.**

> **Who may write to this file:** any surface that can write. One row per source. Update the
> **Checked** date when you use one. When something turns out to be unreachable or out of date,
> change its note rather than deleting the row.

---

## Team record

| Source | Kind | Where | Access | Good for | Checked |
|---|---|---|---|---|---|
| **u2p-project-planning** | Repository, `loanpal-engineering` | Cloned in the enclosing folder | Local, read and edit. **Cannot commit or push.** Contributions go as a branch and a pull request for Joel | The durable team record: entity model, scenario walkthroughs, a 26-scenario pressure-test campaign, open items, a decision log and meeting notes. Also a glossary and an onboarding document | 11 Sep 2026 |
| **Scenario beat scripts** | Confluence, ProsOperations space, page "Scenarios" | Atlassian | Connector | Seventeen scripts, S1 to S17, each naming the entities lit at every beat. S15 and S16 are the multi-trade cases, S8 and S17 the membership cases, S12 the declined-financing case | 10 Sep 2026 |

**Vocabulary warning.** Only **S16 and S17** have been rewritten into the current vocabulary, where
the spine is the Project and the Job is the work entity. **S4, S5, S13, S14, S14B and S15** still call
the spine a Job and the work a Workstream. Joel deferred a coordinated rename on 5 September. Read a
page's header before trusting its nouns.

**Andrew's position in that repository.** Nothing he has authored is in it. The Thompson scenario was
adopted as S15 on 1 September and he is cited in its provenance file.

---

## Boards

The boards are the source of truth. Any local copy is a copy, and when they disagree the board wins
and the local file gets updated.

| Source | Kind | Where | Good for | Checked |
|---|---|---|---|---|
| **Pros Entities** | FigJam, the team's collaboration surface | File `pNgQNZTXaNC8CFK2yFTItu` | **DRAFT v3**, the current team model, at node `498:4910`. DRAFT v2 at `45:282`. **Andrew's Model v3** at `498:5293` | 10 Sep 2026 |
| **Upgrade to Pros** | FigJam, Andrew's | File `6MefcsO9RsEcIQzjCPBiiX` | Page "Object mapping, Model C" at `461:5406`. Model C v1, the project management diagram, the Thompson scenario told without the model, and the Model C v3 structure diagram. Daidipya's Base Entity Map at `591:2905` and his glossary at `642:4228` | 10 Sep 2026 |

**How to read them.** The Figma text extraction tool fails on large board nodes. Use a rendered
screenshot at high resolution instead, because the small annotation is usually where the argument is.

---

## The other models

| Whose | Where it is | Shape |
|---|---|---|
| **Andrew, Model C** | This folder, plus both boards | Project mandatory and existing before pricing. Lead per trade, surviving decline. Money at the container |
| **Team, DRAFT v3** | Pros Entities board | Project is the spine and models one customer journey. Job executes one committed scope component. Service Plan sits beside Project |
| **Daidipya, Base Entity Map** | Upgrade to Pros board, plus a glossary | No spine; the Lead is the deal. A sub-Job is the schedulable unit |
| **Joel, Full entity map** | Pros Entities board, DRAFT v2 | Project existed but was optional and grouped Jobs after the sale. Carried the service flywheel |

A full even-handed comparison of the first three is in the entity modelling thread. **It predates
DRAFT v3** and should be read as background rather than as current.

---

## Configuration reference

| Source | What it is |
|---|---|
| **Project management configuration** | Three boards, ten stages, five sub-statuses, five gates, with minimal and maximal examples. In the entity modelling thread. Written before Model C, and the stage and gate values in every mockup come from it. Note there are duplicate copies in the modelling thread and the design handoff folder |
