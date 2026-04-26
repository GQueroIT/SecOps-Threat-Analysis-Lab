# Tool Exposure

## Splunk
Purpose:
Used to ingest and correlate authentication and privilege events.

### Skills Practiced:
- Event hunting
- Regex field extraction
- Statistical event analysis
- Source concentration analysis
- Privilege activity correlation

### Queries Practiced:

index=main sshd

index=main "Accepted password"

index=main ("Accepted password" OR "Failed password")
| stats count by host

index=main "Accepted password"
| rex "from (?<source_ip>\\S+)"
| stats count by source_ip

index=main sudo
| stats count by COMMAND

### Real-World Use Case
Supports SIEM-based threat detection and investigation workflows.
