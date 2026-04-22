# RX-only before license — what you can legally do right now

You have a DM-32UV in your hand and a Technician exam in your future. Until the exam is behind you, you're **not a licensed amateur operator**. This note captures exactly what that means in practice.

## The rule, simplified

- **Listening to anything is legal.** 47 CFR Part 97 regulates transmission, not reception. You can monitor ham bands, NOAA, GMRS (you have that license anyway), public-safety, aviation, marine, etc., with no license of any kind.
- **Transmitting on ham bands (2 m, 70 cm, HF segments, etc.) without a license is a violation.** Even briefly. Even as a test. Even kerchunking a repeater "just to see."
- **Transmitting on GMRS is fine for you** (you have the license) — though see the [part90-vs-part95](part90-vs-part95.md) radio-certification nuance.
- **Emergencies:** 47 CFR §97.403 permits anyone to use any frequency in a genuine emergency endangering life or property. Don't treat this as a loophole for curiosity.

## What RX-only looks like on your radio

Two layers of discipline:

### 1. Codeplug TX-disable

Every ham-band channel in your codeplug should be programmed with **TX disabled**. The DM-32UV CPS has a per-channel "TX prohibit" or "RX-only" flag. When set, keying the PTT on that channel does nothing. This is the reliable way to make sure you can't accidentally transmit on ham while trying to.

### 2. Physical discipline

- **Don't press PTT on ham channels until you pass Tech.** Even with TX-disable, avoid the motion. Build the habit.
- **Monitor, note, learn.** Listen for hours. Learn local conventions. Hear how people identify, what tones they use, what nets run when.

## What to do while studying

Concrete, low-stakes practice:

- Tune to a local 2 m repeater (see [Memphis ham repeaters](../05-memphis-setup/local-ham-repeaters.md)) and leave it on during dinner. Listen for nets.
- Check the Delta Amateur Radio Club schedule for nets, meetings, exam sessions.
- Listen to DMR traffic on a local repeater in the DMR zone.
- Practice programming channels manually (VFO mode) to get comfortable with the menu.
- Monitor NOAA; learn what "this is a routine weekly test" sounds like.

**Studying the exam material** is the main project. Free question pools and practice exams at:

- [hamstudy.org](https://hamstudy.org) — most popular, flashcards + timed practice
- [ARRL's question pool](https://www.arrl.org/question-pools) — official source
- [ham-prep.com](https://www.hamradioprep.com) — paid course if you prefer structured video

The Tech pool is ~426 questions; exams draw 35. Most people pass in a few weeks of casual study.

## What's OK vs not OK — quick table

| Action | Pre-Tech | Post-Tech |
|--------|----------|-----------|
| Listen to any ham band | ✅ | ✅ |
| Key PTT on a ham channel | ❌ | ✅ (with callsign ID) |
| Transmit on GMRS (you're licensed) | ✅ (noting Part 90 caveat) | ✅ (same) |
| Listen to NOAA, public-safety, marine | ✅ | ✅ |
| Program the radio | ✅ | ✅ |
| Check into a net on ham | ❌ | ✅ |
| Bounce off Parrot (TG 9990) for DMR self-test | ❌ (TX is TX) | ✅ once you also have a DMR ID |
| Emergency use | ✅ (§97.403) | ✅ |

## After you pass

Within hours of the VEC confirming your pass:

- FCC application fee paid ($15)
- Callsign issued (typically 1–2 business days)
- You're officially on the air; update your codeplug to flip TX-prohibit flags off on ham channels
- Apply for a DMR ID at [radioid.net](https://radioid.net) — may take a few days to issue

That's a Phase 3+ concern. Today's posture: **monitor, study, enjoy the radio as a receiver.**

## Next

- [ham-radio-landscape](ham-radio-landscape.md) — license class details
- [dmr-concepts](dmr-concepts.md) — what you're hearing on DMR
- [Memphis ham repeaters to monitor](../05-memphis-setup/local-ham-repeaters.md) *(Phase 1c)*
