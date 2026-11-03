# Troubleshooting

## Agent is not visible or is disconnected

- Confirm the Wazuh agent service is installed and running.
- Confirm the server address in the agent configuration is correct.
- Check that the VMs can reach each other on the private lab network.
- Review host firewall rules and the current Wazuh port requirements.
- Check agent logs on Windows and manager logs on Ubuntu.
- Confirm that the agent was enrolled with the intended Wazuh server.

## Agent is active, but no Windows events appear

- Confirm the event channel exists and contains events locally.
- Confirm the Wazuh agent configuration includes the correct channel.
- Check permissions and agent log messages.
- Restart the agent after configuration changes.
- Allow time for new events, then search by endpoint and time range.

## Sysmon events are missing

- Confirm Sysmon is installed and its service is running.
- Open Event Viewer and check `Microsoft-Windows-Sysmon/Operational`.
- Confirm your Sysmon configuration enables the event type you expect.
- Confirm the Wazuh agent is collecting that channel.
- Generate a harmless test event and search for it.

## Dashboard is unavailable

- Confirm the VM is running and has enough memory and disk space.
- Check Wazuh service status using the official troubleshooting guidance.
- Confirm you are using the correct lab address and URL.
- Check whether the host firewall or VM network changed.

## General rule

Change one thing at a time. Record the original setting, the change, and the result. Avoid copying commands from old tutorials without checking them against the documentation for your installed version.
