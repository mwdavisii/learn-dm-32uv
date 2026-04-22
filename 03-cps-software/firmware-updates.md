# Firmware updates — don't, unless

**Default posture: do not flash firmware.** Stock firmware does everything this project needs. A failed firmware update is the one way you can practically brick this radio. This note exists so you know when (rarely) it's worth doing, and how to survive if it's necessary.

## Firmware vs codeplug — the distinction

- **Firmware** = the radio's operating system. Lives in flash memory. Rewrites happen only via a firmware-update procedure.
- **Codeplug** = the settings file (channels, zones, contacts, etc.). Rewrites happen via every normal CPS "Write to Radio."

**Codeplug writes cannot brick the radio.** Firmware writes can.

## How to check your current firmware version

### On the radio

**MENU → Info → Version** (or similar — path varies; see [menu map](../02-radio/menu-map.md))

Record it:

- ⚠️ **Current firmware version:** ___
- ⚠️ **Radio hardware model:** DM-32UV
- ⚠️ **Serial number:** ___

### In CPS

**Program → Radio Info** (reads firmware from radio) — useful cross-check.

## When firmware updates are actually worth doing

| Scenario | Worth it? |
|----------|-----------|
| A specific documented bug you're hitting | ✅ Yes |
| Manufacturer advisory / recall | ✅ Yes |
| New feature you genuinely need (new DMR mode, improved audio) | ✅ Maybe, weigh risk |
| Fix for a security / legal compliance issue | ✅ Yes |
| "I saw a newer version online" | ❌ No |
| "Curiosity" | ❌ No |
| "Someone on Reddit said it's better" | ❌ No |
| "I want to see what's new in the changelog" | ❌ Read the changelog; don't flash |
| "My codeplug is behaving weirdly" | ❌ **99% chance it's a codeplug issue, not firmware** — fix the codeplug first |

## The procedure (if you must)

**Read every step before starting.** Do not half-way this.

### Before

- [ ] Battery ≥ **80%** (ideally 100%)
- [ ] Radio **on the AC charger** during the entire update — external power through the charger cradle is still not a guarantee of uninterrupted supply; a fully-charged battery PLUS the charger is the safest combo
- [ ] Download firmware image + firmware-updater tool **from Baofeng Tech / BTech only** — NEVER a forum attachment or a filesharing link
- [ ] Record the new firmware version and the release notes — know what you're getting
- [ ] **Save a current codeplug backup.** Firmware updates often reset the codeplug; you'll need to re-flash your codeplug afterward.
- [ ] **No storms nearby.** A brown-out during firmware write is exactly the scenario you're trying to avoid.
- [ ] Cable, USB port, COM port all verified working (successful codeplug read within the last 24 hours is a good check)

### During

- [ ] Close all other USB / serial programs
- [ ] Put the radio into firmware-update mode — this usually means holding a specific key combo while powering on (⚠️ verify the exact combo from the manufacturer's firmware update instructions; the DM-32UV docs typically describe it)
- [ ] Launch the firmware updater (separate tool from CPS, usually)
- [ ] Point it at the firmware image file
- [ ] Click "Update" — **do not touch anything, including the computer, for the entire duration** (typically 2–5 minutes for this radio)
- [ ] Progress bar will complete; radio will typically reboot itself
- [ ] **Wait an extra 30 seconds after it looks done** before unplugging anything — some updaters do post-verification

### After

- [ ] Power-cycle the radio
- [ ] Verify version in MENU → Info → Version matches the new one
- [ ] Read the (now likely factory-default) codeplug in CPS
- [ ] Write your saved codeplug back to the radio
- [ ] Verify everything still works (tune NOAA, a ham repeater, a GMRS channel)
- [ ] Update this note: "Firmware updated YYYY-MM-DD from vX to vY; reason: ___"

## If a firmware update fails

### Symptom 1: progress bar stalls

**Don't panic. Don't disconnect.**

- Wait a full minute of no progress before doing anything
- If truly stuck: cancel the updater, unplug cable, cable back in, restart updater, try again
- The radio may appear unresponsive — it's in firmware-update mode, not crashed

### Symptom 2: radio won't power on after update

The radio is in "boot loop" or "dead" state. Recovery procedure for Baofeng DMR radios typically:

1. Remove and reinsert the battery
2. Hold the specific "firmware recovery" key combo (often PTT + side key + power) while reconnecting battery
3. If a service-mode LED lights up, the radio is in recovery — the firmware updater should detect it and offer to retry
4. Retry the update

If recovery doesn't work:

- **Contact Baofeng Tech support** — they can often help via email walkthrough
- **Dealer warranty** — if within the warranty window, exchange it
- **Assume total loss** — in the absolute worst case. This is why we don't flash firmware casually.

⚠️ The exact recovery key combo varies by model and revision. Baofeng's support page or the firmware updater's README usually documents it. If you're about to flash firmware, **find and record this combo before** you start.

## Final rule

**Never update firmware at 2 AM.** Bad decisions happen. If you're tempted to flash firmware, sleep on it.

## Related

- [read-write-radio](read-write-radio.md) — normal codeplug read/write (safe; can't brick)
- [Battery care](../02-radio/charging-battery-care.md) — why battery level matters here
- [install-cps-windows](install-cps-windows.md) — CPS itself doesn't update firmware; there's usually a separate tool
