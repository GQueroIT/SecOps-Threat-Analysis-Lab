# Threat Analysis Report

## Threat Name
SSH Password Guessing Attack

---

## Description

A simulated password guessing attack targeted an exposed SSH service through repeated authentication attempts against a local administrative account. Log telemetry showed activity consistent with brute-force behavior.

---

## Threat Vector

Remote authentication abuse over SSH (TCP/22).

---

## Indicators of Compromise

- Repeated failed password attempts
- Multiple sshd authentication failures
- Single source host generating repeated events
- Credential attack artifacts in /var/log/secure

---

## Attack Evidence

- Source Host
192.168.10.1
- Target Account 
gabrieladmin
- Failed Password Events
12 observed attempts
- MITRE ATT&CK Mapping
- T1110 Brute Force
- T1110.001 Password Guessing
- T1078 Valid Accounts

---

## Risk Assessment

Likelihood: Medium
Impact: High if successful
Overall Risk: Medium-High

---

## Recommended Mitigations

- Enforce MFA where possible
- Implement Fail2Ban
- Use SSH keys over passwords
- Configure login attempt thresholds
- Monitor failed login thresholds in Splunk

## Security Control Gap Identified

Control Tested:
Fail2Ban automated brute-force protection

Observation:
The control was deployed and configured, but response actions (IP banning) did not trigger during simulated attack activity.

Risk:
Partial control effectiveness may allow continued password attack attempts if tuning is incomplete.

Recommendation:
Perform filter tuning, log parsing validation, and repeat enforcement testing in a dedicated follow-up lab.