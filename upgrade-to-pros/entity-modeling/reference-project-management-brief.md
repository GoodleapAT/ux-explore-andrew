# Configurable project management for Merlin

**Design brief. August 2026.**

## The problem

Every contractor we have spoken to tracks their projects differently. Some use status fields, some use phases, some use tags, most use some combination held together by tribal knowledge and a whiteboard. There is no one-size-fits-all pipeline we could ship that would fit more than a fraction of them.

This is not a case of contractors being disorganized. The variation is real and it is rational. A storm restoration company running mostly insurance claims genuinely needs different tracking than a retail replacement shop that only takes cash and financed work. A company operating across forty Massachusetts towns needs different permit handling than one working a single jurisdiction. A five-person shop where one person touches a job end to end needs a different view than a forty-crew operation with dedicated claims specialists.

The evidence for this is not only external. In two passes at sketching a roofing pipeline for our own product, we produced two structurally different but equally defensible configurations, disagreeing with ourselves about whether loan and insurance status should be pipeline columns or secondary fields. If that variance exists within one designer's exploration, it will exist many times over across our customer base.

## The approach

Rather than shipping a pipeline, ship the primitives contractors build a pipeline from, and use DeDe to do the building.

Five primitives, each independently configurable:

**Stage** is where a job is. One at a time. It is what the kanban column represents and what everyone looks at to know how a job is progressing.

**Sub-status** tracks an external process the contractor is waiting on and cannot speed up by working harder. Insurance claim adjudication. Permit approval. HOA sign-off. Financing. Material delivery. Sub-statuses run independently of stage, so a job can sit in production for three weeks while its claim moves through five sub-status values on its own timeline.

**Task** is work the contractor's own team has to do, entirely within their control. Call the customer about shingle color. Confirm the dumpster arrived. Take the pre-install photos. Tasks attach to stages and are marked complete, incomplete, not applicable, or skipped.

**Gate** is a condition that holds a job in place until it is met. A gate can be driven by a sub-status value or by task completion. Each gate exists for a specific real-world reason, not as a generic rule.

**Board** is a filtered view over a range of stages, usually aligned to a team. Boards exist to reduce noise: a production manager should not have to look at leads. A job does not move between boards, it simply becomes visible on a different one when its stage crosses into that board's range.

The distinction between sub-status and task is the one that matters most. Both look like secondary tracking on the surface, but one is monitored and the other is assigned. Conflating them produces a system where "waiting on the city" and "someone needs to make a phone call" look identical, which is exactly the confusion contractors already live with.

## Where DeDe earns its place

Competitors let contractors configure pipelines. AccuLynx, JobNimbus, and Roofr all support customizable stages, and Roofr supports multiple parallel workflows. What none of them solve is that configuration is hard, unfamiliar work that has to happen before the contractor gets any value.

DeDe has two roles.

**At setup**, a contractor describes how their business works in their own words, optionally attaching a spreadsheet or connecting an existing tool, and DeDe produces a draft pipeline. Not a form to fill in, a conversation followed by something concrete to react to. The contractor then accepts, edits, or rejects piece by piece. The draft is presented as a narrated walkthrough that builds the structure one layer at a time, so a contractor who has never thought about "pipeline configuration" learns the model as they review it.

**At run time**, DeDe activates the right sub-statuses and tasks for each job based on its attributes, infers from context where attributes have not been set explicitly, and can move jobs forward automatically when triggers fire. Manual override is always available. A contractor can always put a job in a stage themselves and change its state directly.

The most differentiated piece is task generation. Beyond universal tasks and job-type tasks, DeDe compiles tasks from instructions the contractor has accumulated. A contractor works a job in a new town, learns what that town's building department wants, tells DeDe, and the next job in that town arrives with the right document checklist already on it. This is Organization Context becoming operational rather than informational, and it means the system improves through use rather than requiring everything to be encoded up front.

## The pattern that holds it together

