# PRO VS Mini: device notes

Sources: Behringer PRO VS MINI Quick Start Guide (project files) and Firmware 2.0.0 release notes (2024-12-08). A "35 parameter CC list from midi.guide" was mentioned in earlier notes but is not in our files, so it is not reproduced here.

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

## Open items

1. Full CC list and values (midi.guide or Behringer chart).
2. SysEx program and pattern layouts.
3. Whether the updater needs SynthTribe on Windows only; a Linux route for firmware is a separate tool in our plan.
