# Windows Server Maintenance Checklist

## Purpose

This document provides a standard checklist for maintaining Windows Server environments to ensure availability, security, performance, and operational reliability.

## Scope

Applicable to:

- Domain Controllers
- File Servers
- Application Servers
- Database Servers
- Infrastructure Servers

---

## Daily Checks

### Services

Verify critical services are running:

- Active Directory Domain Services
- DNS Server
- DHCP Server
- IIS Services
- SQL Services
- Backup Services

### Event Logs

Review:

- System Logs
- Security Logs
- Application Logs

Investigate:

- Critical Events
- Error Events
- Warning Events

### Resource Utilization

Monitor:

- CPU Usage
- Memory Usage
- Disk Utilization
- Network Utilization

---

## Weekly Checks

### Backup Verification

Verify:

- Backup completion status
- Backup integrity
- Recovery point availability

### Security Review

Review:

- Failed logon attempts
- Privileged account activities
- Account lockouts

### Disk Space Review

Check:

- System Drive
- Application Volumes
- Database Volumes
- Backup Storage

Recommended free space:

- Minimum 20%

---

## Monthly Checks

### Windows Updates

Review:

- Security Updates
- Critical Updates
- Feature Updates

Apply updates according to change management procedures.

### Performance Review

Analyze:

- CPU trends
- Memory trends
- Storage growth
- Network performance

### User and Group Review

Verify:

- Active users
- Disabled users
- Group memberships
- Administrative privileges

---

## Quarterly Checks

### Disaster Recovery Validation

Perform:

- Backup restoration testing
- Recovery procedure validation
- Failover readiness review

### Security Assessment

Review:

- Local Administrators
- Service Accounts
- Password Policies
- Audit Policies

---

## Documentation

Maintain records for:

- Maintenance activities
- Incidents
- Configuration changes
- Security reviews
- Recovery tests

---

## Expected Outcomes

- Improved server availability
- Enhanced security posture
- Reduced operational risks
- Improved recovery readiness
- Stable production environment
