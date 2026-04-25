# Lessons Learned

## What Worked
- Structured step-by-step lab execution made deployment and hardening manageable.
- Capturing evidence throughout the lab improved documentation quality and validation.
- Security baseline verification using SELinux, firewalld, and auditd strengthened understanding of layered controls.
- Phishing threat analysis and incident response scenarios reinforced how technical controls and analyst decision-making connect.

---

## What Was Challenging
- Rocky Linux package repository troubleshooting (Lynis package availability).
- Distinguishing “best first action” decisions in incident response scenarios.
- Interpreting exposed services from an attack surface perspective versus simply identifying open ports.
- Understanding how the same phishing scenario can support multiple attacker objectives.

---

## Security Concepts Reinforced
- Defense in Depth
- Least Privilege
- Mandatory Access Control (SELinux)
- Preventive vs Detective vs Corrective Controls
- Credential Access and Initial Access
- Attack Surface Reduction
- Security Logging and Monitoring
- Phishing Indicators and Social Engineering
- Incident Response Prioritization

---

## Real-World Relevance
- Demonstrated how Linux hardening supports security operations environments.
- Showed how analysts validate controls rather than assume they are functioning.
- Simulated realistic phishing triage and response decision-making.
- Reinforced that security work includes troubleshooting, analysis, and documentation, not just tool usage.
- Reflected common real-world tasks performed in SOC and security engineering environments.

---

## Improvements for Future Labs
- Expand service hardening by reviewing and disabling unnecessary services.
- Incorporate vulnerability scanning or host auditing tools in later labs.
- Add deeper IOC analysis and threat mapping in future phishing scenarios.
- Increase use of log analysis and detection-focused exercises.
- Continue improving analyst-style documentation and evidence organization.