# Baofeng DM-32UV — Learning Vault & Memphis Codeplug

A personal learning resource and working codeplug for a brand-new operator in Memphis, TN running a Baofeng **DM-32UV** dual-band DMR handheld.

> **Start here:** [quickstart](quickstart.md) — on the air in 30 minutes, manual tune, no codeplug needed.

## Who this is for

Goals:
- Understand DMR, ham, and GMRS actually — not just parrot terminology.
- Monitor local Memphis repeaters (RX-only on ham until Tech lands).
- Transmit on GMRS simplex with family.
- Program the radio intentionally, not by copying a random stranger's codeplug.

You're welcome to fork the approach; the Memphis data is specific to my location.

## Map of content

### Shortcuts
- **[quickstart](quickstart.md)** — fastest path from unboxed to hearing NOAA + a Memphis ham repeater + a GMRS channel
- **[glossary](glossary.md)** — jump to any term

### `01-foundations/` — concepts first
- [RF basics](01-foundations/rf-basics.md) — frequency, wavelength, VHF vs UHF, what bands the DM-32UV uses
- [Ham radio landscape](01-foundations/ham-radio-landscape.md) — license classes, Tech privileges, ham vs GMRS/FRS/MURS/CB
- [GMRS basics](01-foundations/gmrs-basics.md) — 30 channels, rules, household license, power limits
- [DMR concepts](01-foundations/dmr-concepts.md) — digital voice, timeslots, talkgroups, color codes, networks
- [Part 90 vs Part 95](01-foundations/part90-vs-part95.md) — certification nuance + my accepted tradeoff
- [RX-only before license](01-foundations/rx-only-before-license.md) — what I can legally do pre-Tech

### `glossary/` — quick-reference terms
[glossary](glossary.md) for the indexed list. 15 individual notes covering: codeplug, zone, channel, simplex, duplex, repeater, CTCSS, DCS, talkgroup, timeslot, color code, callsign, band plan, tone squelch, Part 90/95.

### `05-memphis-setup/` — my local RF landscape
- [Sources & verification methodology](05-memphis-setup/sources-and-verification.md) — where data comes from, refresh cadence, `#verified` tier system
- [Local ham repeaters](05-memphis-setup/local-ham-repeaters.md) — 14 repeaters across 2 m and 70 cm within ~40 mi of Memphis *(all `#unverified` pending Phase 4)*
- [Memphis DMR repeaters](05-memphis-setup/memphis-dmr-repeaters.md) — 5 DMR machines + common talkgroups
- [GMRS channels (Memphis)](05-memphis-setup/gmrs-channels-memphis.md) — full 30-channel table + WROX887 local repeater
- [NOAA Weather (Memphis)](05-memphis-setup/noaa-weather-memphis.md) — KWJ76 on 162.475 MHz + all 7 NWR channels
- [Simplex calling frequencies](05-memphis-setup/simplex-calling.md) — 146.520 / 446.000 + ARRL band-plan sub-bands

### `02-radio/` — the DM-32UV itself
- [DM-32UV overview](02-radio/dm32uv-overview.md) — specs, what's in the box
- [Buttons and knobs](02-radio/buttons-and-knobs.md) — every physical control + common gotchas
- [Menu map](02-radio/menu-map.md) — annotated menu tree + safe defaults
- [Display and indicators](02-radio/display-and-indicators.md) — screen layout, LEDs, beeps
- [Charging and battery care](02-radio/charging-battery-care.md) — lithium rules + firmware warning

### `03-cps-software/` — programming on Windows
- [Install CPS on Windows](03-cps-software/install-cps-windows.md) — download sources, install procedure
- [Driver and cable](03-cps-software/driver-and-cable.md) — USB-serial chipset identification + troubleshooting
- [CPS UI tour](03-cps-software/cps-ui-tour.md) — full walkthrough + CSV import discovery checklist
- [Read / write the radio](03-cps-software/read-write-radio.md) — **safe procedure** — read before write, backup always, versioned saves
- [Firmware updates](03-cps-software/firmware-updates.md) — **default: don't** — rules if you must

### Coming in Phase 3 — codeplug build
- `04-codeplug-model/` — channels, zones, contacts, talkgroups, scan lists, naming conventions
- `codeplug/` — first real `.rdt` + human-editable CSVs + flash procedure

## Phase status

| Phase | Scope | Status |
|---|---|---|
| 0 | Vault scaffold + placeholders | ✅ |
| 1 | Foundations (6 notes) + glossary (15 terms) + Memphis data (6 notes) + quickstart | ✅ *(this commit)* |
| 2 | Radio hardware + CPS software walkthroughs | 🚧 drafts complete — awaiting your Windows CPS install + first read |
| 3 | Codeplug model + first flash | ⏳ |
| 4 | Verification pass — promote `#unverified` → `#verified` | ⏳ |
| 5 | Maintenance playbook — quarterly refresh | ⏳ |

## How to use this vault

- **Read linear** for a structured course: `01-foundations/` → `05-memphis-setup/` → Phase 2 when it exists.
- **Read random-access** when you want to look something up: use the glossary, or search Obsidian for the term.
- **Run the quickstart** as soon as the radio arrives — it's self-contained.
- **Edit freely.** Everything here is my own notes; correct errors, add context, make it yours.
