## Mitigation

### Defensive Control Validation
Several defensive controls were identified and partially validated against the simulated activity.

Preventive Mitigations
- Enforce multi-factor authentication for SSH and privileged access
- Replace password authentication with SSH key authentication
- Apply least privilege to reduce unnecessary sudo capabilities
- Implement account lockout or throttling controls
- Restrict SSH access through source IP allowlisting where appropriate

Detective Mitigations
- Configure Splunk alerts for repeated successful login thresholds
- Alert on failed + successful authentication sequences from same source
- Monitor sudo command execution, especially sensitive administrative commands
- Baseline normal authentication behavior to detect anomalies
- Correlate authentication activity with privileged command telemetry

Corrective Mitigations
- Investigate and validate account legitimacy
- Reset credentials if account misuse suspected
- Review and tighten sudo permissions
- Block or restrict suspicious source IPs
- Tune detections and response playbooks based on observed indicators

### Defensive Control Opportunities Identified
Potential detections that could be implemented:

Authentication Anomaly Alert Example
Trigger alert if:
- More than X successful logins from one source within defined timeframe
- Failed password attempts followed by successful authentication
- Privileged commands executed shortly after authentication

Privilege Use Monitoring Example
Alert on:
- sudo command execution by unusual users
- High-risk commands run through sudo
- Privilege activity outside expected baseline

### Key Mitigation Finding
The lab demonstrated that suspicious valid-account behavior may be identified through layered monitoring controls, and that authentication telemetry combined with privileged activity monitoring strengthens defensive coverage.
