# Audio Attenuator PCB

[![Project Status: WIP – Initial development is in progress, but there has not yet been a stable, usable release suitable for the public.](https://www.repostatus.org/badges/latest/wip.svg)](https://www.repostatus.org/#wip)

## Overview

Primarily was interested in designing a custom PCB for the first time.  This is a pretty basic circuit that attenuates or reduces the volume.  Reason for a static value vs one of those inline volume control knobs is the cheap ones tend to introduce static in to audio when adjusting the dial.  Also stereo separation can sometimes start to offset where one side is louder than the other.

Since this is also a learning experience on PCB design instead of tags I'll be making new subfolders for each version.

## Usage

This is essentially a voltage divider circuit.  The effective reduction is based on the ratio of the two resistor values chosen along with the devices being used for the output and input.  In trial circuits this was 42ohm for `R1` and `R2` and 420ohm for `R3` and `R4`.  This should yield a 10:1 ratio reduction in power which corresponds to 20 db reduction in audio.  When testing with white noise output from computer and in to a tascam dr-07x receiver it showed about a 30 db reduction.  Which would be fine in my case where the tascam only records at mic level input and I need it to handle line level input from a DJ mixer which is commonly being driven to +10db or more.
