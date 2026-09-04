# Linux Server Health Check

A repeatable, command-based health check for a Linux server (Ubuntu/Debian
flavour shown; most commands work on RHEL-family with `dnf` instead of `apt`).
Run as a normal user, use `sudo` only where noted.

## 1. Load and uptime

```bash
uptime                 # load averages (1/5/15 min) and how long the box has been up
```

A load average consistently above the number of CPU cores means the box is
overcommitted.

## 2. CPU

```bash
nproc                  # number of CPU cores
top -bn1 | head -20    # one-shot snapshot of top processes
mpstat 1 5             # per-core utilisation (install sysstat if missing)
```

## 3. Memory

```bash
free -h                # total / used / available — look at "available", not "free"
vmstat 1 5             # swap-in/out; persistent swap activity means RAM pressure
```

## 4. Disk

```bash
df -h                  # per-filesystem usage
df -i                  # inode usage (a full inode table fails even with free space)
du -sh /var/log/* 2>/dev/null | sort -rh | head   # biggest log consumers
```

Check any filesystem at 85%+ and act before it hits 100%.

## 5. Services and boot

```bash
systemctl --failed            # any failed units
systemctl list-units --type=service --state=running | head -40
journalctl -p 3 -xb --no-pager | tail -50   # errors since last boot
```

## 6. Network

```bash
ip -br a                      # interfaces and addresses
ss -tulpn                     # listening sockets (port, process)
```

Every listening port should be explainable. A public service you don't recognise
is a candidate for removal or firewall restriction.

## 7. Logs worth watching

```bash
sudo tail -n 100 /var/log/syslog
sudo tail -n 100 /var/log/auth.log | grep -iE 'failed|invalid|accepted'   # auth attempts
sudo journalctl -u ssh --no-pager | tail -50
```

Repeated `Failed password` lines in `auth.log` mean the box is being probed —
tighten SSH (see the hardening checklist).

## 8. Security quick look

```bash
sudo ufw status               # firewall state (if using ufw)
sudo ss -tulpn | grep -E ':(22|80|443)\s'   # confirm what's actually exposed
who                          # currently logged-in users
last -n 10                   # recent logins
```

## 9. Package updates

```bash
sudo apt update && apt list --upgradable   # how far behind the box is
```

Keep a record of the output; unattended-upgrades can close routine gaps.

## When to act

- Any filesystem over 85%
- Load average above core count
- Swap-in activity that never stops
- Failed systemd units
- Unexplained listening ports
- SSH probes in `auth.log`

If the box matters to your business and any of the above is true, fix it soon —
or ask [Linux Stewards](https://www.linuxstewards.com) to do a proper check and
remediation remotely.
