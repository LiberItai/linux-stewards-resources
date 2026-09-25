# You've been hacked? First steps for a small business

A calm, ordered checklist for the first hours after a small business discovers a
security problem — a compromised email account, ransomware, a defaced website,
or a taken-over account. Maintained by
[Linux Stewards](https://www.linuxstewards.com), a UK-based technology-services
business. If you need this handled for you, see
[linuxstewards.com/services/cybersecurity](https://www.linuxstewards.com/services/cybersecurity).

The instinct under pressure is to delete things and click around. That usually
destroys the evidence you need and can make the damage worse. Work through these
in order.

## Step 0 — stay calm, and do not delete evidence

- [ ] Do not delete emails, files or accounts yet — they may be the evidence you need.
- [ ] Write down what you have observed, with times and screenshots where possible.

## Step 1 — identify what actually happened

| Sign | What it usually means |
|---|---|
| Emails you did not send, or contacts reporting odd messages | Email account taken over |
| Files renamed with a strange extension and a ransom note | Ransomware |
| Website shows spam, ads or a warning | Website compromised |
| You are locked out of an account you use | Account taken over |
| Money moved or a payment made you did not approve | Payment/account fraud |

## Step 2 — contain it (do these first)

- [ ] Disconnect the affected computer from the internet (Wi-Fi off / unplug the cable).
- [ ] From a *different, trusted* device, change the password of the affected account.
- [ ] Turn on two-factor authentication (2FA) on that account immediately.
- [ ] Sign out of all sessions / revoke other devices for that account.

## Step 3 — handle the specific case

**Email takeover:**
- [ ] Check for forwarding rules or filters the attacker added (they often keep a copy of your mail).
- [ ] Check the account's "recent sign-in" or "activity" page for unknown devices or locations.
- [ ] Tell key contacts to treat unexpected messages from you with caution.

**Ransomware:**
- [ ] Do not rush to pay — paying does not guarantee your files back and marks you as a repeat target.
- [ ] Isolate the machine; restore from an offline or versioned backup if you have one.
- [ ] Preserve the ransom note and any affected files as evidence.

**Website defaced or serving spam:**
- [ ] Take the site offline (or ask your host to).
- [ ] Restore from the most recent clean backup.
- [ ] Find and close how they got in (old plugin, weak password, exposed admin page) before bringing it back.

## Step 4 — preserve evidence

- [ ] Save screenshots of anything unusual (messages, ransom notes, changed bank details).
- [ ] Keep the original emails and files, not just notes about them.
- [ ] Note the dates and times you noticed each thing.

## Step 5 — notify the right people

- [ ] If money moved or bank details were changed, contact your bank immediately.
- [ ] If customer or personal data may have been exposed, note it — you may need to tell those affected.
- [ ] In the UK, consider reporting to Action Fraud (police cybercrime reporting).

## Step 6 — after it is contained

- [ ] Review every account's access list and remove anything you do not recognise.
- [ ] Set up or restore proper backups, including at least one offline copy.
- [ ] Harden the entry point so it cannot happen the same way twice.

## When to get it fixed for you

If any of this is unclear, or the incident is ongoing, Linux Stewards offers
security incident help and clean-up quoted up front and delivered remotely. We
contain it, find the entry point, restore clean data, and help you harden the
gap so it does not repeat.

- Website: [linuxstewards.com](https://www.linuxstewards.com)
- Email: info@linuxstewards.com

Small jobs are genuinely welcome.
