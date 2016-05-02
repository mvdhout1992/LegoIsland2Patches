# LegoIsland2Patches

Just some patches I'm working on.

#No CD patch

Change:

.text:0040842C                 jnz     loc_408500

Into:

.text:0040842C                 jmp     loc_408476

And:

.text:00408478                 jz      loc_408500

Into:

.text:00408478                 NOP
.text:00408479                 NOP
.text:0040847A                 NOP
.text:0040847B                 NOP
.text:0040847C                 NOP

(that is, NOP out the jz instruction)

# Load Long Times fix patch?

Game suffers from extreme load times
