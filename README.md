## 🏗 SOC Telemetry & Engineering Matrix


| Analytics Domain | Platform Engine | Focus & Query Syntax | Enterprise Security Portfolio |
| :--- | :--- | :--- | :--- |
| 🛡 **Network Security Monitoring** | Splunk Enterprise | SPL & Advanced Event Chaining | [Enterprise Security Suite](./01-Splunk-Firewall-Dashboard) |
| 🔍 **Threat Detection** | Microsoft Sentinel | KQL & Multi-Source Correlation | [Threat Detection Workspace](./02-Microsoft-Sentinel-KQL) |
| 📊 **Log Analysis** | IBM QRadar | AQL & Privilege Auditing | *In Development* |
| 💻 **Endpoint Defense** | EDR Platforms | Rule Tuning & Playbook Design | *In Development* |

---

### 🌐 Enterprise Network Security Monitoring Suite (Splunk Enterprise)
This production-grade monitoring module utilizes the **BOTS v1 Dataset** to deliver centralized visibility into perimeter traffic patterns and network intrusions. It is split into two specialized monitoring components:

#### 1. 🧱 [Fortigate Firewall Traffic Analytics](./01-Splunk-Firewall-Dashboard)
* **Objective:** Monitors baseline perimeter traffic flow, inbound connection volumes, and geographic origins to detect early-stage reconnaissance.
* **Engineering Skills:** High-throughput data ingestion parsing, CIDR block filtering, top-talker network aggregation, and network volume trend lines.
* **Source Code:** [`fortigate_traffic_dashboard.xml`](./01-Splunk-Firewall-Dashboard)

#### 2. 🚨 [Suricata Intrusion Detection (IDS/IPS) Center](./01-Splunk-Firewall-Dashboard/suricata_ids_dashboard.xml)
* **Objective:** Real-time analysis of signature-based malicious activity, targeting patterns, and active protocol exploitation.
* **Engineering Skills:** Dynamic event-type schema normalization (using `coalesce`), high-severity threat categorization filtering, and nested data parsing (handling JSON sub-fields natively).
* **Source Code:** [`suricata_ids_dashboard.xml`](./01-Splunk-Firewall-Dashboard/suricata_ids_dashboard.xml)

---

### 🎯 Cloud & Hybrid Threat Detection Engine (Microsoft Sentinel)
This section houses production-ready **Kusto Query Language (KQL)** SIEM analytics designed to identify high-fidelity, actionable threats across enterprise infrastructure.

#### 1. 🔑 [Brute Force Account Takeover Detection](./02-Microsoft-Sentinel-KQL)
* **Objective:** Correlates consecutive Windows security event logon failures with a subsequent successful authentication event from the same entity to flag credential compromise.
* **Engineering Skills:** Multi-source dataset correlation using internal table variables (`let`), conditional behavioral threshold rules, memory-optimized inner joins, and entity mapping for SIEM automation.
* **Source Code:** [`brute_force_account_takeover.kql`](./02-Microsoft-Sentinel-KQL/brute_force_account_takeover.kql)



