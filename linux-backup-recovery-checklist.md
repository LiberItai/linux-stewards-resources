# Linux Backup & Recovery Checklist

A backup that has never been restored is not a backup. This checklist focuses on
the part most people skip: proving you can get the data back.

## 1. Decide what matters

- [ ] List what must be recoverable: databases, app files, config, secrets, user data
- [ ] Distinguish "rebuildable" (reinstallable) from "irreplaceable" (customer data)
- [ ] Agree a recovery-point and recovery-time objective (RPO/RTO) for each

## 2. Capture it

- [ ] Back up databases with a consistent method (`mysqldump`, `pg_dump`, or the DB's own tooling)
- [ ] Back up files with a tool that preserves permissions (`tar`, `rsync`, `restic`, `borg`)
- [ ] Back up configuration (`/etc`, `.env`-equivalent, systemd units, cron)

## 3. Store it safely

- [ ] Keep at least one copy off-site and off the same machine
- [ ] Encrypt backups that contain anything sensitive
- [ ] Restrict who can read and delete backups

## 4. Test the restore (the part that matters)

- [ ] Do a test restore to a throwaway host, not just a `tar -t` listing
- [ ] Confirm the database actually comes back and the app connects to it
- [ ] Time the restore so you know whether it meets your RTO
- [ ] Repeat the test on a schedule (quarterly at minimum)

## 5. Automate and monitor

- [ ] Run backups on a schedule, not by hand
- [ ] Alert on backup failure (silent failure is the default failure mode)
- [ ] Log backup size and duration so drift is visible

## 6. Document it

- [ ] Write the restore steps down so someone else can follow them in a crisis
- [ ] Record where the backups live and how to decrypt them

## Sign-off

You are protected when: an off-site copy exists, a test restore has succeeded
recently, and failure alerts actually reach someone.

[Linux Stewards](https://www.linuxstewards.com/services/linux) can set up and
test a proper Linux backup and recovery routine.
