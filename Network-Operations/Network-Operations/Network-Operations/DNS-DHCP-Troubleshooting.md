# DNS and DHCP Troubleshooting Guide

## Purpose

This document provides standard procedures for diagnosing and resolving DNS and DHCP related issues within enterprise network environments.

## Scope

Applicable to:

- Windows DNS Servers
- Windows DHCP Servers
- Linux DNS Services
- Enterprise LAN Environments
- Branch Connectivity Environments
- VPN Connected Networks

---

## Overview

DNS and DHCP are critical infrastructure services supporting enterprise systems.

### DNS Responsibilities

- Name Resolution
- Domain Services
- Application Connectivity
- Active Directory Integration

### DHCP Responsibilities

- IP Address Assignment
- Network Configuration Distribution
- Gateway Assignment
- DNS Server Assignment

---

# DNS Troubleshooting

## Common DNS Issues

### Symptoms

- Unable to access websites
- Domain login failures
- Application connection failures
- Slow network response

---

## Step 1: Verify Network Connectivity

Windows:

```cmd
ping 8.8.8.8
```

Linux:

```bash
ping 8.8.8.8
```

Expected Result:

- Successful network connectivity

---

## Step 2: Verify DNS Resolution

Windows:

```cmd
nslookup google.com
```

Linux:

```bash
dig google.com
```

Expected Result:

- Valid DNS response returned

---

## Step 3: Verify DNS Server Configuration

Windows:

```cmd
ipconfig /all
```

Linux:

```bash
cat /etc/resolv.conf
```

Verify:

- Correct DNS server addresses
- Domain suffix configuration

---

## Step 4: Verify DNS Service Status

Windows:

```powershell
Get-Service DNS
```

Linux:

```bash
systemctl status named
```

or

```bash
systemctl status bind9
```

Expected Result:

- Service running

---

## Step 5: Clear DNS Cache

Windows:

```cmd
ipconfig /flushdns
```

Linux:

```bash
systemctl restart systemd-resolved
```

---

# DHCP Troubleshooting

## Common DHCP Issues

### Symptoms

- No IP address assigned
- APIPA Address (169.254.x.x)
- Incorrect network settings
- Intermittent connectivity

---

## Step 1: Verify Current IP Configuration

Windows:

```cmd
ipconfig /all
```

Linux:

```bash
ip addr
```

Review:

- IP Address
- Subnet Mask
- Gateway
- DNS Servers

---

## Step 2: Renew DHCP Lease

Windows:

```cmd
ipconfig /release
ipconfig /renew
```

Linux:

```bash
dhclient -r
dhclient
```

Expected Result:

- New valid IP address assigned

---

## Step 3: Verify DHCP Server Availability

Check:

- DHCP Service Status
- DHCP Scope Availability
- Available IP Addresses

Windows:

```powershell
Get-Service DHCPServer
```

Expected Result:

- DHCP service running

---

## Step 4: Verify Scope Utilization

Review:

- Address pool usage
- Lease duration
- Reserved addresses

Recommended:

- Maintain at least 20% available addresses

---

# Network Troubleshooting Workflow

          User Reports Issue
                    │
                    ▼
         Verify Physical Connectivity
                    │
                    ▼
            Verify IP Address
                    │
                    ▼
            Verify DHCP Service
                    │
                    ▼
             Verify DNS Service
                    │
                    ▼
            Verify Application
                    │
                    ▼
                 Resolution

---

# Preventive Maintenance

## DNS

- Monitor DNS service status
- Review DNS logs
- Remove stale records
- Verify zone replication

## DHCP

- Monitor scope utilization
- Review lease statistics
- Maintain reservations
- Review DHCP logs

---

# Documentation

Maintain records for:

- DNS Changes
- DHCP Scope Changes
- Network Incidents
- Service Interruptions
- Root Cause Analysis

---

# Expected Outcomes

- Improved DNS reliability
- Improved DHCP availability
- Faster troubleshooting
- Reduced network downtime
- Better operational visibility
- Improved user experience
