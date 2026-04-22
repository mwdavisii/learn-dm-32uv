# Menu map

The full menu tree of the DM-32UV, what each setting does, and safe defaults. ⚠️ = double-check on your unit as menu items vary by firmware revision. 🚫 = generally leave alone.

> Most day-to-day operation can be done without ever going into the menu — channel/zone navigation uses the knobs, PTT is PTT. The menu is for one-time setup, troubleshooting, or niche features.

## Navigation convention

Entering: **MENU**. Navigating: **▲ / ▼** or **number keys** for quick jump. Confirming: **MENU**. Going back: **BACK / EXIT**.

In the sections below, `→` means "next level down."

---

## 1. Radio Set (radio-wide settings)

| Item | What it does | Safe default |
|------|--------------|--------------|
| Squelch | Level at which weak signals break silence (0 = always open, 9 = high threshold) | 3–5 |
| VOX | Voice-activated TX (no PTT) | Off (prevents accidental TX) |
| Power Save | Duty-cycle the receiver to save battery | On (default) |
| Beep | Keypad tones | Your preference; Off is less annoying |
| Roger Beep | Tone at end of TX | Off (considered amateurish on ham) |
| Auto Backlight | Screen backlight timeout | 5–10 sec |
| Backlight Color | Color (blue/green/orange/etc., if supported) | Your taste |
| Brightness | Screen brightness | Medium |
| Auto Power Off | Shut off after N hours idle | Off or 4 h |
| Boot Logo | Splash text/image | Default / customizable |
| Startup Password | Lock radio on boot | Off 🚫 (adds a failure mode) |
| Language | English / Chinese / etc. | English |
| Keypad Lock | Auto-lock after idle | Your preference |
| DTMF | Tone dialing settings | 🚫 for basic use |
| 2-Tone / 5-Tone | Paging | 🚫 |
| Alarm | Emergency alarm config | Leave default; don't test it casually |

## 2. Digital (DMR settings)

| Item | What it does | Default |
|------|--------------|---------|
| Radio ID | Your DMR ID (empty until you get one from radioid.net) | Empty pre-license |
| DMR Services | Advanced DMR features (roaming, private call options) | 🚫 factory |
| Call Alert | Ring / buzz on private call | Off |
| Contact Manager | Quick view of stored contacts | Reference-only |
| Time Slot | Default TS if channel doesn't specify | Leave at channel config |
| Color Code | Default CC if channel doesn't specify | Leave at channel config |

**Pre-license note:** Keep Radio ID empty until you have a ham callsign + DMR ID. The radio will TX as "no ID" on DMR, which repeaters reject — but it won't let you accidentally transmit with a bogus ID.

## 3. Scan

| Item | Purpose |
|------|---------|
| Scan List | Select active scan list |
| Priority Channel | Channel checked most often during scan |
| Scan Mode | Time / Carrier / Search |
| Auto Scan | Auto-resume scanning |

## 4. Channel

| Item | Purpose |
|------|---------|
| Channel Name | Edit visible name |
| TX Freq / RX Freq | Manually edit (usually done in CPS) |
| Mode | Analog / Digital per channel |
| Power | High / Low |
| Bandwidth | 12.5 / 25 kHz (analog) |
| Tone (CTCSS/DCS) | For analog |
| TX Allow / Prohibit | **⚠️ Set "Prohibit" for all ham channels until you pass Tech** |

## 5. Zone

Select active zone; rename zones (usually done in CPS).

## 6. Contact (DMR)

Scroll stored DMR IDs and talkgroups.

## 7. GPS *(if your unit has GPS)*

- GPS On/Off
- GPS Info display
- GPS Reporting

Many DM-32UV units lack GPS — 🚫 if absent or unused.

## 8. Bluetooth *(if supported)*

Some revisions support BT headsets. Pair mode, BT volume. 🚫 if not using.

## 9. Reset / Factory Reset

**⚠️ Wipes your codeplug.** Confirm you have a backup `.rdt` file before ever selecting this. Two levels usually:

- **Profile reset** — settings only
- **Full reset** — wipes everything, reboots to factory defaults

## 10. Info

Firmware version, hardware version, radio serial. **Record these when you first power on** — useful for support and for knowing if a firmware update is even worth considering.

---

## Common menu paths (cheat sheet)

| Goal | Path |
|------|------|
| Set squelch | MENU → Radio Set → Squelch → N |
| Toggle key beep | MENU → Radio Set → Beep |
| Enter my DMR ID (after licensing) | MENU → Digital → Radio ID |
| Factory reset (danger) | MENU → Reset → Full Reset → confirm |
| Check firmware version | MENU → Info → Version |
| Change active zone | MENU → Zone → select |

## ⚠️ Settings that can cause problems

- **Squelch 0** + open-squelch channel = continuous noise, drains battery faster.
- **VOX On** with unplugged earpiece = radio TX's on any loud noise around it.
- **Startup password** = lock yourself out if you forget it.
- **Factory reset** without a backup = lose your codeplug.

## 🚫 Settings generally leave alone

- DTMF, 2-Tone, 5-Tone (paging) — no relevance to your goals
- Encryption (commercial features; illegal on ham bands anyway)
- DMR Services submenu internals
- Factory test / service modes (may appear via key combos)

## Related

- [buttons-and-knobs](buttons-and-knobs.md) — how to get to the menu
- [display-and-indicators](display-and-indicators.md) — what you see on screen
- [CPS UI tour](../03-cps-software/cps-ui-tour.md) — edit most of this more comfortably on the PC
