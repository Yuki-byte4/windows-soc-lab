# Sysmon configuration

This folder documents the Sysmon setup used by the lab.

## Install

1. Download Sysmon only from Microsoft's official Sysinternals page:
   https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon
2. Read the official usage instructions.
3. Select a maintained configuration after reviewing what it collects.
4. Record the configuration source, version, and date below.
5. Confirm events in Event Viewer under `Applications and Services Logs > Microsoft > Windows > Sysmon > Operational`.

## Configuration record

- Sysmon version: TODO
- Configuration source/name: TODO
- Configuration version or commit: TODO
- Install date: TODO
- Event types enabled: TODO
- Known exclusions: TODO

## Important

Do not add a configuration file here until you have reviewed its contents and confirmed its license. A configuration that collects too much can create high event volume; one that collects too little can miss useful context.

## Evidence

Add a redacted screenshot showing the Sysmon Operational channel receiving events under `../../evidence/`.
