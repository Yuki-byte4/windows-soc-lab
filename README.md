# Windows SOC Detection & Incident Investigation Lab

A hands-on, defensive Security Operations Center (SOC) home lab built around **Wazuh**, **Windows event logging**, **Sysmon**, and **MITRE ATT&CK**.

> **Project status:** Starter repository / implementation guide. Replace every `TODO` with your own lab details and evidence as you build it. Do not describe detections as tested until you have generated the event, observed it in Wazuh, and saved evidence.

## Project goals

- Centralize endpoint security telemetry in a SIEM.
- Collect useful Windows events with the Wazuh agent and Sysmon.
- Review alerts and investigate what happened.
- Map relevant behavior to MITRE ATT&CK.
- Write short, evidence-based incident reports.
- Document the setup so another student can reproduce it.

## Lab architecture

```text
+----------------------------+        +-----------------------------+
| Windows 10/11 VM           |        | Ubuntu Server VM            |
|                            |        |                             |
| - Wazuh agent               |------->| - Wazuh manager              |
| - Sysmon                    | logs   | - Wazuh indexer              |
| - Windows Security logs     |        | - Wazuh dashboard            |
+----------------------------+        +-----------------------------+
                 Isolated / host-only lab network where practical
```

The Wazuh all-in-one installation is suitable for a small learning lab. Follow the official Wazuh installation guide for the current supported Ubuntu version and installation commands; versions and commands can change.

## Repository map

| Path | Purpose |
|---|---|
| `docs/architecture.md` | Network and VM design |
| `docs/build-guide.md` | Setup sequence and verification checklist |
| `docs/data-sources.md` | Windows event sources |
| `docs/detection-use-cases.md` | Defensive detection scenarios |
| `docs/investigation-workflow.md` | Repeatable alert triage process |
| `docs/mitre-mapping.md` | ATT&CK mapping notes |
| `docs/troubleshooting.md` | Common lab issues |
| `config/sysmon/README.md` | Sysmon installation and configuration notes |
| `config/wazuh/README.md` | Wazuh agent and rule configuration notes |
| `reports/incident-report-template.md` | Reusable investigation report |
| `reports/lab-validation-template.md` | Record test results honestly |
| `evidence/README.md` | Evidence capture checklist |
| `scripts/README.md` | Safe lab validation notes |

## Suggested build order

1. Create the Ubuntu and Windows VMs.
2. Install Wazuh using the official documentation.
3. Enroll the Windows endpoint with the Wazuh agent.
4. Confirm that Windows security events reach the dashboard.
5. Install Sysmon on the Windows VM using a reviewed configuration.
6. Confirm Sysmon events are collected.
7. Work through one detection use case at a time.
8. Complete an incident report for each validated investigation.
9. Add screenshots with timestamps and redact private information.
10. Update this README with your actual versions, network diagram, and results.

## Lab safety

- Use VMs and accounts that you own or are explicitly authorized to test.
- Keep the lab isolated from public networks where possible.
- Do not run tests against third-party systems.
- Use benign, controlled activity and built-in Windows features to create test events.
- Never publish passwords, API keys, public IP addresses, personal data, or unredacted host details.

## Current implementation status

Update this table as you complete the work.

| Component | Status | Evidence |
|---|---|---|
| Ubuntu Wazuh server | Not started | TODO |
| Windows endpoint VM | Not started | TODO |
| Wazuh agent enrolled | Not started | TODO |
| Windows Security events visible | Not started | TODO |
| Sysmon installed and logging | Not started | TODO |
| Detection scenarios validated | Not started | TODO |
| Incident reports completed | Not started | TODO |

## Official references

- Wazuh documentation: https://documentation.wazuh.com/current/
- Wazuh installation guide: https://documentation.wazuh.com/current/quickstart.html
- Microsoft Sysmon: https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon
- Windows Security auditing: https://learn.microsoft.com/en-us/windows/security/threat-protection/auditing/
- MITRE ATT&CK: https://attack.mitre.org/

## Author

**TODO:** Sopio Dgebuadze, https://www.linkedin.com/in/sopio-d-a817b4377/ 

This repository is a learning portfolio project. All results and screenshots should represent work actually completed in your own lab.
