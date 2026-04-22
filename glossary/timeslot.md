# Timeslot

In DMR Tier II, a single radio frequency is shared by **two simultaneous conversations** using TDMA — Time Division Multiple Access. Radios take turns transmitting in 30-millisecond bursts so fast the human ear hears continuous audio. The two interleaved bursts form **TS1** and **TS2** — the two timeslots.

Why you care: every DMR channel in the [codeplug](codeplug.md) specifies which slot to use. Get it wrong and the repeater silently ignores your transmission.

Conventions on BrandMeister:

- **TS1** often carries wide-area talkgroups (Worldwide, North America, USA Nationwide)
- **TS2** often carries local and state talkgroups (state-wide, regional, local-only)

The repeater operator chooses the assignments — check the repeater's listing before programming a channel.

Simplex DMR (no repeater) conventionally uses TS1 only. Hotspots usually run TS1 for traffic, TS2 for control/status.

See: [talkgroup](talkgroup.md), [color-code](color-code.md), [DMR concepts](../01-foundations/dmr-concepts.md)
