---
tags: [dmr, repeaters, memphis, unverified]
---

# Memphis DMR Repeaters + Talkgroups

DMR repeaters in the Memphis area. RX-only for you until you have a ham callsign AND a DMR ID from radioid.net. This list tells you what's in the air and what talkgroups you might hear. Get the color code right in the codeplug or the repeater ignores your transmissions (relevant once you can TX).

> **Note on source pull (2026-04-18):** Direct fetches against BrandMeister's dashboard/API and RepeaterBook were blocked (403/404) during this research pass. Details below are assembled from secondary sources (RadioReference forums, hearham.com, Delta Amateur Radio Club site, BrandMeister Wiki) and general DMR community knowledge. **All rows `#unverified` — confirm against BrandMeister before committing to a codeplug.**

## Sources + Pull Date

- **Pull date:** 2026-04-18
- **Primary sources attempted:**
  - BrandMeister repeater dashboard — https://brandmeister.network/#/repeaters *(SPA; direct fetch failed)*
  - BrandMeister API — https://api.brandmeister.network/v2/repeaters *(404 on this path)*
  - RepeaterBook TN DMR — https://www.repeaterbook.com/repeaters/feature_search.php?state_id=47&type=DMR *(403)*
  - RadioID.net — https://radioid.net/database/repeaters
  - TGIF Prime — https://prime.tgif.network
- **Secondary sources used:**
  - Delta Amateur Radio Club repeater list — https://deltaclub.org/repeaters
  - hearham.com repeater profiles
  - RadioReference.com "Memphis ham DMR" forum thread
  - BrandMeister Wiki TalkGroup pages (TG 3147, 31470, 31471, 314431)

## Repeater Table

All entries `#unverified` — confirm against BrandMeister dashboard and RepeaterBook before flashing.

| Callsign | Freq (MHz RX) | Offset | Color Code | Network | Location | Notes | Status |
|----------|---------------|--------|------------|---------|----------|-------|--------|
| W4BS | 443.700 | +5 MHz | CC1 | BrandMeister | Memphis, TN — WATN TV tower (~500 ft) | Delta Amateur Radio Club. Static TGs: TS1 TG 3147 (TN Statewide) + TG 314431 (W TN NWS/Skywarn); TS2 TG 314447 (Delta Club) + TG 31471 (Memphis Metro). Weekly Delta net Wed 1930 local on TG 31471. | `#unverified` |
| W4LET | 443.0125 | +5 MHz | CC1 | BrandMeister | Memphis, TN | Leading Edge ARC, open repeater. DMR ID 314706. TS1: TG 1 WW, TG 13 WW English, TG 3 NA, TG 9999 Parrot. TS2: TG 3174 Southeast, TG 310 TAC310, TG 9 / 314706 Local Memphis. | `#unverified` |
| NJ8X | 444.1750 | +5 MHz | CC4 | BrandMeister | Memphis/Shelby Co — LeBonheur Children's Hospital | DMR ID 314457. Both timeslots linked per source. | `#unverified` |
| KA4BNI | 444.7125 | +5 MHz | CC1 | BrandMeister | NE of Memphis area (Martin, TN — EM56NI — borderline >30 mi from 38120; included as a commonly heard regional machine) | DMR ID 310543. TS1: TG 9 Local, TG 2 KA4BNI Cluster. TS2: TG 3147 TN Statewide, TG 31471 Memphis region. **Distance flag — may be outside 30-mi HT range of 38120.** | `#unverified` |
| W4LET (2nd machine?) | 443.9875 | +5 MHz | CC? | BrandMeister (assumed) | Memphis, TN | Appears in RepeaterBook as a second W4LET DMR entry — relationship to 443.0125 machine unclear. | `#unverified` |

**Known gaps / worth hunting on BrandMeister dashboard before codeplug finalization:**
- Southaven / Horn Lake / Olive Branch, MS — likely at least one DMR machine on the MS side within HT range; not confirmed in this pull.
- West Memphis, AR — possibly one BrandMeister or TGIF machine; not confirmed.
- Germantown / Collierville / Bartlett, TN — check RepeaterBook for any club machines.
- Millington, TN — check for any NAS-area activity.

## Common Talkgroups

Convention on BrandMeister US repeaters: **TS1 = wide-area (world / continent / nation)**, **TS2 = regional / state / local / parrot.** Individual repeater owners can and do deviate — always check the specific machine's TG map.

| TG | Name | Scope | Typical TS |
|----|------|-------|------------|
| 91 | Worldwide | Global | TS1 |
| 93 | North America | Continent | TS1 |
| 3100 | USA Nationwide | US | TS1 |
| 3174 | Southeast Regional | US SE region | TS2 (often) |
| 310 | TAC 310 | US chat / tactical | TS2 (PTT) |
| **3147** | **Tennessee Statewide** | **State** | **TS2** (some TN machines run it static on TS1 — check each repeater) |
| 31470 | Mid-South (TN/AR/MS/MO Bootheel) | Regional | TS2 |
| 31471 | Memphis Metro (TN/AR/MS tri-state) | Local/regional | TS2 |
| 314431 | W TN NWS / Memphis Skywarn | NWS (post 2025-02-01) | TS1 or TS2 per machine |
| 314447 | Delta Amateur Radio Club | Club | TS2 |
| 314706 | Memphis Local (W4LET) | Local | TS2 |
| 9 | Local (repeater only) | Single repeater | TS2 |
| 9990 | Parrot (echo test) | Self-test | TS2 (or TS1 on some — W4LET lists 9999 on TS1) |

### Tennessee Statewide TG — confirmation

**Confirmed: TG 3147 is Tennessee Statewide.** Corroborated by multiple sources in this pull (RadioReference Memphis DMR thread, KA4BNI repeater documentation, W4BS/Delta Club repeater docs, BrandMeister Wiki search results). The 10-minute timer applies. The Tennessee Digital Amateur Radio Group net meets on **TG 3147** at 2000 Central / 2100 Eastern.

**TG 31470** is a *different, regional* talkgroup: Mid-South (TN + AR + MS + MO Bootheel). The original project-plan placeholder of 31470 was for the state — that was wrong. Use **3147** for TN statewide; **31470** is a regional supplement; **31471** is Memphis Metro.

The original prompt asked to state both candidates if unable to resolve — resolved: statewide is **3147**.

## Related

- [sources-and-verification](sources-and-verification.md)
- [DMR concepts](../01-foundations/dmr-concepts.md)
- [Talkgroup](../glossary/talkgroup.md)
- [Timeslot](../glossary/timeslot.md)
- [Color code](../glossary/color-code.md)
