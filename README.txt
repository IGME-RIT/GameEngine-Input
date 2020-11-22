Documentation Author: Niko Procopi 2020

This tutorial was designed for Visual Studio 2019
If the solution does not compile, retarget the solution
to a different version of the Windows SDK. If you do not
have any version of the Windows SDK, it can be installed
from the Visual Studio Installer Tool

AtlasEngine - Input
Prerequisites
	Intro C tutorials, Basic OpenGL tutorials, and 
	physics tutorials are required before starting
	the engine series
	
input.cpp handles if keyboard buttons are 
tapped, held, or released.

globals.h now had a global Keyboard struct

main.cpp tests Tap, Hold, and Release 

Each state (tap, hold, release) is an array of 16 ints
this saves memory by storing each key as a bit, rather 
than 512 bytes per state (one byte per key)

By storing keys as bits, we save memory, and loop through
ProcessState less, but then we need bit shifting for gameplay
to check each key

[ Hypothetically ]
By storing keys as bytes, more memory is used, more processing
is used to "ProcessState", but then less processing is used
in gameplay scripts to determine button presses

In other words, it's a trade-off.