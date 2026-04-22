# Part 90 vs Part 95 — what this means for your DM-32UV

The FCC regulates different radio services under different "Parts" of **Title 47 of the Code of Federal Regulations**. Each Part has its own type-acceptance requirements — i.e., what equipment is certified as legal to use in that service. This note explains why this matters, why your radio sits on the wrong side of a line for GMRS, and the posture you've chosen.

## The relevant Parts, in one line each

- **Part 90** — private land mobile: commercial/business/public-safety two-way radio, plus the de-facto home for most ham-world DMR handhelds.
- **Part 95 Subpart E (Part 95E)** — General Mobile Radio Service (GMRS).
- **Part 97** — Amateur (ham) radio. Most radios here are not "type-accepted" at all; ham operators can legally modify and homebrew gear.
- **Part 15** — unintentional radiators (wifi, bluetooth, toys).

## What the DM-32UV is certified under

The Baofeng DM-32UV carries **Part 90 type-acceptance** and is sold as a ham-capable radio. It is **not Part 95E certified**.

Practically:

- On **Part 97** (ham): rules permit home-built and modified equipment, so Part-90 gear is fine in ham service.
- On **Part 90** (commercial): legal only if the operator holds a Part-90 license for the specific channels — not you.
- On **Part 95E** (GMRS): the rules require equipment to be type-accepted specifically for Part 95E. Your radio isn't.

## What that means for you

You have a valid **GMRS license**, but the **radio** isn't certified for GMRS. The rule technically requires both: a valid license *and* Part 95E-certified equipment.

Using a Part 90 radio on GMRS is a rule violation even with a valid GMRS license. This is widely done in practice — the radios are cheap, capable, and legally indistinguishable on the air from certified ones — but the rule exists.

## Enforcement reality

- FCC enforcement on casual GMRS non-compliance is **effectively zero** for personal/family use without interference complaints.
- High-power mobile use, interference with public-safety or licensed users, or commercial activity is where enforcement actually happens.
- The realistic "punishment" for a single user running a Part-90 HT on family GMRS is: nothing. But the rule still exists.

## The compliant alternative (if you ever want it)

If strict compliance matters later (e.g., you join a GMRS repeater club with tight rules, or you want to run 50 W mobile):

- **Baofeng UV-9G** — Part 95E certified, cheap, analog-only
- **Baofeng GM-15 Pro** — Part 95E certified, newer
- **Midland** and **Wouxun** make several Part 95E options
- **Icom IC-F4101** — pricey, professional

Any of those, used in parallel with the DM-32UV (which stays your ham-world radio), resolves the compliance question.

## Quick reference card

| Service | You need | Your gear | Status |
|---------|----------|-----------|--------|
| Ham (Part 97) | License (you're studying) + radio capable of ham bands | DM-32UV is ham-capable | ✅ Radio ready, **license pending** |
| GMRS (Part 95E) | License (you have one) + Part 95E radio | DM-32UV is Part 90, not Part 95E | ⚠️ License ✅, radio technically non-compliant |
| NOAA (Part 15 receive-only) | Receiver only | DM-32UV receives fine | ✅ |

## Next

- [rx-only-before-license](rx-only-before-license.md) — behavior rules on ham bands while you study
- [gmrs-basics](gmrs-basics.md) — the 30 channels and usage rules
- [ham-radio-landscape](ham-radio-landscape.md) — what each ham license class unlocks
