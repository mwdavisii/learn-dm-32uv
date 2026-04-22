# Programming Walkthrough — DM-32UV Memphis Codeplug

Step-by-step instructions for entering the Memphis codeplug into CPS. **Do this in order** — later steps depend on earlier ones (e.g., channels reference talkgroups, zones reference channels).

> **Prerequisites:**
> - CPS installed and cable working ([Install CPS](../03-cps-software/install-cps-windows.md))
> - First read completed, factory backup saved as `backup-YYYY-MM-DD.data` and `codeplug-v0.data` ([Read/write procedure](../03-cps-software/read-write-radio.md))
> - CSV reference files in `codeplug/sources/` open in a text editor or spreadsheet alongside CPS

## Step 0: Clear factory channels

The factory codeplug has ~25 placeholder channels with generic names and test frequencies. Delete all of them before starting — select all rows in **Public → Channel** and click **Delete**. You already have your factory backup in `codeplug-v0.data` if you ever need to restore.

## Order of operations

```
1. Delete factory channels (Step 0 above)
2. Radio settings — DMR ID, option features (Public → DMR ID, Option Feature)
3. DMR Talkgroups (Digital → Talk Groups)
4. DMR RX Groups (Digital → RX Group List)
5. Channels — all types, all zones (Public → Channel)
6. Zones (Public → Zone)
7. Scan Lists (Public → Scan)
8. Key Assignments (Public → Key Function)
9. Save → Write → Verify
```

This order matters because: channels reference talkgroups and RX groups (so those must exist first), and zones reference channels (so channels must exist first).

---

## Step 1: Radio Settings

### DMR ID — Digital → DMR ID

Set your DMR ID here. You don't have one yet, so set to `0` or leave the default. **Update this when you register at radioid.net after getting your Tech license.**

### Option Feature — Public → Option Feature

Opens as a tabbed dialog with 12 tabs. Most defaults are fine. Key tabs:

**Power on/off tab:**
- **Power On Display Line 1** — change "Welcome" to your name or callsign
- **Power On Display Line 2** — "DM-32UV" is fine, or use your GMRS callsign
- **Allow Reset** — leave checked

**Other tab** (the important one):
- **TOT(s)** — 120 (TX timeout in seconds — good safety default)
- **VOX Level** — 1 (VOX is controlled per-channel; the import CSV disables it on all channels)
- **Weather Alarm** — checked (enables 1050 Hz NWR alert detection)
- **Language** — English

Everything else: leave at defaults. Click **OK** when done.

---

## Step 2: DMR Talkgroups (Digital → Talk Groups)

In the left pane, click **Digital → Talk Groups**. Delete any factory entries (e.g., "Contacts 1").

Import file: **`codeplug/sources/dmr-talkgroups.csv`** — click **Import** at the bottom of the grid and select this file.

CPS format (4 columns): `No., Name, ID, Type` — with types `Group Call` or `Private Call`.

**All 14 talkgroups** should appear after import.

### Talkgroup quick reference (enter these)

| # | TG | Name | Type |
|---|-----|------|------|
| 1 | 91 | WW | Group |
| 2 | 93 | NA | Group |
| 3 | 3100 | USA | Group |
| 4 | 3174 | SE Reg | Group |
| 5 | 310 | TAC310 | Group |
| 6 | 3147 | TN State | Group |
| 7 | 31470 | MidSouth | Group |
| 8 | 31471 | MEM Metro | Group |
| 9 | 314431 | TN NWS | Group |
| 10 | 314447 | DeltaARC | Group |
| 11 | 314706 | MEM Loc | Group |
| 12 | 9 | Local | Group |
| 13 | 9990 | Parrot | Private |
| 14 | 9999 | Parrot99 | Private |

---

## Step 3: DMR RX Groups (Digital → RX Group List)

In the left pane, click **Digital → RX Group List**. Delete any factory entries (e.g., "RX Group 1").

Import file: **`codeplug/sources/dmr-rx-groups.csv`** — click **Import** and select this file.

CPS format (3 columns): `No., RX Group Name, Contact Members` — members are pipe-delimited (`|`). Names must match Talk Groups exactly.

4 groups should appear after import:

- **RX-Wide** — WW, NA, USA, SE Reg, TAC310 *(wide-area monitoring)*
- **RX-TN** — TN State, MidSouth, MEM Metro, TN NWS *(Tennessee/regional)*
- **RX-Memphis** — MEM Metro, DeltaARC, MEM Loc, Local *(Memphis-focused)*
- **RX-All** — all 12 group talkgroups *(scan/monitor — hear everything)*

---

