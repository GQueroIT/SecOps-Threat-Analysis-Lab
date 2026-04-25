## Commands Used

### System Identification
```bash
hostnamectl
```
Displays hostname, OS version, kernel version, and system identity information.

```bash
whoami
```
Displays current logged-in user.

```bash
sudo whoami
```
Validates privilege escalation through sudo.

---

### Patch Management
```bash
sudo dnf update -y
```
Updates installed packages and applies security patches.

---

### Security Control Validation
```bash
getenforce
```
Checks SELinux enforcement mode.

```bash
sudo systemctl status firewalld
```
Validates host firewall service status.

```bash
sudo systemctl status auditd
```
Validates audit logging service status.

---

### Log Review and Monitoring
```bash
sudo tail /var/log/secure
```
Reviews authentication and privilege escalation logs.

---

### Network and Attack Surface Analysis
```bash
ip a
```
Displays network interfaces and IP configuration.

```bash
sudo ss -tulnp
```
Enumerates listening services and exposed ports.

```bash
systemctl list-unit-files --type=service --state=enabled
```
Lists services enabled at boot for hardening review.

```bash
systemctl is-enabled sshd firewalld auditd
```
Validates critical security services are enabled.