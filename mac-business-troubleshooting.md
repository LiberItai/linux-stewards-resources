# Mac in a small business: accounts, backups and troubleshooting

A plain-English guide to running Macs in a small business — more than one user,
data that matters, and the settings that keep it safe. This is about the daily
business setup, not the "Mac is slow or frozen" fixes (see the Windows & Mac
troubleshooting checklist in this repository).

Maintained by [Linux Stewards](https://www.linuxstewards.com). While Linux is our
specialist strength, macOS is fully supported.

## 1. Separate accounts for each person

Use one macOS user account per person rather than a shared login. This keeps
files private, makes it clear who changed what, and makes offboarding simple.

- Apple menu → System Settings → Users & Groups → Add User.
- Give each person a **standard** account, not an administrator account.
- Keep at least one administrator account (yours) separate from daily work.

Standard accounts stop staff from installing software or changing security
settings by accident.

## 2. Backups that actually restore

Time Machine is a good start but it is a single copy on a single disk. For a
business, follow the 3-2-1 rule: three copies of important data, on two different
types of media, one of them off-site.

- System Settings → General → Time Machine → Add Backup Disk.
- Test the restore at least once: open the backup and confirm you can find and
  open a real file. An untested backup is a hope, not a backup.
- For business-critical data, add a cloud copy (a synced folder is *not* a backup —
  a deleted file disappears from the sync too; use a versioned cloud backup).

## 3. Turn on full-disk encryption

System Settings → Privacy & Security → FileVault → Turn On. Save the recovery key
somewhere safe and separate from the Mac. A lost key with no backup means the
data is gone — FileVault does its job a little too well.

## 4. App installs and Gatekeeper

By default macOS blocks apps from unidentified developers — that is a feature,
not a bug. When a legitimate app will not open:

- Right-click (or Control-click) the app and choose Open, then confirm — this
  allows that specific app once without turning Gatekeeper off.
- Do **not** disable Gatekeeper globally (the `spctl --master-disable` route) just
  to make an install work.

Prefer the App Store or the software vendor's own site; be suspicious of free
copies of paid software.

## 5. Sharing files between Macs

- For files on the same network: System Settings → General → Sharing → File
  Sharing, then add folders and pick which users can reach them.
- For files used from anywhere, use a proper shared drive (cloud or a small
  server) rather than emailing attachments back and forth.

## 6. Common business-Mac problems

- **"Disk Almost Full"** — check System Settings → General → Storage; the
  recommendations (empty Trash, review large files) are usually enough. Time
  Machine local snapshots can also fill a disk — connect the backup disk to
  flush them.
- **App asks for permission it should already have** — System Settings →
  Privacy & Security → [Camera / Microphone / Files & Folders] and re-check the
  app's toggle.
- **Keychain keeps prompting** — Keychain Access app → run Keychain First Aid,
  then sign out and back in to iCloud Keychain if it persists.
- **A staff Mac leaves the business** — sign them out of iCloud and any business
  accounts, remove their local user, and (for a business-managed device) remove
  the device from Apple Business Manager so the next owner can use it.

## 7. When the business grows

Once there are more than a few Macs, Apple Business Manager and mobile device
management (MDM) let you push settings, apps and security policy from one place.
That is a step change in setup cost, so do it when you have several devices to
look after, not before.

## Get help

Linux Stewards provides remote Windows, Mac and Linux support for small
businesses — from one-off fixes to a managed setup.

[Ask about Mac and IT support](https://www.linuxstewards.com/services/pc-it-support?utm_source=github&utm_medium=organic_content&utm_campaign=os_it_support_202609&utm_content=mac_business_guide)

---

A free resource from [Linux Stewards](https://www.linuxstewards.com/). Reuse under
this repository's MIT licence.
