# SEGame
Space game demo

As published in the International OS-9 Underground magazine:

Mapping in OS-9 WindInt GFX Screens - by Allen C. Huffman

We have always lacked high speed games under OS-9 due to the inability to directly access screen memory.  The original VDGint graphics driver (used
by many Tandy games) did allow this capability, but most users don't use VDGint due to lack of space in their bootfile preferring, instead, the GRFint
or Windint windowing drivers.  Unfortunately, these drivers do not provide you with any system calls to tell a programmer where the screen is located in
the system memory map.

Several clever programmers have come up with ways to do this.  Also, the NitrOS-9 patches (which optimize OS-9 to run faster if your computer has a
6309 chip installed) provide the much needed system call for this as well.

This article will attempt to cover both methods.  The stock OS-9 method, provided by Robert Gault, will return information for the CURRENTLY DISPLAYED
screen.  This means that the user MUST be looking at the graphics screen for it to work properly.  If a user attempts to run the program then flips to
another screen before it starts, the program will crash.  The NitrOS-9 method, on the other hand, provides information based on a path to the window,
whether it's currently displayed or not.

Some sample RMA assembly code is provided which shows how to map in a screen and manipulate it.  A small space game demonstration is provided for
your entertainment.  It is nothing fancy, but it does show some simple game programming techniques.
