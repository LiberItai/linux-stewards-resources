# Secure remote access: how it works and how to stay safe

Remote access lets a technician see and control your computer over the internet,
or lets you reach your own office machine from elsewhere. It is powerful — and a
common way people get scammed, so this guide covers both how it works and how to
do it safely.

Maintained by [Linux Stewards](https://www.linuxstewards.com).

## The two kinds of remote access

- **Attended (screen-sharing) access** — you are at the computer, you open the
  tool, and you read out or send a **one-time session code**. The other person can
  only connect while that session is open. This is what legitimate support uses.
- **Unattended access** — you install software that lets a device be reached any
  time without you present. Convenient for your *own* machines, but only ever set
  this up with a tool you trust and a strong password or key.

For one-off support, attended access is the safe default. There is no reason a
support call should need unattended access.

## What makes a remote-access session safe

- **A one-time code** that changes for every session — not a fixed password.
- **Your consent is visible**: you see the connection request, and you can end the
  session at any time by closing the app.
- **You can watch** what the other person does on screen while it happens.
- **The session ends cleanly**: closing the app or clicking "end session" stops
  the connection; restarting the computer also clears an attended session.

## Red flags — the scam patterns

- A caller *you did not contact* offers to "fix" a virus or refund you and asks
  you to install a remote-access app. This is the classic tech-support scam.
  Hang up.
- Anyone who asks you to log into your bank with them watching.
- Anyone who asks for a password, PIN or payment card over chat while connected.
- Pressure to act fast or keep it secret.

A genuine provider you approached yourself will confirm the scope and price first,
will not ask for your bank password, and will be happy for you to watch the whole
session.

## Before you let anyone in

- [ ] Confirm you contacted them, or you know exactly who they are.
- [ ] Close anything sensitive — banking, email, personal documents — before the session.
- [ ] Use the tool's **attended** mode with a one-time code, not unattended access.
- [ ] Agree what will be done and what it costs before they start.
- [ ] Remove the remote-access software afterwards if you will not need it again.

## Setting up remote access to your own machine

For reaching your *own* computer when away, the same rules apply with a little
more care:

- Use a well-known, maintained remote-access tool (for example the built-in remote
  desktop in Windows Pro, or a reputable third-party tool for unattended access).
- Turn on two-factor authentication on the account that controls the remote access.
- Use a long, unique password — not the one you use elsewhere.
- Turn off the "always on" service when you are not travelling; an open remote
  door is a door a thief can also try.

## For Linux machines

On Linux, remote support is usually SSH for servers (key-based, no passwords) or
a screen-sharing session for desktops. Keep SSH on key authentication only, on a
non-default port or behind a firewall, and disable password login:

```bash
sudo nano /etc/ssh/sshd_config
# set: PasswordAuthentication no
sudo systemctl restart ssh
```

## Get support done safely

Linux Stewards provides remote Windows, Mac and Linux support with scope and
price agreed before work begins — attended, one-time sessions you can watch and
end at any time.

[Request remote IT support](https://www.linuxstewards.com/services/pc-it-support?utm_source=github&utm_medium=organic_content&utm_campaign=os_it_support_202609&utm_content=secure_remote_access)

---

A free resource from [Linux Stewards](https://www.linuxstewards.com/). Reuse under
this repository's MIT licence.
