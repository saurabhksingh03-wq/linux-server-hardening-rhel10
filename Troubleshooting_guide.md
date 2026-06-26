# Linux Server Hardening – Troubleshooting Guide

## Scenario 1 – Unable to SSH into the Server

### Checks

1. Verify EC2 Security Group allows port 22.
2. Check SSH service status.

```bash
sudo systemctl status sshd
```

3. Validate SSH configuration.

```bash
sudo sshd -t
```

4. Review SSH logs.

```bash
sudo journalctl -u sshd
```

5. Check firewall rules.

```bash
sudo firewall-cmd --list-all
```

Resolution:
Correct SSH configuration, restart sshd, and verify Security Group settings.

---

## Scenario 2 – Firewall Blocking HTTP Access

### Checks

```bash
sudo firewall-cmd --list-all
```

If HTTP is missing:

```bash
sudo firewall-cmd --permanent --add-service=http
sudo firewall-cmd --reload
```

Verify:

```bash
curl http://localhost
```

---

## Scenario 3 – User Cannot Execute sudo Commands

### Checks

```bash
id username
```

Verify membership in the wheel group.

```bash
groups username
```

List sudo permissions.

```bash
sudo -l -U username
```

Resolution:

```bash
sudo usermod -aG wheel username
```

---

## Scenario 4 – Password Expired

Verify password policy.

```bash
sudo chage -l username
```

Reset password.

```bash
sudo passwd username
```

---

## Scenario 5 – SSH Service Fails After Configuration Change

Validate configuration.

```bash
sudo sshd -t
```

Restore backup if required.

```bash
sudo cp /etc/ssh/sshd_config.bak /etc/ssh/sshd_config
```

Restart service.

```bash
sudo systemctl restart sshd
```

---

## Scenario 6 – Firewalld Not Running

Check service.

```bash
sudo systemctl status firewalld
```

Start service.

```bash
sudo systemctl enable firewalld
sudo systemctl start firewalld
```

---

## Scenario 7 – Disk Space Full

Check disk usage.

```bash
df -h
```

Identify large directories.

```bash
du -sh /*
```

Clean unnecessary logs and temporary files.

---

## Scenario 8 – High CPU Usage

Check running processes.

```bash
top
```

or

```bash
ps -eo pid,ppid,cmd,%mem,%cpu --sort=-%cpu
```

Investigate the process consuming excessive CPU.

---

## Scenario 9 – User Cannot Access a File

Check permissions.

```bash
ls -l filename
```

Check ownership.

```bash
stat filename
```

Correct permissions if required.

```bash
chmod
chown
chgrp
```

---

## Scenario 10 – Service Not Starting

Check status.

```bash
systemctl status service_name
```

Review logs.

```bash
journalctl -u service_name
```

Validate configuration before restarting the service.
