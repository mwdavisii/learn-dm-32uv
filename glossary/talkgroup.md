# Talkgroup

A **numeric label that tags a DMR conversation** so radios can filter for specific audiences on a shared radio channel. Different from a radio channel, timeslot, or frequency — layered on top.

Example: TG 91 = "Worldwide" on BrandMeister. Anyone on any BrandMeister-connected repeater, anywhere on Earth, who keys up on TG 91 gets heard globally — but only by radios configured to listen to TG 91.

A single DMR repeater carries many talkgroups simultaneously; your codeplug subscribes each channel to one or a small group of TGs via RX groups.

Common US ham talkgroups (verify current numbers at [BrandMeister](https://brandmeister.network)):

| TG | Scope |
|----|-------|
| 91 | Worldwide |
| 93 | North America |
| 3100 | USA Nationwide |
| 3147 | Tennessee Statewide |
| 31470 | Memphis Metro |
| 9990 | Parrot (self-test bounce-back) |

TGs are sometimes dynamic (click-to-subscribe) versus static (always-carried by a repeater). The repeater owner decides.

See: [timeslot](timeslot.md), [color-code](color-code.md), [DMR concepts](../01-foundations/dmr-concepts.md)
