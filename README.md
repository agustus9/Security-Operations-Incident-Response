# 🛡️ Enterprise Security Operations & Incident Response Lab

A production-grade engineering sandbox documenting high-fidelity detection engineering, automated incident response playbooks, and continuous compliance monitoring architectures across multi-vendor SIEM and EDR platforms.

---

## 🏗️ SOC Telemetry & Engineering Matrix

This repository tracks active security analytics, parsing raw infrastructure logs to isolate indicators of compromise (IOCs) and reduce adversary dwell time.


| Analytics Domain | Platform Engine | Focus & Query Syntax |
| :--- | :--- | :--- |
| **Continuous Monitoring** | Splunk Enterprise | Simple XML Dashboard Design, Volumetric Scaling, Firewall Logs |
| **Threat Detection** | Microsoft Sentinel | Kusto Query Language (KQL), Multi-Source Event Correlation |
| **Log Analysis** | IBM QRadar | Ariel Query Language (AQL), Privilege Alteration Auditing |
| **Endpoint Defense** | EDR Controls & DLP | Rule Tuning, Playbook Design, Data Exfiltration Prevention |

---

## 📂 Active Engineering Projects

### [01. Fortigate Firewall Continuous Monitoring Suite](./01-Splunk-Firewall-Dashboard)
* **Objective:** Engineering a centralized, simple XML monitoring dashboard within Splunk to baseline perimeter traffic and isolate malicious inbound scanning.
* **Log Sources:** BOTS v1 Dataset (`sourcetype=fortigate_traffic`)
* **Key Components:** RFC 1918 CIDR filtering, Logarithmic Y-axis chart scaling, Protocol distribution mapping.

### [02. Multi-Platform Identity Threat Detection (ITDR)](./02-SIEM-Threat-Hunting)
* **Objective:** Deploying advanced KQL and SPL correlation rules to flag sophisticated identity-centric attacks before credential abuse occurs.
* **Log Sources:** MicrosoftEntraID SignInLogs, Okta Syslog, AppAudit Trails
* **Key Components:** MFA Fatigue push-spam correlation, unauthorized capability modifications, malicious privilege escalation tracking.

### [03. Adversarial Simulation & Detection Validation](./03-Attack-Simulation-Labs)
* **Objective:** Executing automated attack simulations in sandboxed networks to baseline indicators of compromise and validate alerting rules.
* **Tools Used:** Hydra Brute-Force, Metasploit Framework, BeEF Browser Exploitation
* **Key Components:** Log telemetry parsing, rule tuning, alert fatigue mitigation.

---

## ⚙️ Core Technical Competencies Demonstrated
* **Query Optimization:** Proficient in designing performant data queries utilizing Splunk SPL (`stats`, `streamwindow`), Sentinel KQL (`join`, `extend`), and QRadar AQL.
* **Framework Alignment:** Mapping security monitoring controls directly against the **MITRE ATT&CK** matrix and **NIST SP 800-53** continuous monitoring guidelines.
* **Triage Acceleration:** Engineering dashboards and alert rules that flatten background noise, cutting down tier-one alert fatigue by optimizing data visualizations.
