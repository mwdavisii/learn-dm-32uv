# Buttons and knobs

Every physical control on the DM-32UV, what it does, and the common gotchas.

> **Verify against your unit.** Button labels and positions may vary slightly between firmware revisions — items marked ⚠️ deserve a real-world check.

## Top of radio

| Control | Function |
|---------|----------|
| **Volume / Power knob** (rotary + push) | Rotate: audio volume. Hold 1 sec: power on/off. |
| **Channel knob** (rotary, no click-stop) | Within the current zone, rotates through channels. Turn past last channel = wraps to first. |
| **Antenna connector (SMA-F)** | Screw on finger-tight. Never TX without antenna. |
| **Flashlight LED** *(on some units — ⚠️ verify)* | Activated by side button, not auto. |
| **Indicator LED(s)** | Green = RX, Red = TX, Red-blink = low battery / alert |

## Front — display and keypad

```
+------------------------+
|       LCD DISPLAY      |
|                        |
+------------------------+
|  [MENU]   [BACK/EXIT]  |
|  [  ▲ ]   [  ▼  ]      |   ← directional / scroll
|  [ 1 ] [ 2 ] [ 3 ]    |
|  [ 4 ] [ 5 ] [ 6 ]    |
|  [ 7 ] [ 8 ] [ 9 ]    |
|  [ * ] [ 0 ] [ # ]    |
+------------------------+
```

| Key | Short press | Long press |
|-----|-------------|------------|
| **MENU** | Enter menu system | — |
| **BACK / EXIT** | Back one level / cancel | Exit menu |
| **▲ / ▼** | Scroll in menu, browse channels in MR mode, or change digit in VFO mode | — |
| **0–9** | Direct entry in VFO mode; menu shortcut | Often assigned: zone switch, scan, FM radio, etc. ⚠️ verify per your firmware |
| **\* (asterisk)** | Switch A/B (dual-standby display) or scan toggle | — |
| **#** | Keypad lock toggle (on many Baofengs) | Alternate tone / function |

## Side buttons (left side)

Top to bottom, usually:

| Control | Default function |
|---------|------------------|
| **PTT** (large, main) | Hold to transmit |
| **PF1 / Side-top** (programmable) | Usually **monitor** (hold: open squelch + continuous RX) |
| **PF2 / Side-bottom** (programmable) | Usually **flashlight** or **alarm** |

Both PF1 and PF2 are **programmable via CPS** under the "Key Definitions" / "Buttons" section. Popular assignments:

- Scan toggle
- Talkgroup select
- Zone up / down
- Squelch open (monitor)
- Power level toggle (H/L)
- Emergency alarm

## "If you want to do X" quick reference

| Goal | Sequence |
|------|----------|
| Power on | Hold volume knob ~1 sec |
| Change zone | Menu → Zone → select (or long-press programmed key) |
| Change channel within zone | Rotate channel knob |
| Switch between VFO (manual tune) and MR (channel mode) | Menu → Radio → Mode → VFO/MR, or long-press a key ⚠️ |
| Enter frequency manually (VFO) | Switch to VFO, then press number keys for each digit |
| Lock keypad | Press `#` (or menu setting) |
| Set volume | Rotate volume knob |
| Toggle flashlight | Press assigned PF2 side button |
| Toggle high / low power | Menu → Channel → Power, or a key if assigned |
| Factory reset (careful) | Menu → Reset → confirm |

## Common gotchas

- **Accidental band switch** — pressing A/B while idle can swap which VFO is "active," confusing you about what band you're on.
- **Accidental FM radio activation** — some keys toggle the built-in broadcast-FM receiver; if you suddenly hear a music station, check for an FM-radio icon on screen.
- **Accidental VFO/MR toggle** — you meant to change channel, ended up on 446.000 MHz manually. Re-long-press to get back to MR (channel) mode.
- **Accidental menu entry** — MENU → number shortcuts can land you deep in config. BACK/EXIT your way out.
- **Monitor-held opens squelch forever** — if audio is hissing at you, you probably have PF1 (monitor) pressed.

## Programmable side keys — recommended assignments

These get set in [CPS](../03-cps-software/cps-ui-tour.md) under Key/Button Definitions. Suggested starting points:

| Key | Suggested function | Reason |
|-----|-------------------|--------|
| PF1 (top side) | **Monitor** (hold = open squelch) | Most useful "is there traffic?" check |
| PF2 (bottom side) | **Flashlight** | Keep the default — practical |
| Long-press PF1 | **Zone up** | Fast zone navigation |
| Long-press PF2 | **Zone down** | Complement zone-up |

Revisit after a week of use — if you find yourself digging in menus for something, reassign a key to it.

## Related

- [menu-map](menu-map.md) — everything under the MENU button
- [display-and-indicators](display-and-indicators.md) — reading the LEDs and screen
- [CPS UI tour](../03-cps-software/cps-ui-tour.md) — where to set Button Definitions
