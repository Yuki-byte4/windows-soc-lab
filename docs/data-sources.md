# Data sources

## Windows Security event channel

Windows Security auditing records selected account, logon, policy, and other security activity. The events available depend on the audit policy configured on the endpoint.

Useful event IDs to learn:

| Event ID | General meaning | Investigation note |
|---:|---|---|
| 4624 | Successful logon | Check logon type, account, source details, and time. |
| 4625 | Failed logon | Several failures may be worth reviewing, but can also be caused by a typo or stale credential. |
| 4634 | Account logoff | Useful for timeline context. |
| 4648 | Logon attempted using explicit credentials | Review the process and account context. |
| 4672 | Special privileges assigned to a new logon | Not automatically malicious; common for admin accounts. |
| 4720 | User account created | Confirm whether the change was approved. |
| 4722 | User account enabled | Check who made the change and why. |
| 4726 | User account deleted | Confirm change authorization. |

Event IDs are clues, not verdicts. Interpret them with the full event details and surrounding activity.

## Sysmon Operational channel

Sysmon provides detailed endpoint telemetry. Common event types include:

| Sysmon Event ID | General meaning |
|---:|---|
| 1 | Process creation |
| 3 | Network connection (if enabled in the configuration) |
| 7 | Image loaded (if enabled; can be high volume) |
| 11 | File created |
| 13 | Registry value set |
| 22 | DNS query |

Not every event type is enabled by every configuration. Record your Sysmon configuration and verify which events it produces.

## Collection checklist

- [ ] Windows Security channel is collected.
- [ ] Sysmon Operational channel is collected.
- [ ] Event timestamps are visible.
- [ ] Endpoint identity is consistent.
- [ ] Events can be searched by event ID.
- [ ] Time zone is documented.
