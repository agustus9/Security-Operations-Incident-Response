# 🔍 Microsoft Sentinel KQL - Brute Force Account Takeover

## 🎯 Detection Objective
Identifies Windows hosts experiencing brute-force or password-spraying activity that terminates in a successful system logon, mapping directly to MITRE ATT&CK Credential Access (TA0006).

## 🔍 Logic Breakdown
* **Thresholding:** Isolates source IPs generating 5 or more distinct logon failures (Event ID 4625) inside a 1-hour window.
* **Correlation:** Uses an `inner join` operation to cross-reference those specific bad actors against successful logins (Event ID 4624).
