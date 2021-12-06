---
title: "Enigma"
draft: false
categories:
    - Documentation
tags:
    - "Enigma"
    - Manual Pages
---

**Created by:** Brandon Ingli

## `$enigma`
`$enigma [message] [r1] [r1o] [r2] [r2o] [r3] [r3o] [ref]`

Encode or decode a message using Spike's enigma machine.

Parameter|Details|Default
---|---|---
message | String to encode/decode | (Required; no default)
r1 | Name of rotor to use in rightmost position | `I`
r1o | Starting offset for rightmost rotor, 0<=x<=25 | `0`
r2 | Name of rotor to use in center position | `II`
r2o | Starting offset for center rotor, 0<=x<=25 | `0`
r3 | Name of rotor to use in leftmost position | `III`
r3o | Starting offset for leftmost rotor, 0<=x<=25 | `0`
ref | Name of reflector to use | `B`

Rotor Names: `I`, `II`, `III`, `IV`, `V`  
Reflector Names: `A`, `B`, `C`

Note: This enigma may have the rotors in reverse order when compared to other enigma machines, including the Enigma I it emulates.

## The History

The *Enigma Machine* was a device used by the German military in World War II to encode messages. This enigma machine emulates an Enigma I without a plugboard.

Messages are encoded by being sent as electrical signals through a series of rotors. There were 5 of these available, and could be installed into one of three slots in the machine. Each rotor could be in any of 26 positions at a given time. Inside, the rotors are wired to match one input with one output on the other end. When a key is pressed, the electrical signal representing that letter travels through the rotors, is reflected at the end, and sent back through the rotors to light a corresponding light. The reflector ensures that a letter never encodes to itself.

What makes the cipher tricky is that fact that these rotors rotate. The rightmost rotor rotates once every time you press a key. Once that rotates fully, the middle rotor rotates once as well. When the middle rotor has completed a full rotation, the leftmost rotor also rotates.

For more information, please see the [Wikipedia Entry](https://en.wikipedia.org/wiki/Enigma_machine) for the Enigma machine.