## Step 4: Channels

The big one. Open **Public → Channel** in the left pane. Delete all factory channels first.

Import file: **`codeplug/sources/channels-import.csv`** — click **Import** and select this file. All 71 channels should appear.

CPS format: 39 columns matching the DM-32UV export format. The human-readable per-zone CSVs (`channels-wx.csv`, `channels-gmrs-simplex.csv`, etc.) are kept as reference documentation.

### Important CPS fields explained

| CPS Field | What it means | Gotchas |
|-----------|---------------|---------|
| Channel Type | Analog or Digital | Set first — it changes which fields are available |
| RX Freq | What you listen on | Always the repeater output for repeater channels |
| TX Freq | What you transmit on | Same as RX for simplex; repeater input for repeaters |
| Power | High or Low | High = ~5W, Low = ~1W (radio dependent) |
| Bandwidth | 12.5K (narrow) or 25K (wide) | GMRS/WX = narrow; ham analog = wide (25K) |
| CTCSS/DCS Decode | Tone squelch on receive | Filters noise; set per repeater |
| CTCSS/DCS Encode | Tone sent when you TX | Required to open the repeater |
| Color Code | DMR only, 0–15 | Must match the repeater — wrong CC = ignored |
| Time Slot | DMR only, 1 or 2 | Must match the talkgroup assignment per repeater |
| Contact/TG | DMR only — which talkgroup | Select from the list you built in Step 2 |
| RX Group | DMR only — which RX group | Select from the list you built in Step 3 |
| **TX Prohibit** | **Yes = RX only, No = can TX** | **Set Yes on ALL ham channels (pre-Tech) and ALL WX channels** |

### Enter channels in this order

Work through the CSV files one zone at a time. For each row:

1. Click **Add** (or the + button) in the channel grid
2. Set **Channel Type** first (Analog or Digital)
3. Fill in every field from the CSV row
4. Double-check **TX Prohibit** — this is the most important safety field

#### Zone 1: WX (7 channels)
File: `channels-wx.csv`
- All Analog, Low power, 12.5K narrow, no tones, TX Prohibit = Yes
- These are receive-only; you legally cannot transmit on NWR frequencies

