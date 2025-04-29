# Open-Source SIEM, IDS, SOAR Integration for Real-Time Threat Detection and Automated Response

Final Year Cybersecurity Capstone Project | April 2025  
**Author: Meyyappan Venkatesh**

---

## 1. Project Overview

Modern organizations face a growing onslaught of cyber threats, yet many still rely on fragmented, manual defenses.  
This project delivers a unified, automated threat detection and response framework, entirely built with open-source technologies — demonstrating that **robust cybersecurity** can be **affordable**, **scalable**, and **realistic** for small-to-medium enterprises (SMEs).

The system integrates:
- **Wazuh** for centralized log collection, rule-based analysis, and alerting (SIEM/XDR)
- **Suricata** for real-time network intrusion detection (IDS)
- **Shuffle** for security orchestration and automated response workflows (SOAR)
- **VirusTotal API** for threat intelligence enrichment

Deployed within a secure VMware-based virtual lab, this solution detects, analyzes, and autonomously mitigates real-world cyber threats Key achievements include **real-time detection**, **automated incident response**, **minimal human intervention**, and a design that is **scalable**, **affordable**, and **practically replicable**.

---

## 2. Project Objectives

- Deploy a unified cybersecurity framework combining SIEM, XDR, IDS, and SOAR functionalities.
- Detect and respond automatically to security incidents with minimal analyst workload.
- Automate actions like IP blocking, malware file quarantine, and real-time alert notifications.
- Provide a cost-effective and scalable security solution tailored for SMEs and resource-constrained environments.

---

## 3. System Architecture

<p align="center">
  <img src="https://github.com/MeyyappanVenkatesh/Open-Source-SIEM-IDS-SOAR-Integration/blob/main/screenshots/Network%20diagram.png" alt="Network Diagram" width="480" height="auto">
</p>

> **Figure 1**: Integrated Virtual Lab Environment with Wazuh, Suricata, Shuffle, VirusTotal, and Attack Simulation VM (Kali Linux).

---

## 4. System Requirements for Lab Simulation

To fully deploy and simulate the cybersecurity threat detection and automated response framework, the following minimum system resources are recommended:

| Component             | Specification              |
|------------------------|-----------------------------|
| Host Machine CPU       | 8 physical cores (Intel i7/i9 or AMD Ryzen 7/9 recommended) |
| Host Machine RAM       | 32 GB minimum (higher preferred for smooth multitasking) |
| Host Machine Storage   | 250 GB free disk space (SSD recommended for performance) |
| Virtualization Software| VMware Workstation Pro or VMware Player (or equivalent VirtualBox) |
| Network Setup          | NAT Network (Internet access required) |
| Virtual Machines       | 4 VMs (Wazuh Server, Shuffle SOAR Server, Ubuntu Endpoint, Kali Linux Attacker) |

---

## 5. Use Cases Implemented

| UC ID | Use Case Name                              | Detection & Response Workflow |
|:-----|:--------------------------------------------|:-------------------------------|
| UC01  | Nmap Port Scan Detection                   | Suricata detects → Wazuh alerts |
| UC02  | SSH Brute-Force Detection and IP Blocking  | Wazuh detects → Shuffle blocks IP |
| UC03  | Malware Detection with VirusTotal and Quarantine | Wazuh + VirusTotal scan → Shuffle deletes file, disables interface |
| UC04  | Off-Hours Employee Logon Monitoring        | Wazuh detects → Shuffle sends dynamic time-stamped alert |
| UC05  | Rapid File Change Detection (Ransomware Behavior) | Wazuh correlates mass file changes → ransomware alert |
| UC06  | Data Exfiltration Attempt Detection        | Suricata detects sensitive file downloads |
| UC07  | Suspicious Command Execution Monitoring    | Auditd detects → Wazuh raises suspicious activity alerts |

---

## 6. Repository Structure

```plaintext
/docs          - Final project report, supporting screenshots, architecture diagrams
/configs       - Wazuh custom rules, Suricata local rules, Auditd audit.rules
/scripts       - Helper scripts for simulation (ransomware simulation, alert enrichment)
/screenshots   - Proofs of attack simulation, alert detection, and automated responses
/README.md     - This file
```

## 7. Virtual Machine Credentials

| Virtual Machine         | Username   | Password  |
|--------------------------|------------|-----------|
| Wazuh Server             | wazuh      | 12345     |
| Shuffle SOAR Server      | shuffle    | 12345     |
| Ubuntu Employee Endpoint | employee   | 12345     |
| Kali Linux Attacker      | kali       | kali      |

---

## 8. Dashboard Access Credentials

| Platform         | URL                                         | Username | Password       |
|------------------|---------------------------------------------|----------|----------------|
| Wazuh Dashboard  | https://192.168.76.130                      | admin    | SecretPassword |
| Shuffle SOAR UI  | https://192.168.76.133:3443                 | admin    | admin          |

---
