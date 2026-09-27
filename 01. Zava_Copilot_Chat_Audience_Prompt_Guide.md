# Zava Copilot Chat — Audience Prompt Guide

Use this guide during the Copilot Chat section of the workshop.

> **Important**
> - Your results will differ from the demo because Copilot uses your own Microsoft 365 work context.
> - Replace names, dates, meetings, emails, and files with items from your own work.
> - When a prompt uses `/`, select the relevant work item from Copilot rather than typing the placeholder literally.
> - Do not send emails or create calendar invitations unless you intend to.
> - If a capability is not available in your tenant, skip it and continue with the next prompt.

---

## 1. Catch up and prioritise work

### Demo pattern

```text
Catch me up on what happened since Friday.

Give me only the top 3 things requiring my attention.

Consider important emails, Teams conversations and meetings, and anything I need to prepare for today.

Group them as:
- Urgent
- Before my next meeting
- FYI

Show the supporting sources.
```

### Try it with your own work

```text
Catch me up on the last two working days.

Give me only the top 3 things requiring my attention, grouped as:
- Urgent
- Before my next meeting
- FYI

Show the supporting source for each.
Keep it concise.
```

### If the result is too broad

```text
Give me only the 3 items that require a decision, response, preparation, or action from me.
Ignore general FYI activity unless it is likely to affect my work today.
```

---

## 2. Ground Copilot on a specific email, meeting, or file

Press `/` in Copilot Chat and select the relevant work item.

### Compare an earlier request with a later update

```text
Using these sources, tell me in 4 bullets what changed between the original request and the later meeting, and what I can now confidently say.

Separate:
1. the original concern
2. the latest confirmed information
3. anything that is still uncertain
```

### Generic version

```text
Using /[email or meeting] and /[later meeting, email, or file], tell me:
- what changed
- what is now confirmed
- what is still unresolved
- what action I should take

Keep it to 5 bullets.
```

### Extract decisions and actions from one work item

```text
Using /[meeting or email], give me only:
- decisions made
- actions assigned to me
- unresolved questions
- deadlines or commitments

Keep it concise.
```

---

## 3. Draft a response using confirmed facts

### Zava demo

```text
Draft a concise reply to Amber confirming the privacy position for Northstar.

Keep it customer-ready and only use the facts confirmed in the meeting.
```

### Generic version

```text
Draft a concise reply to this stakeholder based only on the confirmed facts in the sources we have just reviewed.

Use a professional, direct tone.
Do not add assumptions or commitments that are not supported by the sources.
```

### Shorter version

```text
Draft a response I could send.
Keep it under 120 words.
Lead with the answer, then give the minimum supporting context.
```

> Review the draft before sending.

---

## 4. Schedule a follow-up meeting

### Zava demo

```text
Find 30 minutes with Kai Carter on Tuesday afternoon and schedule a meeting called:

Team Challenge – Android Readiness Check
```

### Generic version

```text
Find 30 minutes with [person] on [day or time window] and schedule a meeting called:

[meeting title]
```

### With agenda

```text
Find 30 minutes with [person] on [day or time window].

Schedule a meeting called "[meeting title]".

Use this agenda:
- current status
- unresolved issues
- decision needed
```

> Only create the meeting if you genuinely want the invitation sent.

---

## 5. Find organisational information with Search

Search examples:

```text
Team Challenge pilot readiness
```

```text
latest onboarding policy
```

```text
Q3 customer review
```

```text
project launch decision
```

Think of this as:

**Search = locate something you know or suspect exists.**

---

## 6. Prepare a decision using explicit work sources

Use `/` to add the relevant files, meetings, and emails first.

### Zava demo

```text
Using these sources, assess whether Zava is ready to proceed with the Team Challenge pilot.

Give me only:

1. Recommendation
2. Top 3 reasons supporting it
3. Top 3 remaining risks or decisions

Keep it concise.
```

### Generic version

```text
Using only these sources, assess the current situation.

Give me:

1. Recommendation
2. Top 3 pieces of evidence supporting it
3. Top 3 risks, assumptions, or unresolved decisions

Clearly distinguish facts from your interpretation.
Keep it concise.
```

---

## 7. Challenge the first recommendation

Use a deeper reasoning option when available.

### Zava demo

```text
Challenge this recommendation as if you were reviewing it for leadership.

Give me:
- the strongest reason to delay
- the top 3 assumptions that could be wrong
- 3 pieces of evidence you would want before approval
- whether any of this materially changes the recommendation

No more than 8 bullets.
```

### Generic version

```text
Challenge your previous answer.

Identify:
- the strongest counterargument
- the 3 assumptions most likely to be wrong
- the evidence I should validate before acting
- whether the recommendation changes

Keep it to 6–8 bullets.
```

### Useful follow-up

```text
What would have to be true for the opposite recommendation to be correct?
```

---

## 8. Analyse structured data

When **Analyse data** is available, attach or reference the relevant workbook.

### Zava demo

```text
Analyse this workbook and give me only:

- the 4 numbers that matter most
- the biggest remaining risk
- whether the numbers strengthen or weaken a Conditional Go

Keep it under 120 words.
```