#### Zone 2: GMRS Simplex (22 channels)
File: `channels-gmrs-simplex.csv`
- All Analog, 12.5K narrow
- Ch 1–7 and 15–22: High power, TX Prohibit = **No** (you're GMRS licensed)
- Ch 8–14: **Low power** (0.5W FRS cap), TX Prohibit = No
- Ch 20 (GMRS-20): CTCSS 141.3 Hz encode+decode (travel channel convention)

#### Zone 3: GMRS Repeater (9 channels)
File: `channels-gmrs-repeater.csv`
- All Analog, High power, 12.5K narrow
- **TX freq is different from RX freq** — this is the repeater offset
- RX = 462.xxx (repeater output), TX = 467.xxx (repeater input)
- G-WROX887: tone 141.3 assumed but `#unverified`
- TX Prohibit = **No**

#### Zone 4: MEM 2m (10 channels)
File: `channels-ham-2m.csv`
- All Analog, High power, **25K wide** (standard for 2m FM)
- CTCSS encode + decode = 107.2 Hz on all repeaters (verify individually later)
- TX freq includes the repeater offset (already calculated in the CSV)
- Simplex channels (CALL 520, CALL 550): TX = RX, no tone
- **TX Prohibit = Yes on every channel** — you're pre-Tech

#### Zone 5: MEM 70cm (7 channels)
File: `channels-ham-70cm.csv`
- Same as 2m but on 70 cm band, +5 MHz offset
- **TX Prohibit = Yes on every channel**

#### Zone 6: DMR Mem (16 channels)
File: `channels-dmr.csv`
- All Digital, High power
- No bandwidth or CTCSS fields (digital doesn't use them)
- **Color Code** varies: CC1 for most, **CC4 for NJ8X** — watch this carefully
- **Time Slot** varies per talkgroup — check each row
- **Contact/TG** — select the talkgroup from your Step 2 list
- **RX Group** — select the appropriate group from Step 3
- **TX Prohibit = Yes on every channel** — no Tech license + no DMR ID

---

## Step 5: Zones

In the left pane, click **Zone**.

Reference file: `codeplug/sources/zones.csv`

Create 6 zones. For each zone:

1. Click **Add**
2. Name the zone (e.g., "WX", "GMRS Sim")
3. Add channels to the zone in the order listed in the CSV
4. Most CPS versions let you select channels from a list and move them into the zone

### Zone order on the radio

The order you create zones is typically the order they appear when you rotate the channel knob's zone selector. Put the ones you'll use most at the top:

1. **WX** — always accessible for weather
2. **GMRS Sim** — your primary TX capability right now
3. **GMRS Rpt** — repeater access
4. **MEM 2m** — monitoring
5. **MEM 70cm** — monitoring
6. **DMR Mem** — monitoring

---

## Step 6: Scan Lists (optional but recommended)

Create scan lists so you can monitor multiple channels while parked on one.

| Scan List     | Channels to include                 | Use case                               |
| ------------- | ----------------------------------- | -------------------------------------- |
| WX Scan       | All 7 WX channels                   | Find strongest weather station         |
| GMRS Scan     | GMRS-15 through GMRS-22 + G-WROX887 | Monitor active GMRS simplex + repeater |
| Ham 2m Scan   | All MEM 2m channels                 | Sweep 2m repeaters for activity        |
| Ham 70cm Scan | All MEM 70cm channels               | Sweep 70cm repeaters                   |
| DMR Scan      | All DMR Mem channels                | Sweep DMR talkgroups                   |

Set **Priority Channel 1** to the most important channel in each list (e.g., WX3-162475 for weather, W4BS 2m for 2m ham).

---

## Step 7: Key Assignments (Keys section)

Suggested button mappings:

| Button | Function | Why |
|--------|----------|-----|
| Side Key 1 (short) | Monitor (open squelch) | Quick listen past tone squelch |
| Side Key 1 (long) | Scan On/Off | Toggle scanning |
| Side Key 2 (short) | Zone Select | Quickly switch zones |
| Side Key 2 (long) | Power Toggle (High/Low) | Adjust power on the fly |

Adjust to your preference — these are just starting points.

---

## Step 8: Save, Write, Verify

### Save
1. **File → Save As → `codeplug-v1.data`** in your `codeplug/` folder
2. Update `codeplug/changelog.md`:

```markdown
## v1 — 2026-XX-XX
- First Memphis codeplug build
- 71 channels across 6 zones: WX (7), GMRS Sim (22), GMRS Rpt (9), MEM 2m (10), MEM 70cm (7), DMR Mem (16)
- All ham + DMR channels TX Prohibited (pre-Tech, no DMR ID)
- GMRS channels TX enabled (licensed)
- All ham repeater data #unverified — pending Phase 4 verification
```

### Write to radio
1. **Program → Write to Radio**
2. Wait 60–120 seconds — **don't touch anything**
3. On completion, disconnect cable

### Verify (the fun part)
Power-cycle the radio, then work through this checklist:

- [ ] **Zone 1 (WX):** Tune to WX3-162475. Hear the forecast loop? Radio works.
- [ ] **Zone 2 (GMRS Sim):** Tune to GMRS-01. Key up briefly if you have a second radio to test with.
- [ ] **Zone 3 (GMRS Rpt):** Tune to G-WROX887. Listen for any repeater activity.
- [ ] **Zone 4 (MEM 2m):** Tune to W4BS 2m (146.820). Wait for the 8 PM net, or just listen for kerchunks.
- [ ] **Zone 5 (MEM 70cm):** Tune to W4BS 70 (443.200). May be quiet outside net times.
- [ ] **Zone 6 (DMR Mem):** Tune to W4BS TN. You should see DMR decode indicators if there's traffic. DMR is bursty — you may need to wait a few minutes.
- [ ] **Zone names display correctly** on the LCD
- [ ] **Channel names display correctly** and aren't truncated badly
- [ ] **Scan works** — start a scan in the GMRS zone, confirm it sweeps

If anything is wrong, write `codeplug-v0.data` back to the radio to restore factory, diagnose at your leisure. See [Read/write procedure](../03-cps-software/read-write-radio.md) for rollback steps.

---

## What to do after this

1. **Phase 4 — Verification pass:** Tune each repeater channel and confirm you actually hear something. Promote `#unverified` → `#verified` in the source markdown files.
2. **Get your Tech license:** When you pass, update Radio ID in General Settings, flip TX Prohibit → No on ham channels, save as `codeplug-v2.data`.
3. **Register for a DMR ID:** At radioid.net. Enter it in CPS, flip TX Prohibit on DMR channels, save as `codeplug-v3.data`.

## Related

- [codeplug-zones-and-naming](codeplug-zones-and-naming.md) — zone design rationale
- [codeplug-overview](codeplug-overview.md) — summary view
- [Read/write procedure](../03-cps-software/read-write-radio.md) — safe flash process
- [CPS UI tour](../03-cps-software/cps-ui-tour.md) — where everything lives in CPS
