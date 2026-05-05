# Linux logs

### auth.log
- Located in /var/log
- Records authentication-related events
- (Logins, sudo usage, SSH, PAM)

### System log (syslog)
- Records system events

### auditd
- Needs to be installed and enabled
- Rules are located in `/etc/audit/rules.d/audit.rules`
- augenrules --load to reload after updating rules
- Systemctl restart auditd
- `/var/log/audit/audit.log` is where auditd logs are stored

### Navigation
- cat
- grep
- tail
- tail -f (follow mode)
- more
- less

