# Daily Study Log

## Day Number
1

---

## Topics Studied
- Phishing indicators and typosquatting
- Attack vectors vs attacker objectives
- Initial Access and Credential Access
- Preventive, detective, and corrective controls
- Linux security baseline concepts
- SELinux, firewalld, auditd fundamentals
- Attack surface reduction principles

---

## Labs Completed
- Rocky Linux jump box deployment
- Linux hardening baseline validation
- Authentication log review
- Listening services attack surface analysis
- Phishing threat analysis scenario
- Incident response triage mini scenarios

---

## Questions Practiced

1. What phishing indicators were present in the simulated Microsoft 365 phishing email?

2. Which attack chain phases did the phishing scenario support, and why?
- Initial Access
- Credential Access
- Potential follow-on Privilege Escalation discussion

3. What is the difference between an attack vector and an attacker objective?

4. Incident Response Scenario:
A user clicked the phishing link, entered credentials, and received unexpected MFA prompts.
What should be the first response priority?

5. Incident Response Scenario:
A user clicked the malicious link but did not enter credentials.
How does the response priority change and why?

6. If MFA blocked attacker login after stolen credentials were used, is this:
- Successful compromise
- Prevented compromise
- Attempted compromise
Explain why.

7. Which observed security controls in the lab were preventive versus detective controls?

8. Which exposed or enabled services appeared to be possible hardening candidates and why?
- CUPS
- Avahi
- Bluetooth

9. How did dual-NIC architecture support future segmentation or security lab scenarios?

10. How did defense in depth appear in both the Linux hardening work and phishing scenario?

---

## Weak Areas Identified
- Incident response prioritization decision-making
- Service hardening considerations for Linux
- Documentation language & structure
- Incident response prioritization “best first action” questions

---

## Notes
Key finding:
Layered security controls significantly reduce likelihood of successful compromise.

Interesting findings:
- CUPS and Avahi identified as potential hardening review candidates.
- MFA can serve as both preventive control and detection opportunity.

---

## Tomorrow's Focus
- Service hardening and attack surface reduction
- Vulnerability scanning concepts
- Malware analysis fundamentals