Every primitive follows the same model: **preset, recommend, customize.** GoodLeap ships presets. DeDe recommends configurations and new options based on what the contractor describes. The contractor accepts, modifies, or builds their own.

This consistency matters because it means contractors learn one mental model and apply it everywhere, rather than encountering a different configuration pattern for boards than for gates than for tasks.

Underneath, the conditional logic is also one thing rather than several. The same attribute-rule engine decides whether a stage applies to a job, whether a sub-status activates, which set of sub-status values to use, and which tasks load. One concept pointed at four targets, which is simpler to build and simpler for DeDe to explain.

## Eligibility is not gating

Two things look similar and must not be conflated.

**Eligibility** means a stage or sub-status does not apply to this job at all. A repair job below the permit threshold will never need permit approval. A cash job has no insurance claim. The correct treatment is to hide or clearly mark as not applicable.

**Gating** means it does apply, but not yet. The permit has been applied for and is pending. The claim is filed and awaiting an adjuster. The correct treatment is blocked-but-pending, something the contractor is working toward.

A contractor looking at a greyed-out stage needs to know immediately whether to do something about it or ignore it permanently. Getting this wrong produces a board full of indicators people learn to disregard.

## What this looks like in practice

Three illustrative configurations follow. They are deliberately different from each other, and the differences are the argument for the whole approach.

### Dana's Roofing: the middle case

Mid-size company, mixed retail and insurance work, three people touching a job. Three boards matching her team split. Ten stages. Five sub-statuses, two universal and three conditional. Five gates, each tied to something that has burned her: crews showing up before HOA approved a shingle color, jobs starting before a claim came back, invoices going out with an open permit.

This is the configuration used in the design work and detailed in the reference document.

### Sunrise Roofing: the minimal case

Three crews, retail only, no storm work, no insurance. The owner quotes and sells, one person handles everything after.

One board. Five stages: Lead, Quoted, Sold, Scheduled, Done. One universal sub-status, Financing. Permit as a conditional sub-status because half their work is under the local repair threshold. One gate: financing NTP before scheduling, because they got burned once. Two or three tasks per stage, mostly reminders.

Almost nothing in the default preset survives contact with this company, and that is fine. Shipping them Dana's configuration would be actively worse than shipping them nothing.

### Meridian Exteriors: the maximal case

Forty crews across three states, roughly eighty percent insurance restoration, dedicated canvassing, sales, and claims teams.

Five boards, because their disciplines are genuinely separate: Canvass & Leads, Sales, Claims & Compliance, Production, Closeout & AR. Notably they want a dedicated claims board with real stages, which is the structure we sketched and then deleted as unnecessary for Dana. Eight sub-statuses including supplement tracking, mortgage endorsement, and warranty registration. Heavy task checklists, with jurisdiction-generated permit tasks doing real work across dozens of municipalities. Nine gates.

The supplement sub-status is their most-used field and does not appear in Dana's configuration at all.

## What is deferred

**Migration.** How DeDe handles importing jobs already in flight in another system, and reconciling them against a newly defined pipeline. Harder than initial setup and needs its own design.

**Saved views.** Filtering a board by job type or attribute and saving that as a returnable view.

**Role assignment on tasks.** Tasks likely need optional owners. This pulls people and roles into the model and expands scope.

**Automations.** Gates are passive, they block. Automations are active, they cause movement based on triggers: API events, signatures, dates, deliveries. The same trigger often serves both. Trust and confirmation behavior for AI-driven automation needs resolution before this ships.

**Personal Context.** A second tier below Organization Context, likely relevant to task generation.

## Open questions

How opinionated should gates be? A hard gate that cannot be overridden versus a warning that can. Too many hard gates and contractors work around the system; too few and gates stop meaning anything.

Should AI-inferred activation be proposed or automatic? If DeDe reads a note and activates HOA tracking on its own, the contractor needs to understand why and dismiss it cleanly if wrong.

How much does board and stage granularity actually help? Roofr advises eight to ten stages total and pushing detail into checklists. Our default is ten. Worth validating that contractors do not want fewer.
