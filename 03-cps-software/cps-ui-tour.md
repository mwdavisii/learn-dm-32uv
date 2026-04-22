# CPS UI tour

Walkthrough of the DM-32UV CPS main window and what each section configures. Updated from the actual CPS (confirmed 2026-04-19).

## Main window layout

```
┌─── File  Model  Setting  Program(P)  Tool(T)  View(V)  Help(H) ──┐
│                                                                    │
│  ┌──────────────────────┐  ┌──────────────────────────────────┐  │
│  │ DMR Radio             │  │                                    │  │
│  │ ├─ Public             │  │   No. | Name | Type | RX Freq |   │  │
│  │ │  ├─ Channel         │  │       TX Freq | Power | Width |   │  │
│  │ │  ├─ VFO A           │  │       CTC/DCS Dec | CTC/DCS Enc | │  │
│  │ │  ├─ VFO B           │  │       Color Code | Tx Contact |   │  │
│  │ │  ├─ Zone            │  │       RX Group List | Time Slot   │  │
│  │ │  ├─ Scan            │  │                                    │  │
│  │ │  ├─ Roaming Zone    │  │   (grid rows for selected item)   │  │
│  │ │  ├─ Roaming Channel │  │                                    │  │
│  │ │  ├─ Radio Information│  │                                    │  │
│  │ │  ├─ Option Feature  │  │                                    │  │
│  │ │  ├─ Key Function    │  │                                    │  │
│  │ │  ├─ One Key Operation│  │                                    │  │
│  │ │  └─ APRS            │  │                                    │  │
│  │ ├─ Digital            │  │                                    │  │
│  │ │  ├─ DMR ID          │  │                                    │  │
│  │ │  ├─ Talk Groups     │  │                                    │  │
│  │ │  ├─ CSV Contacts    │  │                                    │  │
│  │ │  ├─ RX Group List   │  │                                    │  │
│  │ │  ├─ Digital Emergency│  │                                    │  │
│  │ │  ├─ Digital Encrypt  │  │                                    │  │
│  │ │  └─ Quick Text messages│ │                                    │  │
│  │ └─ Analog             │  │                                    │  │
│  │    ├─ DTMF            │  │                                    │  │
│  │    ├─ Two Tone        │  │                                    │  │
│  │    ├─ Five Tone       │  │                                    │  │
│  │    ├─ BDC1200         │  │                                    │  │
│  │    └─ Analog Contacts │  │                                    │  │
│  └──────────────────────┘  └──────────────────────────────────┘  │
│  [ Add ] [ Delete ] [ Insert ] [ Up ] [ Down ] [ Import ] [ Export ]│
└────────────────────────────────────────────────────────────────────┘
```

- **Left pane:** hierarchical tree — DMR Radio → Public / Digital / Analog
- **Right pane:** grid editor for the currently selected section
- **Menu bar:** File / Model / Setting / Program(P) / Tool(T) / View(V) / Help(H)
- **Bottom buttons:** Add, Delete, Insert, Up, Down, **Import**, **Export** (context-sensitive — available on Channel grid)

## What each section does

### Public

Radio-wide configuration — channels, zones, scans, hardware settings.

- **Channel** — the main channel table (see column reference below)
- **VFO A / VFO B** — default VFO frequencies for the A and B sides of the display
- **Zone** — named groups of channels; each zone holds a list of channels you scroll through with the knob
- **Scan** — scan list definitions: which channels to sweep, priority channels, timing
- **Roaming Zone / Roaming Channel** — DMR roaming between repeaters carrying the same talkgroup. Advanced; skip for first codeplug.
- **Radio Information** — radio model, firmware version, serial number. Read-only reference.
- **Option Feature** — radio-wide settings: squelch level, VOX, TX timeout, boot display, power-on password, etc. **This is where "General Set" lives in this CPS version.**
- **Key Function** — side key and top key button mappings (short press + long press)
- **One Key Operation** — quick-access key combos. Advanced; skip for now.
- **APRS** — APRS configuration. Not relevant for first codeplug unless you plan to use APRS.

