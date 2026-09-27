# Zava Copilot in Excel — Audience Prompt Guide

Use this guide during the **Copilot in Excel** section of the workshop.

## Before you start

1. Download the **starter workbook** supplied by the facilitator.
2. Save your own copy to **OneDrive** or the workshop SharePoint location.
3. Rename it if useful, for example:

   `YourName_Zava_Copilot_Excel_Lab.xlsx`

4. Open the workbook in Excel with Copilot available.
5. Do **not** use the instructor solution workbook unless the facilitator asks you to.

> **Important**
> - We are all using the same starter workbook so the prompts, sheet names, and expected patterns are consistent.
> - Copilot output can still vary slightly.
> - Review formulas and proposed edits before accepting them.
> - If Copilot cannot complete an edit, keep following the demo and move to the next task rather than spending the session troubleshooting.

---

# Scenario

You are **Corey Gray**, Customer Experience Program Manager at **Zava**.

Zava is preparing and running an enterprise **Team Challenge** pilot. Corey works with customer data, pilot assumptions, member activity, support tickets, platform exports, and monthly KPIs.

The Excel workflow is:

**Validate → Model → Calculate → Reconcile → Explain variance → Exercise**

---

# 1. Data Validation

Open:

`01 Customer Master`

## Goal

Check the customer master before Zava migrates it into a new customer hub.

## Prompt

```text
Validate the data in the `01 Customer Master` sheet before it is migrated to the new customer hub.

Identify:
- potential duplicate customers based on similar names or shared website domains
- naming inconsistencies
- shared administrator emails across unrelated accounts
- country or region conflicts
- missing required values
- status or go-live-date conflicts

Create a new sheet called `Validation Findings` with:
- severity
- issue type
- affected record(s)
- evidence
- recommended action

Do not change or delete any customer records yet.
```

## Follow-up

```text
Summarize the findings for an operations lead.

Tell me:
- which issues should block migration
- which can be corrected safely
- which require a human decision

Keep it to 6 bullets.
```

## What to look for

- Does Copilot show the evidence behind each issue?
- Does it separate a likely error from something that needs human review?
- Did it avoid changing source data without approval?

---

# 2. Data Analysis — Pilot Sensitivity Model

Open:

- `02 Pilot Assumptions`
- `02 Weekly Projection`
- `02 Sensitivity`

## Goal

Understand how different employee **opt-in** and **week-3 retention** rates affect pilot outcomes.

## Prompt

```text
Using `02 Pilot Assumptions` and `02 Weekly Projection`, populate both sensitivity tables in `02 Sensitivity` using formulas linked to the assumptions.

Rows are opt-in rates and columns are week-3 retention rates.

The first table should calculate week-3 active participants.

The second table should calculate week-6 completions using the week-6 continuation rate from the assumptions.

Keep the formulas linked so the tables update if an assumption changes.
```

## Interpret the model

```text
Add a short commentary below the sensitivity tables.

Explain:
1. how opt-in and retention interact
2. which combinations clearly meet or exceed Zava's pilot targets
3. what operating range Zava should aim for if it wants a reasonable buffer above the minimum targets

Reference specific values from the tables.
```

## Stress-test it

```text
Stress-test the recommendation.

Which assumption would have the biggest practical impact if it is wrong?

What additional data would you want before scaling the pilot?
```

## What to look for

- Are the cells formula-driven rather than hard-coded?
- Do the formulas reference the assumptions?
- Does Copilot distinguish a base case from a recommendation?
- Does it explain what could invalidate the recommendation?

---

# 3. Formula Generation

Open:

- `03 Activity Log`
- `03 Support Tickets`

## Goal

Create recurring operational summaries without manually writing every formula.

## Prompt A — activity

```text
Create a new sheet called `Program Summary`.

Build a table for August 2026 and September 2026 showing total sessions for:
- Cardio
- Strength
- Mobility
- Mindfulness

Generate formulas that calculate the totals from `03 Activity Log`.

Do not hard-code the answers.
```

## Prompt B — support

```text
In the same sheet, add a second table showing the number of support tickets by month for:
- Access / Login
- Notifications
- Activity Sync
- Challenge Setup
- Privacy Question

Also calculate average resolution hours for each month.

Use formulas linked to `03 Support Tickets`.
```

## Audit a formula

```text
Pick one formula you created and explain it in plain English.

Tell me:
- what each range is doing
- what each condition is doing
- what could cause the result to be wrong
```

## Optional formula check

```text
Review the formulas you created.

Identify any inconsistent ranges, missing criteria, hard-coded values, or formulas that would break if new rows were added.
```

## What to look for

Typical functions may include:

- `SUMIFS`
- `COUNTIFS`
- `AVERAGEIFS`

The goal is not only to generate formulas. It is to **inspect and understand them**.

---

# 4. Reconciliation

Open:

- `04 CRM Roster`
- `04 Platform Export`

## Goal

Compare the approved customer roster with what exists in the Team Challenge platform.

## Prompt

