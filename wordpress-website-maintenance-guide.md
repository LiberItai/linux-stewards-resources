# WordPress website: maintenance, updates and emergency recovery

A plain-English guide to keeping a WordPress website healthy — and to getting it
back when something breaks. Maintained by
[Linux Stewards](https://www.linuxstewards.com), a UK-based technology-services
business. If you would rather have this handled for you, see
[linuxstewards.com/services/website-build](https://www.linuxstewards.com/services/website-build).

WordPress powers a huge share of the web, but a WordPress site is not "build it
and forget it". It is a living system made of three moving parts — the core,
the theme, and the plugins — and most emergencies come from one of those parts
changing or falling behind.

## The golden rule: back up before you change anything

Every update, plugin install and troubleshooting step below is safe only if you
can undo it. Before touching a working site:

- [ ] Take a full backup (files **and** database — they are stored separately).
- [ ] Confirm the backup actually restores (a backup you cannot restore is not a backup).
- [ ] Know where the backup lives and how to reach it if the site itself is down.

## Routine maintenance (do this monthly)

- [ ] Update WordPress core, the theme and all plugins — on a schedule, not "eventually".
- [ ] Delete unused themes and plugins (an unmaintained plugin is a common break-in point).
- [ ] Remove old admin accounts and any user who no longer needs access.
- [ ] Check comments/spam and any forms for junk that is piling up.
- [ ] Check disk space and the site's error log for warnings you can fix early.

## Updating safely

1. Back up first (see above).
2. Update one thing at a time — core, then theme, then plugins — so if something
   breaks you know exactly which change caused it.
3. Test the key pages after each update (home page, a normal page, a form, checkout).
4. If a plugin has not been updated by its author for a long time, treat it as
   a risk and look for a maintained replacement.

## The most common WordPress emergencies, in order

| Symptom | Most likely cause | First move |
|---|---|---|
| White screen / blank page | Plugin or theme conflict, PHP error | Rename the plugins folder (see below) |
| "Error establishing a database connection" | Wrong DB credentials, host down, or DB corrupted | Check credentials and host status, restore DB |
| Site redirects to spam / shows ads | Malware or a compromised admin account | Take offline, restore clean backup, change passwords |
| 500 error after an update | A plugin/theme incompatible with the new version | Disable the recently updated plugin |
| Very slow site | Heavy plugins, large images, no caching | Disable/defer heavy plugins, optimise images |
| Locked out of wp-admin | Wrong password, brute-force lockout, or takeover | Use the "lost password" flow, then enable 2FA |

## The "safe mode" trick for a broken site

If the site is showing a white screen or 500 error and you cannot reach wp-admin:

1. Use your hosting file manager (or FTP) to find the `wp-content` folder.
2. Rename the `plugins` folder to `plugins-disabled` — this disables every plugin
   without deleting anything.
3. Reload the site. If it works, one of the plugins is the cause.
4. Rename the folder back, then re-enable plugins one at a time until the culprit
   reappears.

## WordPress security basics

- [ ] Use a unique, strong admin password and a password manager.
- [ ] Turn on two-factor authentication (2FA) for every admin account.
- [ ] Keep the number of administrator accounts to a minimum.
- [ ] Use a well-maintained security/backup plugin — and keep it updated.
- [ ] Set up automatic off-site backups so a server failure does not lose the site too.

## When to get it fixed for you

If the site is your business and it is down, compromised, or the cause is
unclear, Linux Stewards offers WordPress repair, recovery and maintenance quoted
up front and delivered remotely. We find the cause, restore from a clean backup
where needed, and confirm the site is reachable and clean before we call it done.

- Website: [linuxstewards.com](https://www.linuxstewards.com)
- Email: info@linuxstewards.com

Small jobs are genuinely welcome.
