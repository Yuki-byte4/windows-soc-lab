# Wazuh configuration notes

Keep notes about the Wazuh server, agent, and any custom rules here. Do not commit credentials, certificates, private keys, or complete configuration files containing secrets.

## Agent collection

The Windows agent should collect the event channels required by the lab:

- `Security`
- `Microsoft-Windows-Sysmon/Operational`

Check the current Wazuh documentation for the correct Windows eventchannel configuration syntax for your installed version.

## Custom rules

Start by understanding the built-in Wazuh rules and alert fields. Add a custom rule only after you have:
1. Captured a real event from your lab.
2. Inspected its decoded fields.
3. Identified a clear detection condition.
4. Tested the rule against both matching and non-matching events.
5. Documented false positives and limitations.

Store reviewed custom rule files here, with comments and a note about the Wazuh version tested. Do not copy rule IDs from an unrelated tutorial without checking for conflicts.

## Rule test record

- Wazuh version:
- Rule file:
- Rule ID:
- Event fields matched:
- Positive test:
- Negative test:
- False positives:
- Date tested:
