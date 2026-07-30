# Guitar Synthesizer

A monophonic guitar synthesizer pedal built from scratch. Custom PCB (STM32H7), custom analog front end, pitch detection in firmware, and a digital synth engine driving an external DAC.

This repo is a work in progress. More detail, build logs, and eventually demo videos will go up as the project progresses.

## What the pedal does

Takes an electric guitar signal in, filters and biases it, and feeds it to an STM32H723VET6 microcontroller (MCU). The MCU detects pitch (in <20ms) and uses that to generate a synth note, which outputs through an external 32-bit DAC (PCM5101APWR). There are two footswitches, one used for true bypass, and another used for a sustain mode. A volume pot is also used alongside a 12-position rotary switch for selecting synth presets.

## Current status

- The Rev 2 PCB has been manufactured and hand-soldered.
- The analog front end has been tested with real guitar signal.
- I am currently finishing the PCB design for the next board revision (which includes protection diodes, PCB-mounted rotary switch/pot/input jack, daughterboards for the footswitches)
- Firmware and DSP work (pitch detection, synth engine) is yet to be completed. My Rev 2 test used an STM32H723ZG Nucleo board, which developed a hardware fault. I replaced this with a NUCLEO-G071RB board, which was only powerful enough to test my analog front end.

## Repo layout
```text
└── electronics/
    ├── schematics/       # Schematic PDFs for each subsystem
    ├── gerbers/          # Gerber exports for manufacturing the PCB
    ├── simulation/       # LTSpice simulations for the filtering, clamping and board power
    ├── bom/              # Bill of materials
    └── altium/           # Complete Altium project files
```
