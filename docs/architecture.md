# Lab architecture

## Purpose

This lab sends Windows endpoint telemetry to a central Wazuh server so that alerts can be reviewed and investigated from one dashboard.

## Recommended virtual machines

These are starting points, not strict requirements. Adjust them to the capacity of your host computer.

| VM | Suggested resources | Role |
|---|---:|---|
| Ubuntu Server | 2–4 vCPU, 4–8 GB RAM, 50 GB disk | Wazuh all-in-one server |
| Windows 10/11 | 2 vCPU, 4–8 GB RAM, 60 GB disk | Monitored endpoint |

Running the Wazuh indexer, manager, and dashboard together can use significant memory. If your computer has limited RAM, start with one Windows endpoint and avoid running unnecessary VMs at the same time.

## Network

Use a host-only or internal virtual network for the lab traffic where practical. Give the Ubuntu server a stable private address and record it below.

| Setting | Your value |
|---|---|
| Hypervisor | TODO |
| Ubuntu version | TODO |
| Windows version | TODO |
| Lab network range | TODO |
| Wazuh server IP | TODO |
| Windows endpoint IP | TODO |
| Wazuh version | TODO |
| Wazuh agent version | TODO |

Do not publish a real public IP address or details that expose your home network.

## Data flow

1. Windows records security and system events.
2. Sysmon adds process and other system telemetry.
3. The Wazuh agent reads configured event channels and forwards events.
4. Wazuh manager analyzes incoming events and creates alerts when rules match.
5. The dashboard is used to search, filter, and review alerts.

## Ports

Check the current Wazuh documentation for the ports required by the exact deployment method and version you use. Do not open services to the public internet just to make the lab work. Restrict access to the lab network and host firewall rules.
