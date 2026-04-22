# Duplex

Radio operation where transmit and receive use **different frequencies**. Used for [repeater](repeater.md) contacts: you transmit up to the repeater on one frequency (the input), the repeater rebroadcasts on another (the output), and you listen on the output.

On the DM-32UV, a duplex channel has:

- **RX freq** = repeater output
- **TX freq** = repeater input (RX freq + or − an offset)
- **Offset** = the standard difference for the band: typically −600 kHz on 2 m, +5 MHz on 70 cm, +5 MHz on GMRS

Technically this is **half-duplex** (not talking and listening simultaneously). True **full-duplex** — simultaneous two-way on separate frequencies — exists but isn't what ham/GMRS HTs do.

See: [simplex](simplex.md), [repeater](repeater.md), [channel](channel.md)
