# Small-business data protection & continuity checklist

A plain-English checklist for protecting the data a small business runs on —
customer records, accounts, documents, email and the website — and for keeping
working when something breaks. It is aimed at everyday Windows and Mac users, not
server administrators. (For Linux servers and databases, see
[Linux Backup & Recovery](linux-backup-recovery-checklist.md).)

## 1. Know what you would lose

- [ ] List the data that actually matters: customer/contact records, invoices and accounts, documents, email, the website and any files only one person holds
- [ ] For each item, note where it lives (a PC, a laptop, a phone, cloud storage, the website) and who can reach it
- [ ] Flag anything that exists in only one place with no copy — that is your highest risk

## 2. Follow the 3-2-1 backup rule

- [ ] Keep at least **3** copies of important data (the original plus two backups)
- [ ] Store them on at least **2** different kinds of media (e.g. an external drive and cloud storage)
- [ ] Keep at least **1** copy off-site (cloud, or a drive stored somewhere else)
- [ ] Back up on a schedule, not when you remember — daily or weekly depending on how often the data changes

## 3. Treat cloud sync and backup as different things

- [ ] Understand that a synced folder (OneDrive, Google Drive, Dropbox, iCloud) copies deletions and corruption instantly — it is not a backup
- [ ] Keep a versioned or snapshot backup in addition to any sync, so you can go back to an earlier copy
- [ ] Check that the backup keeps versions for long enough to catch a mistake (weeks, not hours)

## 4. Reduce ransomware and phishing risk

- [ ] Keep at least one backup offline or immutable so malware cannot encrypt or delete it along with the working copy
- [ ] Do day-to-day work in a standard (non-administrator) user account
- [ ] Turn on multi-factor authentication (MFA/2FA) for email, banking and any admin account
- [ ] Teach staff the one-question phishing check: "Was I expecting this, and is the sender address exactly right?"

## 5. Control who can reach the data

- [ ] Use a password manager rather than one shared password
- [ ] Keep a short list of who has access to each account or system
- [ ] When someone leaves, remove their access to email, shared folders, cloud storage and the website on their last day (offboarding)
- [ ] Review that access list every few months

## 6. Write a one-page continuity plan

- [ ] Decide what happens if the main PC/laptop dies: where the spare is, and how long to restore from backup
- [ ] Decide what happens if email or the website is down: who you call and the recovery steps
- [ ] Decide what happens if you are locked out of an account: the recovery email/phone and how to get back in
- [ ] Store the plan somewhere everyone who needs it can find it (not only on the machine that might fail)

## 7. Prove it works (the part most people skip)

- [ ] Restore a test file or folder from backup every quarter, not just check that "it ran"
- [ ] Time how long a full restore would take, so you know whether it fits your day
- [ ] Fix anything the test reveals before you need it for real

---

Maintained by [Linux Stewards](https://www.linuxstewards.com). Prefer to have
this set up and tested for you? Linux Stewards provides remote help worldwide:
[linuxstewards.com/services](https://www.linuxstewards.com/services).
