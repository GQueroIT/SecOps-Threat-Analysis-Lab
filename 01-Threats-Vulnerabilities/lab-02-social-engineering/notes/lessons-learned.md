## Lessons Learned

### What Worked

- Ncrack generated realistic authentication attack telemetry
- Splunk correlation successfully identified attack indicators
- Secure logs provided reliable evidence for analysis

### What Was Challenging

- Packet-level SSH visibility was limited due to encryption
- Wireshark was less useful for credential visibility than host logs
- Shared folder and log ingestion troubleshooting required adjustment

### Security Concepts Reinforced

- Authentication abuse
- Brute-force detection
- Defense in depth
- SIEM-based threat analysis

---

## Real-World Relevance

This lab simulated a common attack pattern defenders monitor in production environments and reinforced how credential attacks are detected through authentication telemetry.

## Improvements For Future Labs

- Add Fail2Ban enforcement testing
- Create Splunk alerting use case
- Expand into password spraying simulation
