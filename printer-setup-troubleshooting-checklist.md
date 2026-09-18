# Printer setup & troubleshooting (Windows & Mac)

Plain-English steps for setting up a new printer or fixing one that will not print,
shows "offline", or prints badly — before you spend on a call-out. This is a free
guide from [Linux Stewards](https://www.linuxstewards.com); if you would rather have
it done for you, we provide remote IT help worldwide.

## Start here (in order)

1. **Check power and connection.** Is the printer switched on, and is the power cable
   seated at both ends? Is the USB cable plugged in, or is the printer on your Wi-Fi?
2. **Restart.** Power the printer off, wait 10 seconds, then power it back on. Then
   restart the computer you are printing from.
3. **Check for error states.** Look at the printer's screen or lights: paper jam, empty
   paper tray, low or missing ink/toner, or a blinking warning light.
4. **Check the print queue.** On Windows open *Settings → Bluetooth & devices → Printers
   & scanners* and open the queue; on Mac open *System Settings → Printers & Scanners*
   and click the printer. Clear any stuck or paused jobs.

## Getting the printer recognised

- **USB printer:** unplug and replug the USB cable, and try a different port. If Windows
  does not install it automatically, use *Add a printer* and let it search.
- **Network/wireless printer:** make sure the printer and computer are on the same
  network (a 2.4 GHz guest network can separate them). Add it via *Add a printer* rather
  than expecting it to appear by itself.
- **Driver missing:** install the printer's driver from the manufacturer's own website
  (HP, Canon, Epson, Brother, etc.), not from a random download site. Macs usually need
  no extra driver for AirPrint printers.
- **Set it as default.** In *Printers & scanners*, right-click (or Control-click on Mac)
  the printer and choose *Set as default* so jobs stop going to the wrong printer.

## "Offline" or "not responding" fixes

- Clear all stuck jobs, then **remove and re-add** the printer.
- On Windows, restart the print spooler: open *Services*, find *Print Spooler*, click
  *Restart*.
- On Mac, reset the printing system: in *Printers & Scanners*, right-click in the printer
  list and choose *Reset printing system*, then add the printer again.
- Check the printer's own network status page or app for its IP address, and confirm the
  computer can reach it.

## Print quality problems

- Run the printer's own head-cleaning or alignment routine from its screen or app.
- Replace any low or dried-out ink/toner cartridges (genuine or a reputable compatible
  brand).
- Check the paper: wrong type, damp paper, or a mis-set paper size causes smears and jams.
- Print a test page to confirm the driver is the correct model, not a near-match.

## When to call for help

- You have cleared the queue, re-added the printer and restarted the spooler, but it is
  still offline or silent.
- The printer works from one device but not others on the same network.
- There are repeated paper jams or hardware fault lights that do not clear.
