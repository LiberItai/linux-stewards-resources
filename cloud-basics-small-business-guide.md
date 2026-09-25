# Cloud basics for small business: hosting, storage and backup in plain English

A plain-English guide to what "the cloud" actually is, the three shapes it comes
in, and how to decide what belongs there. Maintained by
[Linux Stewards](https://www.linuxstewards.com), a UK-based technology-services
business. If you would rather have this set up for you, see
[linuxstewards.com/services/hosting-devops](https://www.linuxstewards.com/services/hosting-devops).

"The cloud" simply means someone else's computers, rented over the internet
instead of bought and kept in your office. That one idea shows up in three very
different ways, and mixing them up causes most of the confusion.

## The three shapes of "cloud"

1. **Software as a Service (SaaS)** — programs you use in a browser: email
   (Google Workspace, Microsoft 365), accounts, CRM, bookkeeping. You do not
   install or maintain anything; you pay a subscription and log in.
2. **Cloud storage / sync** — files stored remotely and synced across devices
   (OneDrive, Google Drive, Dropbox, iCloud). Handy, but see the warning below.
3. **Cloud hosting / infrastructure** — your website or application runs on a
   rented server instead of a machine you own. This is where "the server" lives
   when you use most modern web hosts.

## Cloud vs. on-premises (when it actually matters)

| | Cloud | On-premises (own hardware) |
|---|---|---|
| Up-front cost | Low, pay monthly | High, buy hardware |
| Who maintains it | The provider (mostly) | You |
| Where your data lives | The provider's data centre | Your office |
| Internet dependence | Needs a connection | Works offline |

For most small businesses the practical question is not "cloud or not" — it is
**which** services, **who can reach your data**, and **how you get it back out**.

## Sync is not backup

A synced folder (OneDrive, Google Drive, Dropbox, iCloud) copies deletions and
corruption instantly to every device. If a file is deleted, encrypted by
malware, or overwritten by mistake, the sync cheerfully spreads the damage. Keep
a separate, versioned backup in addition to any sync — see our
[data protection & continuity checklist](business-data-protection-checklist.md).

## Before you move something to the cloud

- [ ] List what the data or system is, and why it needs to move.
- [ ] Confirm who owns the account — use a business account you control, not one tied to a single employee.
- [ ] Check where the data will be stored and whether that matters to you (or your customers).
- [ ] Confirm the monthly cost, including the parts that are easy to miss (storage, bandwidth, support).
- [ ] Plan the way back: can you export your data and leave if you need to?

## A safe migration checklist

- [ ] Back up everything before you start.
- [ ] Move one system or dataset at a time, not everything at once.
- [ ] Test the new setup with a small amount of real data before switching over.
- [ ] Keep the old system running in parallel until the new one is proven.
- [ ] Record the new login details and recovery methods somewhere safe.

## When to get it fixed for you

If the options are unclear or you would rather not spend the time on trial and
error, Linux Stewards offers cloud and hosting setup, migration and backup help
quoted up front and delivered remotely. We set it up, test that it works and
that your data can be restored, and hand over the credentials and a short
handover note.

- Website: [linuxstewards.com](https://www.linuxstewards.com)
- Email: info@linuxstewards.com

Small jobs are genuinely welcome.
