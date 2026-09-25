# Linux workstation troubleshooting

A practical, command-first guide to fixing a Linux desktop or laptop used for
day-to-day work — not a server. This covers the problems you hit on a workstation:
a desktop that will not start, no sound, missing Wi-Fi, a broken package manager,
or a frozen screen. Shown for Ubuntu/Debian-family systems; the ideas transfer to
Fedora and others (swap `apt` for `dnf`).

Work top to bottom. Run commands as your normal user and use `sudo` only where
noted. If a step feels risky, stop and back up first.

## 1. Recover a frozen or black screen

- Try the magic SysRq safe restart first: hold `Alt` + `SysRq` (often `Print
  Screen`), then slowly press `R E I S U B` — each key a second apart. This shuts
  down cleanly when the mouse and keyboard seem dead.
- Switch to a text console to rescue a stuck graphical session:
  `Ctrl+Alt+F3`, log in, then `sudo systemctl restart gdm3` (or `lightdm`,
  `sddm` — whichever display manager you use).
- If the screen is black but the machine is on, check whether it is the display
  or the whole system: press `Ctrl+Alt+F3`; a login prompt means the OS is fine
  and only the desktop session crashed.

## 2. Find what actually went wrong

```bash
journalctl -b -1 -p 3 --no-pager | tail -50   # errors from the previous boot
journalctl -b -0 -p 3 --no-pager | tail -50   # errors from this boot
```

The last lines before a crash usually name the culprit — a driver, a disk, a
package. `dmesg` gives kernel-level messages (hardware, drivers):

```bash
sudo dmesg | tail -40
```

## 3. No sound

```bash
systemctl --user status pipewire pipewire-pulse   # or pulseaudio on older systems
pactl list sinks short                            # what the system thinks it can output to
wpctl status                                      # WirePlumber view (PipeWire systems)
```

If the sink list is empty or wrong, restart the audio stack:

```bash
systemctl --user restart pipewire pipewire-pulse wireplumber
```

Then check the output device in Settings → Sound — a laptop often "plays" to the
wrong HDMI/headphone output.

## 4. Wi-Fi missing or dropping

```bash
nmcli device status          # is the Wi-Fi radio on and managed?
nmcli radio wifi on          # re-enable a software-disabled radio
nmcli device wifi list       # can the adapter see networks at all?
```

If `nmcli device status` shows the adapter as `unmanaged` or missing entirely,
the driver is usually the problem:

```bash
lspci -k | grep -A3 -i network    # identify the chip and its kernel driver
```

Common fixes, in order: reboot after a kernel update; install `linux-firmware`;
or search for your exact chip model — a Realtek or MediaTek chip often needs a
specific firmware package.

## 5. Package manager errors

```bash
sudo apt update            # refresh the package lists first
sudo apt --fix-broken install   # repair a half-installed package
sudo dpkg --configure -a   # finish any interrupted configuration
```

"Unable to lock" errors just mean another process is using the package manager —
close the Software Centre or wait. For "held broken packages", run
`sudo apt update` then retry; if it persists, read the specific package names it
names and check for a third-party repository (`/etc/apt/sources.list.d/`) pinning
an incompatible version.

## 6. The system will not boot to the desktop

1. At the boot menu choose the **previous kernel** (advanced options) — a bad
   kernel or driver update is the most common cause.
2. Boot into **recovery mode**, then drop to a root shell and:
   ```bash
   sudo apt update && sudo apt dist-upgrade   # or fix the package that broke it
   sudo dpkg --configure -a
   ```
3. Check disk space — a full root partition stops the desktop from starting:
   ```bash
   df -h /
   ```

## 7. Free disk space safely

```bash
du -sh ~/.cache ~/.local/share/Trash ~/Downloads 2>/dev/null
sudo journalctl --vacuum-size=200M                  # trim old logs
sudo apt clean                                      # clear the package cache
```

Aim to keep at least 10–15% of the root filesystem free.

## When to stop and get help

Stop if a step needs data you cannot afford to lose or a command you do not
understand. Write down the last error line, what you changed, and the hardware
model — that summary turns a slow repair into a fast one.

Linux is our specialist strength. Linux Stewards provides remote Linux,
Windows and Mac support for individuals and small businesses, with scope and
price agreed before work begins:

[Ask Linux Stewards about Linux support](https://www.linuxstewards.com/services/linux?utm_source=github&utm_medium=organic_content&utm_campaign=os_it_support_202609&utm_content=linux_workstation_troubleshooting)

---

A free resource from [Linux Stewards](https://www.linuxstewards.com/). Reuse under
this repository's MIT licence.
