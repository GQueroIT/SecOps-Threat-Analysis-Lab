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
- A security analyst notices repeated authentication attempts against hundreds of user accounts. Each account receives only one failed login attempt every thirty minutes, and the attempted password is identical across all accounts. What attack is MOST likely occurring? (Answer: password spraying)
- A company discovers an attacker copied password hashes from a compromised domain controller and is attempting to recover plaintext passwords without interacting with the authentication server. What attack is occuring? ()

---

## Weak Areas Identified

---

## Notes 

---

## Tommorrow's Focus
