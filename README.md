# Audio Attenuator PCB

[![Project Status: WIP – Initial development is in progress, but there has not yet been a stable, usable release suitable for the public.](https://www.repostatus.org/badges/latest/wip.svg)](https://www.repostatus.org/#wip)

## Overview

Primarily was interested in designing a custom PCB for the first time.  This is a pretty basic circuit that attenuates or reduces the volume.  Reason for a static value vs one of those inline volume control knobs is the cheap ones tend to introduce static in to audio when adjusting the dial.  Also stereo separation can sometimes start to offset where one side is louder than the other.

This is primarily designed to handle the scenario where you have line level output and you need to feed it in to an input that takes mic level audio.  Using the given values will give a 10:1 reduction in power which corresponds to 20 db reduction in audio.  This is the least it will reduce the audio.  In reality the output impedance also plays a role.  For example if you have an output impedance of 1000 Ohm, that adds to the 1k Ohm resistor meaning it becomes 2k and 100.  Which gives you about a 30 db reduction in audio.  In the situation of a really hot line level audio needing to feed a mic input that still works fine.  If you're interested in learning more [this](https://diyaudioheaven.wordpress.com/tutorials/power-impedance-etc/) has a pretty good summary of what's all happening.

## Requirements

### Building it

- `R1` and `R2` are the larger of the two resistor values.  Recommend 1k ohm 1/4 watt 1% and then match them to find two as close together as possible
- `R3` and `R4` are the smaller of the two resistor values.  Recommend 100 ohm 1/4 watt 1% and then match them to find two as close together as possible
- `J1` and `J2` are based off the audio jacks I found on amazon.  Take note that a few have same footprint but pins are arranged differently.  Should have one in middle towards front and 4 along back.  Only the two outer pins are used.  Below are links to actual component used including the alternate 4 pin and 3 pin versions
    - [CUI SJ1-3525N](https://www.digikey.com/en/products/detail/cui-devices/SJ1-3525N/738687) - 5 pin version.  The extra pins are commonly used amps and such where if nothing is plugged in to jack then audio will pass through and come out via RCA jacks or something but then when you plug headphones in it will disconnect the path to RCA jacks and send audio to headphones.  Gives more flexibility to buy some extra to use in other circuits and only a couple cents more.
    - [CUI SJ1-3524N](https://www.digikey.com/en/products/detail/cui-devices/SJ1-3524N/738688) - 4 pin version
    - [CUI SJ1-3523N](https://www.digikey.com/en/products/detail/cui-devices/SJ1-3523N/738689) - 3 pin version.  Least expensive of the three and should work for most otehr circuits out there.

### PCB

- May make use of [DigiKey KiCad Library](https://github.com/Digi-Key/digikey-kicad-library)

## Usage

This is essentially a voltage divider circuit.  The effective reduction is based on the ratio of the two resistor values chosen along with the devices being used for the output and input.  In trial circuits this was 470ohm for `R1` and `R2` and 47ohm for `R3` and `R4`.  This should yield a 10:1 ratio reduction in power which corresponds to 20 db reduction in audio.  When testing with white noise output from computer and in to a tascam dr-07x receiver it showed about a 30 db reduction.  Which would be fine in my case where the tascam only records at mic level input and I need it to handle line level input from a DJ mixer which is commonly being driven to +10db or more.  I then swapped to 1k and 100 ohm resistors as they are far more common in packs of resistors.

## Changelog

### 2 - 2021-09-25

- re-arrange things to be more uniform
- shorten it slightly (Save $0.25! )
- widen the trace size
- makes use of a ground plane
- add some fancy labels
- label the resistors with actual values for most common scenario

### 1 - 2021-09-05

- Initial design