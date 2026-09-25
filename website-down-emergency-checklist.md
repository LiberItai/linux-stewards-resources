# Website down or showing an error? An emergency checklist

A calm, ordered checklist for when your website is down, showing an error page,
or throwing a security warning. Maintained by
[Linux Stewards](https://www.linuxstewards.com), a UK-based technology-services
business. If you would rather have this fixed for you, see
[linuxstewards.com/services/hosting-devops](https://www.linuxstewards.com/services/hosting-devops).

When a site goes down, the instinct is to click and restart things at random.
That usually makes it harder to find the cause. Work through these in order.

## Step 0 — confirm it is actually down
1. Open the site in a private/incognito window (rules out a cached or logged-in
   view).
2. Try a simple "is it down" checker for a second opinion from outside your
   network.
3. Note the EXACT symptom: does it time out, show 404, show 500, or show a
   security warning? Each points to a different cause.

## Step 1 — identify the error class

| Symptom | Most likely area |
|---|---|
| Timeout / site never loads | Hosting or server down |
| 500 Internal Server Error | Code, server, or a recent change |
| 404 Not Found | Missing page or wrong link/route |
| Security/SSL warning | Expired or broken certificate |
| DNS error (NXDOMAIN / "site not found") | Domain or DNS records |
| Very slow but loads | Resource/performance or a hung service |

## Step 2 — check what changed last
1. Was a plugin, theme or framework updated today?
2. Was there a deploy, a code change, or a content edit?
3. Did the domain, hosting or DNS change recently?

Most site outages follow a change. The change is usually the cause.

## Step 3 — the cheap checks first
- **SSL certificate:** check its expiry and whether the browser trusts it.
- **DNS:** check the domain still resolves to the right place (`A`/`CNAME` records).
- **Hosting status:** check your provider's status page — the problem is sometimes
  theirs, not yours.
- **Disk/limits:** a full disk or an exceeded plan limit is a common silent cause.

## Step 4 — do NOT do these while panicking
- Do not delete files or the database unless you have a working backup.
- Do not disable plugins at random — note what you change so it can be undone.
- Do not change DNS records "just to see" — propagation can take hours and make
  the problem harder to trace.

## What to gather before asking for help
- The exact URL and the exact error message (a screenshot is ideal).
- What changed just before it broke.
- Where the site is hosted and where the domain is registered.
- Whether you have a recent backup, and where it lives.

## When to get it fixed for you
If any of this is unclear, or the site is your business and you need it back
now, Linux Stewards offers deployment and hosting debugging, quoted up front and
delivered remotely. We find whether it is the host, the code, the DNS or the
certificate, fix the cause, and confirm the site is reachable before we call it
done.

- Website: [linuxstewards.com](https://www.linuxstewards.com)
- Email: info@linuxstewards.com

Small jobs are genuinely welcome.
