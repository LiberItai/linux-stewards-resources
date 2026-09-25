# Business email not sending or landing in spam? SPF, DKIM and DMARC in plain English

A plain-English guide for small-business owners whose domain email is not
arriving, not sending, or going to spam. Maintained by
[Linux Stewards](https://www.linuxstewards.com), a UK-based technology-services
business. If you would rather have this fixed for you, see
[linuxstewards.com/services/email-office-cloud](https://www.linuxstewards.com/services/email-office-cloud).

When your @yourbusiness email misbehaves, the cause is usually one of three
DNS records that tell other mail systems your domain is real and trustworthy.
You do not need to be technical to understand what they do.

## The three records

- **SPF** — a list of servers allowed to send mail *on behalf of* your domain.
  If your website or a service sends mail using your domain but is not on the
  list, receiving servers may reject it.
- **DKIM** — a signature added to each message that proves it really came from
  you and was not tampered with in transit.
- **DMARC** — a policy that tells receiving servers what to do when a message
  fails the SPF or DKIM checks (do nothing, quarantine, or reject), and where to
  send reports.

Most small businesses either have none of these, or have them misconfigured by a
half-finished setup. That is why mail intermittently fails or lands in spam.

## The most common problems, in order

1. **You send from your domain but SPF is missing** — messages from your website
   form, newsletter or booking system get rejected or junked.
2. **You changed email provider but left old records** — conflicting records make
   receiving servers distrust everything.
3. **DMARC policy is set to `reject` but SPF/DKIM are incomplete** — legitimate
   mail gets bounced and you do not know why.
4. **The form or app sends "from" an address it is not authorised to** — a very
   common cause of silent contact-form failure.

## How to check it yourself (free)

1. Send a test email from your business address to a personal address you can
   read (e.g. a free Gmail account).
2. Open the message and choose "Show original" / "View source".
3. Look for `spf=pass`, `dkim=pass` and `dmarc=pass` in the headers. Any
   `fail` or `softfail` is your culprit.

There are also free online tools that check your domain's SPF/DKIM/DMARC records
for you — search "SPF DKIM DMARC checker" and enter your domain.

## What to gather before asking for help

- Your domain name.
- Where you host your email (Google Workspace, Microsoft 365, cPanel, etc.).
- Whether the problem is sending, receiving, or both.
- A sample of any bounce or error message you see.

## When to get it fixed for you

If the records are unclear or you would like it handled without the trial and
error, Linux Stewards offers domain email and DNS help from £29, with SPF/DKIM/
DMARC setup from £79, delivered remotely. We publish the correct records, verify
them, and get your business mail delivering and trusted again.

- Website: [linuxstewards.com](https://www.linuxstewards.com)
- Email: info@linuxstewards.com

Small jobs are genuinely welcome.
