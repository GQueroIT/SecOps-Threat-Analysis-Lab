# Lab 01 - Secure Linux Jump Box Deployment & Phishing Threat Analysis

## What This Lab Demonstrates
This lab demonstrates foundational security operations skills through Linux hardening, control validation, security analysis, and structured documentation.

---

## Objective
 Deploy and harden a Rocky Linux security operations jump box while performing introductory phishing threat analysis and documenting baseline security controls.

---

## Scenario
Simulated phishing email:
- fake Microsoft 365 password reset notice
- Urgent language
- Suspicious link
- Credential harvesting attempt

## Threat Summary
A simulated phishing email attempted to induce credential theft through a spoofed password reset notification.

## Indicators of Phishing
- Urgent social engineering language
- Suspicious hyperlink
- Domain spoofing attempt
- Credential harvesting objective

## Likely Attacker Objective
- Credential compromise
- Initial access
- Possible privilege escalation

## Potential Mitigations
- User awareness training
- MFA
- Email filtering
- SPF/DKIM/DMARC
- Conditional access controls

## Security Control Mapping
Preventive:
- Email filtering
- MFA

Detective:
- Alerting
- Log review

Corrective:
- Credential reset
- Incident response process

---

## Scope
This lab focuses on the following outcomes:
- Linux system deployment
- Initial host hardening
- Security baseline  validation
- Phishing threat analysis
- Security control mapping
- Evidence-driven documentation

---

## Concepts Covered
- Defense in Depth
- Least Privilege
- Mandatory Access Control (MAC)
- Host-Based Firewalling
- Security Logging and Monitoring
- Attack Surface Reduction
- Phishing Indicators
- Preventive, Detective, and Corrective Controls

---

## Tools Used
- Rocky Linux
- VirtualBox
- Bash
- firewalld
- SELinux
- auditd
- journalctl
- VirusTotal
- MXToolBox

---

## Threat Analysis
The phishing scenario simulated a credential harvesting attempt leveraging urgency, spoofing, and social engineering techniques to obtain unauthorized access. The scenario was analyzed using indicators of compromise, attacker objectives, and mapped mitigations.

---

## Security Controls

- Least Privilege
- Host firewall
- SELinux enforcement
- Reviewed Linux authentication and privilege escalation logs in /var/log/secure
- Validated sudo activity was being recorded
- Secure admin account separation

---

## Linux Security Baseline Checklist
- Patch management status 
- SELinux enforcing 
- firewalld active 
- auditd enabled 
- Non-root admin account 
- Root SSH disabled
- Dual NIC configuration documented

---

## Lab Architecture
Dual-NIC VM design:
- NAT adapter
- Host-only adapter
Validated dual-NIC architecture from the guest operating system:
- enp0s3 (NAT) active for outbound connectivity
- enp0s8 (host-only) staged for future segmented lab scenarios

---

## Procedure Performed
1. Downloaded and validated Rocky Linux 9 installation media
2. Deployed ROCKY-SEC01 virtual machine in VirtualBox
3. Configured dual-NIC architecture (NAT + host-only)
4. Created privileged non-root administrative account
5. Verified SELinux enforcement
6. Validated firewalld status
7. Verified auditd logging service
8. Reviewed authentication and sudo logs in /var/log/secure
9. Enumerated listening services using ss -tulnp
10. Reviewed enabled services for preliminary hardening analysis
11. Documented phishing threat scenario and mapped controls

---

## Findings
- Core security controls were operating as expected
- Authentication and privilege escalation activity was successfully logged
- Exposed listening services and non-essential enabled services were identified for future hardening
- Phishing scenario analysis highlighted credential theft risks and layered mitigations

---

### Preliminary Hardening Review Findings
Identified several non-essential enabled services for future review and potential attack surface reduction, including Bluetooth, Avahi, and CUPS.

---

## Mitigation Recommendations
- Review and disable unnecessary services (Bluetooth, Avahi, CUPS)
- Restrict SSH exposure and harden remote access
- Continue baseline hardening reviews
- Implement periodic audit and log review procedures
- Reinforce phishing protections through technical and administrative controls

---

## Verification & Validation
Validated:
- Hostname configuration
- Privileged sudo access
- SELinux enforcing mode
- firewalld active status
- auditd active status
- Network interfaces and dual-NIC configuration
- Listening services and enabled service inventory

---

## Technical Skills Demonstrated
- Linux Administration
- Security Hardening
- Log Analysis
- Attack Surface Review
- Threat Analysis
- Security Documentation

---

## Lessons Learned
- Validated SELinux mandatory access controls were operating in enforcing mode as part of the Linux security baseline.

---

## Evidence

This lab includes captured evidence documenting deployment, security baseline validation, threat analysis activities, and preliminary hardening review.

### Build and Installation Evidence
- 01-iso-selection.png — Rocky Linux installation media selection
- 02-vm-creation.png — Virtual machine creation in VirtualBox
- 03-vm-settings.png — VM resource and display configuration
- 04-media-validation.png — Installation media integrity validation
- 05-language-selection.png — Initial installer configuration
- 06-software-selection.png — Server with GUI package selection
- 07-network-hostname.png — Dual-NIC and hostname configuration
- 08-storage-partitioning.png — Automatic partitioning configuration
- 09-admin-user-creation.png — Administrative account creation
- 10-installation-start.png — Installation initiation
- 11-install-progress.png — Package installation progress

### Security Baseline Validation Evidence
- 12-first-login.png — Initial system access validation
- 13-hostname-validation.png — Host identity verification
- 14-privilege-escalation-validation.png — sudo privilege verification
- 15-system-patching.png — Patch management execution
- 16-selinux-validation.png — SELinux enforcing verification
- 17-firewalld-validation.png — Host firewall validation
- 18-auditd-validation.png — Audit logging service verification

### Security Analysis Evidence
- 19-auth-log-review.png — Authentication and sudo log review
- 20-network-interface-review.png — Network interface validation
- 21-package-repository-troubleshooting.png — Repository troubleshooting evidence
- 22-listening-services-review.png — Attack surface enumeration
- 23-enabled-services-review.png — Enabled service hardening review

### Evidence Highlights
Collected evidence supports validation of:
- Linux hardening controls
- Logging and monitoring functionality
- Attack surface review findings
- Phishing threat analysis documentation
- Baseline security verification procedures

---

## Files
- README.md
- threat-analysis-report.md
- linux-baseline-checklist.md
- design-decisions.md
- troubleshooting.md