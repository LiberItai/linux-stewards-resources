# Linux Server Incident Response — First 30 Minutes

A calm, ordered response when a Linux server is down, unresponsive, or behaving
badly. Work top-down; capture evidence before making changes. Free to use.

> Maintained by [Linux Stewards](https://www.linuxstewards.com?utm_source=github&utm_medium=organic&utm_campaign=zero_cost_acquisition&utm_content=incident_response_guide).
> Prefer help doing it? Remote Linux support worldwide:
> [linuxstewards.com/services/linux](https://www.linuxstewards.com/services/linux?utm_source=github&utm_medium=organic&utm_campaign=zero_cost_acquisition&utm_content=incident_response_guide)

## 0. Do not panic-change things

- Note the exact symptom and when it started.
- Confirm what changed recently: deployments, config edits, package updates,
  cron jobs, certificate renewals, disk fills, DNS changes.
- If it is a public-facing outage, communicate status early rather than silently
  fiddling.

## 1. Is it reachable?

```bash
ping -c 3 <host>
curl -I --max-time 10 https://<host>/      # app layer
ssh -o ConnectTimeout=10 user@<host>        # ssh layer
```

- Ping OK but ssh/app fail → likely a service, resource, or firewall problem.
- Ping fails → network, host, or provider issue (check provider status page).

## 2. Get a foothold and check the basics

```bash
uptime                    # load average
free -h                   # memory
df -h                     # disk (a full / or /var/log is the #1 cause)
df -i                     # inode exhaustion
```

## 3. What is consuming resources?

```bash
top -bn1 | head -25
ps aux --sort=-%mem | head -10
journalctl -p 3 -xb       # errors since last boot
```

## 4. Disk full — the classic outage

```bash
du -xh / 2>/dev/null | sort -rh | head -20
journalctl --disk-usage
```

If `/var/log` is full: identify the noisy service, then rotate/clean the logs
deliberately (do not blindly `rm`).

## 5. Service down?

```bash
systemctl list-units --state=failed
systemctl status <unit> --no-pager
journalctl -u <unit> -n 100 --no-pager
```

## 6. Reboot as a last resort, not a first reflex

Rebooting without reading the logs can hide a recurring cause. Restart the
specific failing service first; reboot only when the box is truly wedged.

## 7. Capture evidence, then restore

- Save `journalctl` and `dmesg` output before restarting anything.
- Make one change at a time and observe.
- After recovery, document root cause + the fix so it is fixed once.

## When to get help

If a production server is down and you are not certain of the cause, or the fix
needs doing right the first time, [Linux Stewards](https://www.linuxstewards.com?utm_source=github&utm_medium=organic&utm_campaign=zero_cost_acquisition&utm_content=incident_response_guide)
provides remote Linux support for small businesses and individuals — small jobs
welcome, clear scope before work starts.
