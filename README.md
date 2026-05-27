# 🛡️ Security Operations & Incident Response Sandbox

## 🏗️ SOC Telemetry & Engineering Matrix


| Analytics Domain | Platform Engine | Focus & Query Syntax | Enterprise Security Portfolio |
| :--- | :--- | :--- | :--- |
| 🛡️ **Network Security Monitoring** | Splunk Enterprise | SPL & Advanced Event Chaining | [Enterprise Security Suite](./01-Splunk-Firewall-Dashboard) |
| 🔍 **Threat Detection** | Microsoft Sentinel | KQL & Multi-Source Correlation | [Threat Detection Workspace](./02-Microsoft-Sentinel-KQL) |
| 📊 **Log Analysis** | IBM QRadar | AQL & Privilege Auditing | [Log Analysis Workspace](./03-IBM-QRadar-AQL) |
| 💻 **Endpoint Defense** | EDR / Sysmon | Behavior Tuning & Rule Design | [Endpoint Defense Workspace](./04-Endpoint-Defense) |

---

### 🌐 Enterprise Network Security Monitoring Suite (Splunk Enterprise)
Utilizes the BOTS v1 dataset to deliver centralized visibility into perimeter traffic patterns and network intrusions.
* 🧱 **[Fortigate Firewall Traffic Analytics](./01-Splunk-Firewall-Dashboard):** Monitors baseline perimeter traffic flow, inbound connection volumes, and geographic origins to detect reconnaissance.
* 🚨 **[Suricata Intrusion Detection (IDS/IPS) Center](./01-Splunk-Firewall-Dashboard/suricata_ids_dashboard.xml):** Real-time analysis of signature-based malicious activity, targeting patterns, and active protocol exploitation.

---

### 🎯 Cloud & Hybrid Threat Detection Engine (Microsoft Sentinel)
Houses production-ready Kusto Query Language (KQL) analytics designed to identify high-fidelity, actionable threats across enterprise infrastructure.
* 🔑 **[Brute Force Account Takeover Detection](./02-Microsoft-Sentinel-KQL):** Correlates consecutive Windows security event logon failures with a subsequent successful authentication event from the same entity.

---

### 📊 Enterprise Log Analysis Module (IBM QRadar)
Advanced log parsing utilizing Ariel Query Language (AQL) to monitor insider threats and configuration drift across Linux infrastructure.
* 🔑 **[Privilege Escalation & Sudo Auditing](./03-IBM-QRadar-AQL):** Tracks non-root users executing administrative commands via `sudo` to find compromised accounts or policy violations.

---

### 💻 Behavioral Endpoint Defense Workspace (EDR/Sysmon)
Detection engineering patterns modeled in Sigma/YAML syntax focused on endpoint visibility, malicious process tracking, and living-off-the-land techniques.
* ⚙️ **[Suspicious Encoded PowerShell Execution](./04-Endpoint-Defense):** Flags instances where PowerShell is launched with hidden or base64-encoded strings, a common tactic for script-based malware deployment.
