# Threat Analysis Report

## Threat Name
Valid Accounts Abuse and Suspicious Privileged Activity

---

## Description
Simulated suspicious authentication activity involving repeated successful SSH logins, failed authentication attempts, and post-authentication privileged command execution to analyze indicators associated with valid account abuse and suspicious account behavior.

---

## Threat Vector
Attacker simulation leveraged repeated SSH authentication activity against a Linux host using a valid account, followed by privileged command execution through sudo. Activity generated authentication artifacts, source concentration indicators, and privileged command telemetry for detection validation.

---

## Threat Classification
Activity aligns with:

- Valid Accounts Abuse
- Suspicious Authentication Behavior
- Privilege Use Following Access
- Credential Abuse Indicators

---

## Indicators Identified

Source IPs Observed:
- 192.168.10.10
- ::1

Target Account:
- gabrieladmin

Service Targeted:
- SSH

Indicators Observed:
- Repeated successful logins
- Failed password attempts
- Session open/close activity
- Concentrated authentication activity from one source
- Sudo privileged command execution
- /bin/whoami command artifact

---

## MITRE ATT&CK Mapping

T1078 — Valid Accounts

T1110.001 — Password Guessing

Potential Follow-On Behavior:
Privilege use following valid account access

---

## Splunk Analysis Findings

Authentication Source Distribution:
- 192.168.10.10 generated 7 successful authentication events
- ::1 generated 2 successful authentication events

Privileged Command Findings:
- /bin/whoami observed twice in sudo telemetry

Key Correlated Activity:
Repeated successful authentication activity from a concentrated source was correlated with privileged command execution under root context.

---

## Security Impact
This activity demonstrates how valid credentials may be abused without exploiting software vulnerabilities and how suspicious post-authentication behavior can be identified through log correlation and command telemetry.

---

## Defensive Controls

Preventive Controls
- Multi-factor authentication
- SSH key authentication
- Least privilege enforcement
- Strong password policy
- Account lockout controls

Detective Controls
- Splunk authentication monitoring
- Source concentration analysis
- Privileged command monitoring
- Secure log review
- Authentication anomaly detection

Corrective Controls
- Account investigation and reset
- Source IP restriction
- Privileged activity review
- Access review and containment

---

## Key Finding
Detection controls successfully identified suspicious authentication patterns, concentrated source activity, and privileged command execution following account access.
