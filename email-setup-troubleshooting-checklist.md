# Small-business email setup & troubleshooting checklist

A plain-English checklist for setting up and fixing business email on everyday
Windows, Mac and mobile devices. It is written for small-business owners who are
not IT staff — the goal is to get email working reliably and avoid the two most
common problems: lost mail and missed logins. (For server-side email, treat this
as the user-facing half; the server itself is a separate Linux job.)

## 1. Choose an address people will trust

- [ ] Use an address on your own domain (you@yourcompany.com) rather than a free personal address — it reads as more established and is easier to keep if you change providers
- [ ] Set up a second, non-obvious address for the admin/logins side of the business (billing, domains, hosting) so a staff change never locks you out of accounts
- [ ] Record the domain registrar, the DNS/nameserver provider and the email host in one place — you will need all three at some point

## 2. Set up email on each device the right way

- [ ] Use the provider's own instructions (IMAP for mail on several devices, not POP3, so read/deleted state stays in sync everywhere)
- [ ] On a phone or tablet, install the provider's app or add the account to the built-in Mail app, then confirm both sending and receiving work with a test message
- [ ] On a computer, use a mail app you are comfortable with (Outlook, Apple Mail, Thunderbird, or the provider's webmail) — consistency matters more than which one
- [ ] Set a clear display name (your real name or company name) that appears alongside the address

## 3. Stop mail from going to spam

- [ ] Ask the provider to enable SPF, DKIM and DMARC for your domain, or add the records yourself if you manage DNS — this measurably reduces the chance your mail is marked spam
- [ ] Send a test to a personal Gmail/Outlook address and check it lands in the inbox, not spam
- [ ] Keep the sending volume reasonable and avoid buying lists — a reputation takes a long time to build and seconds to lose

## 4. Protect the account (this is where businesses get hurt)

- [ ] Turn on two-factor authentication (2FA/MFA) for every mailbox — email is the master key to most other accounts
- [ ] Use a password manager so each account has a unique, strong password
- [ ] Set a recovery email and phone number on the account, and check they are current
- [ ] Never click a link in an unexpected "your mailbox is full / verify your account" email — type the provider's address yourself instead

## 5. Fix the common problems in order

- [ ] **Can't send but can receive** — check the outgoing (SMTP) server name, port and that authentication is enabled; also check the mailbox isn't over its storage quota
- [ ] **Can't receive but can send** — check the inbox isn't full, look for a mis-typed forwarding rule or filter, and confirm the incoming (IMAP) server details are correct
- [ ] **Mail going to spam** — check SPF/DKIM/DMARC are passing (see step 3) and that your domain isn't on a blocklist
- [ ] **Forgotten password / locked out** — use the recovery path you set in step 4; if there is none, this is why the admin/backup address in step 1 matters

## 6. Keep it maintainable

- [ ] Export a backup of important mail at least once a quarter (a local archive or a second mailbox copy)
- [ ] Keep a one-page note of every mailbox, who uses it and what it's for, and update it when someone joins or leaves
- [ ] When a person leaves, change shared passwords and revoke their mailbox access the same day

---

Need this done for you instead? [Linux Stewards](https://www.linuxstewards.com/contact)
provides remote email setup and troubleshooting for small businesses — entry
fixes start from £12.
