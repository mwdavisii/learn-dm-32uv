# RF basics

Before anything else, a working mental model of **radio frequency** (RF). Skip only if you already know why a 2 m radio has a bigger antenna than a 70 cm one.

## What is RF?

Electrical energy oscillating fast enough to radiate through space as an electromagnetic wave. "Fast enough" in practice means roughly **3 kHz and up**. The number of oscillations per second is the **frequency**, measured in **hertz (Hz)**. Your DM-32UV operates in the **megahertz (MHz)** range — millions of oscillations per second.

## Frequency and wavelength

They're inversely related. In free space:

```
wavelength (meters) ≈ 300 ÷ frequency (MHz)
```

- 146 MHz → ~2 meters → why we call it the **"2 m" ham band**
- 446 MHz → ~0.7 meters → **"70 cm" ham band**
- 462 MHz (GMRS) → also roughly 65 cm

Antenna length scales with wavelength. That's why a 2 m whip is about 18" and a 70 cm stubby is a few inches — they're tuned to a fraction (usually 1/4) of the wavelength.

## VHF vs UHF

| Band group | Frequency range | Common use | Practical behavior |
|------------|-----------------|------------|---------------------|
| **VHF** (Very High Freq) | 30–300 MHz | Ham 2 m, NOAA weather, MURS, marine | Travels further outdoors, worse at punching through buildings |
| **UHF** (Ultra High Freq) | 300 MHz–3 GHz | Ham 70 cm, GMRS, FRS, DMR, phones | Shorter range in open terrain, better indoors and in urban clutter |

Rule of thumb for an HT (handheld): **VHF for open/rural, UHF for urban/indoor**. Your DM-32UV is dual-band so you don't have to pick.

## Propagation, quickly

- **Line-of-sight** matters more as frequency goes up. VHF and UHF mostly don't bounce off the ionosphere like HF does — what you can see, you can roughly hear.
- **Repeaters** exist to extend that line-of-sight by sitting on tall towers and rebroadcasting. More on that in [ham-radio-landscape](ham-radio-landscape.md).
- Buildings, trees, hills, and even weather (to a small extent) attenuate your signal. Moving 20 feet can turn a dead channel into a clean one.

## Bands the DM-32UV actually uses

| Band | Approx. frequency | Service |
|------|-------------------|---------|
| 2 m | 144–148 MHz | Amateur (ham) — RX-only for you pre-Tech |
| 1.25 m | 220 MHz | Not supported on this radio |
| 70 cm | 420–450 MHz | Amateur (ham) — RX-only for you pre-Tech |
| GMRS | 462/467 MHz | General Mobile Radio Service — you have a license |
| NOAA NWR | 162.4–162.55 MHz | Receive-only weather |

Anything outside those ranges is either unsupported, illegal to transmit on without other licensing, or not useful to you. See [part90-vs-part95](part90-vs-part95.md) for the certification nuance.

## Next

- [ham-radio-landscape](ham-radio-landscape.md) — what ham is, license classes, what Tech unlocks
- [gmrs-basics](gmrs-basics.md) — the 30 GMRS channels and the rules
- [dmr-concepts](dmr-concepts.md) — digital voice on your radio
