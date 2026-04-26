# Lessons Learned

## What Worked
- Simulated suspicious authentication behavior generated strong detection artifacts.
- Splunk correlation successfully validated authentication and privileged activity.
- Regex extraction improved visibility into source IP concentration.
- Sudo telemetry provided valuable post-authentication evidence.

---

## What Was Challenging
- Cross-platform SCP log transfer troubleshooting required layered problem solving.
- Field extraction issues in Splunk required adapting search logic.
- Linux permissions and path syntax issues required troubleshooting.

---

## Security Concepts Reinforced
- Valid Accounts Abuse
- Authentication anomaly detection
- Least privilege
- Log correlation
- Defense in depth
- Behavioral analysis

---

## Real-World Relevance
This lab simulated realistic analyst workflows involving detection, investigation, and correlation of suspicious authentication behavior and privilege use.

---

## Improvements for Future Labs
- Add alert thresholds for repeated successful logins
- Expand into account misuse incident response scenario
- Simulate lateral movement indicators
- Add Splunk alert creation for anomalous authentication behavior
