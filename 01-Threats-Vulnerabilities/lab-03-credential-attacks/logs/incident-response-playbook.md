# Incident Response Playbook

## Scenario
Potential valid account abuse with suspicious privileged activity detected through authentication and sudo telemetry.

---

## Detection
Indicators triggering investigation:

- Repeated SSH logins from concentrated source
- Failed and successful authentication mixture
- Privileged sudo command execution
- Unexpected administrative activity

---

## Identification
Validate:

- Source IP involved
- User account activity
- Authentication frequency
- Privileged commands executed
- Related session activity

Artifacts Reviewed:
- /var/log/secure
- Splunk SSH events
- Splunk sudo telemetry
- Source IP extraction results

---

## Containment
Immediate Actions

- Investigate account legitimacy
- Restrict suspicious source IP if necessary
- Disable or monitor affected account
- Review privileged access activity

---

## Eradication
- Reset credentials if compromise suspected
- Review SSH access controls
- Validate sudo privileges
- Tune detection thresholds if needed

---

## Recovery
- Restore account access securely
- Confirm no unauthorized persistence
- Continue monitoring for recurring activity

---

## Lessons Applied
- Authentication events should be correlated with post-auth activity
- Source concentration may indicate anomalous behavior
- Privileged command telemetry provides valuable detection context
