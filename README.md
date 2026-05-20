## 📂 Active Engineering Projects

### [01. Fortigate Firewall Continuous Monitoring Suite](./01-Splunk-Firewall-Dashboard)
* **Objective:** Engineering a centralized, simple XML monitoring dashboard within Splunk to baseline perimeter traffic and isolate malicious inbound scanning.
* **Log Sources:** BOTS v1 Dataset (`sourcetype=fortigate_traffic`)
* **Key Components:** RFC 1918 CIDR filtering, Logarithmic Y-axis chart scaling, Protocol distribution mapping.

### [02. Multi-Platform Identity Threat Detection (ITDR)](./02-SIEM-Threat-Hunting)
* **Objective:** Deploying advanced KQL, SPL, and AQL correlation rules to flag sophisticated identity-centric attacks before credential abuse occurs.
* **Log Sources:** MicrosoftEntraID SignInLogs, Okta Syslog, AppAudit Trails
* **Key Components:** MFA Fatigue push-spam correlation, unauthorized capability modifications, malicious privilege escalation tracking.

### [03. Adversarial Simulation & Detection Validation](./03-Attack-Simulation-Labs)
* **Objective:** Executing automated attack simulations in sandboxed networks to baseline indicators of compromise and validate alerting rules.
* **Tools Used:** Hydra Brute-Force, Metasploit Framework, BeEF Browser Exploitation
* **Key Components:** Log telemetry parsing, rule tuning, alert fatigue mitigation.
