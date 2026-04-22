# DMR concepts

**Digital Mobile Radio** is a digital voice standard that replaces analog FM on many modern land-mobile and ham radios. Your DM-32UV speaks DMR. This note gets you from "I have no idea what a talkgroup is" to "I know enough to configure the DMR zone in my codeplug."

## Analog FM vs DMR — what's different

| Thing | Analog FM | DMR |
|-------|-----------|-----|
| Audio | Continuously varying radio wave | Digitized, compressed, transmitted as data |
| Behavior at the edge of range | Gets noisier, then scratchier, then fades | Sounds crystal clear, then suddenly cuts to silence (the "DMR cliff") |
| Users per radio channel | 1 at a time | **2 at a time** (two timeslots) |
| Audio quality | Degrades gradually | Either perfect or gone |
| Identification | By voice ID | Radio transmits your DMR ID automatically |
| Privacy/selectivity | CTCSS/DCS tones (weak) | Color code + talkgroup (strong) |

DMR isn't "better" or "worse" — different. On a strong signal, DMR is cleaner. At the fringe, analog is usable where DMR is silence. Most modern repeaters run one or the other, not both.

## Tier I, II, III

- **Tier I:** license-free, unused in the US.
- **Tier II:** licensed, conventional (single repeater or simplex). **This is what you have.**
- **Tier III:** trunked, multi-repeater. Commercial/public-safety stuff.

Whenever ham-world people say "DMR," they mean Tier II.

## Timeslots

A DMR signal uses **TDMA** — Time Division Multiple Access. Each radio transmits in brief bursts, and the repeater interleaves two simultaneous conversations on a single radio frequency. The two slots are called **TS1** and **TS2**. See [timeslot](../glossary/timeslot.md).

Why you care: each DMR channel in your codeplug specifies which timeslot to use. Get it wrong and the repeater will ignore you.

## Talkgroups

A **talkgroup (TG)** is a numeric label for a conversation channel that rides on top of the DMR radio channel. Think of it like a Discord channel for voice. Multiple talkgroups share the same radio frequency + timeslot, and your radio filters so you only hear the one(s) you've subscribed to. See [talkgroup](../glossary/talkgroup.md).

Examples:

| TG | Common name | Scope |
|----|-------------|-------|
| 91 | Worldwide (BrandMeister) | Global — loud and busy |
| 93 | North America (BrandMeister) | Continent-wide |
| 3100 | USA Nationwide | US-only |
| 3147 | Tennessee Statewide | State-level |
| 31470 | Memphis Metro | Regional — Memphis area |
| 9990 | Parrot | Bounce-back test — your voice plays back to you for self-test |

Your Memphis DMR codeplug will list a handful of these per local repeater; see [Memphis DMR repeaters](../05-memphis-setup/memphis-dmr-repeaters.md) once populated.

## Color code

A **color code** (CC) is DMR's access-control number: an integer 0–15 that both the repeater and your radio must agree on. Functionally identical in purpose to a CTCSS tone on analog FM — keep out co-channel users — but implemented as a digital field rather than a subaudible tone. See [color-code](../glossary/color-code.md).

Get the color code wrong on a channel, and the repeater silently rejects your traffic.

## DMR networks

The DMR repeater world is glued together by **networks** that route talkgroup traffic between repeaters:

- **BrandMeister** — the largest ham DMR network. Open, community-run, most common in the US. [brandmeister.network](https://brandmeister.network)
- **TGIF Network** — smaller, some niche talkgroups, laid-back moderation
- **DMR+ / IPSC** — older / regional networks

Most Memphis-area DMR repeaters run BrandMeister. Your codeplug will list each repeater's network so you know what TGs are reachable.

## DMR ID

To transmit on DMR, you need a **unique numeric DMR ID** (7 digits in the US, e.g., `3147123`). You get one for free at [radioid.net](https://radioid.net) — **after** you have a ham callsign. The ID is programmed into the radio once, globally.

**You don't have one yet** because you don't have a ham callsign yet. RX-only on DMR until you pass Tech. No DMR ID, no TX.

## Hotspots (for later)

A **DMR hotspot** (Pi-Star, openSPOT, SharkRF) is a tiny personal transceiver + internet bridge that lets you work BrandMeister without a local repeater. Great for home use once you have a license and a DMR ID. Out of scope for this vault's current phase.

## Next

- [rx-only-before-license](rx-only-before-license.md) — rules for listening to DMR pre-Tech
- [talkgroup](../glossary/talkgroup.md), [timeslot](../glossary/timeslot.md), [color-code](../glossary/color-code.md) — term deep-dives
- [Contacts & talkgroups in the codeplug](../04-codeplug-model/contacts-and-talkgroups.md) *(Phase 3)*
