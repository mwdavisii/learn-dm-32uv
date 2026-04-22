---
tags: [memphis, verify]
---

# Local ham repeaters — Memphis area (2 m / 70 cm analog FM)

RX-only for you until Tech license. Listed here so you know what's in the air; will be programmed into the codeplug in Phase 3. Monitor a few to get a feel for local ops and net schedules. Focus is Shelby County TN plus nearby DeSoto County MS and Crittenden County AR — Memphis is a tri-state metro, so useful traffic crosses state lines on a daily basis.

> **Data caveat:** Source pull from RepeaterBook returned limited data (automated fetch blocked with HTTP 403 on `Display_State.php` and `prox_result.php`, 2026-04-18). List below is compiled from general knowledge of the Memphis area plus what could be confirmed from the Delta Amateur Radio Club site. **Verify each entry against RepeaterBook directly before relying on it.** Only two rows (W4BS 146.820 and W4BS 443.200) are corroborated by a second source today; the rest are plausible but entirely `#unverified`.

## Sources

| Source | URL | Pulled |
|--------|-----|--------|
| RepeaterBook — TN state view | https://www.repeaterbook.com/repeaters/Display_State.php?state=Tennessee | 2026-04-18 (blocked, 403) |
| RepeaterBook — alt state view | https://www.repeaterbook.com/row_static/feature/USState.php?stid=TN | 2026-04-18 (blocked, 403) |
| RepeaterBook — proximity search (Memphis, 40 mi) | https://www.repeaterbook.com/repeaters/prox_result.php?city=Memphis&state_id=47 | 2026-04-18 (blocked, 403) |
| Delta Amateur Radio Club | https://www.deltaclub.org/ | 2026-04-18 (OK — confirmed 146.820 and 443.200) |

Re-pull via browser (not automated fetch) and update this table when values are corroborated. Bump rows from `#unverified` to `#verified` per the rules in [sources-and-verification](sources-and-verification.md).

## 2 m band (144–148 MHz)

| Callsign | Freq (MHz RX) | Offset | Tone (CTCSS Hz) | Band | Location | Notes | Status |
|----------|---------------|--------|-----------------|------|----------|-------|--------|
| W4BS     | 146.820 | −0.600 | 107.2 | 2 m | Memphis, TN (Shelby) | **Delta ARC primary.** Nightly info net 8:00 PM local | #unverified |
| W4MAS    | 146.880 | −0.600 | 107.2 | 2 m | Memphis, TN (Shelby) | Mid-South ARA; wide-area machine | #unverified |
| K4AM     | 147.360 | +0.600 | 107.2 | 2 m | Memphis, TN (Shelby) | Commonly programmed in local codeplugs | #unverified |
| W4GMC    | 147.135 | +0.600 | 107.2 | 2 m | Memphis, TN (Shelby) | General coverage | #unverified |
| WB4GNA   | 145.330 | −0.600 | 107.2 | 2 m | Memphis, TN (Shelby) | Verify — tone may vary | #unverified |
| K5DSO    | 146.745 | −0.600 | 107.2 | 2 m | Olive Branch / Southaven, MS (DeSoto) | DeSoto County coverage | #unverified |
| W5JWC    | 147.240 | +0.600 | 107.2 | 2 m | West Memphis, AR (Crittenden) | Crittenden County side of river | #unverified |
| KD4GT    | 146.700 | −0.600 | 107.2 | 2 m | Millington, TN (north Shelby) | Verify location | #unverified |

## 70 cm band (420–450 MHz)

| Callsign | Freq (MHz RX) | Offset | Tone (CTCSS Hz) | Band | Location | Notes | Status |
|----------|---------------|--------|-----------------|------|----------|-------|--------|
| W4BS     | 443.200 | +5.000 | 107.2 | 70 cm | Memphis, TN (Shelby) | **Delta ARC secondary.** Backup for nightly net | #unverified |
| W4MAS    | 444.525 | +5.000 | 107.2 | 70 cm | Memphis, TN (Shelby) | Mid-South ARA 70 cm machine | #unverified |
| K4AM     | 442.100 | +5.000 | 107.2 | 70 cm | Memphis, TN (Shelby) | Verify tone | #unverified |
| W4GMC    | 444.075 | +5.000 | 107.2 | 70 cm | Memphis, TN (Shelby) | General coverage | #unverified |
| K5DSO    | 443.600 | +5.000 | 107.2 | 70 cm | Southaven, MS (DeSoto) | MS side UHF | #unverified |
| W5JWC    | 442.700 | +5.000 | 107.2 | 70 cm | West Memphis, AR (Crittenden) | AR side UHF | #unverified |

Combined count: 14 rows (8 on 2 m, 6 on 70 cm). If RepeaterBook shows more on a manual pull, append here.

## Delta Amateur Radio Club repeaters

DARC is the dominant club in the Memphis metro and its machines are where most local traffic lives. From the DARC website (deltaclub.org, pulled 2026-04-18) they "provide five VHF/UHF repeaters"; two are explicitly documented:

- **W4BS 146.820 (−0.600, PL 107.2)** — primary, 2 m
- **W4BS 443.200 (+5.000, PL 107.2)** — secondary, 70 cm

**Nightly Information Net — 8:00 PM local** on 146.820 (fallback to 443.200 if the 2 m machine is down). This is the highest-value thing to monitor while RX-only: you'll hear callsign practice, local traffic style, and announcements of upcoming club events / hamfests / VE sessions (useful for scheduling your own Tech exam).

Other common Memphis-area club callsigns to watch for on RepeaterBook (affiliation unverified here):

- **W4MAS** — Mid-South Amateur Radio Association
- **K4AM** — often cited in local codeplugs
- **W4GMC** — general Memphis-area coverage

When a verified pull lands, annotate the table above with the correct "Operated by:" tag so the DARC vs. non-DARC distinction stays visible.

## Related

- [sources-and-verification](sources-and-verification.md)
- [RX-only discipline pre-Tech](../01-foundations/rx-only-before-license.md)
