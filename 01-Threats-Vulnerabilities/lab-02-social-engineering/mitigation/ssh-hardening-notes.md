# SSH Hardening Notes

## Controls Reviewed
- Strong password policy
- Disable root SSH login
- Limit login attempts
- SSH key authentication (future enhancement)
- Change default SSH configuration settings
- Fail2Ban automated banning

## Relevant SSH Hardening Settings
Examples reviewed:

PermitRootLogin no
PasswordAuthentication yes
MaxAuthTries 3
LoginGraceTime 30
AllowUsers gabrieladmin

## Security Benefit
These controls reduce brute-force exposure and credential abuse risk.