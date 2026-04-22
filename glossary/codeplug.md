# Codeplug

The complete configuration of a programmable radio: every channel, zone, contact, talkgroup, scan list, button assignment, and radio-wide setting, all bundled into one file that can be written to the radio or loaded from disk.

"Programming" a DMR radio almost always means **editing a codeplug in software, then writing it to the radio over USB** — not entering each channel via the front panel. Codeplugs are typically binary files in a manufacturer-specific format (DM-32UV uses `.rdt`).

A good codeplug is ruthlessly organized: [zone](zone.md)s scroll cleanly, [channel](channel.md) names are short and consistent, TX is disabled where it must be, and the operator can find anything within two knob-turns.

See: [channel](channel.md), [zone](zone.md), [Codeplug overview (full note)](../04-codeplug-model/codeplug-overview.md)
