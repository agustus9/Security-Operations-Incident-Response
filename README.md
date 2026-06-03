# Security Operations & Incident Response Sandbox

## SOC Telemetry & Engineering Matrix


| Analytics Domain | Platform Engine | Focus & Query Syntax | Enterprise Security Portfolio |
| :--- | :--- | :--- | :--- |
| **Network Security Monitoring** | Splunk Enterprise | SPL & Event Chaining | [Enterprise Security Suite](./01-Splunk-Firewall-Dashboard) |
| **Threat Detection** | Microsoft Sentinel | KQL & Multi-Source Correlation | [Threat Detection Workspace](./02-Microsoft-Sentinel-KQL) |
| **Log Analysis** | IBM QRadar | AQL & Privilege Auditing | [Log Analysis Workspace](./03-IBM-QRadar-AQL) |
| **Endpoint Defense** | EDR / Sysmon | Behavior Tuning & Rule Design | [Endpoint Defense Workspace](./04-Endpoint-Defense) |

---

### Enterprise Network Security Monitoring Suite (Splunk Enterprise)
Uses the BOTS v1 dataset to provide visibility into perimeter traffic patterns and network intrusions.
* [**Fortigate Firewall Traffic Analytics**](./01-Splunk-Firewall-Dashboard/fortigate_blocked_countries.json): Monitors perimeter traffic flow, connection volumes, and geographic origins to flag suspicious reconnaissance using `iplocation` and field filters.
* **[Suricata Intrusion Detection (IDS/IPS) Center](./01-Splunk-Firewall-Dashboard/suricata_ids_dashboard.xml):** Provides real-time analysis of signature-based scanning activity, targeting patterns, and protocol anomalies.

---

### Cloud & Hybrid Threat Detection Engine (Microsoft Sentinel)
Contains active Kusto Query Language (KQL) analytics designed to identify actionable threats across cloud and enterprise infrastructure.
* **[Brute Force Account Takeover Detection](./02-Microsoft-Sentinel-KQL):** Correlation logic that pairs consecutive Windows security event logon failures with a subsequent successful authentication event from the same account.

---

### Enterprise Log Analysis Module (IBM QRadar)
Log parsing queries using Ariel Query Language (AQL) to monitor internal threats and unexpected configuration changes across Linux environments.
* **[Privilege Escalation & Sudo Auditing](./03-IBM-QRadar-AQL):** Tracks non-root accounts executing administrative commands via `sudo` to catch potentially compromised users or policy violations.

---

### Behavioral Endpoint Defense Workspace (EDR/Sysmon)
Detection engineering patterns written in Sigma/YAML syntax focusing on process tracking, parent-child process validation, and endpoint visibility.
* **[Suspicious Encoded PowerShell Execution](./04-Endpoint-Defense):** Detects instances where PowerShell is launched with hidden or base64-encoded strings to bypass standard security filters.