```text
Reconcile `04 CRM Roster` against `04 Platform Export`.

Match primarily by Employee ID and use email only as a secondary check.

Create a new sheet called `Reconciliation Findings` and identify:
- CRM-only records
- platform-only records
- duplicate platform users
- email mismatches
- region mismatches
- consent conflicts
- status conflicts

Include:
- Employee ID
- value from each source
- issue category
- recommended action
- review status

Do not modify either source sheet.
```

## Apply only safe corrections

```text
Create a new sheet called `Reconciled Roster`.

Apply only safe, deterministic corrections where a unique Employee ID match makes the correction unambiguous.

Do not automatically resolve:
- consent conflicts
- employment-status conflicts
- duplicate-identity conflicts
- platform-only conflicts

Mark those as `Needs human review`.

Summarize what still needs action.
```

## What to look for

Copilot should treat:

- obvious deterministic corrections differently from
- business decisions that require human review.

The pattern is:

**Compare → classify → explain → correct only what is safe**

---

# 5. Variance Analysis

Open:

`05 Monthly KPI`

## Goal

Understand how Team Challenge performance changed through the year and what leadership should investigate.

## Prompt

```text
Analyze `05 Monthly KPI` and create a new sheet called `Quarterly Variance`.

Use the `Aggregation` column to calculate Q1, Q2, Q3, and Q4 for each metric:
- use an average where the row says Average
- use a sum where the row says Sum

Then calculate:
- absolute change for Q2 vs Q1, Q3 vs Q2, and Q4 vs Q3
- percentage change for Q2 vs Q1, Q3 vs Q2, and Q4 vs Q3

Use the `Favorable Direction` column to label each change as:
- Favorable
- Unfavorable
- Neutral
```

## Leadership commentary

```text
Add a concise leadership commentary below the table focused on Q4.

Reference specific metrics.

Explain:
- what improved
- what deteriorated
- whether the deterioration looks broad or concentrated
- what management should investigate next
```

## Investigate whether the issue is temporary

```text
Which Q4 changes look like a temporary incident rather than a sustained trend?

Use the monthly pattern to support the answer rather than relying only on the quarterly total.
```

## What to look for

Remember:

- higher retention can be good
- higher support-ticket volume can be bad
- lower resolution time can be good

Copilot should use the **business meaning** of the metric, not assume that every increase is positive.

---

# 6. Participant Exercise — Scenario Analysis

Open:

`06 Exercise Scenario`

## Task

Build the model yourself using Copilot.

## Prompt

```text
Using the assumptions in `06 Exercise Scenario`, fill both sensitivity workspaces with formulas.

For each opt-in-rate and week-3-retention combination, calculate:
- week-3 active participants
- week-6 completions

Keep all formulas linked to the assumptions so changing eligible employees or the week-6 continuation rate updates the results.
```

## Interpret it

```text
Based on the sensitivity tables, explain whether this pilot has a comfortable margin above its success thresholds or whether small changes in retention could put the result at risk.

Keep the answer to 5 bullets and reference specific values.
```

---

# 7. Participant Exercise — Plan vs Actual

Open:

`06 Exercise Plan vs Actual`

## Prompt

```text
Add columns for:
- absolute variance
- percentage variance
- assessment of Favorable or Unfavorable

for every KPI in `06 Exercise Plan vs Actual`.

Use the `Favorable Direction` column when deciding whether a higher or lower actual is good.

Use formulas rather than hard-coded results.
```

## Diagnose the most important gap

```text
Which KPI has the most important unfavorable gap?

Based on the `Context / Notes` column and the pattern across related KPIs, does it look like:
- a one-time operational incident
or
- evidence of a broader problem?

Explain your reasoning and identify what should be checked next.
```

---

# Useful Copilot in Excel follow-up prompts

## Explain a formula

```text
Explain the formula in this cell in plain English.
```

## Check formula consistency

```text
Compare the formulas in this table and identify any cell that uses a different range or logic from the others.
```

## Find anomalies

```text
Identify the 5 most unusual values in this table and explain why they stand out.
```

## Create a management summary

```text
Summarize this analysis for a senior leader.

Give me:
- the main finding
- the strongest evidence
- the biggest risk
- the next action

Keep it under 120 words.
```

## Challenge the interpretation

```text
Challenge the conclusion from this analysis.

What alternative explanation could fit the same data, and what additional evidence would help distinguish between them?
```

## Ask for evidence

```text
For each conclusion, show me the exact cells or rows that support it.
```

## Protect against over-editing

```text
Before making any changes, tell me exactly which cells, formulas, or sheets you plan to modify.
```

---

# A simple mental model

| Task | Pattern |
|---|---|
| Check whether data can be trusted | **Validate** |
| Explore different possible outcomes | **Model** |
| Build calculations without memorising syntax | **Generate formulas** |
| Compare two sources that should agree | **Reconcile** |
| Understand what changed over time | **Variance analysis** |
| Turn numbers into a decision | **Interpret and challenge** |

---

# Final reminder

The strongest Copilot in Excel workflow is not:

**"Give me the answer."**

It is:

**Describe the analytical outcome → let Copilot build it → inspect the formulas → validate the assumptions → interrogate the result.**
