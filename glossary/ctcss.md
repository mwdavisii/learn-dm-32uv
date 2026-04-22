# CTCSS (Continuous Tone-Coded Squelch System)

A sub-audible tone (one of ~50 standardized frequencies between 67.0 Hz and 254.1 Hz) transmitted continuously alongside your voice on **analog FM**. The receiver is configured to stay silent unless it detects the matching tone, so you only hear transmissions "addressed" to you.

Also called **PL** (Motorola's "Private Line" trademark, which leaked into common usage) or simply "tone squelch."

Uses:

- [repeater](repeater.md) access: the repeater rejects signals without the right tone to prevent co-channel interference opening it
- GMRS family groups: everyone programs the same tone so they only hear each other
- Scanner suppression: ignore unwanted users on a shared channel

CTCSS is **not** privacy or encryption — anyone with a scanner can disable tone squelch and hear you fine. It's purely an access/suppression mechanism.

Analog analog. DMR uses [color-code](color-code.md) for the equivalent purpose.

See: [dcs](dcs.md) (the digital-coded cousin), [color-code](color-code.md), [repeater](repeater.md)
