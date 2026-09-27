# Zava Declarative Agent — Approval Concierge
## Audience Step-by-Step Build Guide

> **Scope of this exercise**
>
> We are building a **declarative agent directly in Microsoft 365 Copilot Agent Builder**.
>
> We are **not** building a custom agent in Copilot Studio.
>
> The core exercise is intentionally **retrieval-first**: the agent finds, summarizes, and prioritizes approval information from Microsoft 365 knowledge sources.
>
> It does **not** actually approve or reject business requests.

---

# What you are building

You are **Corey Gray**, Customer Experience Program Manager at **Zava**.

Corey receives approval requests from different teams. Instead of opening a list, several emails, supporting documents, and Teams messages separately, he wants one place to ask:

> **What approvals are waiting for me, and what do I need to know before I act?**

You will build:

**Zava Approval Concierge**

The agent should be able to:

- find approval requests assigned to the user
- identify which are still pending
- surface overdue or due-soon items
- summarize the request
- show the requestor, due date, priority, and source
- use supporting documents or email context when available
- explain what information is missing
- never pretend it has approved or rejected something

---

# Mental model

A declarative agent is a configured version of Microsoft 365 Copilot.

You declare:

| Component | What it controls |
|---|---|
| **Name** | What users see |
| **Description** | What the agent is for |
| **Instructions** | How it should behave |
| **Knowledge** | What organisational information it can search |
| **Capabilities** | Optional built-in abilities such as data analysis or image generation |
| **Skills** | Optional reusable packaged workflows, where available |
| **Starter prompts** | Examples that show users what to ask |

For this exercise, the most important pieces are:

**Instructions + Knowledge + Starter prompts**

---

# Before you start

Your facilitator should provide a SharePoint approval source, such as:

**Zava Approval Requests**

The source should contain fields similar to:

- Approval ID
- Title
- Request Type
- Requestor
- Approver
- Status
- Submitted Date
- Due Date
- Priority
- Amount / Impact
- Business Justification
- Supporting Document
- Approval Link

The facilitator may also provide:

- an `Approval Supporting Documents` SharePoint folder
- approval-related emails
- an approval-related Teams chat

---

# Step 1 — Open Agent Builder

In Microsoft 365 Copilot:

1. Open **Agents & Skills** or the agent area in the left navigation.
2. Select **New agent** / **Create agent**.
3. You can either:
   - describe the agent conversationally, or
   - choose **Skip to configure** and build it manually.

For this workshop, start conversationally so you can see Agent Builder create the first version.

---

# Step 2 — Describe the agent

Paste:

```text
Create an agent called Zava Approval Concierge.

Its purpose is to help employees find and understand approval requests that need their attention.

The agent should:
- identify pending approval requests assigned to the user
- show overdue and due-soon approvals first
- summarize each request without making the decision for the user
- show the requestor, due date, priority, status, and supporting source
- use supporting approval documents when available
- explain what information is missing before the user can make a decision
- never claim that it approved or rejected a request

Keep responses concise and action-oriented.
```

Let Agent Builder generate the first configuration.

---

# Step 3 — Inspect what Agent Builder created

Open **Configure**.

Review:

- Name
- Description
- Instructions
- Knowledge
- Capabilities
- Skills, if available
- Starter prompts

Do not assume the generated instructions are correct just because they are detailed.

---

# Step 4 — Set the name

Use:

```text
Zava Approval Concierge
```

If the name is too long for your environment, use:

```text
Zava Approvals
```

---

# Step 5 — Set the description

Use:

```text
Finds and summarizes approval requests that need your attention, using approved Zava Microsoft 365 sources. It helps you understand what is pending, why it matters, what evidence is available, and what is still missing before you decide.
```

The description should explain **when someone should use the agent**.

---

# Step 6 — Replace the instructions with a deliberate version

Paste the following into **Instructions**.

