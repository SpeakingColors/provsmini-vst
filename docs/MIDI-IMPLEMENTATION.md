# PRO VS Mini: MIDI implementation (work in progress)

Device: Behringer PRO VS MINI (4-voice hybrid vector synthesizer, 5 voices from firmware 2.0.0). Checked 2026-11-16.

Status of this page: the CC table below was compared on 2026-11-23 with the official Behringer "PRO VS MINI Quick Start Guide" V 2.0 (multilingual PDF, 82 pages, created 2024-06-13; the MIDI continuous controller table is on PDF page 75, printed pages 148 and 149). The copy used was the PDF served by Adorama's product-manual page, the same file Behringer ships. Every CC number and range in the table matches the guide. The guide itself prints "Voice C Coarse Tuning" for both CC 117 and CC 118, so CC 118 is unclear in the manufacturer's own text. CC 5 and CC 9 are not in this guide; they come from the Firmware 2.0.0 release notes. The guide lists no NRPN and no SysEx. Nothing here has been tested on hardware.

Status values: documented (manufacturer text, cited), untested (not tried on the owner's device), captured (owner's device; none yet).

## Channels and switches (menu items)

| Item | Detail | Source | Status |
|---|---|---|---|
| MIDI Tx channel | 1 to 16 or off | Quick Start Guide, MIDI menu (via DEVICE-NOTES.md) | documented, untested |
| MIDI Rx channel | 1 to 16 or off | same | documented, untested |
| MIDI Velocity | on/off | same | documented, untested |
| MIDI CC | on/off | same | documented, untested |
| Sync source / type | Internal, MIDI, USB, Trigger; 1, 2, 4, 24, 48 ppq | same | documented, untested |

## Control Change

Source of the first table: PRO VS MINI Quick Start Guide, MIDI CC table (page 75 of the 82-page Spanish copy on manualslib.mx, read as text extraction; the Behringer PDF itself could not be fetched). Ranges were matched to CC numbers by position, so re-check against the original PDF. The values below are as printed; nothing is tested on hardware.

| CC | Parameter | Range as read | Status |
|---|---|---|---|
| 1 | Modulation | 0-127 | documented (official Quick Start Guide V 2.0), untested |
| 24-27 | Voice A, B, C, D wave | 0-127 | documented (official Quick Start Guide V 2.0), untested |
| 28 | LFO 2 amount | 0-99 | documented (official Quick Start Guide V 2.0), untested |
| 47 | Filter envelope amount | 0-127 | documented (official Quick Start Guide V 2.0), untested |
| 54, 55 | LFO 1, LFO 2 waveform | 0-127 | documented (official Quick Start Guide V 2.0), untested |
| 56 | LFO 1 destination (VCF, OSC) | 0-127 | documented (official Quick Start Guide V 2.0), untested |
| 70 | LFO 1 amount | 0-99 | documented (official Quick Start Guide V 2.0), untested |
| 71 | Filter resonance | 0-99 | documented (official Quick Start Guide V 2.0), untested |
| 72, 73 | LFO 1, LFO 2 rate | 0-99 | documented (official Quick Start Guide V 2.0), untested |
| 74 | Filter cutoff | 0-99 | documented (official Quick Start Guide V 2.0), untested |
| 81-84 | Amp envelope A, D, S, R | 0-99 | documented (official Quick Start Guide V 2.0), untested |
| 85-88 | Filter envelope A, D, S, R | 0-99 | documented (official Quick Start Guide V 2.0), untested |
| 91, 92 | Chorus depth, rate | 0-99 | documented (official Quick Start Guide V 2.0), untested |
| 111-114 | Voice A-D fine tuning | 0-99 | documented (official Quick Start Guide V 2.0), untested |
| 115-117 | Voice A-C coarse tuning | 0-99 | documented (official Quick Start Guide V 2.0), untested |
| 118 | Printed as Voice C coarse (duplicate of 117); probably Voice D, guess | 0-99 | unverified, documented (official Quick Start Guide V 2.0), untested |
| 5 | Portamento | not documented | documented (Firmware 2.0.0 release notes), untested |
| 9 | FX engine (Chorus, Ensemble, Reverb) | value layout not documented | documented (Firmware 2.0.0 release notes), untested |

The value-to-waveform mapping for the wave and LFO waveform CCs is not printed in what was read; do not send values for those until it is confirmed.

## NRPN

No NRPN documentation was found. Treat the device as not using NRPN until a manual says otherwise.

## SysEx

The menu offers Prog Bulk, Prog Single, Patt Bulk and Patt Single sends over USB, and "SysEx Receive Listening" (Quick Start Guide). The byte layouts were not found. Do not implement SysEx until a layout is documented or captured from the owner's device.

## Next steps to close the gaps

1. Read the full PRO VS MINI user manual (Behringer / Music Tribe) MIDI chapter and copy the CC table here with page numbers.
2. Capture CC and SysEx output from the owner's device (date and file noted per row) to move rows to "captured".
3. Only then add a parameter table in code.

Sources named above: Behringer PRO VS MINI Quick Start Guide (V 2.0 per a search listing; the guide in our project files is the source for DEVICE-NOTES.md); Firmware 2.0.0 release notes (2024-12-08).
