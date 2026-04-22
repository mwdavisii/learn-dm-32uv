# Sources and verification — Memphis data

How I source the data in this folder, how current each source is, and how I track which entries are actually audible from my location vs. sourced-but-unchecked.

## Primary sources

| Data type | Source | URL | Notes |
|-----------|--------|-----|-------|
| Ham 2 m / 70 cm analog repeaters | **RepeaterBook** | https://www.repeaterbook.com | Community-maintained, search by ZIP + radius |
| DMR repeaters | **BrandMeister** | https://brandmeister.network | Canonical for BrandMeister-connected machines |
| DMR repeaters (cross-check) | RepeaterBook, DMR filter | https://www.repeaterbook.com | Sometimes lists TGIF + other network machines BM doesn't |
| DMR talkgroups | **BrandMeister TG master list** | https://brandmeister.network | Click a repeater to see its static TGs |
| DMR ID lookups | **RadioID.net** | https://radioid.net | For operator + repeater IDs |
| GMRS repeaters (private + public) | **myGMRS.com** | https://mygmrs.com | Most comprehensive GMRS repeater list |
| NOAA Weather Radio | **NWS / weather.gov** | https://www.weather.gov/nwr/station_listing?state=TN | Authoritative NWR station data |
| NWS Memphis office | weather.gov/meg | https://www.weather.gov/meg | Local NWS office page |
| Simplex + band plan | **ARRL Band Plan** | https://www.arrl.org/band-plan | Voluntary national conventions |
| FCC rules + license lookup | FCC ULS | https://wireless2.fcc.gov/UlsApp/UlsSearch/searchLicense.jsp | Check your license, or look up a callsign |

## Pull dates table

| Source | Last pulled | By |
|--------|-------------|-----|
| RepeaterBook (ham, 38120 + 40 mi) | 2026-04-18 | initial Phase 1 draft |
| BrandMeister (Memphis area DMR) | 2026-04-18 | initial Phase 1 draft |
| myGMRS.com (Memphis) | 2026-04-18 | initial Phase 1 draft |
| weather.gov NWR (TN) | 2026-04-18 | initial Phase 1 draft |
| ARRL band plan | 2026-04-18 | initial Phase 1 draft |

Refresh cadence: **quarterly** (see `refresh-sources.md` — Phase 5).

## Verification tiers

Every row in every Memphis CSV / table carries one of these tags in a comment column:

- **`#verified`** — I have personally tuned to it and confirmed it exists: a carrier breaks squelch, DMR syncs, NOAA plays the weather loop, GMRS opens correctly. Not just "on paper."
- **`#unverified`** — sourced from one of the URLs above, looks plausible, but I haven't actually confirmed I can hear it from my location. **Default state for all new entries.**
- **`#aspirational`** — a distant or marginal repeater that might require elevation or favorable conditions. Worth keeping for road trips or high-gain experimentation; don't expect to hit it from indoors.

> **Tag semantics:** These are **CSV-local / human-readable tags**, not Obsidian-indexed tags. Obsidian's tag index only scans markdown notes, not CSV file contents. The small set of Obsidian tags used in markdown notes (`#verify`, `#memphis`, `#legal`) is separate.

## Verification pass (Phase 4)

After the first codeplug is flashed, plan is to spend ~1 week monitoring each zone:

1. For each ham zone channel: keep the radio on the channel for a full day at a time, listen for traffic or nets
2. For each DMR repeater channel: check that the sync indicator lights up (and that a talkgroup subscription plays traffic if any is active)
3. For GMRS channels: family radio bench test (simplex between two radios)
4. For NOAA: should simply tune and hear the continuous loop — if yes, `#verified` immediately

Promote to `#verified` any channel that passes. Demote to `#aspirational` or remove any that doesn't.

## Updating this document

- When pulling fresh data, bump the matching row in the "Pull dates" table.
- If a source URL changes or a service shuts down, record it here and adjust.
- Note any non-obvious source judgments (e.g., "this repeater appears on RepeaterBook but not BrandMeister; I'm listing it anyway because...") so future-me knows why.

## Related

- [local-ham-repeaters](local-ham-repeaters.md)
- [memphis-dmr-repeaters](memphis-dmr-repeaters.md)
- [gmrs-channels-memphis](gmrs-channels-memphis.md)
- [noaa-weather-memphis](noaa-weather-memphis.md)
- [simplex-calling](simplex-calling.md)
