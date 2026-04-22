# GMRS channels — Memphis

I hold a valid FCC GMRS license and intend to transmit on this band using a Part 90-accepted radio (Baofeng DM-32UV) rather than a Part 95-certified GMRS set. That tradeoff, along with the technical and legal reasoning, is captured in [Part 90 vs Part 95](../01-foundations/part90-vs-part95.md). All 30 GMRS channels below are usable for **listening** without qualification; **transmit** is subject to the GMRS power limits shown per-channel and to the FCC rules (no encryption, station ID every 15 min, etc.).

## GMRS channel map (FCC Part 95 Subpart E)

Canonical and identical across the US. Channel numbers 1–22 match FRS; the eight "repeater" channels (15R–22R) share the same RX frequency as their simplex counterparts but use the 467 MHz input pair for uplink.

| Ch | Name | TX MHz | RX MHz | Max Pwr | Typical use |
|----|------|--------|--------|---------|-------------|
| 1 | FRS/GMRS 1 | 462.5625 | 462.5625 | 5 W | shared with FRS |
| 2 | FRS/GMRS 2 | 462.5875 | 462.5875 | 5 W | shared with FRS |
| 3 | FRS/GMRS 3 | 462.6125 | 462.6125 | 5 W | shared with FRS |
| 4 | FRS/GMRS 4 | 462.6375 | 462.6375 | 5 W | shared with FRS |
| 5 | FRS/GMRS 5 | 462.6625 | 462.6625 | 5 W | shared with FRS |
| 6 | FRS/GMRS 6 | 462.6875 | 462.6875 | 5 W | shared with FRS |
| 7 | FRS/GMRS 7 | 462.7125 | 462.7125 | 5 W | shared with FRS |
| 8 | FRS 8 | 467.5625 | 467.5625 | 0.5 W | interstitial, low-power only |
| 9 | FRS 9 | 467.5875 | 467.5875 | 0.5 W | interstitial |
| 10 | FRS 10 | 467.6125 | 467.6125 | 0.5 W | interstitial |
| 11 | FRS 11 | 467.6375 | 467.6375 | 0.5 W | interstitial |
| 12 | FRS 12 | 467.6625 | 467.6625 | 0.5 W | interstitial |
| 13 | FRS 13 | 467.6875 | 467.6875 | 0.5 W | interstitial |
| 14 | FRS 14 | 467.7125 | 467.7125 | 0.5 W | interstitial |
| 15 | GMRS 550 | 462.5500 | 462.5500 | 5 W HT / 50 W fixed | main GMRS simplex |
| 16 | GMRS 575 | 462.5750 | 462.5750 | 5 W HT / 50 W fixed | main GMRS simplex |
| 17 | GMRS 600 | 462.6000 | 462.6000 | 5 W HT / 50 W fixed | main GMRS simplex |
| 18 | GMRS 625 | 462.6250 | 462.6250 | 5 W HT / 50 W fixed | main GMRS simplex |
| 19 | GMRS 650 | 462.6500 | 462.6500 | 5 W HT / 50 W fixed | main GMRS simplex |
| 20 | GMRS 675 | 462.6750 | 462.6750 | 5 W HT / 50 W fixed | "travel" channel, often used for road trips |
| 21 | GMRS 700 | 462.7000 | 462.7000 | 5 W HT / 50 W fixed | main GMRS simplex |
| 22 | GMRS 725 | 462.7250 | 462.7250 | 5 W HT / 50 W fixed | main GMRS simplex |
| 15R | GMRS 550 Repeater | 467.5500 | 462.5500 | 5 W HT / 50 W fixed | repeater input on 467 |
| 16R | GMRS 575 Repeater | 467.5750 | 462.5750 | 5 W HT / 50 W fixed | repeater input |
| 17R | GMRS 600 Repeater | 467.6000 | 462.6000 | 5 W HT / 50 W fixed | repeater input |
| 18R | GMRS 625 Repeater | 467.6250 | 462.6250 | 5 W HT / 50 W fixed | repeater input |
| 19R | GMRS 650 Repeater | 467.6500 | 462.6500 | 5 W HT / 50 W fixed | repeater input |
| 20R | GMRS 675 Repeater | 467.6750 | 462.6750 | 5 W HT / 50 W fixed | repeater input |
| 21R | GMRS 700 Repeater | 467.7000 | 462.7000 | 5 W HT / 50 W fixed | repeater input |
| 22R | GMRS 725 Repeater | 467.7250 | 462.7250 | 5 W HT / 50 W fixed | repeater input |

Notes:
- "HT / fixed" power split: the 50 W ceiling applies to base/mobile on channels 15–22 and their repeater inputs 15R–22R. Handhelds are capped at 5 W on those channels.
- FRS interstitial channels 8–14 are hard-capped at 0.5 W for any radio; GMRS licensees must still observe that limit on those frequencies.
- Channel 20 (462.675) is the de facto "travel" channel and is commonly tone-squelched with 141.3 Hz by convention.

## Memphis-area GMRS repeaters

**Source:** myGMRS.com (<https://mygmrs.com/repeaters>) is the primary directory; RepeaterBook (<https://www.repeaterbook.com/gmrs/>) used for cross-reference. **Pulled 2026-04-18.**

Automated access to myGMRS.com was blocked (HTTP 403 — the public directory pages require either a logged-in session or bypass protection that tools/scrapers don't clear). Only what appears in public search-engine indexes could be captured for this pass. All rows below are `#unverified`.

| Callsign / Name | Output Freq | Input Freq | Tone | Location | Notes | Status |
|-----------------|-------------|------------|------|----------|-------|--------|
| WROX887 | 462.6750 | 467.6750 | unknown (likely 141.3 travel-tone; verify) | East Memphis Hilton Hotel area, Memphis TN | Indexed on RepeaterBook (Tennessee, ID 419). Open/closed status not captured. `#unverified` | listed |

Memphis-area suburbs worth re-checking with a logged-in myGMRS session: Germantown, Collierville, Bartlett, Cordova, Arlington, Lakeland, Millington, plus Mid-South cross-state neighbors Southaven / Olive Branch / Horn Lake MS and West Memphis AR. None returned publicly-indexed entries on this pass.

> **Action item:** Log into myGMRS.com with the user's callsign, re-run the TN / state=TN location=Memphis search, and update this table. Also pull Repeaterbook Tennessee listings filtered to the Memphis metro once the site is reachable (RepeaterBook returned 403 to WebFetch on 2026-04-18; try a browser pull). Private / membership-required repeaters will only surface after login.

If on re-check no additional repeaters appear: **"No additional publicly-listed Memphis-area GMRS repeaters on myGMRS.com as of [date]. Private repeaters may exist; check local Facebook GMRS groups (e.g., 'Mid-South GMRS', 'Memphis GMRS') for details."**

## Related

- [sources-and-verification](sources-and-verification.md)
- [GMRS basics](../01-foundations/gmrs-basics.md)
- [Part 90 vs Part 95](../01-foundations/part90-vs-part95.md)
