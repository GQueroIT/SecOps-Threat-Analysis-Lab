# Threat Analysis Report

## Threat Name
Microsoft Email Phishing

---

## Description
A phishing campaign leveraging brand impersonation and social engineering attempted to induce credential theft through a spoofed Microsoft password reset notification.

---

## Threat Vector
The attacker used a phishing email containing a fraudulent link designed to harvest credentials. The attack used typosquatting, urgency, and fear-based pretexting to pressure the victim into taking action.

---

## Indicators of Compromise (IOC)
- Suspicious typosquatted sender domain
- Fraudulent credential harvesting URL
- Urgent account lockout lure
- Brand impersonation
- Suspicious login/MFA prompts
- Potential unauthorized sign-in attempts

---

## Potential Impact
Confidentiality:
- Exposure of user credentials
- Potential unauthorized access to sensitive data

Integrity:
- Potential unauthorized modification of systems or data

Availability:
- Possible account lockout or disruption of access

---

## Detection Opportunities
- Multi-factor authentication (MFA) prompts indicating suspicious sign-in activity
- Email security filtering
- Suspicious domain reputation checks
- User-reported phishing emails
- Authentication and sign-in log monitoring
- SIEM alerting for anomalous login attempts

---

## Mitigation Controls

Preventive Controls
- Multi-factor authentication (MFA)
- Email filtering controls
- SPF, DKIM, and DMARC
- Security awareness training
- Conditional access policies

Detective Controls
- Authentication log review
- Security monitoring and alerting
- IOC analysis
- Phishing reporting processes

Corrective Controls
- Password reset
- Session/token revocation
- Incident response procedures

---

## Response Recommendations
1. Reset or disable potentially compromised credentials
2. Review authentication activity for suspicious sign-ins
3. Block malicious sender/domain
4. Investigate potential endpoint impact if link was accessed
5. Notify users and report phishing indicators
6. Update detections or controls based on findings

---

## Lessons Learned
- Typosquatting and urgency are common phishing indicators
- Credential harvesting attempts may support both credential access and initial access objectives
- MFA can act as an effective preventive control
- Layered defenses reduce likelihood of successful compromise
- Incident response priorities vary based on suspected identity versus endpoint compromise