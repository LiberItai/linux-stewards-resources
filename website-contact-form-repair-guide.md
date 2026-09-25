# Website contact form not sending enquiries? A step-by-step fix guide

A plain-English guide for small-business owners whose website contact form has
stopped delivering messages. Maintained by
[Linux Stewards](https://www.linuxstewards.com), a UK-based technology-services
business. If you would rather have this diagnosed and fixed for you, see
[linuxstewards.com/services/website-quick-fixes](https://www.linuxstewards.com/services/website-quick-fixes).

When a contact form "stops working", the problem is almost never the form alone.
A form is four parts, and the break can be in any of them:

1. **The form itself** — wrong field, broken validation, or the submit button
   no longer firing.
2. **The sending path** — the script/service that turns a submission into an
   email.
3. **Email delivery** — your mailbox rejecting or silently dropping the message
   (spam filters, missing SPF/DKIM/DMARC, a full or misconfigured inbox).
4. **DNS and hosting** — the records that tell the world where your mail should
   go.

## Start here: reproduce it

1. Submit the form yourself with a test message and an email address you can
   check (not the same mailbox the form sends to — you want to see the raw
   result).
2. Note exactly what happens: does the page thank you, error, or hang? Do you
   get an auto-reply?
3. Check **spam/junk** in the receiving inbox before assuming nothing arrived.

## The most common causes, in order

### 1. The form sends to a mailbox that no longer exists
If the form is set to deliver to a deleted address (a former employee, a
decommissioned domain), messages go nowhere. Fix: point the form at a current,
monitored mailbox.

### 2. The sending email is not authorised (SPF/DKIM/DMARC)
If the form sends "from" your domain but the DNS records are missing or wrong,
many providers will reject or junk it. Fix: publish the correct SPF, DKIM and
DMARC records for your domain.

### 3. A plugin or service update broke the connection
If you use WordPress or a form plugin, an update can break the mail-sending
integration. Fix: update or reconnect the sending service, or switch to a
dedicated transactional mail route.

### 4. The form uses a mail service that changed its rules
Some free senders now require domain verification. If verification lapsed, sends
silently stop. Fix: re-verify the domain in the sending service.

### 5. Messages are going to spam
If you receive them but customers say you never reply, the messages are likely
in junk. Fix: improve deliverability records and, if possible, set the form to
send from a properly authenticated address.

## What to gather before asking for help

- The form's page URL.
- The receiving email address the form should deliver to.
- A short note on when it last worked and what changed since (a plugin update, a
  new website, a domain or email move).
- Whether the messages arrive anywhere (including spam).

## When to get it fixed for you

If any of the above is unclear or you would like it handled without the trial
and error, Linux Stewards offers a fixed-price contact-form repair from £29,
delivered remotely. We trace the whole path — form, sending, delivery and DNS —
and get customer messages reaching you again.

- Website: [linuxstewards.com](https://www.linuxstewards.com)
- Email: info@linuxstewards.com

Small jobs are genuinely welcome.
