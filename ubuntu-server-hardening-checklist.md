# Ubuntu Server Hardening Checklist

A minimal, ordered hardening list for a fresh (or newly inherited) Ubuntu
server. Each step is low-risk on its own; test in a non-production environment
first when in doubt.

## 1. Baseline

- [ ] Confirm the OS and kernel are current: `sudo apt update && sudo apt upgrade`
- [ ] Enable automatic security updates:
      `sudo apt install unattended-upgrades && sudo dpkg-reconfigure --priority=low unattended-upgrades`
- [ ] Set the hostname to something meaningful: `sudo hostnamectl set-hostname <name>`

## 2. Users and access

- [ ] Disable direct `root` SSH login (`PermitRootLogin no` in `/etc/ssh/sshd_config`)
- [ ] Create a dedicated admin user and add it to `sudo`
- [ ] Use SSH keys only; disable password SSH auth (`PasswordAuthentication no`)
- [ ] Remove or lock unused accounts (`sudo passwd -l <user>`)
- [ ] Confirm only the people who need access have it: `getent group sudo`

## 3. Firewall

- [ ] Install/enable `ufw`: `sudo apt install ufw && sudo ufw enable`
- [ ] Allow only required ports (e.g. `sudo ufw allow OpenSSH`, `sudo ufw allow 80,443/tcp`)
- [ ] Review: `sudo ufw status verbose`

## 4. SSH hardening

In `/etc/ssh/sshd_config`:

- [ ] `PermitRootLogin no`
- [ ] `PasswordAuthentication no`
- [ ] `X11Forwarding no`
- [ ] `MaxAuthTries 5`
- [ ] `Protocol 2` (default on modern OpenSSH)
- [ ] Restart and verify: `sudo systemctl restart ssh && sudo systemctl status ssh`

## 5. Services and surface area

- [ ] List what's running: `systemctl list-units --type=service --state=running`
- [ ] List what's exposed: `sudo ss -tulpn`
- [ ] Remove or disable anything unnecessary
- [ ] Keep public services (web, database) bound to localhost where possible

## 6. Monitoring and logging

- [ ] Install a lightweight monitor (e.g. `htop`, `glances`, or a proper agent)
- [ ] Configure log rotation (default `logrotate` covers most services)
- [ ] Add a simple disk/load alert (cron + `df` / `uptime` is enough to start)

## 7. Backups (before anything else matters)

- [ ] Confirm what needs backing up (databases, app files, config)
- [ ] Set up automated off-site backups and **test a restore** — an untested
      backup is not a backup

## 8. Application layer

- [ ] Apply TLS (Let's Encrypt via `certbot`) to every public service
- [ ] Set sane file permissions (`find /var/www -type f -exec chmod 640 {} \;` as needed)
- [ ] Keep application secrets out of the codebase and out of world-readable files

## Sign-off

A server is "hardened enough" when: no password SSH, no root SSH, a firewall
that denies by default, only necessary services exposed, automatic security
updates, and a tested backup.

Need it done rather than doing it yourself? [Linux Stewards](https://www.linuxstewards.com)
provides remote Linux hardening and administration.
