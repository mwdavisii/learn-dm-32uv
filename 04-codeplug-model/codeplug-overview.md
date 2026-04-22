# Codeplug Overview — Memphis DM-32UV v1

Summary of the complete codeplug. This is the "map" — for step-by-step entry instructions, see [programming-walkthrough](programming-walkthrough.md).

## At a glance

| Metric | Value |
|--------|-------|
| Total channels | 71 |
| Zones | 6 |
| DMR talkgroups | 13 |
| DMR RX groups | 4 |
| TX-enabled channels | 31 (GMRS only) |
| TX-prohibited channels | 40 (WX + all ham + all DMR) |
| Scan lists | 5 (recommended) |

## Channel breakdown by zone

| Zone | Channels | Type | TX | Band |
|------|----------|------|-----|------|
| WX | 7 | Analog | Prohibited | VHF (162 MHz) |
| GMRS Sim | 22 | Analog | **Enabled** | UHF (462/467 MHz) |
| GMRS Rpt | 9 | Analog | **Enabled** | UHF (462/467 MHz) |
| MEM 2m | 10 | Analog | Prohibited | VHF (144–148 MHz) |
| MEM 70cm | 7 | Analog | Prohibited | UHF (420–450 MHz) |
| DMR Mem | 16 | Digital | Prohibited | UHF (443–445 MHz) |

## Data sources

All channel data is derived from the markdown files in `05-memphis-setup/`:

| File | Feeds zone(s) |
|------|---------------|
| `noaa-weather-memphis.md` | WX |
| `gmrs-channels-memphis.md` | GMRS Sim, GMRS Rpt |
| `local-ham-repeaters.md` | MEM 2m, MEM 70cm |
| `simplex-calling.md` | MEM 2m (CALL 520, CALL 550), MEM 70cm (CALL 446) |
| `memphis-dmr-repeaters.md` | DMR Mem |

## CSV source files

Located in `codeplug/sources/`. All CSV files are in **CPS-importable format** — they match the exact column layout the DM-32UV CPS expects, so you can use the **Import** button directly.

| File                         | Format                                                       | Contents                                    |
| ---------------------------- | ------------------------------------------------------------ | ------------------------------------------- |
| **`channels-import.csv`**    | CPS channel import (39 columns)                              | **All 71 channels** — the main import file  |
| **`dmr-talkgroups.csv`**     | CPS Talk Groups import (4 columns)                           | 14 DMR talkgroup contacts                   |
| **`dmr-rx-groups.csv`**      | CPS RX Group List import (3 columns, pipe-delimited members) | 4 DMR RX group definitions                  |
| `zones.csv`                  | Human-readable reference                                     | 6 zone definitions with channel assignments |

## Verification status

**All ham and DMR data is `#unverified`** as of the initial build. See [Sources & verification](../05-memphis-setup/sources-and-verification.md) for the tier system and promotion criteria.

Channels that are easy to verify immediately after programming:

- **WX3-162475** — if you hear the weather forecast loop, it's verified
- **W4BS 2m (146.820)** — tune in at the 8 PM nightly net
- **GMRS-01 through GMRS-22** — these are canonical FCC frequencies and don't need verification

## Codeplug versioning

| Version | Description | Date |
|---------|-------------|------|
| v0 | Factory backup (first read from radio) | |
| v1 | First Memphis codeplug — 71 channels, 6 zones, all ham TX prohibited | |
| v2 | *(future)* Tech license — enable ham TX | |
| v3 | *(future)* DMR ID registered — enable DMR TX | |

## Known limitations and future improvements

- **WROX887 tone unverified** — assumed 141.3 Hz; confirm via myGMRS.com or on-air test
- **W4LET parrot TG** — some sources say 9999 instead of 9990; try both if echo test doesn't work
- **NJ8X color code** — listed as CC4, which is unusual; double-check against BrandMeister dashboard
- **KA4BNI distance** — Martin, TN may be outside HT range from Memphis 38120; keep in codeplug but flag if no decode
- **W4LET second machine (443.9875)** — relationship to primary 443.0125 unclear; omitted from v1 pending investigation
- **No MS/AR DMR repeaters** — DeSoto County and West Memphis may have machines; investigate for v2
- **Simplex channels limited** — only 146.520, 146.550, and 446.000 included; add more from the full simplex tables in `simplex-calling.md` if desired

## Related

- [codeplug-zones-and-naming](codeplug-zones-and-naming.md) — zone design and naming conventions
- [programming-walkthrough](programming-walkthrough.md) — step-by-step CPS entry guide
- [Read/write procedure](../03-cps-software/read-write-radio.md)
- [Sources & verification](../05-memphis-setup/sources-and-verification.md)
