# 🛠️ Ransomware Simulation Script

This Python script is used to simulate a ransomware attack scenario within the virtual lab. It helps test the effectiveness of Wazuh’s File Integrity Monitoring (FIM) and custom ransomware detection rules.
## 📌 Script: `wazuh-ransomware-poc.py`

### ✅ Purpose

The script mimics the behavior of ransomware by:

| Mode      | Action                                                                  |
|-----------|-------------------------------------------------------------------------|
| `prepare` | Creates nested directories and random text files                        |
| `attack`  | Encrypts all files recursively and deletes the originals                |
| `restore` | Decrypts all `.encrypted` files and restores them to their original state |

## 📂 Recommended Execution Directory

This script should be placed and executed inside a Wazuh FIM-monitored directory. For example:

```bash
cd /home/employee/Downloads/ransomware-simulation
python3 wazuh-ransomware-poc.py prepare
```
Make sure your ossec.conf on the Wazuh agent includes the directory: `<directories check_all="yes">/home/employee/Downloads/ransomware-simulation</directories>`
Then restart the agent: `sudo systemctl restart wazuh-agent`

---

### 🧩 Dependencies

```markdown

Install the required Python package:

```bash
pip3 install cryptography
```
### 🧩 How to Run It

```markdown

Run the script in one of the following modes:

```bash
# Step 1: Prepare test files and folders
python3 wazuh-ransomware-poc.py prepare

# Step 2: Simulate a ransomware attack
python3 wazuh-ransomware-poc.py attack

# Step 3: Restore original files (optional)
python3 wazuh-ransomware-poc.py restore
```
Each command performs the following:

1) prepare: Creates 10 folders with 20 random .txt files each
2) attack: Encrypts and deletes original files
3) restore: Decrypts files with .encrypted extension back to .txt
