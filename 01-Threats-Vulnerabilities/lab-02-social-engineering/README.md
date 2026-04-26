# Lab 02 — Password Attacks, Authentication Abuse & Credential Defense

## Objective

Simulate and analyze a password-based attack against an SSH service, generate evidence from host logs and SIEM analysis, identify indicators of compromise, and document defensive controls for credential abuse.

---

## Technologies Used

* Rocky Linux
* Ncrack
* Splunk Enterprise
* Linux Secure Logs (`/var/log/secure`)
* SCP
* Fail2Ban (Conceptual Mitigation)

---

## Scenario

A simulated brute-force/password guessing attack was launched against an SSH service running on Rocky Linux. Authentication attempts were captured in secure logs, transferred to the host system, ingested into Splunk, and analyzed to validate detection capability.

---

## Attack Simulation

### Attack Command Used

```bash
ncrack -U gabrieladmin -P badpass.txt ssh://192.168.10.1
```

### Attack Characteristics Observed

* Repeated failed SSH authentication attempts
* Multiple password guesses against a single account
* Source host correlation
* Log artifacts generated for SIEM detection

---

## Detection & Analysis

### Evidence Sources

* Host Authentication Logs
* Splunk Event Correlation
* Wireshark Packet Observation

### Splunk Queries Used

**Query 1 — SSH Events**

```spl
index=main sshd
```

**Query 2 — Authentication Failures**

```spl
index=main "authentication failure"
```

**Query 3 — Failed Password Events**

```spl
index=main "Failed password"
```

**Query 4 — Count Failed Attempts**

```spl
index=main "Failed password"
| stats count
```

**Query 5 — Source Correlation**

```spl
index=main ("authentication failure" OR "Failed password")
| stats count by rhost
```

---

## Findings

### Indicators Identified

* Source IP: 192.168.10.1
* Target User: gabrieladmin
* Service Targeted: SSH
* Failed Attempts Observed: 12

### Evidence Summary

Splunk analysis confirmed repeated failed authentication attempts from a single source host against one account, consistent with password guessing activity.

---

## Threat Analysis

### Attack Classification

This activity aligns with:

* Brute Force
* Password Guessing
* Authentication Abuse

### MITRE ATT&CK Mapping

* T1110 — Brute Force
* T1110.001 — Password Guessing
* T1078 — Valid Accounts

---

## Defensive Controls

### Preventive Controls

* Strong password policy
* Multi-factor authentication
* SSH key authentication
* Account lockout controls

### Detective Controls

* Splunk failed login monitoring
* Authentication anomaly detection
* Secure log review

## Defensive Control Validation

As part of this lab, an automated defensive control was deployed using Fail2Ban to mitigate SSH brute-force activity.

Validation Results:
- SSH protection jail was configured and enabled
- Simulated password attack activity was generated using Ncrack
- Authentication abuse was successfully detected and correlated in Splunk
- Fail2Ban enforcement logic did not trigger bans during validation
- Additional filter tuning is required before the control can be considered fully operational

### Key Finding
Detection controls were validated successfully.
Preventive control deployment was successful.
Preventive control response requires further tuning and testing.

### Corrective Controls

* Fail2Ban blocking
* Source IP restriction
* Credential reset procedures

---

## Tool Exposure

### Ncrack

Used to simulate password guessing behavior against SSH.

### Splunk

Used to ingest authentication logs, search attack indicators, and quantify failed login activity.

---

## Lessons Learned

* Credential attacks leave strong evidence in authentication logs.
* SIEM correlation significantly improves detection visibility.
* SSH encryption limits payload visibility in packet captures.
* Defense-in-depth is essential against password attacks.

---

## Future Improvements

* Implement Fail2Ban enforcement validation
* Create Splunk alerting for failed authentication thresholds
* Simulate password spraying scenario
* Expand lab into incident response use case

---

## Summary

This lab successfully simulated an SSH password attack, captured authentication evidence, analyzed indicators in Splunk, and mapped practical defensive controls aligned with real-world credential attack detection.
