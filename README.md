## 🏗 SOC Telemetry & Engineering Matrix


| Analytics Domain | Platform Engine | Focus & Query Syntax |
| :--- | :--- | :--- |
| **Continuous Monitoring** | Splunk Enterprise | Simple XML Design, Firewall (`fortigate_traffic`) & IDS/IPS (`suricata`) Logs |
| **Threat Detection** | Microsoft Sentinel | KQL, Multi-Source Correlation |
| **Log Analysis** | IBM QRadar | AQL, Privilege Auditing |
| **Endpoint Defense** | EDR | Rule Tuning, Playbook Design |


### Enterprise Network Security Monitoring Suite (Firewall & IDS/IPS)
* **Objective:** Centralized monitoring for perimeter traffic and network intrusions.
* **Log Sources:** BOTS v1 Dataset (`surcotype=fortigate_traffic`, `suricata`)
* **Key Components:** CIDR filtering, IP tracking, and alert mapping.
