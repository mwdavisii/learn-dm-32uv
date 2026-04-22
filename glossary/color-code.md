# Color code

An integer 0–15 that functions as DMR's equivalent of a [ctcss](ctcss.md) tone — an access-control number that must match between radio and [repeater](repeater.md) for traffic to pass. "Color" is metaphorical; it's just a number.

Each DMR channel in your codeplug has a color-code field. If the repeater is configured for CC 1 and you try to key up on CC 2, the repeater drops your traffic without complaint. No error tone, no indication — your PTT just does nothing useful.

Most ham DMR repeaters default to **CC 1** (by convention, not rule). Commercial systems use other values to avoid accidental co-channel interference.

The repeater's published info tells you the CC. Get it right; it's not a thing to guess.

See: [ctcss](ctcss.md) (analog equivalent), [timeslot](timeslot.md), [talkgroup](talkgroup.md)
