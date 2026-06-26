| Command                                         | Purpose             | Verification              |
| ----------------------------------------------- | ------------------- | ------------------------- |
| `sudo dnf update -y`                            | Update all packages | `dnf history`             |
| `hostnamectl`                                   | Display hostname    | Verify hostname           |
| `sudo hostnamectl set-hostname devops-project1` | Set hostname        | `hostnamectl`             |
| `timedatectl`                                   | Check timezone      | Verify timezone           |
| `sudo timedatectl set-timezone Asia/Kolkata`    | Set timezone        | `timedatectl`             |
| `groupadd`                                      | Create Linux groups | `cat /etc/group`          |
| `useradd -m`                                    | Create user         | `cat /etc/passwd`         |
| `passwd`                                        | Set password        | Login test                |
| `usermod -aG wheel`                             | Add sudo access     | `id username`             |
| `chmod`                                         | Change permissions  | `ls -l`                   |
| `chown`                                         | Change ownership    | `ls -l`                   |
| `firewall-cmd`                                  | Configure firewall  | `firewall-cmd --list-all` |
| `journalctl`                                    | View logs           | `journalctl -u sshd`      |
| `last`                                          | Login history       | Verify users              |
| `lastb`                                         | Failed logins       | Verify failed attempts    |
| `sshd -t`                                       | Validate SSH config | No output means success   |
| `systemctl restart sshd`                        | Restart SSH         | `systemctl status sshd`   |
