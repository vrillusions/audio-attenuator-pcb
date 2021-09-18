# Audio Attenuator PCB

[![Project Status: WIP – Initial development is in progress, but there has not yet been a stable, usable release suitable for the public.](https://www.repostatus.org/badges/latest/wip.svg)](https://www.repostatus.org/#wip)

## Overview

Primarily was interested in designing a custom PCB for the first time.  This is a pretty basic circuit that attenuates or reduces the volume.  Reason for a static value vs one of those inline volume control knobs is the cheap ones tend to introduce static in to audio when adjusting the dial.  Also stereo separation can sometimes start to offset where one side is louder than the other.

Since this is also a learning experience on PCB design instead of tags I'll be making new subfolders for each version.

## Requirements

### Building it

- `R1` and `R2` are the smaller of the two resistor values.  So far I've been using 42 ohm
- `R3` and `R4` are the larger of the two resistor values.  So far I've been using 420 ohm
- `J1` and `J2` are based off the audio jacks I found on amazon.  Take note that a few have same footprint but pins are arranged differently.  Should have one in middle towards front and 4 along back.  Only the two outer pins are used.

### PCB

- May make use of [DigiKey KiCad Library](https://github.com/Digi-Key/digikey-kicad-library)

## Usage

This is essentially a voltage divider circuit.  The effective reduction is based on the ratio of the two resistor values chosen along with the devices being used for the output and input.  In trial circuits this was 42ohm for `R1` and `R2` and 420ohm for `R3` and `R4`.  This should yield a 10:1 ratio reduction in power which corresponds to 20 db reduction in audio.  When testing with white noise output from computer and in to a tascam dr-07x receiver it showed about a 30 db reduction.  Which would be fine in my case where the tascam only records at mic level input and I need it to handle line level input from a DJ mixer which is commonly being driven to +10db or more.

## Changelog

### 1 - 2021-09-05

- Initial design