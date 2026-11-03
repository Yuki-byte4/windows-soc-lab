# MITRE ATT&CK mapping notes

Use ATT&CK to describe behavior only when the observed evidence supports the mapping. A Windows event ID by itself does not prove an ATT&CK technique occurred.

| Lab scenario | Possible ATT&CK area | Mapping guidance |
|---|---|---|
| Repeated failed logons | Credential Access — Brute Force (T1110) | Map only when the pattern and context support an attempted guessing activity. |
| Suspicious or unexpected process execution | Execution — Command and Scripting Interpreter (T1059) | A process event alone is not enough; inspect the interpreter, command line, parent process, and context. |
| New local account | Persistence — Create Account (T1136) | Use only if the account creation is unauthorized or otherwise fits the technique. |

Reference: https://attack.mitre.org/

For each completed investigation, record:
- Technique ID and name:
- Evidence supporting the mapping:
- Evidence that is missing:
- Confidence: Low / Medium / High
- Why this mapping is appropriate:

Do not force a mapping when the event is ordinary administration or the evidence is incomplete.
