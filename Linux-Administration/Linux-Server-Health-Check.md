# Linux Server Health Check Guide

## Purpose

This document provides a standard procedure for monitoring and maintaining Linux server health to ensure system availability, security, performance, and operational stability.

## Scope

This procedure applies to:

- Ubuntu Linux Servers
- CentOS Linux Servers
- Application Servers
- Database Servers
- Infrastructure Servers

---

## Daily Health Checks

### Server Availability

Verify server accessibility:

```bash
ping <server-ip>
```

Check system uptime:

```bash
uptime
```

Expected Result:
- Server reachable
- No unexpected reboots

---

### CPU Utilization

Check CPU load:

```bash
top
```

or

```bash
htop
```

Review:

- CPU utilization
- Load average
- Running processes

Expected Result:

- CPU utilization within normal operating range
- No runaway processes

---

### Memory Utilization

Check memory usage:

```bash
free -h
```

Review:

- Used memory
- Available memory
- Swap usage

Expected Result:

- Sufficient available memory
- Minimal swap usage

---

### Disk Utilization

Check disk space:

```bash
df -h
```

Review:

- Root filesystem
- Application storage
- Log storage

Expected Result:

- Filesystems below 80% utilization

Action Required:

- Investigate filesystems above 80%

---

### Critical Services

Verify service status:

```bash
systemctl status nginx
systemctl status tomcat
systemctl status postgresql
```

Expected Result:

- All required services running

---

## Weekly Health Checks

### Log Review

Review:

```bash
journalctl -xe
```

Check:

- Authentication failures
- Service crashes
- Hardware errors
- Security events

---

### Security Updates

Check available updates:

Ubuntu:

```bash
apt update
apt list --upgradable
```

CentOS:

```bash
yum check-update
```

Review security patches before deployment.

---

### User Account Review

Check active users:

```bash
cat /etc/passwd
```

Review:

- Administrative users
- Service accounts
- Inactive accounts

---

## Monthly Health Checks

### System Performance Review

Analyze:

- CPU trends
- Memory trends
- Storage growth
- Network utilization

Review historical monitoring data where available.

---

### Backup Validation

Verify:

- Backup completion
- Backup integrity
- Recovery point availability

Perform sample restoration testing.

---

### Scheduled Task Review

Check cron jobs:

```bash
crontab -l
```

Review:

- Backup jobs
- Monitoring jobs
- Maintenance jobs

---

## Security Hardening Review

Verify:

### SSH Configuration

```bash
cat /etc/ssh/sshd_config
```

Review:

- Root login settings
- Password authentication
- Access restrictions

### Firewall Status

Ubuntu:

```bash
ufw status
```

CentOS:

```bash
firewall-cmd --list-all
```

Verify required ports only.

---

## Incident Response Procedure

When issues are detected:

1. Identify affected service.
2. Review logs.
3. Assess impact.
4. Apply corrective action.
5. Verify service recovery.
6. Document incident and resolution.

---

## Documentation

Maintain records of:

- Maintenance activities
- Security reviews
- Patch installations
- Backup verification
- Incident investigations
- Recovery testing

---

## Expected Outcomes

- Improved system availability
- Enhanced security posture
- Reduced operational risks
- Better performance visibility
- Improved recovery readiness
- Stable Linux server operations
