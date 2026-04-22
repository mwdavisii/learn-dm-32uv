# NOAA Weather Radio (NWR) — Memphis, TN

**Source:** NOAA NWR station listing (TN) — https://www.weather.gov/nwr/station_listing?state=TN • NWS Memphis — https://www.weather.gov/meg/ • NWR general info — https://www.weather.gov/nwr/
**Pull date:** 2026-04-18

## What is NOAA Weather Radio?

NOAA Weather Radio (NWR) is a nationwide network of VHF transmitters broadcasting a continuous forecast loop from the nearest NWS office, plus SAME-encoded alerts for severe weather, civil emergencies, and AMBER alerts. It is an invaluable backup when cellular or internet is down. NWR is **RX-only** on civilian radios — transmitting on 162.400–162.550 MHz is prohibited.

## Memphis-area NWR station `#unverified`

> Verify against https://www.weather.gov/nwr/station_listing?state=TN before promoting to `#verified`.

| Field | Value |
|-------|-------|
| Callsign | **KWJ76** (traditional Memphis NWR — verify) |
| Frequency | **162.475 MHz** (WX3) |
| Transmitter location | Memphis, TN (tower height not confirmed here) |
| Operated by | NWS Memphis (WFO MEG), https://www.weather.gov/meg/ |
| Typical coverage | Shelby, Tipton, Fayette (TN); DeSoto, Tate, Tunica, Marshall (MS); Crittenden (AR) — confirm exact county list from station_listing page |

If the station_listing lookup shows a different callsign/frequency for the Memphis transmitter, update this table and the marked row in the channel table below.

## Standard NWR channel table (authoritative, nationwide)

| WX Ch | Freq (MHz) | Notes |
|-------|------------|-------|
| WX1   | 162.550    | — |
| WX2   | 162.400    | — |
| WX3   | **162.475** | **Memphis NWR (KWJ76)** `#unverified` |
| WX4   | 162.425    | — |
| WX5   | 162.450    | — |
| WX6   | 162.500    | — |
| WX7   | 162.525    | — |

These seven channels are fixed by NOAA and are identical on every weather-capable receiver (handhelds, scanners, marine radios, etc.).

## Alert tones

NWR severe-weather alerts are preceded by the **1050 Hz Warning Alarm Tone (WAT)** — a one-second tone burst (historically used before the SAME digital header was added in the 1990s and still transmitted today for legacy receivers). Modern receivers also decode the **SAME (Specific Area Message Encoding)** digital header that precedes the WAT, which allows filtering by county FIPS code and event type.

The **DM-32UV** (and essentially every scanner on the market) supports a **weather-alert scan mode** that monitors the selected NWR channel with audio muted and only unmutes when the 1050 Hz WAT is detected. This is the preferred way to run NWR on an HT — no constant forecast-loop audio, but you still get severe-weather wake-up alerts.

## Phase 4 verification

Tune the Memphis NWR channel (162.475 MHz / WX3) once the codeplug is loaded. If you hear the continuous forecast loop, promote to `#verified` immediately. **This is the easiest test in the verification pass** — no repeater handshake, no license required, just an always-on carrier you either hear or you don't.

If 162.475 MHz is silent:
1. Try the other six NWR channels — the primary Memphis transmitter may have moved, or a neighboring transmitter (e.g., Jackson TN, Millington, or a MS/AR site) may be the strongest signal at your QTH.
2. Re-check the station_listing URL above for current callsign + frequency.
3. Note antenna/propagation — NWR is VHF line-of-sight; indoor rubber-duck reception in a basement can fail even when the transmitter is healthy. See RF basics for propagation context.

## Related

- [sources-and-verification](sources-and-verification.md)
- [RF basics](../01-foundations/rf-basics.md) (VHF propagation context)
