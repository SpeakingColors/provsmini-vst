# PRO VS Mini: device notes

Sources: Behringer PRO VS MINI Quick Start Guide (project files) and Firmware 2.0.0 release notes (2024-12-08). A "35 parameter CC list from midi.guide" was mentioned in earlier notes but is not in our files, so it is not reproduced here (the table below is from the Quick Start Guide instead).

## Hardware (Quick Start Guide)

- Hybrid synthesizer with four vector-morphing oscillators per voice and an analog low-pass filter. The Quick Start Guide describes it as 4-voice; firmware 2.0.0 raises it to 5 voices.
- USB-C (power and USB MIDI) and MIDI IN on DIN.
- Waveform mix joystick: moving it up raises oscillator B against D, left raises A against C.
- Mix envelope with loop and repeat options and up to 4 points, a sequencer, an arpeggiator, 5 LFO waveforms (triangle, square, sawtooth, ramp, S&H).

## Firmware 2.0.0

- 5-voice polyphony.
- Arpeggiator Hold mode and Chord mode (chord sets: Major, Minor, EDM1, EDM2, Jazz, Octave, 4th, 5th). Disabled in sequencer mode.
- Portamento: MIDI CC 5, also in the OSC SET menu.
- FX engine (SYST menu, "FX ENGINE"): Chorus, Ensemble, Reverb, adjustable via MIDI CC 9.
- New Ultimate Patch factory presets (needs a factory reset after updating). Updates through the SynthTribe app (firmware section).

## MIDI and SysEx menu items (Quick Start Guide)

- MIDI Tx and MIDI Rx channel 1 to 16 or off; MIDI Velocity on/off; MIDI CC on/off.
- SysEx sends over USB: Prog Bulk, Prog Single, Patt Bulk, Patt Single. "SysEx Receive Listening" lets it receive over USB.
- Sync source: Internal, MIDI, USB or Trigger; sync type 1, 2, 4, 24 or 48 ppq.
- Factory Reset also shows the firmware version.

## MIDI CC list (printed in the Behringer PRO VS MINI Quick Start Guide)

Source tag for every row: "official: PRO VS MINI Quick Start Guide V 2.0, MIDI continuous controller table (PDF page 75 of the 82-page multilingual file)". Checked again on 2026-11-23 against that PDF: the CC numbers and ranges in the table below match it. Untested on hardware.

| CC | Parameter | Range as read |
| --- | --- | --- |
| 1 | Modulation | 0-127 |
| 24, 25, 26, 27 | Voice A, B, C, D wave | 0-127 |
| 28 | LFO 2 amount | 0-99 |
| 47 | Filter envelope amount | 0-127 |
| 54, 55 | LFO 1, LFO 2 waveform (triangle, square, saw) | 0-127 |
| 56 | LFO 1 destination (VCF, OSC) | 0-127 |
| 70 | LFO 1 amount | 0-99 |
| 71 | Filter resonance | 0-99 |
| 72, 73 | LFO 1, LFO 2 rate | 0-99 |
| 74 | Filter cutoff | 0-99 |
| 81, 82, 83, 84 | Amplitude envelope attack, decay, sustain, release | 0-99 |
| 85, 86, 87, 88 | Filter envelope attack, decay, sustain, release | 0-99 |
| 91, 92 | Chorus depth, rate | 0-99 |
| 111, 112, 113, 114 | Voice A, B, C, D fine tuning | 0-99 |
| 115, 116, 117, 118 | Voice A, B, C, D coarse tuning | 0-99 |

Known problems in the printed table: CC 118 is labelled "Voice C Coarse Tuning", the same as CC 117; it is probably Voice D, but that is a guess (UNVERIFIED). Value-to-waveform mapping for the wave CCs is not printed in what we read (UNVERIFIED).

Also official (Firmware 2.0.0 release notes): CC 5 = portamento, CC 9 = FX engine control (chorus, ensemble, reverb). The CC 9 value layout is not documented (UNVERIFIED).

## Not documented (as far as we found, checked 2026-11-15)

- No NRPN documentation was found for this device.
- No SysEx specification was found: the guide only names the menu items (Prog Bulk, Prog Single, Patt Bulk, Patt Single). The byte layout is unknown (UNVERIFIED, needs an owner capture).
- Program change behaviour and the exact USB MIDI port name are not documented in what we read.
- The Music Tribe CDN returned server errors for the Quick Start Guide and release notes; the guide was read from the same PDF served by Adorama. The Firmware 2.0.0 release notes (CC 5 and CC 9) were not re-read.

## Open items

1. Re-check the CC list and ranges against the original Behringer PDF; confirm on hardware (status per row: [MIDI-IMPLEMENTATION.md](MIDI-IMPLEMENTATION.md)).
2. SysEx program and pattern layouts.
3. Whether the updater needs SynthTribe on Windows only; a Linux route for firmware is a separate tool in our plan.
