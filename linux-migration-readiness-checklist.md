# Linux Migration Readiness Checklist

Moving an existing workload (web app, database, file server) to Linux — or from
one Linux host to another — goes wrong most often in the planning, not the
execution. Work through this before you start.

## 1. Know what you are migrating

- [ ] Inventory the application(s): what runs, on which ports, with which accounts
- [ ] List every dependency (language runtime, libraries, cron jobs, systemd units)
- [ ] Capture the exact versions, not just "latest"
- [ ] Identify external integrations (email, DNS, payment, third-party APIs)

## 2. Data and state

- [ ] Enumerate databases, file stores, and any stateful data
- [ ] Confirm the size and a safe, tested backup before you begin
- [ ] Note anything that writes to local disk (sessions, uploads, caches)

## 3. Config and secrets

- [ ] Collect all environment variables and config files
- [ ] Store secrets separately (never copy them through a chat or a commit)
- [ ] Record DNS, TLS/certificate, and firewall rules that will need recreating

## 4. Destination readiness

- [ ] Provision the target host and confirm SSH access
- [ ] Install the base packages and set the timezone and locale
- [ ] Apply the standard hardening baseline (users, SSH keys, firewall)

## 5. Cutover plan

- [ ] Define the order of migration and a rollback path for each step
- [ ] Pick a low-traffic window and agree it with stakeholders
- [ ] Decide how to verify each piece after it moves (a health check per service)

## 6. Post-migration

- [ ] Re-point DNS and confirm TLS certificates renew correctly
- [ ] Update monitoring and backups to target the new host
- [ ] Keep the old host reachable for a defined grace period, then decommission it

## Sign-off

You are ready when you can name every moving part, have a tested backup, and have
a rollback for each step. [Linux Stewards](https://www.linuxstewards.com/services/linux)
can plan and run Linux migrations remotely, or review your plan before you start.
