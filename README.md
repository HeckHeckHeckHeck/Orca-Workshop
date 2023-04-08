# Orca-Workshop

Orca is an esoteric programming language and live editor designed to quickly create procedural sequencers.   
Orca is one of the inventions of Devine Lu Linvega of the small artist collective 'Hundred Rabbits'.

In this workshop we will:

1. Look at a few orca demos to get an impression
2. Get an orca setup running on your machine
3. Get a very quick language overview
4. Play through some tutorials together
5. Get hooked and get lost in the rabbithole of orca

Please find a collection of orca resources at the end of this document.

## Installation

### Orca

There are many implementations of Orca.   
The ones that work well for this workshop are:

* Easy setup: electron/js
* Advanced setup: ANSI-C implementation

#### Easy setup

The quickest way to get started on any platform is to just use the 'fancy' electron framework version. I recommend doing that for the workshop, to avoid the "install-party" effect.
Download and run the binary release. The source link is just for your reference.

* Binary release: https://hundredrabbits.itch.io/orca
* Source/Docs: https://github.com/hundredrabbits/Orca

#### Advanced Setup

My favourite setup though, is running the ANSI-C version in [Cool-Retro-Term](https://github.com/Swordfish90/cool-retro-term).  
Orca AND Cool-Retro-Term are available in many package managers, have a look in yours. Maybe you are lucky...   
Of course you can run this version of orca in any terminal.

* Source/Docs: https://github.com/hundredrabbits/Orca-c

### Pilot

Orca cant make any sounds on its own, it can only generate MIDI, OSC or UDP output.  
Pilot is a 'companion' program (from hundredrabbits as well) that is a fun little synthesizer and is very easy to use with orca over UDP.   
Download and run the binary release. The source link is just for your reference.

* Binary release: https://hundredrabbits.itch.io/pilot
* Source/Docs: https://github.com/hundredrabbits/Pilot

## Language Quick Overview

* Esoteric Programming Language
* 'Frame-Oriented' (execution model)
* 26 operators `A`-`Z`
* 1 datatype - Base36
* Uppercase operators execute on every frame
* Lowercase operators execute on a 'Bang'
* Data is just Base36 numbers '0-9' and 'a-z'
* I/O: no I just O. MIDI/OSC/UDP

# Tutorials

This is the Tutorial main function. Return here after every tutorial to decide what you wanna do next.   
Definitely, do the **Tutorial 1: First Bleeps**, first.

If you are reading this you must be have completed **Tutorial 1: First Bleeps**. Congratulations! You did so, right?

Your next options are:  
1.) You feel like the lazy beaver and just want to improve your bleepyness the easy way, and quickly sound
like you know what your doing?   
**Tutorial 2a: CakeTracker** is for you

2.) You feel more like the clever rabbit, you need the deep dive, and in the end you want to know more about orca than your
fellow workshop-mates that just bleep-away with their 2 operators?   
**Tutorial 2b: ScopeHero** is for you.

## Tutorial 1: First Bleeps

In this tutorial we will only learn 2 of the 26 operators, and we will already be making polymetric noise.   
Isn't that great?

Have a look into the directory `tutorials/1_first_bleeps/`.
There is an orca program for each chapter.

### 1. Bangs

The 'bang' is the trigger that activates lower-case operators.   
There is technically only one operator that directly generates a bang. Its the operator `D`.

* `D` - Delay, bang periodically (count / frame-modulo)

### 2. First Bleeps

Operators you learn in this chapter:

* `;` - Send UDP packet (- / data)

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

## Tutorial 2a: CakeTracker

### 1. Counter

In this chapter you learn 1 of 2 operators that can count.

* `C` - Count (rate / modulo)

### 2. Track

The track lets us store a list and access its elements.

* `T` - Track (index, length / list)

You guessed it, using a counter you can now iterate the elements of a list

### 3. Variables

In this chapter you learn all the operators related to variables:

* `V` - Variable, r/w single (Write: name / val | Read: - / name)
* `K` - Kontakt, read multiple (Read: count / names)

### 4. CakeTracker

**Putting it all together**
Using the values of our list (in track) as note-numbers, we are now the new-age melody heroes.   
Enjoy the eternal bleeps of the spotless beethoven.

## Tutorial 2b: Scopehero

This is a very empowering tutorial with its 13 operators covered.   
Have a look into the directory `tutorials/2_scopehero/`.   
There is an orca program for each chapter.

### 1. Arithmetic

In this chapter you learn (almost) all the operators to generate and manipulate numbers:

* `C` - Count (rate / modulo)
* `I` - Increment (increment / max)
* `R` - Random (min / max)
* `A` - Add (operand / operand)
* `B` - Subtract (operand / operand)
* `M` - Multiply (operand / operand)

### 2. Variables

In this chapter you learn all the operators related to variables:

* `V` - Variable, r/w single (Write: name / val | Read: - / name)
* `K` - Kontakt, read multiple (Read: count / names)

### 3. Writer

There are a number of operators to write data into the grid.
In this chapter we only look at one:

* `X` - Write (x, y / data )

### 4. Flying Operators

In this chapter you learn about all the _flying_ operators `\o/ \o/ \o/`:

* `E` - East
* `W` - West
* `N` - North
* `S` - South

### 5. Scope

**Putting it all together**

Yay, by now we have already learned 15 operators, more than half of them all.   
Now we can combine them to create a 'scope' to visualize and debug any variable values.

### 6. ScopeHero

**Putting it even togetherererer**

What is even more fun than 1 scope, is 3 scopes.  
Let generate 2 'signals', add them together to create a third signal, and use our scope technique to visualize whats going on.

## Resources

### Orca

#### General

* Maybe the most official home of Orca: https://100r.co/site/orca.html
* Docs/Examples: https://wiki.xxiivv.com/site/orca.html

#### ANSI-C version

* https://github.com/hundredrabbits/Orca-c

#### JS/Electron version

* Browser/online version: https://hundredrabbits.github.io/Orca/
* Binaries (js/electron): https://hundredrabbits.itch.io/orca
* Sources/Docs: https://github.com/hundredrabbits/Orca

### Pilot

* Source/Docs: https://github.com/hundredrabbits/pilot