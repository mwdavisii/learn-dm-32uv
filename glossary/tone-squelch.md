# Tone squelch

General term for any mechanism that keeps a receiver's audio muted unless an encoded "matching tone" is detected along with the carrier. Umbrella over [ctcss](ctcss.md) (analog sub-audible tone) and [dcs](dcs.md) (digital code word).

Without tone squelch, the radio unmutes whenever carrier is detected on the frequency — including noise, weak signals, and other users you don't care about. With tone squelch set, the radio stays silent unless the specific tone arrives.

Operator trade-offs:

- **Tone squelch on (encode + decode):** cleaner — you only hear your group. But you miss emergency calls from anyone without the tone.
- **TSQL / encode only:** send the tone (to open a repeater) but listen to everything on the channel. Good for monitoring a repeater that's shared with other users.
- **Carrier squelch / no tone:** open mode, hear everyone on-channel, send nothing. For scanning/monitoring only.

For DMR, [color-code](color-code.md) + [talkgroup](talkgroup.md) play the same role with stronger filtering.

See: [ctcss](ctcss.md), [dcs](dcs.md), [color-code](color-code.md)
