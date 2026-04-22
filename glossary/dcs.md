# DCS (Digital-Coded Squelch)

The digital cousin of [ctcss](ctcss.md). Instead of a continuous sub-audible tone, DCS sends a repeating low-speed digital code (a 3-digit octal number like `023` or `754`) under your voice on analog FM. The receiver stays silent unless it detects the matching code.

Functionally identical to CTCSS in use — repeater access, group squelch — but uses ~100+ different codes instead of ~50 tones, so more groups can coexist on the same channel without collision.

Conventions:

- Written as `DCS 023N` (normal) or `DCS 023I` (inverted). Most gear uses "normal."
- Some repeaters use CTCSS, some use DCS, a few use both. Match whatever the repeater owner publishes.

Your radio's CPS offers CTCSS or DCS per channel as alternative tone-squelch modes. Pick whichever the specific repeater / group requires.

See: [ctcss](ctcss.md), [repeater](repeater.md)