```text
# Purpose

You are the Zava Approval Concierge.

Help the current user find, understand, and prioritize approval requests that require their attention.

# Source of truth

Use the configured Zava Approval Requests knowledge source as the primary source for approval status.

Use supporting SharePoint documents, Outlook email, Teams messages, and People data only to add context.

Do not infer that an item is approved, rejected, cancelled, or completed unless the configured approval source says so.

# Pending approval definition

Treat an item as pending only when:
- it is assigned to the current user or the user explicitly asks about a named approver, and
- its status indicates that approver action is still required.

If the source does not clearly show that an approval is pending, say that the status is unclear.

# Workflow: show pending approvals

When the user asks for pending approvals:

1. Find approval items assigned to the user.
2. Keep only items that still require approver action.
3. Prioritize:
   - overdue
   - due within 2 business days
   - high priority
   - remaining pending items
4. Present a concise table with:
   - Approval ID
   - Request
   - Requestor
   - Due date
   - Priority
   - Status
   - Why attention is needed
5. Cite or link to the supporting source when available.
6. End with the number of pending approvals found and call out any item where the evidence is incomplete.

# Workflow: explain one approval

When the user asks about a specific approval:

1. Find the approval record.
2. Summarize:
   - what is being requested
   - who requested it
   - why it is needed
   - due date
   - business impact
   - key supporting evidence
3. Identify missing or conflicting information.
4. Give the user questions they may want answered before making the decision.
5. Do not recommend approval or rejection unless the user explicitly asks for decision support.
6. If asked for decision support, separate:
   - confirmed facts
   - risks
   - assumptions
   - missing evidence

# Boundaries

This agent is for finding, summarizing, and preparing users to act on approvals.

Do not claim that you submitted, approved, rejected, edited, or completed an approval unless a configured action actually performed that transaction and returned confirmation.

If the user asks you to approve or reject an item and no such action is available, tell them that you can prepare the decision context but they must complete the action in the source approval system.

Do not invent approval IDs, due dates, requestors, values, or statuses.

# Response style

Be concise.

Lead with the user's required action.

Prefer tables for approval lists.

Clearly separate confirmed facts from assumptions or missing information.
```

---

# Step 7 — Add the approval knowledge source

In **Knowledge**:

1. Select **Add** / **Search** / **Browse**.
2. Add the SharePoint list supplied by the facilitator:
   - `Zava Approval Requests`
3. Confirm it appears as a configured source.

If the list is supplied as a direct SharePoint link, add the link to the **specific list**, not just the SharePoint site.

> A SharePoint site does not automatically include all SharePoint lists as agent knowledge.

---

# Step 8 — Add supporting documents

Add the facilitator-provided SharePoint folder or files, for example:

```text
Approval Supporting Documents
```

This could contain:

- purchase request briefs
- project exception requests
- marketing campaign requests
- security exception documents
- customer pilot approval briefs

The approval list tells the agent **what is pending**.

The documents help explain **why the request exists**.

---

# Step 9 — Optional: add Outlook email knowledge

If your tenant and license allow it:

1. In Knowledge, use **Search**.
2. Choose **My emails**.

This can help the agent find conversation context around an approval.

Important:

- Email knowledge is personal to the person using the agent.
- It is not the authoritative approval-status source in this exercise.
- Use the approval list for status.
- Use email for context.

---

# Step 10 — Optional: add Teams knowledge

If your facilitator supplied an approval-related chat or meeting:

1. Add the specific Teams chat or meeting.
2. Avoid adding broad Teams history unless you genuinely need it.

This teaches an important design principle:

> **More knowledge is not automatically better knowledge.**

Use the narrowest sources that support the scenario.

---

# Step 11 — Review People knowledge

If **Reference people in organization** is available, leave it enabled for this exercise.

People knowledge can help the agent understand:

- names
- roles
- reporting relationships
- contact context

It should not be treated as the source of approval status.

---

# Step 12 — Do you need Capabilities?

For this basic approval agent:

**No extra capability is required.**

You do not need image generation.

You do not need code interpreter just to retrieve and summarize approvals.

This is deliberate.

Only add a capability when it helps the agent accomplish its actual job.

---

# Step 13 — Understand custom skills

If your tenant exposes **Skills**, open the section and look at it.

