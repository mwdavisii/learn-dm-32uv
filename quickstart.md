# Quickstart — On the air in 30 minutes

You just unboxed a Baofeng DM-32UV. You want to hear *something* before dinner. This page is the shortest path — no codeplug needed yet, just manual VFO tuning.

> **Before you start:** you're pre-Tech. **Do not press PTT on any ham channel.** GMRS is fine (you're licensed). Full discipline rules in [RX-only before license](01-foundations/rx-only-before-license.md).

## 1 — Charge the battery *(skip if already charged)*

Snap the battery onto the back of the radio, plug the charger base in, drop it in. Red LED = charging, green = done. Takes ~4 hours from empty. Don't use while fast-charging. *More in `[charging-battery-care](02-radio/charging-battery-care.md)` (Phase 2).*

## 2 — Attach the antenna and power on

Screw the antenna on finger-tight. **Never transmit without the antenna attached** — on a ham radio this can damage the PA; on a DMR HT it's risky. Power on: hold the top-right knob a second.

## 3 — Tune NOAA weather (works from anywhere in Memphis)

The easiest confirmation your radio works.

- Go to **VFO mode** (manual tune) — `[VFO/MR]` button, or `[A/B]` if it's a split-band model. Menu → `Radio` → `Mode` → `VFO`.
- Enter: **`162.475`** MHz (Memphis NWR, station **KWJ76** — WX3 on the standard weather channel table)
- Mode: **Narrow FM**
- You should hear the continuous weather forecast loop within a few seconds.

**If you hear a computer voice reading forecasts: your radio works.** That's a real received signal. Note it as `#verified` mentally — we'll record it formally in Phase 4.

## 4 — Tune a Memphis ham repeater (RX-only — do not key up)

- Enter: **`146.820`** MHz (**W4BS** 2 m, Delta Amateur Radio Club)
- Offset: −600 kHz (repeater input is 146.220; you don't care for RX)
- Tone: open squelch is fine for listening; if nothing is heard and you suspect activity, set CTCSS 107.2 Hz (decode) to filter noise
- Mode: wide FM (or leave default)

Delta ARC runs a **nightly net at 8:00 PM local time on W4BS 146.820.** Tune in on a weeknight and you'll hear 15–30 people check in by callsign over ~30 minutes. Best introduction to Memphis ham activity.

**Reminder:** PTT stays untouched on this channel until your Tech license arrives.

## 5 — Try a GMRS simplex channel (you can TX here)

- Enter: **`462.5625`** MHz (GMRS channel 1, shared with FRS 1)
- Mode: narrow FM
- Tone: open squelch to start

If you own a pair of cheap family radios, power one up, set it to channel 1 with no tone, and key it up nearby. Your DM-32UV should hear it clearly — and you can key up in reply. This is your first legitimate TX.

See the [full GMRS channel list](05-memphis-setup/gmrs-channels-memphis.md) for all 30 channels.

## Done — what's next

You've confirmed the radio works on all three relevant services: NOAA, ham RX, GMRS simplex. Next:

1. Read [Ham radio landscape](01-foundations/ham-radio-landscape.md) to understand what you were just hearing.
2. Skim [Memphis ham repeaters](05-memphis-setup/local-ham-repeaters.md) and [Memphis DMR repeaters](05-memphis-setup/memphis-dmr-repeaters.md) to see what else is in the air.
3. When you're ready to stop manually tuning and start using a real codeplug, Phase 2 covers CPS software and Phase 3 builds the Memphis codeplug.

## If something didn't work

- **Nothing on NOAA?** Try 162.400, 162.425, 162.450, 162.500, 162.525, 162.550 — you might be on a different Memphis NWR station than expected. Indoor reception is often weak; step outside.
- **Nothing on 146.820?** The net only runs nightly at 8 PM. Outside that window the repeater might be quiet. Try 146.940, 147.060, 145.230 (other Memphis repeaters from `[local-ham-repeaters](05-memphis-setup/local-ham-repeaters.md)`).
- **Radio won't turn on?** Battery seated? Charged? Do the top-knob hold for a full second.
- **Weird display / unknown menu state?** Factory reset (see menu map — Phase 2) gets you a known state.
