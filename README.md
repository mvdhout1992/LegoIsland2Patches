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

# No intro vids

NOP out calls to 0x0081C693 at addresses:

0x00402AEA  
0x00402B20  
0x00402B56  

# Long load time fix patch

Game suffers from extreme load times

Running in windowed mode decrases load times by ~5x.  In full screen mode the loading pizza animation is smooth, in windowed mode it's very laggy. Might be related?

To fix long load times change:

.text:0042A870                 call    ds:GetTickCount

into:

.text:0042A870                 retn

# /force command line arg

Maybe decreases load time?

# Windowed mode

Change:

004029AC     C685 74FEFFFF >MOV BYTE PTR SS:[EBP-18C],0

Into:

004029AC     C685 74FEFFFF >MOV BYTE PTR SS:[EBP-18C],1

# Debug level select menu

To change 'game credits' menu into Debug level select menu..

Change:

.data:00972704                 db    4

and

.data:00972708                 db    2

Into:

.data:00972704                 db    1

and

.data:00972708                 db    11

To change the text 'Game Credits' into 'Debug' on the menu name change:

009726C4  21 43 52 45 44 49 54 53

To

009726C4  44 65 62 75 67 00 00 00

# Debug info window

When windowed mode is enabled a debug menu can be enabled by pressing F9