A custom skill is a reusable packaged workflow that can contain:

- its own instructions
- reference files
- templates
- optional scripts

A skill is useful when a task needs to be performed in a consistent, repeatable way.

Example future skill:

```text
Approval Triage Skill
```

It could standardize:

- due-date bands
- risk labels
- output format
- a repeatable approval briefing

For this workshop, **do not depend on a custom skill**.

The core approval agent should work without one.

If Skills are not visible, continue. They may be unavailable in your tenant.

---

# Step 14 — Add starter prompts

Create starter prompts such as:

### Pending approvals

```text
Show my pending approvals.
```

### Urgent approvals

```text
Which approvals are overdue or due within the next two business days?
```

### Explain one

```text
Summarize the highest-priority approval and tell me what I should review before deciding.
```

### Missing evidence

```text
Which pending approvals are missing information I need to make a decision?
```

---

# Step 15 — Test the agent

Open **Try it**.

Start with:

```text
Show pending approvals assigned to Corey Gray.
```

For a shared workshop source, using the persona name makes testing deterministic.

Check that the response:

- only shows pending items
- does not include approved or rejected items
- surfaces due dates
- shows the source
- does not invent anything

---

# Step 16 — Test prioritization

```text
Which approvals need attention first?

Prioritize overdue, due-soon, and high-priority items.

Explain the reason for the order.
```

---

# Step 17 — Test a specific approval

```text
Tell me everything I need to know about APR-1042 before I make a decision.

Separate:
- confirmed facts
- risks
- missing information
- questions I should ask
```

Replace the ID with one from your workshop data.

---

# Step 18 — Test the boundary

Ask:

```text
Approve APR-1042.
```

For this retrieval-first workshop agent, the correct behavior is:

- it should **not** claim success
- it should explain that it can prepare the decision context
- it should direct you to the approval source if no transactional action exists

This is an important agent-design test.

---

# Step 19 — Refine based on failures

If the agent includes completed approvals:

```text
Update the agent so that "pending" only includes items where approver action is still required.

Never include Approved, Rejected, Cancelled, or Completed items in a pending-approval list.
```

If it is too verbose:

```text
For lists of approvals, use a compact table and no more than 2 lines of commentary after the table.
```

If it makes assumptions:

```text
Update the agent so that missing data is labelled "Not available in configured sources" rather than inferred.
```

Then test again.

---

# Step 20 — Create and share

Once the tests are satisfactory:

1. Select **Create** / **Update**.
2. Use the agent yourself.
3. If allowed by your organisation, share it with colleagues.
4. If your organisation requires governance, submit it to the organisational catalog for admin review.

---

# What this agent is and is not

## It IS good at

- retrieving approval information
- summarizing requests
- prioritizing based on known data
- bringing together supporting Microsoft 365 context
- identifying missing information
- preparing the user to make a decision

## It is NOT automatically an approval workflow

A retrieval-only agent does not automatically:

- change an approval record
- approve or reject a Power Automate approval
- update a line-of-business system
- call an external system just because it knows about it

Those scenarios require an appropriate **action/integration** in addition to knowledge retrieval.

---

# What each component contributed

| Component | What it did in this exercise |
|---|---|
| **Description** | Told users and Copilot what the agent is for |
| **Instructions** | Defined "pending", output format, workflow, and boundaries |
| **SharePoint list** | Source of truth for approval status |
| **Supporting files** | Added evidence and business context |
| **Email** | Added personal conversation context |
| **Teams** | Added collaboration context |
| **People** | Helped resolve people information |
| **Capabilities** | Not required for the core scenario |
| **Custom skills** | Optional advanced repeatability, not required |
| **Starter prompts** | Taught users how to use the agent |

---

# Key lesson

A declarative agent is not just:

> **"Copilot + some documents."**

It is:

> **Copilot + purpose + instructions + selected knowledge + optional capabilities/skills + testing + governance**

For this scenario:

**Knowledge tells the agent what happened.**

**Instructions tell the agent how to behave.**

**Actions would be required if you wanted the agent to change the external approval system.**
