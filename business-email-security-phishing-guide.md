# Business email security: spotting phishing, spoofing and invoice fraud

A plain-English guide to the email attacks that cost small businesses money —
and how to spot them before they land. Maintained by
[Linux Stewards](https://www.linuxstewards.com), a UK-based technology-services
business. If you would rather have this hardened for you, see
[linuxstewards.com/services/cybersecurity](https://www.linuxstewards.com/services/cybersecurity).

Email is how money moves in most small businesses: invoices, payment details,
logins and instructions all arrive by email. That is exactly why it is the main
target. Most email attacks are not "hacking" — they are tricking a person into
doing the wrong thing.

## The four attacks to know

1. **Phishing** — a message pretending to be from a trusted sender, asking you to
   click a link or open an attachment. The link leads to a fake login page that
   steals your password.
2. **Spoofing** — a message that *looks* like it is from your own domain or a
   known contact, but is sent by someone else. (See our
   [SPF, DKIM & DMARC guide](business-email-spf-dkim-dmarc-guide.md) for how to
   stop others sending "from" your domain.)
3. **Invoice / payment-change fraud (BEC)** — a message that looks like a real
   supplier or your boss, saying the bank details have changed. The money goes
   to the attacker, not the real supplier.
4. **Credential theft** — a fake login page captures your email password, then
   the attacker uses your real account to reach your customers and contacts.

## Red flags to check before you click or act

- [ ] Is the sender address exactly right — not just the display name, but the full address?
- [ ] Was I expecting this message and this attachment?
- [ ] Is it urgent or threatening ("act now or your account will be closed")?
- [ ] Does it ask me to enter a password, or open an unexpected attachment?
- [ ] Is there a payment detail change, and is it plausible?

## Invoice and payment fraud — the one rule that stops most of it

Never change payment details on the strength of an email alone. If a supplier
(or "your boss") asks you to pay a new account, **call them on a number you
already have and trust** — not a number in the message — and confirm verbally.

## What to do if you clicked or entered a password

1. Change the password for that account immediately — from a different, trusted device.
2. Turn on two-factor authentication (2FA) if it is not already on.
3. Check for "forwarding rules" or "filters" the attacker may have added inside the mailbox.
4. If money is involved, contact your bank straight away — speed matters.

## Hardening your business email

- [ ] Turn on 2FA/MFA on every mailbox and admin account.
- [ ] Use unique passwords stored in a password manager (never one shared password).
- [ ] Publish SPF, DKIM and DMARC so others cannot spoof your domain.
- [ ] Teach everyone the one-question check: *"Was I expecting this, and is the sender address exactly right?"*

## When to get it fixed for you

If you think an account has been compromised, or you would like email security
set up and verified, Linux Stewards offers email security and DNS help from £29,
delivered remotely. We lock the account down, check for forwarding rules and
other changes, and get SPF/DKIM/DMARC set so your mail is trusted.

- Website: [linuxstewards.com](https://www.linuxstewards.com)
- Email: info@linuxstewards.com

Small jobs are genuinely welcome.
