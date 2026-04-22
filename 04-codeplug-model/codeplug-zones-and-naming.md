# Codeplug Zone Layout & Naming Conventions

How channels are organized on the radio. Each **zone** is a logical group you scroll through with the channel knob. The DM-32UV supports up to 64 channels per zone (A/B sides — verify on your firmware). Zones appear in the order listed here.

## Zone map

| # | Zone Name | Type | Ch Count | TX? | Notes |
|---|-----------|------|----------|-----|-------|
| 1 | **WX** | Analog RX-only | 7 | No | NOAA Weather Radio — all 7 NWR frequencies |
| 2 | **GMRS Sim** | Analog | 22 | Yes (licensed) | GMRS simplex ch 1–22 |
| 3 | **GMRS Rpt** | Analog | 9 | Yes (licensed) | GMRS repeater pairs 15R–22R + WROX887 |
| 4 | **MEM 2m** | Analog RX-only | 10 | **No** (pre-Tech) | Memphis 2 m ham repeaters + 146.520 calling |
| 5 | **MEM 70cm** | Analog RX-only | 7 | **No** (pre-Tech) | Memphis 70 cm ham repeaters + 446.000 calling |
| 6 | **DMR Mem** | Digital RX-only | ~20 | **No** (pre-Tech, no DMR ID) | Memphis DMR repeaters × talkgroups |

**Total: ~75 channels across 6 zones** — well within the DM-32UV's capacity.

## Naming convention

Baofeng CPS typically allows **8–12 characters** per channel name (verify on your CPS version). Names should be readable at a glance on the radio's LCD.

### Format by channel type

| Type | Format | Example | Explanation |
|------|--------|---------|-------------|
| NOAA WX | `WX#-FFF.FFF` | `WX3-162475` | WX channel number + freq (no decimal, 6 digits) |
| GMRS simplex | `GMRS-##` | `GMRS-01` | Channel number, zero-padded |
| GMRS repeater | `GMRS-##R` | `GMRS-20R` | Channel number + R for repeater |
| GMRS named rpt | `G-NAME` | `G-WROX887` | Named GMRS repeater |
| Ham 2m repeater | `CALL 2m` | `W4BS 2m` | Callsign + band |
| Ham 70cm repeater | `CALL 70` | `W4BS 70` | Callsign + band |
| Ham simplex | `CALL FFF` | `CALL 520` | "CALL" + last 3 digits of freq |
| DMR channel | `CALL TG#` | `W4BS TN` | Callsign + short talkgroup label |

### Rules

1. **No spaces where they'd cause truncation** — if your CPS shows only 8 chars, drop the space: `W4BS2m`.
2. **Callsign first** for repeater channels — makes scanning the list natural.
3. **Band identifier** (`2m` / `70`) distinguishes same-callsign repeaters on different bands.
4. **DMR talkgroup labels** use short mnemonics: `WW` (Worldwide 91), `NA` (North America 93), `TN` (TN Statewide 3147), `MEM` (Memphis Metro 31471), `DAR` (Delta ARC 314447), `LOC` (Local 9), `PAR` (Parrot 9990).

## Zone details

### Zone 1: WX (NOAA Weather)
All RX-only. Narrow FM. No tone. Program all 7 so you can scan if your primary (WX3) is weak.

### Zone 2: GMRS Sim (GMRS Simplex)
Channels 1–22. TX enabled. Power: High on ch 1–7 and 15–22 (up to 5 W HT); Low on ch 8–14 (0.5 W interstitial cap). No tone by default; add 141.3 Hz on channel 20 ("travel channel") as a convenience.

### Zone 3: GMRS Rpt (GMRS Repeaters)
Channels 15R–22R use the standard +5 MHz input offset (TX on 467.xxx, RX on 462.xxx). WROX887 is programmed separately with whatever tone is confirmed. TX enabled.

### Zone 4: MEM 2m (Memphis 2 m Ham)
All **TX Prohibited** until Tech license. 8 repeater channels + 146.520 calling freq + 146.550 (common alternate simplex). CTCSS decode set per repeater for tone squelch. Offset set correctly even though you won't TX — it's good practice and ready for when you get licensed.

### Zone 5: MEM 70cm (Memphis 70 cm Ham)
All **TX Prohibited**. 6 repeater channels + 446.000 calling freq. Same logic as 2 m zone.

### Zone 6: DMR Mem (Memphis DMR)
All **TX Prohibited** (no Tech + no DMR ID). Each physical repeater gets multiple channel entries — one per talkgroup you want to monitor. Color code and timeslot set per repeater/TG combo.

## When your Tech license arrives

1. **Ham analog zones (MEM 2m, MEM 70cm):** Flip `TX Prohibit` from Yes → No on every channel. Update the codeplug version.
2. **DMR zone:** Register at radioid.net, get your DMR ID, enter it in CPS under `General Set → Radio ID`. Then flip TX Prohibit → No on DMR channels.
3. Save as a new codeplug version (`codeplug-vN.data`), write to radio, verify.

## Related

- [codeplug-overview](codeplug-overview.md) — full codeplug summary
- [CPS UI tour](../03-cps-software/cps-ui-tour.md) — where to enter all of this
- [Sources & verification](../05-memphis-setup/sources-and-verification.md)
