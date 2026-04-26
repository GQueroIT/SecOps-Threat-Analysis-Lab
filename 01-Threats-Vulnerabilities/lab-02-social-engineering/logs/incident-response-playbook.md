# Incident Response Playbook

## Incident Type
SSH Password Guessing / Brute Force Attack

--------------------------------------------------

## Purpose
Provide a structured process to detect, contain, investigate, eradicate, and recover from SSH password guessing activity.

--------------------------------------------------

## Detection

### Indicators of Attack
- Repeated failed SSH login attempts
- Authentication failures against the same account
- Multiple attempts from one source IP
- Increased failed login volume over short time periods

### Detection Queries

Query 1
index=main "Failed password"

Query 2
index=main ("authentication failure" OR "Failed password")
| stats count by rhost

Query 3
index=main "Failed password"
| stats count

--------------------------------------------------

## Initial Triage

Questions to Answer

- Is the activity ongoing?
- Is a single account or multiple accounts targeted?
- Did any authentication succeed?
- Is a privileged account involved?
- Is the source internal or external?

Evidence to Preserve

- Splunk search results
- Secure log events
- Source IP information
- Failed login timestamps
- Packet capture evidence if applicable

--------------------------------------------------

## Containment

Immediate Actions

1. Block or restrict source IP if malicious.

2. Verify Fail2Ban status.

Commands:

sudo systemctl status fail2ban

sudo fail2ban-client status sshd

3. Restrict SSH access to trusted hosts if necessary.

--------------------------------------------------

## Investigation

Review for:

- Successful logins after failed attempts
- Privilege escalation attempts
- Additional targeted accounts
- Recurring attack patterns

MITRE ATT&CK Mapping

T1110  Brute Force

T1110.001 Password Guessing

T1078 Valid Accounts

--------------------------------------------------

## Eradication

If compromise is suspected:

- Reset credentials
- Disable affected account temporarily
- Review SSH configuration
- Remove attacker access if obtained

Recommended SSH Hardening

PermitRootLogin no

PasswordAuthentication no

--------------------------------------------------

## Control Validation Finding

Validation during this exercise identified a control-gap condition:

- Detection mechanisms functioned as expected
- Automated prevention did not fully trigger
- Further tuning is required before relying on automated blocking

Follow-Up Action:
Escalate for control engineering review and retest after tuning.

--------------------------------------------------

## Recovery

Recovery Actions

- Restore normal access if safe
- Increase monitoring temporarily
- Validate controls are functioning
- Continue watching for repeat activity

--------------------------------------------------

## Post-Incident Improvements

Implement or Improve

- Strong password policies
- Account lockout thresholds
- MFA
- Fail2Ban tuning
- Splunk alerting
- SSH key authentication

Suggested Alert Threshold

Trigger alert for:

5 failed SSH login attempts from one source within 5 minutes

--------------------------------------------------

## Escalation Criteria

Escalate if:

- Successful login follows repeated failures
- Privileged accounts are targeted
- Multiple users are targeted
- Attack persists after containment
- Lateral movement indicators appear

Escalate To

- Security Operations
- System Administration
- Incident Response Lead

--------------------------------------------------

## Lessons Learned

What Worked

- Splunk correlation identified attack activity
- Authentication logs provided clear evidence
- Source attribution was possible

Improvement Opportunities

- Add automated blocking
- Build detection alerting
- Improve SSH hardening baseline
- Expand response automation

--------------------------------------------------

## Expected Outcome

- Attack detected
- Source identified
- Activity contained
- Credentials protected
- Defensive posture improved