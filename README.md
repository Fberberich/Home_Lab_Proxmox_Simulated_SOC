# Proxmox SOC Home Lab

This project is a home lab built on a Proxmox hypervisor, designed to simulate a Security Operations Center (SOC) environment. It includes Ubuntu VMs, Splunk Cloud integration, and both red and blue team operations.

## Lab Architecture

- **Proxmox VE** as the hypervisor
- **Ubuntu VMs** (clients, servers, attacker, logger)
- **Splunk Cloud** for SIEM and monitoring
- **Security tools**: Zeek, Suricata, Wazuh, Auditd

## Virtual Machines

| VM Name           | Role                      |
|------------------|---------------------------|
| ubuntu-client-01 | Simulated user workstation|
| ubuntu-server-01 | Web server (Apache/Nginx) |
| ubuntu-server-02 | File server (Samba/FTP)   |
| attacker-01      | Kali Linux (red team)     |
| logger-01        | Central syslog collector  |

## Network Configuration

All VMs are on a virtual LAN using Proxmox bridges. Internet simulation is provided via NAT.

## Monitored Logs

- `/var/log/auth.log` – SSH & sudo attempts
- `/var/log/syslog` – System events
- Apache logs – Access and error logs
- Zeek logs – HTTP, DNS, SSL, etc.
- Suricata – IDS alerts
- Wazuh – Host intrusion detection

## Simulated Attacks

- Brute-force SSH (hydra/medusa)
- SQL injection (`sqlmap`)
- Nmap scans
- Directory brute-forcing (`nikto`, `dirb`)

## Blue Team Detection

- Splunk dashboards and alerts
- Correlation rules for anomalies
- Custom playbooks for incident response

## Skills Gained

- Log analysis with Splunk
- Threat hunting and alert triage
- Network and endpoint security
- SOC operations and playbook development
- Red/Blue team simulations

## Documentation

Log every simulation, detection, and incident. Create markdown files for:
- Attack simulation details
- Detection queries and dashboards
- Playbooks and responses

## Prerequisites Before Running The Simulated Environment.
- Create VMs and the environment itself within Proxmox
    - Link to download Kali Linux OS 
    - Link to download Ubuntu
- Sign up for Splunk Cloud and download Splunk Forwarder to non-attacker boxes
    - [Link](https://www.splunk.com/en_us/download/splunk-cloud.html) to sign up for Splunk Cloud
    - [Link](https://www.splunk.com/en_us/blog/learn/splunk-universal-forwarder.html) to Splunk Forwarder

Lastly.. Good Luck with this lab! More importantly.. HAVE FUN!!!