### Generic version

```text
Analyse this workbook and give me:

- the 5 numbers or trends that matter most
- the largest outlier or risk
- one conclusion the data supports
- one conclusion the data does not support

Keep it under 150 words.
```

### Ask Copilot to explain the evidence

```text
For each conclusion, point me to the specific row, column, table, or source value that supports it.
```

---

## 9. Use Memory for personal working preferences

### Example preference to save

```text
Remember that I prefer leadership updates to be concise:
- recommendation first
- no more than 3 key risks
- no more than 3 actions
- avoid long narrative unless I ask for detail
```

### Verify what Copilot remembers

```text
What do you remember about how I prefer leadership updates?
```

Use Memory for **how you like to work**, not as the source of truth for project facts.

---

## 10. Turn a useful response into a Page

After a useful response, use **Edit in Pages** if available.

Then ask:

```text
Add a short section called "Leadership decisions" with the three decisions required today.
```

Other useful Page prompts:

```text
Turn this into a concise executive brief with:
- recommendation
- evidence
- risks
- decisions
- next actions
```

```text
Remove repetition and make this easier for a senior leader to scan in under two minutes.
```

---

## 11. Use a Notebook for ongoing project context

After adding the relevant project sources to a Notebook:

```text
Based only on the material in this notebook, what are the top 3 unresolved questions we should track during the project?

Keep it concise.
```

### Other useful Notebook prompts

```text
Based only on this notebook, summarize:
- decisions already made
- open risks
- commitments
- upcoming decision points
```

```text
What has changed across these project sources, and which earlier assumptions are no longer valid?
```

Think of it as:

**Memory = how I work**  
**Notebook = what belongs to this project**

---

## 12. Ask an Agent for reusable specialist expertise

### Zava demo

```text
Ask the Zava Customer Insight Agent whether current customer feedback introduces any additional Team Challenge pilot risk that leadership should know about.

Give me only 3 bullets.
```

### Generic version

```text
Ask [agent name] to review this situation using its specialist knowledge.

Give me:
- the most important finding
- the biggest risk
- the next action

Keep it to 3 bullets.
```

---

## 13. Save a useful prompting pattern in Prompt Lab

### Morning work triage

```text
Catch me up on the last two working days.

Give me the top 3 things requiring attention:
- Urgent
- Before my next meeting
- FYI

Show the supporting source for each.
Keep it concise.
```

### Project status pattern

```text
Summarize what changed on [project] since my last update.

Give me:
- decisions made
- new risks
- actions assigned to me
- anything that needs my response

Show the supporting sources.
```

---

## 14. Scheduled prompt — weekly meeting preparation

```text
Review my important meetings over the next five business days.

For each meeting, use relevant Microsoft 365 work context to give me:

- purpose and expected outcome
- latest relevant developments
- unresolved decisions
- actions I owe
- three questions I should be ready to answer
- the most useful supporting sources

Keep each meeting concise.

Prioritize meetings where I have a decision, action, or preparation responsibility.
```

### Shorter version

```text
Prepare me for my important meetings over the next five business days.

For each meeting give me:
- purpose
- latest development
- decision or action needed from me
- 3 questions I should be ready to answer
- supporting sources

Keep it concise.
```

Scheduled prompts may run asynchronously. A result may appear later in Copilot Chat rather than immediately after you select **Run now**.

---

## 15. Post-meeting follow-through

```text
Using /[meeting], give me only:
- decisions made
- actions I own
- actions owned by others
- unresolved questions

Then draft the follow-up message I should send.
```

### Turn meeting output into a work plan

```text
Convert these meeting actions into a simple table with:
- action
- owner
- due date
- dependency
- status

Do not invent due dates that were not agreed.
```

---

# Useful prompt controls

Add these phrases when Copilot gives you too much output:

```text
Keep it under 120 words.
```

```text
No more than 5 bullets.
```

```text
Recommendation first.
```

```text
Separate confirmed facts from assumptions.
```

```text
Use only the sources I selected.
```

```text
Show the supporting source for each point.
```

```text
Do not make commitments that are not present in the source material.
```

```text
Tell me what evidence is missing.
```

---

# A simple mental model

| What you need to do | Copilot capability |
|---|---|
| Understand what is happening | Work IQ / Chat |
| Find something | Search |
| Force specific evidence | `/` work references |
| Complete work | Email / calendar actions |
| Pressure-test a decision | Deeper reasoning |
| Analyse structured information | Analyse data |
| Personalise how Copilot works with you | Memory |
| Keep an editable output | Pages |
| Maintain project context | Notebook |
| Reuse specialist expertise | Agents |
| Reuse a good prompt | Prompt Lab |
| Run a routine automatically | Scheduled prompts |
| Return to created work | Library |

---

## Final reminder

A strong Copilot workflow is often:

**Catch up → Ground → Understand → Act → Challenge → Verify → Organise → Reuse**

Do not judge a prompt only by whether Copilot produced fluent text. Check the sources, assumptions, and evidence before acting.
