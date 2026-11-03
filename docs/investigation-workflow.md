# Alert investigation workflow

Use this workflow for each alert or event you investigate.

## 1. Validate the alert

- What rule or event triggered?
- Which endpoint reported it?
- What is the event timestamp and time zone?
- Is the event data complete?
- Is the alert severity appropriate?

## 2. Gather context

- Which user account was involved?
- What process or logon type is recorded?
- Are there related events immediately before or after?
- Is the activity expected for this endpoint?
- Is there a known maintenance task or approved change?

## 3. Build a timeline

Record events in chronological order. Keep timestamps and time zones consistent.

| Time (with zone) | Event | Source | Notes |
|---|---|---|---|
| TODO | TODO | TODO | TODO |

## 4. Decide what the evidence supports

Use careful language:
- **Observed:** directly present in the event or alert.
- **Likely:** supported by multiple facts, but not certain.
- **Not established:** cannot be concluded from the available evidence.

Do not label an event malicious just because it is unusual.

## 5. Recommend a response

For a learning lab, describe sensible defensive actions such as verifying the user activity, checking change records, reviewing related events, and escalating when evidence supports it. Do not take disruptive action on a real system without authorization.

## 6. Document and close

Complete `reports/incident-report-template.md`, attach redacted evidence, and record detection gaps or false positives.
