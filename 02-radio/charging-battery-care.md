# Charging and battery care

The DM-32UV uses a Baofeng BL-32 (or compatible) lithium-ion battery. Li-Ion is forgiving if you respect a few rules, and unforgiving if you don't.

## How to charge

### Drop-in cradle (standard)

1. Plug the AC adapter into the charging base
2. Drop the radio (battery attached) into the cradle, or drop the battery alone in
3. **Red LED** on the cradle = charging
4. **Green LED** = fully charged (~3–4 hours from empty)
5. Remove radio; optionally leave on charger — the charger is designed to manage trickle safely

### Direct charging *(if your unit supports it — ⚠️ verify)*

Some DM-32UV units support direct USB-C charging on the radio body, avoiding the cradle. Check for a charging port behind a rubber cover on the side of the radio. If present, any 5V USB-C charger works for slow charging.

## Li-Ion do's

✅ **Use the included charger** (or a known-good Baofeng replacement)
✅ **Charge to full occasionally** (but not every cycle — see below)
✅ **Store at 40–60% charge** for long-term (months in a drawer)
✅ **Room-temperature operation** ideal (never leave in a hot car or below freezing for extended periods)
✅ **Replace the battery** when runtime drops below ~60% of new — typical after 300–500 full cycles

## Li-Ion don'ts

❌ **Don't discharge to 0% repeatedly** — deep discharges kill Li-Ion faster than anything
❌ **Don't store fully charged long-term** — storage at 100% accelerates aging (counterintuitive but true)
❌ **Don't use random 12V chargers** — correct voltage for Baofeng is typically 8.4–12V input to the cradle; check the AC adapter label
❌ **Don't charge a swollen battery** — dispose at a battery recycling point
❌ **Don't puncture / squeeze / overheat** — fire risk is real with Li-Ion

## ⚠️ Critical warning: firmware updates

**Never attempt a firmware update on low battery.** Failed firmware writes due to power loss are the **primary way you can brick this radio** beyond easy recovery. Before any firmware update:

1. Battery ≥80% (ideally 100%)
2. Radio on the charger during the update
3. No storms nearby
4. Use the manufacturer's exact firmware updater — not a random download

See [firmware updates](../03-cps-software/firmware-updates.md) for full policy (default: **don't**).

## Battery lifespan and spares

- **Expected life:** 2–3 years of moderate use
- **Cycle count:** ~300–500 charge/discharge cycles to 80% of original capacity
- **Replacement:** spare BL-32 batteries from Baofeng Tech, Amazon, or HamRadioOutlet — usually $25–40 for OEM, similar for reputable aftermarket
- **Swap tip:** keep a charged spare in your bag; two 2200 mAh batteries beat one larger battery because you can field-swap

## Travel considerations

### FAA carry-on rules (US, as of current regs)

- Li-Ion batteries ≤100 Wh: **carry-on allowed**, up to 2 spares
- BL-32 is ~17 Wh (well under limit)
- Check luggage: **no loose Li-Ion spares** — always in carry-on
- Radio + installed battery can be in checked or carry-on

### Outside the US

Rules vary. Lufthansa / British Airways / major carriers allow ≤100 Wh in carry-on. Always check the airline's Li-Ion policy before a flight.

## What the battery icons mean

The display shows 4 bars typically:

| Indicator | Charge level | Action |
|-----------|-------------|--------|
| 🔋 [████] | 80–100% | Ready |
| 🔋 [███▁] | 50–80% | Ready |
| 🔋 [██▁▁] | 25–50% | Start thinking about a charge for the day |
| 🔋 [█▁▁▁] + slow beep | 10–25% | Charge soon |
| 🔋 [▁▁▁▁] + fast beep | <10% | Charge NOW; avoid TX |
| 🔋 flashing | Critical | Radio will shut down soon |

## Related

- [dm32uv-overview](dm32uv-overview.md) — battery model and capacity specs
- [Firmware updates](../03-cps-software/firmware-updates.md) — why battery level matters for updates
- [display-and-indicators](display-and-indicators.md) — battery icons and low-battery beeps
