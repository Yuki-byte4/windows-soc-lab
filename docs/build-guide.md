# Build guide

This guide gives the build sequence. Use the current official Wazuh documentation for exact commands because supported versions and installation steps can change.

## 1. Prepare the virtual machines

- [ ] Create an Ubuntu Server VM.
- [ ] Create a Windows 10/11 VM.
- [ ] Put both VMs on a suitable private lab network.
- [ ] Update both operating systems.
- [ ] Record VM resources and software versions in `docs/architecture.md`.
- [ ] Take clean snapshots before installing monitoring components.

## 2. Install the Wazuh server

1. Read the official quickstart: https://documentation.wazuh.com/current/quickstart.html
2. Confirm that your Ubuntu release is supported.
3. Follow the current all-in-one installation instructions.
4. Save the dashboard URL and server address privately.
5. Sign in and confirm that the manager, indexer, and dashboard services are healthy.
6. Do not commit credentials or installation secrets.

**Validation:** Open the dashboard locally from the lab and confirm the services are running. Record the Wazuh version and add a redacted screenshot to `evidence/`.

## 3. Enroll the Windows agent

1. In the Wazuh dashboard, open the agent deployment section.
2. Select Windows and follow the generated instructions for your server address.
3. Install the agent on the Windows VM.
4. Start the Wazuh agent service.
5. Confirm that the endpoint appears as active in the dashboard.

**Validation:** Record the endpoint name as a lab alias (for example, `WIN-ENDPOINT-01`) rather than publishing a personal computer name.

## 4. Confirm Windows Security event collection

- Confirm the Windows Security event channel is enabled and accessible.
- Review the Wazuh agent configuration and ensure the Security event channel is included.
- Restart the agent after configuration changes.
- Generate a harmless, expected Windows event by using normal administrative activity in your own VM.
- Search for the event in the Wazuh dashboard.

Do not assume collection is working just because the agent is active. Confirm that events arrive.

## 5. Install Sysmon

1. Download Sysmon from Microsoft's official Sysinternals page: https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon
2. Read the current Sysmon documentation.
3. Choose a reviewed configuration suitable for a small lab.
4. Install Sysmon in the Windows VM according to Microsoft's instructions.
5. Confirm the `Microsoft-Windows-Sysmon/Operational` event channel exists and receives events.
6. Configure the Wazuh agent to collect that channel.
7. Confirm Sysmon events appear in Wazuh.

Do not blindly use an unknown configuration from the internet. Sysmon configurations affect event volume and quality.

## 6. Validate one use case at a time

For each scenario in `detection-use-cases.md`:

- [ ] Write down the expected event source and event ID.
- [ ] Generate only the benign test activity described.
- [ ] Find the event in Wazuh.
- [ ] Record the timestamp, endpoint, rule/alert details, and relevant fields.
- [ ] Explain what the event does and does not prove.
- [ ] Save a redacted screenshot.
- [ ] Complete an incident report if the event warrants investigation.

## 7. Finish the documentation

- Update the status table in the root README.
- Add only screenshots and results from your own lab.
- Record false positives and gaps.
- Explain what you would improve next.