### Digital

DMR-specific configuration — must be set up before creating digital channels.

- **DMR ID** — your RadioID.net DMR ID number. Set to 0 or leave default until you register. **This is where you enter your ID when you get one.**
- **Talk Groups** — every DMR talkgroup you want to use (TG number, name, call type — Group or Private)
- **CSV Contacts** — DMR contact database. Can hold a large list of DMR user IDs for caller ID display. Not required for first codeplug, but nice to have later.
- **RX Group List** — bundles of talkgroups that a channel listens to simultaneously
- **Digital Emergency Systems** — emergency call configuration. Skip for now.
- **Digital Encrypt Systems** — DMR encryption settings. **Not legal on ham bands.** Skip.
- **Quick Text messages** — pre-canned DMR text messages. Optional convenience feature.

### Analog

Analog signaling configuration — tone systems beyond basic CTCSS.

- **DTMF** — DTMF tone sequences (autopatch, repeater control). Rarely needed on modern ham repeaters.
- **Two Tone / Five Tone** — legacy paging/signaling systems. Skip.
- **BDC1200** — 1200-baud data (APRS-adjacent). Skip for now.
- **Analog Contacts** — analog contact list entries. Optional.

## Channel grid columns

When you click **Public → Channel**, the right pane shows a grid with these columns:

| Column | Meaning |
|--------|---------|
| No. | Row number (auto-assigned) |
| Name | Display name on the radio LCD |
| Type | Digital or Analog |
| RX Frequency | Receive frequency in MHz |
| TX Frequency | Transmit frequency in MHz (same as RX for simplex; repeater input for repeaters) |
| Power | High / Middle / Low |
| Width | 12.5KHz (narrow) or 25KHz (wide) — analog only; digital is always 12.5K |
| CTC/DCS Dec | CTCSS/DCS decode tone (receive squelch) — analog only |
| CTC/DCS Enc | CTCSS/DCS encode tone (transmit) — analog only |
| Color Code | 0–15, DMR only — must match repeater |
| Tx Contact | DMR talkgroup/contact for transmit — select from Talk Groups list |
| RX Group List | Which RX group this channel monitors — select from RX Group List |
| Time Slot | Slot 1 or Slot 2, DMR only |

**Note:** There may be additional columns visible by scrolling right, including **TX Prohibit** (critical for RX-only channels), **Scan List**, and others. Scroll or widen the window to see all columns.

## Import / Export buttons (CSV workflow confirmed)

The **Import** and **Export** buttons at the bottom of the Channel grid confirm that **CSV import is supported for channels**. This is the fast path for programming:

1. **Export** a single test channel first to see the exact CSV format the CPS expects (column order, header names, encoding)
2. Reformat the `codeplug/sources/channels-*.csv` files to match that format
3. **Import** them into CPS

**Action item:** Export one row, inspect the CSV, and record the exact format here:

- **Column order:** ⚠️ TO FILL after export test
- **Header row included?** ⚠️ TO FILL
- **Delimiter:** ⚠️ TO FILL (comma, tab, etc.)
- **Encoding:** ⚠️ TO FILL (UTF-8, ANSI, etc.)

## Menu bar reference

| Menu | Key items |
|------|-----------|
| **File** | New, Open, Save, Save As |
| **Model** | Radio model selection (verify it says DM-32UV) |
| **Setting** | Display/UI preferences for the CPS app itself |
| **Program(P)** | **Read from Radio**, **Write to Radio**, Port selection |
| **Tool(T)** | **Embedded Information** (password: `374612`), Test Mode (password: `66660501` — leave alone) |
| **View(V)** | Window layout options |
| **Help(H)** | About, possibly user manual |

## Related

- [install-cps-windows](install-cps-windows.md) — get CPS installed before you can tour it (includes language fix and passwords)
- [driver-and-cable](driver-and-cable.md) — get the cable recognized before you can read/write
- [read-write-radio](read-write-radio.md) — the safe procedure, uses the Program menu
- [Codeplug overview](../04-codeplug-model/codeplug-overview.md) — what you're about to program
