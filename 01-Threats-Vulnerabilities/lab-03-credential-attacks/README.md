# Lab 03 — Valid Accounts Abuse & Privileged Activity Detection

## Objective
Simulate and analyze suspicious authentication behavior involving repeated SSH logins, failed password attempts, and privileged command execution, then validate detection through host logs and Splunk correlation.

---

## Technologies Used
- Rocky Linux
- Splunk Enterprise
- SSH / OpenSSH
- Linux Secure Logs (/var/log/secure)
- SCP
- Sudo Logging
- Fail2Ban (Defensive Control Exposure)

---

## Scenario
A suspicious authentication activity scenario was simulated involving repeated successful and failed SSH logins against a Linux host followed by privileged command execution using sudo. Authentication and command artifacts were captured in secure logs, securely transferred to the host system, ingested into Splunk, and analyzed to validate detection of valid account abuse and post-authentication suspicious activity.

---

## Attack Simulation

### Activity Simulated
Repeated SSH logins were generated to simulate suspicious valid account access behavior.

Commands Used

ssh localhost
exit

ssh localhost
exit

ssh localhost
exit

Additional failed authentication attempts were captured during testing.

---

## Privileged Activity Simulation
Command Executed

sudo whoami

Purpose:
Simulate suspicious privileged activity occurring after account access.

---

## Detection & Analysis

### Evidence Sources
- Linux secure authentication logs
- Splunk event correlation
- Source IP extraction analysis
- Sudo command telemetry

---

## Splunk Queries Used

### Broad SSH Activity Hunt
index=main sshd

### Successful Authentication Events
index=main "Accepted password"

### Authentication Event Frequency
index=main ("Accepted password" OR "Failed password")
| stats count by host

### Source IP Extraction
index=main "Accepted password"
| rex "from (?<source_ip>\\S+)"
| stats count by source_ip

Results:
- 192.168.10.10 — 7 events
- ::1 — 2 events

### Privileged Command Analysis
index=main sudo
| stats count by COMMAND

Key Finding:
- /bin/whoami observed through sudo telemetry

---

## Findings
Indicators identified:
- Repeated successful authentication events
- Failed password attempts
- Concentrated authentication activity from one source
- Post-authentication privileged command execution
- Session lifecycle activity (open, disconnect, close)

Correlated Activity Observed:
Successful account access was correlated with privileged command usage under root context.

---

## MITRE ATT&CK Mapping
- T1078 — Valid Accounts
- T1110.001 — Password Guessing

---

## Defensive Controls

### Preventive
- Multi-factor authentication
- SSH key authentication
- Least privilege
- Account lockout thresholds

### Detective
- Splunk authentication monitoring
- Source concentration analysis
- Privileged command monitoring
- Authentication anomaly alerting

### Corrective
- Credential reset procedures
- Source IP restrictions
- Privileged access review

---

## Tool Exposure

### Splunk
Used for:
- Event hunting
- Regex field extraction
- Authentication correlation
- Privileged activity analysis

### Linux / SSH
Used for:
- SSH authentication simulation
- Secure log analysis
- SCP secure log transfer troubleshooting

---

## Lessons Learned
- Authentication activity gains stronger context when correlated with post-auth privileged behavior.
- Regex extraction in Splunk improves investigation visibility.
- Source concentration analysis can support anomaly detection.
- Secure log transfer troubleshooting reinforced networking, permissions, and SCP workflow knowledge.

---

## Future Improvements
- Add Splunk alert thresholds for suspicious login frequency
- Expand into valid account abuse incident response scenario
- Simulate lateral movement indicators
- Add detection rules for post-auth privileged activity

---

## Files
- README.md
- analysis/threat-analysis-report.md
- analysis/pbq-analysis.md
- mitigation/security-control-mapping.md
- mitigation/incident-response-playbook.md
- evidence/screenshots/
- logs/secure-copy.log
- notes/lessons-learned.md

---

## Summary
This lab simulated suspicious valid-account activity through repeated SSH authentication, failed password attempts, and privileged command execution. Authentication evidence was analyzed through Splunk hunting, source IP extraction, and command correlation to validate detection of suspicious authentication and post-authentication activity.
