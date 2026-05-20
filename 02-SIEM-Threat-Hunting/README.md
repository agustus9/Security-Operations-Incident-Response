# 🔍 Multi-Platform Threat Hunting & Log Analysis

## 📋 Scenario & Business Problem
Adversaries frequently use brute-force tools to guess passwords or spam users with multi-factor authentication (MFA) prompts hoping they click approve out of frustration. Once inside an account, they try to modify security parameters or elevate their privileges. 

If these events are buried in millions of standard logs, defenders miss them. This project builds clean, intermediate-level hunting queries to parse authentication logs and administrative audit trails to surface active brute-force attempts, MFA anomalies, and unauthorized profile alterations.

## 💡 Solution Architecture
This project implements focused hunting logic across **Microsoft Sentinel (KQL)**, **Splunk (SPL)**, and **IBM QRadar (AQL)**.
1. **MFA Spam Detection:** Identifies instances where an external account generates a high volume of MFA errors in a short period.
2. **Brute-Force Aggregation:** Groups failed sign-in logs by source IP addresses to flag brute-force scanning metrics.
3. **Privilege Tampering Audits:** Monitors system logs for specific administrative actions like role modifications or capability assignments.

## 🏗️ Technical Components
* **Query Standards:** Microsoft Sentinel KQL, Splunk SPL, IBM QRadar AQL
* **Log Sources Evaluated:** MicrosoftEntraID SignInLogs, Okta Syslog, Linux/App Audit Trails
* **Framework Alignment:** MITRE ATT&CK (Credential Access: T1110 - Brute Force, T1621 - Multi-Factor Authentication Request Generation)

---

## 🛠️ Intermediate Threat Hunting Queries

### Query 1: Microsoft Sentinel (KQL) - Password Spraying & Brute Force Hunting
This query monitors cloud sign-in logs to identify any unique external IP addresses that have generated more than 10 failed login attempts within a specific evaluation window.

```kusto
SigninLogs

| where ResultType == "50126" // Protocol error code for invalid username or password
| summarize FailureCount = count() by IPAddress, Location, UserPrincipalName
| where FailureCount > 10

| sort by FailureCount desc
```

### Query 2: Splunk (SPL) - Okta Multi-Factor Authentication (MFA) Anomalies
This query scans the Okta system logs to look for accounts experiencing a high count of authentication rejections or failures, highlighting a potential MFA fatigue or brute-force attack.

```splunk
index=security sourcetype="okta:system:log" displayMessage="*Authentication failed*" OR displayMessage="*MFA*REJECT*"
| stats count as FailureCount by actor.alternateId, client.ipAddress, displayMessage
| where FailureCount > 5
| sort - FailureCount
```

### Query 3: IBM QRadar (AQL) - Administrative Privilege Alteration Tracking
This query monitors system logs for events containing actions related to role creations, capability assignments, or group changes to detect potential out-of-band privilege modifications.

```aql
SELECT username AS 'Admin User', IdentityName AS 'Target Account', EventName(eventid) AS 'Action', DATEFORMAT(starttime, 'yyyy-MM-dd HH:mm:ss') AS 'Event Time'
FROM events
WHERE (payload CONTAINS 'addRole' OR payload CONTAINS 'CapabilityAssignment' OR payload CONTAINS 'GroupModification')
ORDER BY starttime DESC
```

---

## 🚀 How to Deploy & Run
1. **For Azure/Sentinel:** Navigate to **Microsoft Sentinel** -> **Logs**, paste the KQL query, and select your desired time range to hunt for outliers.
2. **For Splunk:** Paste the SPL query directly into the Search bar inside the **Search & Reporting** app window.
3. **For QRadar:** Go to the **Log Activity** tab, select **Advanced Search** from the search options bar, paste the AQL query, and hit search.
