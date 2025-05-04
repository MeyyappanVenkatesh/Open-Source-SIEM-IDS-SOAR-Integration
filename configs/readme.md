# 🔧 Configuration Files

This folder contains all configuration files used in the project setup. Below is a list of each file, its purpose, and its target placement on the respective virtual machines.

| File Name                  | Description                                                      | Destination Path on VM                          | Applies To                |
|---------------------------|------------------------------------------------------------------|--------------------------------------------------|---------------------------|
| `ossec_config_Manager.conf` | Wazuh manager configuration including integrations with Shuffle & VirusTotal | `/var/ossec/etc/ossec.conf` (on **Wazuh Server**) | Wazuh Manager             |
| `ossec_config_Agent2.conf`  | Custom agent configuration for endpoint monitoring               | `/var/ossec/etc/ossec.conf` (on **Ubuntu Endpoint**) | Wazuh Agent (Endpoint)   |
| `local_rules.xml`           | Custom Wazuh detection rules for ransomware, login times, commands, etc. | `/var/ossec/etc/rules/local_rules.xml`          | Wazuh Manager             |
| `suricata.yaml`             | Core configuration for Suricata IDS                              | `/etc/suricata/suricata.yaml`                   | Suricata (Ubuntu Endpoint) |
| `local.rules`               | Custom Suricata detection rules (e.g., credit card leaks, Nmap)  | `/etc/suricata/rules/local.rules`              | Suricata (Ubuntu Endpoint) |

> ⚠️ After copying each file, restart the appropriate service:
> - `sudo systemctl restart wazuh-manager` or `wazuh-agent`
> - `sudo systemctl restart suricata`

