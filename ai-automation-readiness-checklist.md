# AI Automation Readiness Checklist

Before spending money on "AI automation" for a business process, work through
this. It separates processes that are genuinely ready from ones that will burn
budget and produce a fragile demo.

## 1. Is the process actually repeatable?

- [ ] It happens regularly (weekly or more often) with low variation
- [ ] The inputs are consistent and machine-readable (structured data, forms, files)
- [ ] There is a clear, correct output a person could check
- [ ] A written step-by-step already exists (or someone can write it in 30 minutes)

If the process is ad-hoc, judgment-heavy, or changes constantly, automation is
premature.

## 2. Is there a measurable win?

- [ ] It consumes real staff time every week (hours, not minutes)
- [ ] It is error-prone today, and errors have a real cost
- [ ] The volume justifies the build and maintenance cost
- [ ] You can name the metric that would prove it worked (time saved, errors cut)

A process done once a month for 20 minutes is usually not worth automating.

## 3. Is the data clean enough?

- [ ] The inputs live somewhere structured (a database, spreadsheet, or API)
- [ ] There are no "hidden" steps that only one person knows
- [ ] Edge cases are known and enumerable

"AI will figure it out" is not a data strategy. Garbage in, garbage out still
applies.

## 4. Is there a human in the loop where it matters?

- [ ] A person reviews sensitive or high-stakes outputs before they go out
- [ ] There is a rollback/undo path
- [ ] Errors fail visibly, not silently

Automation should make the human faster, not remove accountability.

## 5. Is the cost honest?

- [ ] You have priced the tooling (API costs, hosting, maintenance) — not just the demo
- [ ] You know who will maintain it after launch
- [ ] You have compared it to "just do it manually" over the next 12 months

## Verdict

- **4+ checks in every section** — strong candidate for automation; scope a small pilot.
- **2–3 checks in most sections** — a partial win is possible; fix the data/process first.
- **Mostly unchecked** — skip AI; tidy the process and data first.

## A good first automation

Pick the single most repetitive, well-understood task (document intake, email
triage, report generation, data cleanup) and automate that one well — not five
things half-finished.

[Linux Stewards](https://www.linuxstewards.com/services/business-automation)
helps small businesses scope and build the right automation, or tells you
honestly when it isn't worth doing.
