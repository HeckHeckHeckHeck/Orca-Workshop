# Orca-Workshop

## Installation

### Orca

There are many implementations of Orca.   
The ones that work for this workshop are:

* JS/electron: https://github.com/hundredrabbits/Orca
* ANSI-C: https://github.com/hundredrabbits/Orca-c

#### Easy setup

The quickest way to get started on any platform is to just use the 'fancy' electron framework version. I recommend doing that for the workshop, to avoid the "install-party" effect.

* Binary release: https://hundredrabbits.itch.io/orca

#### Advanced Setup

My favourite setup though, is running the ANSI-C version in [Cool-Retro-Term](https://github.com/Swordfish90/cool-retro-term)  
Orca AND Cool-Retro-Term are available in many package manager, have a look in yours. Maybe you are lucky...

### Pilot

Orca cant make any sounds, it can only generate MIDI, OSC or UDP output.
Pilot is a 'companion' program (from hundredrabbits as well) that is a fun little synthesizer and is very easy to use with orca over UDP.

* Github/Docs: https://github.com/hundredrabbits/Pilot
* Binary release: https://hundredrabbits.itch.io/pilot

## Language Quick Overview

* Esoteric Programming Language
* 'Frame-Oriented' language
* 26 operators `A`-`Z`
* Uppercase operators execute on every frame
* Lowercase operators execute on a 'Bang'
* Data is just Base36 numbers '0-9' and 'a-z'
* I/O: no I just O. MIDI/OSC/UDP


# Tutorials

## Tutorial: Bangs and Sounds

### 1. Bangs

Operators you learn in this chapter:

* 'D' - Delay, bang periodically
*


### 2. Sounds
Operators you learn in this chapter:
* `;` - UDP

for synthesizing the actual waves we are using 'Pilot', a soft-synth which we control with UDP packets.
So, the commands we send using the UDP output operator are actually Pilot commands, not orca.

Pilot commands are 3-5 'bytes' long, where the first 3 are required.   
The format is: `CH` `OCT` `NOTE` [`VOL`] [`DECAY`]

Where:
* `CH` - Channels 1-f exist, they all sound different (and they are monophonic)
* `OCT` - Around 8 octaves should definitely exist
* `NOTE` - Note names where Upper-case are white keys and Lower-case are Black-keys
* `VOL` - The Volume 0-z (even though the doc says 0-f, but hey we love clipping dont we?)
* `DECAY` - The 'length' of the note, 0-f (?)

Example:   
`;13C` - Pilot plays note 'C' of octave 3 (default volume and length)

### Putting It All Together


## Tutorial: Flying East Scope

### 1. Arithmetic

Operators you learn in this chapter:

* `C` - Count (speed / modulo)
* `I` - Increment (increment / max)
* `R` - Random (min / max)
* `A` - Add (operand/operand)
* `B` - Subtract (operand/operand)
* `M` - Multiply (operand/operand)

### 2. Variables

Operators you learn in this chapter:

* `V` - Variable r/w single (Write: name / val | Read: - / name)
* `K` - Kontakt read multiple (Read: count / names)

### 3. Flying East

Operators you learn in this chapter:

* `X` - Write
* `E` - East

### Putting It All Together



