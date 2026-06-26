# Linux Server Hardening & Security Optimization (RHEL 10)

## Project Overview

This project demonstrates the implementation of production-level Linux server hardening techniques on a Red Hat Enterprise Linux (RHEL 10) server hosted on AWS EC2.

The objective was to secure the server by following Linux security best practices, implementing least-privilege access, hardening SSH, configuring firewall rules, enforcing password policies, managing file permissions, and validating the configuration through logging and security audits.

---

## Project Objectives

* Secure a Linux server using industry best practices.
* Implement Role-Based Access Control (RBAC).
* Configure secure SSH access.
* Restrict network access using Firewalld.
* Enforce password aging policies.
* Manage Linux file ownership and permissions.
* Perform system logging and security auditing.
* Validate the complete server configuration.

---

## Environment

* Operating System: Red Hat Enterprise Linux 10
* Cloud Platform: AWS EC2
* Instance Type: t2.micro
* Package Manager: DNF

---

## Project Architecture

```
Internet
     │
     ▼
AWS Security Group
     │
     ▼
Linux Firewall (Firewalld)
     │
     ▼
RHEL 10 Server
     │
 ┌───┼──────────────┐
 │   │              │
 ▼   ▼              ▼
SSH  HTTP         HTTPS
 │
 ▼
Role-Based Users
```

---

## Tasks Performed

### Phase 1

* Server Provisioning
* System Update
* Hostname Configuration
* Timezone Configuration

### Phase 2

* User Management
* Group Management
* Home Directory Creation

### Phase 3

* Sudo Configuration
* Principle of Least Privilege
* Wheel Group Management

### Phase 4

* SSH Hardening
* Disabled Root Login
* Restricted Authentication Attempts
* Session Timeout Configuration
* SSH Configuration Validation

### Phase 5

* Firewalld Configuration
* Allowed SSH
* Allowed HTTP
* Allowed HTTPS
* Verified Active Zones

### Phase 6

* Password Aging Policies
* Account Locking
* Password Expiry
* Warning Period Configuration

### Phase 7

* File Permissions
* Ownership Management
* chmod
* chown
* chgrp

### Phase 8

* System Logging
* journalctl
* last
* lastb
* who
* w
* uptime
* Log Monitoring

### Phase 9

* Complete Security Audit
* Configuration Validation
* Service Verification
* Access Verification

---

## Linux Commands Used

* hostnamectl
* timedatectl
* dnf
* useradd
* groupadd
* passwd
* usermod
* id
* chmod
* chown
* chgrp
* journalctl
* firewall-cmd
* sshd
* systemctl
* chage
* last
* lastb
* who
* w
* lsblk
* df
* free
* grep

---

## Key Skills Demonstrated

* Linux Administration
* Server Hardening
* SSH Security
* User & Group Management
* Firewall Configuration
* Password Policy Management
* File Permission Management
* System Monitoring
* Troubleshooting
* Security Best Practices

---

## Learning Outcomes

Through this project, I gained practical experience in securing Linux servers using production-grade security practices. The project enhanced my understanding of Linux administration, system security, access control, logging, and troubleshooting while following industry-standard hardening procedures.

---

## Future Improvements

* Configure Fail2Ban
* Integrate LDAP Authentication
* Centralized Logging
* Ansible Automation
* CIS Benchmark Compliance
* SELinux Policy Customization

---

## Author

Saurabh Singh

Learning DevOps through hands-on projects.
