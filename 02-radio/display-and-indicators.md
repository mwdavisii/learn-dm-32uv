# Display and indicators

What the color LCD shows and what the LEDs / beeps mean.

> ⚠️ = verify on your physical unit; layouts vary by firmware.

## LCD layout (idle on a channel)

Approximate layout:

```
┌─────────────────────────────────┐
│ 🔋[████▁]  📶[▂▄▆_]  🔒  📅 21:47│  ← status bar
├─────────────────────────────────┤
│        ZONE: Memphis 2m          │  ← current zone name
│                                   │
│      [ 02 ]  W4BS 2m              │  ← channel # + name
│                                   │
│        146.820 MHz                │  ← frequency (large)
│                                   │
│  DMR  TS1  CC1  TG-             │  ← mode + DMR params
│           *or*                    │
│  FM   T:107.2  CW                 │  ← mode + analog params
└─────────────────────────────────┘
```

### Common icons (top status bar)

| Icon | Meaning |
|------|---------|
| 🔋 [▉▉▉▉▁] | Battery level (4 bars full, 0 bars dead) |
| 📶 [▂▄▆▇] | Signal strength (S-meter) during RX |
| 🔒 | Keypad lock active |
| 🔔 | Call alert on |
| ▶️ | Scan active |
| 🛰️ | GPS lock (if equipped) |
| 🅰️ / 🅱️ | Which VFO / band is active |
| 📢 | Monitor (squelch open) |
| ⚡ | External power (charging while on) |

### Channel info area

- **Zone name** at top — reminds you which zone you're in
- **Channel number + name** — big, readable
- **Frequency** — shown in VFO mode, sometimes in MR mode too
- **Mode indicators** (bottom line):
  - `FM` / `NFM` — analog FM (wide / narrow)
  - `DMR` — digital
  - `T: 107.2` — CTCSS tone transmitted (analog)
  - `D: 023N` — DCS code (analog)
  - `CW` — carrier wave (rare, advanced)
  - `TS1` / `TS2` — DMR timeslot
  - `CC1` — DMR color code
  - `TG-<name>` — current DMR talkgroup selection
- **Lock icons** for TX-prohibit, keypad lock, etc.

## LED behavior

| LED | Color | Meaning |
|-----|-------|---------|
| Indicator (top) | **Green solid** | Receiving / squelch open |
| Indicator (top) | **Red solid** | Transmitting |
| Indicator (top) | **Red flashing** | Low battery warning, or unsuccessful TX (no repeater response on DMR) |
| Indicator (top) | **Off** | Idle, no traffic |
| Flashlight (if equipped) | White | Manual flashlight toggle |

## Audio indicators

| Sound | Cause |
|-------|-------|
| Short high beep | Key press (if keypad beep enabled) |
| Double beep | Menu navigation / confirm |
| Rising tone | Power on |
| Falling tone | Power off |
| Long low beep every ~30 sec | Low battery warning |
| "Roger" beep at TX release | If Roger Beep enabled (off by default — recommend keeping off) |
| Continuous warble | Emergency alarm activated — press cancel / power cycle to clear ⚠️ |
| DMR sync "chirp" | Repeater responded to your PTT (DMR only) — means you got heard |

## What "everything normal" looks like

Idle on a ham repeater RX (e.g., W4BS 146.820):

- Zone name top: `Memphis 2m`
- Channel: `[02] W4BS 2m`
- Frequency: `146.820 MHz`
- Mode line: `FM T:107.2` (if CTCSS set for scanning clean)
- No LED
- Silent

Someone keys up on the repeater:

- LED turns **green**
- Signal meter shows bars
- Audio plays their voice

You key up (when TX enabled, post-license):

- LED turns **red**
- Screen dims slightly or shows "TX" icon
- Mode indicator may flash

## What "something's weird" looks like

| Symptom | Likely cause |
|---------|--------------|
| Screen dark, no response | Battery dead or not seated; try charge |
| Squealing / feedback | Nearby strong signal; or mic gain too high |
| No audio on known-good channel | Volume low; squelch too high; tone mismatch |
| Red LED stays on, no TX heard | PTT stuck, or channel is TX-prohibited |
| Strange icons you don't recognize | See [buttons] — may have hit a key combo |
| Random language change | Menu → Radio Set → Language |

## Related

- [buttons-and-knobs](buttons-and-knobs.md) — which key you accidentally pressed
- [menu-map](menu-map.md) — toggling beeps, colors, brightness
- [charging-battery-care](charging-battery-care.md) — what the battery icons mean
