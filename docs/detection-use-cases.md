# Detection use cases

These are investigation exercises, not claims that detections are already working. Complete the validation fields after testing in your own VM.

## UC-01 — Repeated failed logons

**Goal:** Identify repeated failed sign-in attempts on the Windows endpoint.

- Source: Windows Security
- Event ID: `4625`
- What to review: target account, logon type, source address/workstation when present, timestamp, and nearby successful logons.
- Benign test: create a controlled failed sign-in attempt using a test account in your own Windows VM. Do not test against any account or system you do not own.
- Caution: a few failures can be caused by a mistyped password, saved credentials, or a background service.

**Validation record**
- Date/time:
- Endpoint:
- Event found in Wazuh?:
- Alert/rule details:
- Screenshot:
- Analyst conclusion:

## UC-02 — Successful logon after failed attempts

**Goal:** Build a timeline around failed and successful logon events.

- Sources: Windows Security
- Event IDs: `4625`, `4624`
- What to review: same account, time gap, logon type, source details, and whether the successful logon was expected.
- Benign test: use your own test account and normal sign-in activity.
- Caution: event correlation requires care; matching only by nearby timestamps is not enough to prove a relationship.

**Validation record**
- Date/time:
- Endpoint:
- Events found:
- Timeline:
- Screenshot:
- Analyst conclusion:

## UC-03 — New local account created

**Goal:** Review account-management activity.

- Source: Windows Security
- Event ID: `4720`
- What to review: new account name, subject account that performed the action, timestamp, and whether the change was approved.
- Benign test: create a clearly named temporary test account in your own VM through Windows Settings or Computer Management, then remove it when finished.
- Caution: account creation may be part of normal administration.

**Validation record**
- Date/time:
- Endpoint:
- New test account alias:
- Event found in Wazuh?:
- Screenshot:
- Analyst conclusion:

## UC-04 — Process creation review

**Goal:** Learn to inspect process telemetry and its parent-child context.

- Source: Sysmon Operational
- Event ID: `1`
- What to review: image, command line, parent image, user, process ID, and timestamp.
- Benign test: open a standard Windows application such as Notepad and locate its process-creation event.
- Caution: a process name alone rarely proves malicious behavior. Consider path, signer, parent process, command line, user, and surrounding events.

**Validation record**
- Date/time:
- Endpoint:
- Process:
- Parent process:
- Event found in Wazuh?:
- Screenshot:
- Analyst conclusion:

## UC-05 — File creation visibility

**Goal:** Confirm that Sysmon file-creation telemetry is collected.

- Source: Sysmon Operational
- Event ID: `11`
- What to review: target filename, process image, user, and timestamp.
- Benign test: create a harmless text file in a dedicated lab folder.
- Caution: file creation is common activity. This exercise validates visibility, not maliciousness.

**Validation record**
- Date/time:
- Endpoint:
- Test file path (use a generic lab path in public notes):
- Event found in Wazuh?:
- Screenshot:
- Analyst conclusion:

## Summary table

| Use case | Tested? | Event visible? | Alert/rule validated? | Report |
|---|---|---|---|---|
| UC-01 Failed logons | No | No | No | TODO |
| UC-02 Logon timeline | No | No | No | TODO |
| UC-03 Account creation | No | No | No | TODO |
| UC-04 Process creation | No | No | No | TODO |
| UC-05 File creation | No | No | No | TODO |

Change `No` only after you have performed and verified the test.
