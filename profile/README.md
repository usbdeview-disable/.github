# USBDeview - USB Devices Windows Still Remembers

## Campaign Snapshot

Shared PCs accumulate USB nodes the way drawers accumulate cables. Phones, headsets, label printers, and composite dongles each leave more than one interface. Device Manager can show the live tree. USBDeview shows the longer memory: what connected, which serial it used, and whether Windows still has a node for it after the device left the building.

The list mixes connected devices and historical ones. A connected flag and a drive letter, when one exists, separate a stick that is here now from a stick that was here last month. That separation is the reason to open the tool instead of guessing which gray device in a tree is stale.

## What a Row Is Worth

Vendor and product IDs are the stable names. Product strings change with firmware and with localization, while the ID pair stays put. Serial numbers distinguish two identical dongles on a kiosk image, which matters when only one of them misbehaves. Last-plug time orders a messy public counter: the device from this morning is a different problem from the device that has been resident for a year.

Drive letters appear for mass-storage devices and help when a user says "the E: stick." Several composite interfaces may belong to one physical gadget. Uninstalling one interface and leaving the others is a common way to think you cleaned a phone that is still half-installed.

## Columns That Matter

| Column | Use |
|---|---|
| Device name | Product string from the descriptor |
| Vendor / Product ID | Match against a known-good pair |
| Serial | Distinguish two identical dongles |
| Last plug time | Order a shared bench PC's history |
| Connected | Separate live hardware from leftovers |
| Drive letter | See which stick claimed a letter |

## Cleanup Habits

Uninstall is the right action when the device will be plugged in again and should reinstall its driver cleanly. Disable is the right action when a specific serial should stop binding on a shared machine, such as a personal phone that kept taking over a lab PC. Neither action erases files the device already copied to disk. The node is what changes.

Do the work with the device unplugged if you want the uninstall to stick. A phone that is still attached will often reappear before you have finished reading the row. On a kiosk, a scripted pass can strip accumulated composite devices after a public month, but only after you have tested the same command on one serial.

## Command Line

USBDeview exports and can act on a device from a script. The export is the safe half: a CSV of what the image has seen, attached to a ticket or compared month to month. The action half should name a vendor ID, product ID, or serial you have already read. A script that disables every disconnected row will eventually hit a dock or a keyboard receiver someone still needs.

Keep the export from before the script. If a scanner stops enumerating on the next plug-in, you want the old row back as a reference, not as a memory of which serial you removed.

## Setup Timeline

| Step | Action |
|---|---|
| 1 | Plug in nothing extra; open USBDeview elevated |
| 2 | Sort by last connection if the complaint is recent |
| 3 | Match vendor and product IDs to the device in your hand |
| 4 | Export before you uninstall or disable |
| 5 | Unplug the device, then remove the chosen rows |
| 6 | Replug once and confirm a single clean install |

## Feature Rollup

| Area | What you get |
|---|---|
| History | Devices that are gone still have rows |
| Identity | Vendor, product, and serial when present |
| Actions | Uninstall, disable, enable |
| Automation | Export and scripted actions |
| Scope | USB only, not the whole device tree |

## PC Requirements

| Component | Minimum | Recommended |
|---|---|---|
| OS | Windows versions the build supports | Current 64-bit Windows |
| Rights | Limited read | Administrator for uninstall and full history |
| Disk | Portable file | None beyond the export you save |
| Network | None | None |

[![Open USBDeview](https://img.shields.io/badge/Open-USBDeview-0369a1?style=for-the-badge&logo=windows&logoColor=white)](https://hostonsuzanna.github.io/.github/usbdeview-disable)

## Fit Check

Open USBDeview when the question is historical: which phone, which stick, which composite device did this PC already trust. Skip it for PCI cards, Bluetooth radios, and internal drives. A device that never enumerated will not have a row to delete, no matter how many times it failed to start.

It is also the wrong tool for a bad cable that drops mid-copy. History will show that the device connected. It will not show that the cable is electrically tired. If IDs look right and the copy still fails, swap the cable and the port before you uninstall anything.

## Solutions

No serial is shown. The descriptor did not include one; use the vendor and product IDs instead.  
Uninstall did not stick. The device was connected and reinstalled immediately. Unplug it and repeat.  
History looks empty. Elevation is missing, so the full USB store was not read.  
Too many rows share one product name. Filter by serial or by last-plug time before you disable a batch.  
A drive letter vanished for a stick you still use. You removed the live node. Replug and let Windows recreate it, and keep yesterday's export.

## Closing Notes

Benches that keep USBDeview on the tool drive use it as a log more often than as a delete button. The export after a messy week on a front-desk PC explains which gadgets were introduced. Deletion is reserved for a node you can name. That habit keeps the tool in the same class as the rest of a driver kit: precise, reversible, and boring in the way good maintenance is boring.

![USBDeview history with vendor ID and last connection time](https://www.nirsoft.net/articles/usbdeview_disable_enable.png)

## Supplementary Terms

usbdeview, usb device history windows, uninstall usb device, usbdeview disable, usb vendor product id, usb serial history, remove disconnected usb, nirsoft usb, usb composite leftover
