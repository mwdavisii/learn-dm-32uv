# Read and write the radio — safe procedure

The single most important note in Phase 2. Follow this **every time** you change the codeplug. It prevents every common failure mode.

## Core rules (tattoo them)

1. **Read before write.** Always pull the current radio state into CPS before editing, even if you think CPS has the latest.
2. **Backup before anything.** The very first read goes to a dated `backup-YYYY-MM-DD.data` file, untouched forever.
3. **Save new versions, never overwrite.** Each flash gets its own `codeplug-vN.data`. Old versions stay.
4. **Keep a changelog.** One line per version in `codeplug/changelog.md`: what changed and why.
5. **Verify after write.** Power-cycle, tune a known channel, confirm it works before disconnecting.

---

## Pre-flight checklist

Every session, before any read or write:

- [ ] **Battery ≥ 50%**, ideally radio on charger during operation
- [ ] **Radio powered on** and on a normal channel (not deep in a menu, not in firmware-update mode)
- [ ] **Cable fully seated** both ends (K-plug clicked in; USB plugged into a stable port — prefer USB-2 over USB-3)
- [ ] **CPS launched** and correct COM port selected (see [driver-and-cable](driver-and-cable.md))
- [ ] **No other USB-serial programs** holding the COM port (putty, Arduino IDE, etc.)
- [ ] **Quiet environment** — cat, toddler, weather — nothing that will yank the cable mid-transfer

---

## First-ever read (do this as your first CPS operation)

Goal: snapshot the factory codeplug so you have a rollback.

### Steps

1. **Launch CPS.** Don't open any file yet.
2. **Program → Read from Radio** (or equivalent menu path — see [cps-ui-tour](cps-ui-tour.md))
3. A progress bar appears. Read takes **30–90 seconds** depending on radio model. **Don't touch anything during transfer.**
4. On success, CPS displays the codeplug. Browse the Channel list — you'll see factory defaults (some test channels, maybe VHF simplex presets).
5. **File → Save As → `backup-YYYY-MM-DD.data`** (substitute today's date) → save to `codeplug/` folder in your vault.
6. **File → Save As again → `codeplug-v0.data`** → same folder. This is your starting point for future edits — `v0` = factory.
7. **Do NOT write anything back to the radio yet.** You're done with the first read.

### What success looks like

- `codeplug/backup-YYYY-MM-DD.data` exists (~100–500 KB typically)
- `codeplug/codeplug-v0.data` exists (same file, different name)
- CPS shows Channel grid with factory entries
- Radio still works (power-cycle to confirm)

### What failure looks like

- "Cannot communicate with radio" → see [driver-and-cable](driver-and-cable.md) troubleshooting
- Progress bar stalls → cancel, power-cycle radio, reseat cable, retry
- Read completes but codeplug is empty → unusual; retry. If persistent, radio may have a firmware issue.
- Radio crashed / rebooted during read → stop, breathe, power-cycle, try again. Baofeng radios generally recover — one failed read doesn't damage anything.

---

## Standard read / edit / write cycle (for every subsequent session)

### 1. Read current state

**Program → Read from Radio.** Always. Even if you just wrote to it yesterday. This catches any manual changes you made on the radio keypad since then.

### 2. Edit in CPS

Make your changes. Common edits:

- Add a new channel (GMRS repeater you discovered)
- Toggle TX Prohibit flag when you get your Tech license
- Update a talkgroup subscription
- Reorganize zones

### 3. Save as a new version

**File → Save As → `codeplug-vN.data`** where N = previous version + 1. Never overwrite an older version.

**Before** saving, update `codeplug/changelog.md`:

```markdown
## v3 — 2026-05-14
- Added W4BTN 443.950 MHz (Bartlett repeater, #unverified)
- Enabled TX on Memphis 2m zone after Tech license passed
- Added TG 31470 Memphis Metro to DMR RX group
```

### 4. Write to radio

**Program → Write to Radio.** Progress bar again. **60–120 seconds typically**. **Do not touch during transfer.**

### 5. Power-cycle and verify

- Disconnect cable
- Power off radio, wait 3 seconds, power on
- Navigate to a known channel (e.g., NOAA WX3 — 162.475)
- Confirm audio
- Try another: a Memphis 2m repeater, a GMRS channel, a DMR repeater
- Verify zone names look right

### 6. Success or rollback

- **If all good:** changelog already updated; you're done.
- **If something's broken:** write the previous version back immediately.
  1. File → Open → `codeplug-v(N-1).data`
  2. Program → Write to Radio
  3. Verify, breathe
  4. Diagnose the bad version at your leisure

---

## Timing reference

| Operation | Typical time |
|-----------|--------------|
| Read | 30–90 sec |
| Write | 60–120 sec |
| First connection setup | 2–5 min (port selection, verify) |

If reads or writes take dramatically longer, something is wrong — cancel, power-cycle, retry.

---

## Common errors and recoveries

| Error | Cause | Fix |
|-------|-------|-----|
| "Cannot open COM port" | Port in use by another program | Close other apps; check Device Manager |
| "Cannot communicate with radio" | Cable not seated / driver issue / radio off | See [driver-and-cable](driver-and-cable.md) troubleshooting |
| "Write failed at X%" | Cable disconnected / power glitch | Power-cycle radio; try read → see what state it's in; rewrite if needed |
| "Invalid codeplug for this radio model" | Wrong CPS or file from a different model | Use correct CPS version; don't mix `.data` files between radio models |
| Radio rebooted randomly mid-read | Low battery, or firmware quirk | Charge battery to ≥80% and retry |
| Radio "bricked" — won't power on | Probably a firmware issue, NOT a codeplug issue | See [firmware-updates](firmware-updates.md) recovery section |
| Channel count shown < expected | Radio has smaller memory than CPS offers | Unusual but possible; check radio firmware against CPS version |

**Codeplug writes don't brick radios.** Only firmware updates can. If you ever write a bad codeplug, the recovery is always "write a good one again" — never a hardware repair.

---

## First-read confirmation — ⚠️ USER TO FILL

After you execute Task 10:

- **Date of first read:** `2026-__-__`
- **Read duration:** ___ seconds
- **Any warnings?** (dialog boxes, beeps, etc.)
- **Files saved:**
  - `codeplug/backup-2026-__-__.data` ✅
  - `codeplug/codeplug-v0.data` ✅
- **Factory channel count visible in CPS:** ___ channels
- **Notes:**

## Related

- [install-cps-windows](install-cps-windows.md) — get CPS installed
- [driver-and-cable](driver-and-cable.md) — cable recognition
- [cps-ui-tour](cps-ui-tour.md) — UI walkthrough
- [firmware-updates](firmware-updates.md) — the one thing that CAN brick the radio
- [What is a codeplug](../04-codeplug-model/what-is-a-codeplug.md) *(Phase 3)*
