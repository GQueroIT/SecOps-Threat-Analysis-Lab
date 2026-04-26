# Daily Study Log

## Day Number
2

---

## Topics studied

### Password Attack Types
- Brute Force: systematically tries all possible combinations
- Dictionary Attack: uses wordslists or common passwords
- Password Spraying: one common password against many accounts (helps to avoid lockouts)
- Credential Stuffing: reused breached credentials tested across sites
- Rainbow Table Attack: uses precomputed hashes to reverse weakly hashed passwords
- Offline Hash Cracking: attacker steals hashes (like NTLM) and cracks offline
- Hybrid Attacks: dictionary and mutations (Spring-Spring2025!)
- Pass-the-Hash (PtH): using stolen hash without knowing plaintext password
- Kerberoasting: abusing Active Directory service tickets to crack service account password offline

### Authentication Attacks
- MFA fatigue attacks
- Session hijacking
- Replay attacks
- Token theft
- Adversary-in-the-middle (AiTM) phishing
- Privilege escalation via weak authentication

### Defensive Concepts
- Salted hashing
- Password policies
- Account lockout thresholds
- MFA
- Passwordless authentication
- Privileged Access Management (PAM)
- Least Privilege
- Conditional access
- Honeypot accounts / canary credentials

---

## Lab Completed

---

## Questions Practiced
- What makes brute force different from password spraying and dictionary attacks?
- A security analyst notices repeated authentication attempts against hundreds of user accounts. Each account receives only one failed login attempt every thirty minutes, and the attempted password is identical across all accounts. What attack is MOST likely occurring? 
- A company discovers an attacker copied password hashes from a compromised domain controller and is attempting to recover plaintext passwords without interacting with the authentication server. What attack is occuring? 
- A user types the correct banking URL into a browser but is redirected to a malicious clone because DNS records were altered. What is the BEST answer?
- An attacker installs malicious code that remains dormant until a payroll administrator account is deleted, at which point financial databases are erased. What is the BEST answer?
- An attacker intercepts a user's authenticated web session by stealing a valid session cookie and reusing it to impersonate the user. BEST classification?
- A security analyst sees malware that appears to be legitimate backup software, but after installation it opens a remote access channel for attackers. What is the BEST classification?
- An attacker uses previously breached username/password pairs from another service to attempt logins against a corporate VPN portal. What attack is this?
- An attacker compromises thousands of IoT cameras and later uses them to flood a target with traffic. What does the compromised collection of devices represent?
- A user receives a phone call from someone pretending to be IT support who invents a story about suspicious activity and asks for MFA approval.BEST answer?
- An attacker attempts every possible character combination to recover an encrypted password hash. What technique is being used?
- An attacker positions a rogue wireless access point named “Corporate-Guest” near an office and captures employee credentials as users connect.
BEST answer?
- A security administrator sees repeated login attempts against a single administrator account using:

Welcome1
Welcome2
Welcome2025!

Which attack is MOST likely occurring?
- A SOC analyst reviews these events:

Event 1:
One password attempted against 700 accounts.

Event 2:
Stolen credentials from prior breach used against VPN.

Event 3:
Authentication exchange captured and resent later.

Match each event to the BEST attack type:

Choices:

Password spraying
Replay attack
Credential stuffing

Format your answer like:

1 =
2 =
3 =
- An attacker modifies ARP tables so victims send traffic through the attacker’s system without realizing it. BEST answer?
- An attacker sends a malicious link through email to lure victims to a fake Microsoft login portal hosted on a lookalike domain. BEST answer?
- A malicious program hides its processes, avoids detection, and maintains privileged persistence inside the operating system. BEST answer?
- Match each scenario to the MOST likely malware type.

Choices:

Trojan
Worm
Rootkit
Logic Bomb

Scenarios:

1. Malware disguised as software update installs backdoor.

2. Malware spreads automatically through vulnerable hosts.

3. Malicious code triggers when employee account disabled.

4. Malware hides itself while maintaining privileged access.

Format:

1=
2=
3=
4=
- An attacker captures a valid Kerberos ticket and uses it later to authenticate as a legitimate user. BEST answer?
- An attacker changes a banking transfer amount while traffic is moving between two communicating systems. BEST answer?
- A company reports these incidents:

Incident A:
Employees connect to fake corporate Wi-Fi and credentials are captured.

Incident B:
Users typing correct banking URL are redirected to fake clone.

Incident C:
One common password attempted against 900 user accounts.

Incident D:
Stolen breached credentials used against VPN.

Match each incident to BEST answer:

Choices:

Evil twin
Pharming
Password spraying
Credential stuffing

Format:

A=
B=
C=
D=

### Practice Questions:
20/20 completed

- PBQs:
3/3 completed

- Weak Topic Flag:
Pretexting vs Vishing specificity

---

## Weak Areas Identified
- Distinguishing pretexting from vishing in “best answer” scenarios
- Differentiating brute force from hybrid/dictionary attacks in nuanced wording
- Reinforcing replay attacks versus related session hijacking concepts
- Continue improving recognition of attack classifications under CompTIA-style wording traps

---

## Notes 
- Reinforced conceptual differences between brute force, password spraying, dictionary attacks, and credential stuffing
- Learned how MFA fatigue can be combined with pretexting to bypass strong authentication controls
- Strengthened understanding of malware distinctions: virus, worm, trojan, and rootkit
- Practiced identifying attack indicators through scenario-based analysis and PBQs
- Introduced Wireshark as a packet analysis tool tied to MITM and network attack detection concepts
- Recognized importance of identifying attack patterns rather than memorizing definitions

---

## Tommorrow's Focus
- Reconnaissance vs Enumeration concepts
- Vulnerability scanning fundamentals
- Nmap exposure and scan interpretation
- Basic vulnerability assessment workflow
- Detection-focused PBQs involving scanning and attack surface identification