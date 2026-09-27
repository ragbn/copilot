# Zava Copilot in Outlook — Audience Prompt Guide

Use this guide during the **Copilot in Outlook** section of the workshop.

## Scenario

You are **Corey Gray**, Customer Experience Program Manager at **Zava**.

Corey is managing the **Team Challenge pilot**. His Outlook contains customer emails, product updates, meeting invitations, attachments, and recurring operational notifications.

The Outlook workflow is:

**Prioritize → Summarize → Reply → Improve → Schedule → Prepare → Triage → Automate**

> **Important**
> - Use your own work email and calendar only where appropriate.
> - Do not send messages or invitations unless you genuinely intend to.
> - For exercises, stopping at a draft is completely fine.
> - Outlook Copilot experiences can vary by tenant, license, client, sensitivity label, and mailbox configuration.
> - If a capability is unavailable, skip it and continue with the next task.

---

# 1. Summarize a long email thread

Open a recent email conversation with several replies.

Use **Summary by Copilot / Summarize**.

## Follow-up questions

```text
What changed across this thread?

Give me only:
- the original request
- decisions made
- actions I own
- anything still unresolved
```

```text
Which message contains the latest confirmed position?
```

```text
What should I respond to, and what can I ignore?
```

## What to look for

- key points from the thread
- action items
- numbered citations back to the underlying messages, when available

---

# 2. Summarize an attachment

If the email includes a supported PDF, Word, or PowerPoint attachment, use **Summarize a file** when available.

Then ask:

```text
Give me the 5 points from this attachment that are most relevant to the email discussion.
```

```text
Does the attachment support the claim made in the latest email?

Separate:
- supported by the attachment
- not supported by the attachment
- unclear
```

---

# 3. Draft a reply

Use **Draft with Copilot**.

## Example

```text
Draft a concise reply.

Confirm what has been resolved, acknowledge the remaining issue, and state the next action.

Keep it professional and under 120 words.

Do not add commitments that are not present in the email thread.
```

## Customer-facing version

```text
Draft a customer-ready response.

Lead with the answer.

Then give:
- the confirmed position
- any relevant caveat
- the next step

Keep it concise and avoid internal terminology.
```

Before sending, review the draft yourself.

---

# 4. Adjust tone and length

After Copilot creates a draft, try:

```text
Make this shorter.
```

```text
Make this warmer without becoming informal.
```

```text
Make this more direct and executive-friendly.
```

```text
Keep the same meaning but remove defensive language.
```

---

# 5. Use Coaching by Copilot

Write a draft yourself first, then use **Coaching by Copilot**.

A useful test draft:

```text
We have already explained the issue several times and the product is working as designed. The remaining notification issue is not a blocker, so I don't think we should delay the pilot. Please confirm if there is anything else you need because we need to close this today.
```

Ask Copilot to coach the message.

## What to look for

- tone
- clarity
- reader sentiment
- whether the message sounds too abrupt or defensive
- specific suggestions rather than a completely unrelated rewrite

Then rewrite only what you agree with.

---

# 6. Schedule a meeting from an email thread

Open a thread where a meeting is the obvious next step.

Use **Schedule with Copilot** when available.

Copilot can propose:
- title
- attendees
- agenda
- the email thread as context

Before sending, review the invite.

## If creating the meeting manually

Use:

```text
Create a concise agenda for this meeting.

Goal:
Resolve the remaining issue and leave with a clear owner and next action.

Agenda:
- latest status
- remaining risk
- decision needed
- owner and next step

Keep it suitable for a 30-minute meeting.
```

---

# 7. Prepare for an upcoming meeting

Open an upcoming meeting and use **Prepare for this meeting** when available.

Useful follow-ups:

```text
What are the 3 things I need to know before this meeting?
```

```text
What decisions are likely to be required from me?
```

```text
What actions from previous discussions are still open?
```

```text
Which documents or emails should I read before joining?
```

```text
Give me 5 questions I should be ready to answer.
```

> The quality of meeting preparation depends on the related content available to you, such as prior emails, chats, and shared documents.

---

# 8. Triage email with Copilot

In Copilot chat in Outlook, try safe mailbox actions.

Examples:

```text
Show me unread emails from this week where I appear to owe a response.
```

```text
Flag the emails from [person] this week where I have an action.
```

```text
Mark these status-notification emails as read.
```

```text
Move these automated platform-notification emails to the Platform Notifications folder.
```

Start with reversible actions such as **flag**, **mark read**, **categorize**, or **move** before using delete.

---

# 9. Create a mailbox rule with natural language

Example:

```text
Create a rule for future emails from the Zava platform notification address.

Move them to a folder called Platform Notifications.
```

Or:

```text
Create a rule that categorizes future emails from my manager as Important.
```

Copilot should show the proposed rule and ask for confirmation before creating it.

> Rules apply to future incoming messages. They do not automatically process old mail.

---

# 10. Prioritize your inbox

If **Prioritize** is available, configure a few meaningful criteria.

Examples:

```text
It's from my manager.
```

```text
It's about a customer complaint.
```

```text
It mentions Team Challenge pilot.
```

```text
It's an automated platform notification.
```

Use high priority for things that deserve attention and low priority for predictable noise.

> Prioritize applies to mail received after the feature is enabled or the instruction is changed. It does not re-prioritize older messages.

---

# 11. Ask Copilot what changed

For a busy thread:

```text
I read this thread yesterday.

What has changed since then?
```

```text
Give me only the new decisions, commitments, and risks from the most recent replies.
```

This is often more useful than re-summarizing the full conversation.

---

# 12. Turn a thread into an action plan

```text
From this email thread, create a simple action table with:
- action
- owner
- due date
- dependency
- status

Do not invent owners or due dates that were not explicitly agreed.
```

---

# 13. Draft an executive update from email context

```text
Based on this email thread, draft a short update for my manager.

Use:
- current status
- what changed
- biggest risk
- next action

Keep it under 100 words.
```

---

# Useful Outlook prompt controls

```text
Keep it under 120 words.
```

```text
Lead with the answer.
```

```text
Separate confirmed facts from assumptions.
```

```text
Do not add commitments that are not in the thread.
```

```text
Tell me what is still unresolved.
```

```text
Use customer-friendly language.
```

```text
Remove internal terminology.
```

```text
Do not send anything. Draft only.
```

---

# A simple mental model

| Need | Outlook Copilot pattern |
|---|---|
| Understand a long conversation | **Summarize** |
| Understand a document sent by email | **Summarize attachment** |
| Respond faster | **Draft with Copilot** |
| Improve your own writing | **Coaching** |
| Turn discussion into collaboration | **Schedule with Copilot** |
| Arrive prepared | **Prepare for this meeting** |
| Reduce mailbox work | **Triage** |
| Reduce future noise | **Rules** |
| Surface what deserves attention | **Prioritize** |

---

# Final reminder

A useful Outlook Copilot workflow is:

**Understand → Respond → Coordinate → Prepare → Organize**

Review AI-generated content before sending or acting on it.
