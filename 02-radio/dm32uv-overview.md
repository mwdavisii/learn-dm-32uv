# DM-32UV overview

Key specs and what's in the box for the Baofeng DM-32UV dual-band DMR handheld.

> **Verify against your unit** — specs below are from Baofeng Tech / BTech product pages and the DM-32UV manual; your specific unit may differ by firmware / hardware revision. Items marked ⚠️ are worth double-checking on your physical radio.

## Product identity

| Item | Value |
|------|-------|
| Manufacturer | **Baofeng** (marketed in the US through BTech / Baofeng Tech) |
| Model | **DM-32UV** |
| Form factor | Handheld transceiver (HT) |
| Target user | Amateur radio, DMR Tier II, GMRS-capable (not Part 95E certified — see [Part 90 vs Part 95](../01-foundations/part90-vs-part95.md)) |

## RF specifications

| Item | VHF | UHF |
|------|-----|-----|
| Frequency range (RX) | 136–174 MHz | 400–480 MHz |
| Frequency range (TX) | 136–174 MHz | 400–480 MHz |
| Output power (High) | 5 W | 4 W |
| Output power (Low) | ~1 W | ~1 W |
| Channel spacing | 12.5 / 20 / 25 kHz | same |
| Modulation | 16K0F3E (analog FM) / 7K60FXD (DMR) | same |

## DMR-specific

- **Tier:** DMR Tier I (simplex, license-free in EU) + Tier II (licensed, repeater-capable) — **Tier II is what US hams use**
- **Modes:** Analog FM + Digital (DMR) per channel
- **TDMA slots:** TS1 / TS2 selectable per channel
- **Color codes:** 0–15 per channel
- **Contacts (DMR IDs):** up to 10,000
- **Talkgroups:** up to 250 (approximate — verify in CPS)

## Capacity

| Item | Value |
|------|-------|
| Channels | ~4000 |
| Zones | ~250 |
| Channels per zone | up to 64 |
| Scan lists | ~250 |
| RX groups | configurable |

## Physical

| Item | Value |
|------|-------|
| Display | Color LCD (typically 1.77") |
| Battery | Baofeng BL-32 Li-Ion, ~2100–2200 mAh ⚠️ *(check your unit's battery label)* |
| Typical runtime | ~12–16 h mixed use |
| Weight | ~250–280 g with battery |
| Dimensions | ~130 × 60 × 35 mm |
| Antenna connector | **SMA-F on radio** (female, radio side) → SMA-M on antenna ⚠️ *(verify — some Baofengs are reversed)* |
| IP rating | IP54 (splash resistant; not submersible) |
| Programming interface | Proprietary 2-pin serial via K-plug (earphone port) → USB cable |

## What's in the box

Typical contents (verify against your unit):

- Radio body
- Antenna (SMA connector)
- Battery (BL-32 or similar)
- Drop-in charger base
- AC power adapter for charger
- Wrist strap
- Belt clip (usually pre-attached)
- Printed manual (small)
- Programming cable *(sometimes sold separately — verify you have one; you've already confirmed the cable purchase)*

## Notable features

- Dual-band simultaneous standby (RX-watch on both bands when idle; one active)
- Front-facing flashlight
- VOX (voice-activated TX)
- Emergency alarm (configurable)
- Stopwatch, tone generators, FM broadcast RX (if enabled in firmware)
- Scanning with priority channels
- Roaming (DMR) — move between repeaters carrying the same talkgroup

## Frequency ranges used in this codeplug

Cross-reference with [RF basics](../01-foundations/rf-basics.md):

| Service | Band | Freq range |
|---------|------|-----------|
| Ham 2 m | VHF | 144–148 MHz |
| Ham 70 cm | UHF | 420–450 MHz |
| GMRS | UHF | 462.550–462.725, 467.550–467.725 MHz |
| NOAA Weather | VHF | 162.400–162.550 MHz |
| MURS (RX) | VHF | 151–154 MHz |
| FRS (RX) | UHF | shared with GMRS 1–14 |

All within the DM-32UV's VHF 136–174 + UHF 400–480 coverage.

## Related

- [buttons-and-knobs](buttons-and-knobs.md) — physical controls
- [menu-map](menu-map.md) — menu tree
- [display-and-indicators](display-and-indicators.md) — what the screen shows
- [charging-battery-care](charging-battery-care.md) — don't kill your battery
- [CPS software](../03-cps-software/install-cps-windows.md) — programming on Windows
