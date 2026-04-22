# GMRS basics

The **General Mobile Radio Service** is the FCC service you already hold a license for. This note covers what that license actually permits, the 30 GMRS channels, and the practical realities of GMRS on a handheld.

## What GMRS is

- Governed by **47 CFR Part 95 Subpart E** (Part 95E).
- **30 channels** in the UHF 462 and 467 MHz bands.
- Intended for **short-distance two-way voice communication** for personal or small-business use.
- **Licensed service.** Unlike FRS, you need an FCC license to transmit.

## Your license in plain terms

- **Cost:** $35. **Duration:** 10 years. **No exam.**
- **Covers your whole household** — spouse, kids, parents, in-laws — under your single license, all using your assigned callsign (e.g., `WQXX123`).
- **Requirement:** You must identify with your callsign at the end of a conversation or every 15 minutes during one (rules of thumb — see FCC §95.1751 for specifics).
- **Business use** is allowed but limited (not a replacement for a Part 90 commercial license).

## The 30 channels

| Ch | Freq TX | Freq RX | Power class | Typical use |
|-----|---------|---------|--------------|-------------|
| 1–7 | 462.5625–462.7250 | same (simplex) | 5 W on GMRS / 2 W on FRS | Shared with FRS — family radios hear you |
| 8–14 | 467.5625–467.7250 | same (simplex) | **0.5 W max** (FRS-interstitial) | Very low power, short range |
| 15–22 | 462.5500–462.7250 | same (simplex) or repeater RX | Up to 50 W fixed / 5 W HT | Main GMRS channels; repeater-capable |
| 15R–22R | 467.5500–467.7250 TX → 462.5500–462.7250 RX | (repeater pair) | Repeater-TX on 467, listen on 462 | Only when a GMRS repeater is present |

**Simplex** = TX and RX on the same frequency. **Duplex (repeater)** = TX on one freq, RX on another (5 MHz offset in GMRS). See [simplex](../glossary/simplex.md) and [duplex](../glossary/duplex.md).

The "R" channels (15R–22R) use the same display channel number as the base simplex channel but with the 467 MHz TX offset — configured in the codeplug as a separate channel entry.

## Power limits, simplified

- Channels 1–7: up to **5 W** on GMRS-licensed equipment (handheld max)
- Channels 8–14: capped at **0.5 W**, ever — these are "interstitial" channels shared with FRS low-power
- Channels 15–22 (simplex): up to **5 W handheld / 50 W fixed**
- Repeater inputs (15R–22R): same as 15–22

Your DM-32UV can put out roughly 2–5 W on UHF, so you're within limits on the channels that allow 5 W, and you should set power to Low (typ. 0.5 W or lower on many DMR HTs — check [menu-map](../02-radio/menu-map.md) when it exists) on channels 8–14.

## CTCSS / DCS tones

Many GMRS channels use a **sub-audible tone** to keep different families from hearing each other. Your radio has to transmit the right tone to open the squelch on repeaters; for simplex, matched tones mean you only hear the people you intended to. See [ctcss](../glossary/ctcss.md) and [dcs](../glossary/dcs.md).

Standard "no tone" means open squelch — you'll hear anyone on the channel.

## Range reality on a 5 W HT

- **Simplex, urban:** 0.5–2 miles through buildings, maybe 5 miles rooftop-to-rooftop
- **Simplex, open terrain:** 3–10 miles with elevation
- **Via repeater:** depends entirely on the repeater's coverage footprint — can be 20+ miles if the machine is on a tall tower
- **Marketing claims** of "36 MILES!" on bubble-pack family radios are lies under normal conditions. Line-of-sight limits are physical.

## Part 95 vs Part 90 — your radio's situation

Your DM-32UV is a **Part 90** (commercial + ham) radio, **not Part 95E** certified for GMRS. Using a non-Part-95 radio on GMRS is technically non-compliant even with a valid GMRS license.

## Next

- [part90-vs-part95](part90-vs-part95.md) — the certification nuance spelled out
- [Memphis GMRS channels](../05-memphis-setup/gmrs-channels-memphis.md) — the channel list programmed into your codeplug *(Phase 1c)*
- [dmr-concepts](dmr-concepts.md) — the digital voice side of your radio
