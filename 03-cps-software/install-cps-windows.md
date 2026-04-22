# Install CPS on Windows

The Baofeng DM-32UV CPS (Customer Programming Software) is Windows-only. This note walks through getting it installed on your gaming PC.

> **Placeholders marked ⚠️ USER TO FILL** get replaced with your actual download URL, filename, and version after you complete the install (Task 6 of the Phase 2 plan). Until then they're generic.

## Which CPS do I need?

The DM-32UV CPS is sometimes bundled on a CD with the radio. If that's what came in your box, verify it's the correct model before installing — Baofeng sells several DMR HTs with similar names (DM-1701, DM-V1, DM-32UV, RD-5R) and the CPS versions are **not interchangeable**.

If no CD, or you want the latest version (recommended), download fresh.

## Official download sources (primary)

1. **Baofeng Tech / BTech support page** — https://baofengtech.com/support/ (or https://www.baofengtech.com/dm32uv)
   - Look for "DM-32UV CPS" or "DM-32UV Programming Software"
   - Also usually hosts the user manual PDF
2. **The QR code in the printed manual** — scans to the same manufacturer download page

## Acceptable fallback sources

Only if primary is unreachable:

- Dealer pages for retailers that sold you the radio (HamRadio Outlet, GigaParts, DX Engineering, Main Trading Co, etc.)
- **radioddity.com** sometimes mirrors Baofeng CPS for rebadged models — verify it's DM-32UV-specific, not another model

❌ **Do NOT download from random Reddit / Facebook / Chinese filesharing links** — CPS installers have been observed with bundled adware or modified binaries. Stick to manufacturer or dealer sources.

## Record what you got

After downloading, fill in:

- **Filename:** ⚠️ USER TO FILL — e.g., `DM-32UV_CPS_V2.01.03.zip`
- **Version:** ⚠️ USER TO FILL — e.g., `V2.01.03` (visible in the CPS About dialog)
- **Download URL:** ⚠️ USER TO FILL — the exact page you got it from
- **Download date:** ⚠️ USER TO FILL
- **SHA256 hash** *(optional paranoia):* in PowerShell run `Get-FileHash .\DM-32UV_CPS_V2.01.03.zip -Algorithm SHA256`. Without a publisher-published hash this only proves "same file I downloaded before," not authenticity — but it's still useful.

## Install procedure

1. **Extract the ZIP** if the download is zipped. Inside: usually an `Setup.exe` or `.msi` installer plus a `USB_Driver/` folder (if drivers are bundled — see [driver-and-cable](driver-and-cable.md)).
2. **Right-click → Run as administrator** the installer. Windows SmartScreen may warn "Unknown publisher" — this is normal for smaller vendors that don't code-sign installers; "More info → Run anyway" to proceed.
3. Accept the EULA (it's a standard boilerplate).
4. **Install location:** default is usually `C:\Program Files (x86)\BAOFENG\DM-32UV\` or similar. Accept the default unless you have a reason.
5. **Bundled dependencies:** CPS may install:
   - Microsoft Visual C++ runtime (if missing)
   - Microsoft .NET Framework 4.x (if missing)
   Both are safe to accept.
6. Finish → no reboot typically required.
7. Launch from Start menu ("BAOFENG DM-32UV" or similar shortcut).

## Verify the install

- CPS launches without errors
- The main window opens (usually tree on left, editor on right — see [cps-ui-tour](cps-ui-tour.md))
- `Help → About` shows the version number
- Open a test dummy codeplug (File → New) — confirm you can navigate tabs

No radio or cable needed for these verification steps.

## Uninstall (cleanly)

- Settings → Apps → search "Baofeng" or "DM-32UV" → Uninstall
- Remove any remaining folder in `Program Files (x86)` if it lingers
- User data (codeplug files) are stored wherever you saved them (usually `Documents\`), not in the install directory — they survive uninstall

## Post-install: language and passwords

### Language fix (if CPS launches in Chinese)

Some CPS versions default to Chinese. Two fixes:

1. **INI file edit (easiest):** Navigate to the CPS install folder (e.g., `C:\Program Files (x86)\BAOFENG\DM-32UV\`), open the `.ini` file in a text editor, change the language value from `CH` to `EN`, save, and relaunch CPS.
2. **Menu navigation (if you can't find the INI):** Third menu item from the left → second option in the dropdown → pick English from the dropdown in the dialog → OK.

### CPS passwords

The CPS has locked menus under **Tools** that require passwords:

| Menu path | Password | What it does |
|-----------|----------|--------------|
| **Tools → Embedded Information** | `374612` | Radio model info, firmware version, serial — safe to browse |
| **Tools → Test Mode / Adjust Mode** | `66660501` | Calibration and diagnostics — **leave this alone** unless you know what you're doing; bad calibration adjustments can degrade radio performance |

You do **not** need either password for normal codeplug programming (channels, zones, talkgroups, etc.). The Embedded Information password is useful for confirming your radio's firmware version and model string.

## Known install issues and fixes

Placeholder — populate with anything specific you encountered:

- *(none reported yet — fill in after install)*

## Related

- [driver-and-cable](driver-and-cable.md) — getting the USB programming cable recognized
- [cps-ui-tour](cps-ui-tour.md) — what the program looks like after install
- [read-write-radio](read-write-radio.md) — safe procedure to read the factory codeplug
