# Driver and programming cable

The programming cable connects the radio's proprietary K-plug (2-pin earphone-style port) to a USB-A port on your PC. Inside the cable is a USB-to-serial chip; the chip needs a Windows driver before CPS can talk to the radio.

## Identify your cable's chipset

The most common USB-to-serial chips on Baofeng cables:

| Chipset | Driver source | Notes |
|---------|---------------|-------|
| **Prolific PL2303** | https://www.prolific.com.tw/US/ShowProduct.aspx?p_id=225 | Most common on genuine cables |
| **FTDI FT232** | https://ftdichip.com/drivers/vcp-drivers/ | Reliable, auto-installs on Win10/11 usually |
| **CH340 / CH341** (WCH) | http://www.wch-ic.com/downloads/CH341SER_EXE.html | Common on cheap clone cables; auto-installs on Win11 |
| **Silicon Labs CP210x** | https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers | Less common on Baofeng |

### How to tell which you have (before plugging in)

Look at the cable near the USB end for a printed chip name — some are labeled on a sticker ("PL2303HX" or similar). If there's no visible marking, plug it in and check Device Manager (next section).

### How to tell which you have (after plugging in)

1. **Plug cable into a USB port** (radio doesn't need to be connected)
2. Open **Device Manager** (`Win+X` → Device Manager, or Start → type "Device Manager")
3. Expand **Ports (COM & LPT)**
4. You'll see one of:
   - `Prolific USB-to-Serial Comm Port (COM5)` — PL2303
   - `USB-SERIAL CH340 (COM5)` — CH340
   - `USB Serial Port (COM5)` — often FTDI
   - `Silicon Labs CP210x (COM5)` — CP210x
5. Record the **COM port number** (COM5 in the example) — you'll select it in CPS

### If Windows shows "Unknown Device" or a yellow ⚠️

No driver loaded. Install the driver from the table above and unplug/replug the cable. Usually resolves immediately.

## Connect cable to radio

1. Power off the radio (recommended for first connection)
2. Remove the rubber cover on the side of the radio revealing the speaker/mic jacks
3. Insert the cable's K-plug firmly — it's a 2-pin friction fit, should click / seat fully
4. Connect the USB end to PC
5. Power on the radio
6. You should NOT see a "cable detected" notification on the radio — the radio doesn't know; the PC does
7. Verify in CPS: **Program → Port** (or Settings → Comm port) — select the COM port you noted

## CPS can't see the radio — troubleshooting

Run through these in order; most people get fixed by step 1 or 2:

1. **Check Device Manager** for the COM port still appearing. If yellow bang, reinstall driver.
2. **Swap USB ports.** Try a USB-2 port specifically (USB-3 "blue" ports sometimes misbehave with older serial chipsets).
3. **Re-seat the cable** in the radio. The K-plug must be fully inserted — it's tighter than an earphone jack.
4. **Power-cycle the radio.** Sometimes needs to be off when the cable is inserted, then on.
5. **Reduce clutter:** unplug other USB-serial devices, close other programs using serial.
6. **Disable Bluetooth serial ports** if they're hoarding COM numbers.
7. **Reboot the PC** once. If that fixes it, Windows probably just needed to settle.

## Linux note

Your Arch Linux box has `uucp` group membership set up for `/dev/ttyUSB*` access — correct for serial access on Arch. However, the DM-32UV **CPS is Windows-only**, so on Linux you'd need Wine or a Windows VM to run it. We're not going down that path — your gaming PC handles Windows tasks. Linux stays the authoring / vault environment.

(See [part90-vs-part95](../01-foundations/part90-vs-part95.md) footer — nothing changes about the radio, just where the CPS runs.)

## Cable care

- **Don't yank by the cable** to disconnect — pull the plug, not the wire
- **Store coiled loosely** — tight coils stress the connector
- **Don't use as an antenna** (obvious but people joke about it)
- **A backup cable** ($10–20) is smart — if your cable dies, you can't flash the radio at all

## Related

- [install-cps-windows](install-cps-windows.md) — get CPS installed first
- [cps-ui-tour](cps-ui-tour.md) — selecting the COM port inside CPS
- [read-write-radio](read-write-radio.md) — once the cable is talking to the radio, safe procedure to read the codeplug
