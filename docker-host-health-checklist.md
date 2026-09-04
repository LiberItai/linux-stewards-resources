# Docker Host Health Checklist

A quick, repeatable health check for a Linux host running Docker containers.
Run on the Docker host itself.

## 1. Docker daemon

```bash
docker version          # client and server both responding
docker info             # daemon status, storage driver, warnings
systemctl status docker
```

`docker info` prints storage-driver and any warnings — read the warnings.

## 2. Running containers

```bash
docker ps -a                       # running AND stopped/exited containers
docker ps -q | wc -l               # count of running containers
```

Stopped containers that should be running are the first thing to investigate.

## 3. Resource pressure

```bash
docker stats --no-stream          # per-container CPU/memory
free -h                           # host memory
df -h /var/lib/docker             # Docker data directory usage
```

A full `/var/lib/docker` disk breaks builds, pulls, and new containers.

## 4. Image and volume hygiene

```bash
docker images                      # image count and size
docker system df                   # total disk used by images/containers/volumes
docker volume ls                   # orphaned volumes
```

`docker system prune -a` reclaims space but deletes unused images — do it
deliberately, never blindly on a host with data you cannot rebuild.

## 5. Logs and errors

```bash
docker logs <container> --tail 100
journalctl -u docker --no-pager | tail -50
```

## 6. Network exposure

```bash
docker ps --format '{{.Names}} {{.Ports}}'
```

Every published port should be intentional. A database exposed on
`0.0.0.0:5432` is a common and serious mistake.

## 7. Restart policy

- [ ] Critical containers use `--restart unless-stopped` (or a proper orchestrator)
- [ ] Confirm the host itself restarts Docker on boot (`systemctl enable docker`)

## When to act

Any of: full `/var/lib/docker`, a stopped production container, an exposed
database port, or a daemon warning in `docker info`.

[Linux Stewards](https://www.linuxstewards.com/services/linux) provides remote
Docker and container support for small businesses.
