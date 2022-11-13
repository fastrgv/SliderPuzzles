
# SliderPuzzles with Sound


## What's new:

**ver 2.5.4 -- 15nov2022**

* Regrouped these slider puzzles together just for retro-puzzle fans.


**ver 2.5.3 -- 05nov2022**
* Created & enabled embedded "live" solvers for the annoying-sliders and panama apps.
* Improved robustness of all embedded solvers.
* Improved feedback messages in puzzles.
* Fixed a serious error in the sliding block puzzles that caused flickering on Windows.


===============================================================
## Introduction

SliderPuzzles is a collection of retro puzzles with sound that run in a commandline terminal on Windows, OS-X and most Linux distros.

-----------------------------------------------------------
Featuring

	* no installation
	* no dependencies (Ncurses not needed)
	* simply unzip in your Downloads directory, or any other writeable directory, and run;
	* or unzip onto a USB flash drive [w/same file format] and run.
-----------------------------------------------------------

### Details

The 7zip command to extract the archive and maintain the directory structure is "7z x filename".

* Windows versions use runtime-priority control for arcade-level response.

Rebuildable using the free GNU Ada compiler, even on OSX.

Includes 12 puzzle games that use ascii characters only:  rush-hour, klotski, flat7, flatAZ, sokoban, hole-in-one, hole-in-one+4, nine, dirty-dozen, panama, annoying-sliders.

See the image "./puzzles.png" for a visual of some of the available puzzzles.

* Two of these puzzles, Flat7 & FlatAZ, are my own creations. They are 2-dimensional versions of my 3D, OpenGL "Rufas Cube" puzzles, available at:  https://sourceforge.net/projects/rufascube/

Usable keys for all:

* arrow-keys for movement; (see ~/docs/KeyboardMoves.txt)
* in some games you can also use wasd, ijkl for moves.
* (q)=quit
* (?)=help toggle

All puzzles can be called directly from the command line; e.g.

* bin\win\csok.exe	(sokoban from base dir)
* csok.exe				(sokoban from ~\bin\win\ dir)

but it is more convenient to use the selector app, thusly:

* winSlide.bat			(Win64)
* macSlide.sh			(Mac/OSX)
* gnuSlide.sh			(linux)

Use the keyboard arrow keys to highlight the desired game, then press the (enter)-key.

* Windows users note: Using linux executables under WSL [Windows Subsystem for Linux] is not supported. Instead, you should use the windows versions because extraordinary measures have been taken to achieve arcade-level response.

* Similarly, linux users cannot use wine to run Windows executables, with this particular App.

* Many of these 2D slider puzzles are also available in OpenGL-graphical form at: https://sourceforge.net/projects/rufasslider/

* Also using OpenGL graphics, I have created some 3D slider puzzles that run on Windows, OS-X, and Linux. It is available at: https://sourceforge.net/projects/reliquarium/


### For Maximal Enjoyment...
Keyboard setup can be very important for playability.  You should have a very short key-delay and fast repeat rate setting when running the arcade games. The normal settings are fine for puzzles.

Screen setup is important, too. Terminal sizes required:

	* 60x25

It is recommended to resize your terminal window, per the above table; then enlarge the font until the window just barely fits your computer screen.

===========================================================================



### TrafficRush (crush.adb)
Colored, non-graphical Traffic-Rush puzzle game designed to run in a terminal window.

Horizontal and vertical strings of letters represent cars and trucks in a crowded parking garage.  The objective is to move them around lengthwise in order to be able to get red car "a" to the exit, which is either at the right or top of the garage.  Note that the last digits in each puzzle name represents the minimum number of moves to win.

A stand alone autosolver, bfsr, is provided, but now, an autosolver is embedded into this game.  At any time you may press the (=)-key to begin stepping toward a solution.

I created about 20% of these rush-puzzles (filenames that end "my.rush"), including the most difficult one "zzzz_89my.rush".



### BlockSliders, DirtyDozen, AnnoyingSliders
Colored, non-graphical Block Slider puzzle games designed to run in a terminal window.

Colored blocks of letters can be moved horizontally or vertically wherever there is space.  Often, the objective is to move the red block to a specified goal position. Sometimes the goal is to swap the positions of two blocks.

A stand alone autosolver, bfsa, is provided, but now, a "live" autosolver is embedded into these games.  At any time you may press the (=)-key to begin stepping toward a solution.

In cann you must type "0" to restart it, since "r" is reserved to mean "red".

For those times when a solution seems impossible, the more difficult puzzle families have an AutoSolver function using the (=)-key to step closer towards the solution:  crush, cslid, cdd, and cann.  

### Advice to improve puzzle-solving skills:  
Remember that you can **stop** using the autosolvers at any time and try to manually solve the puzzle from a configuration that is a few steps closer to the solution. And because these solvers are "live", you can **resume** using the autosolvers at any time if you get stuck again. Each time you resume, you might need to wait a few seconds for the solver to complete its search.


### Gameplay: crush, cslid, cann (annoying-sliders)

"?" toggles the help screen.  The "+" and "-" keys (next, previous) are used to cycle through the large number of predefined puzzles.  You can reset a puzzle by typing "r". You can autosolve by typing "=". 

First, one selects a vehicle or block by typing its identifier letter.  Then use the arrow keys to move it.  Note that **manual selection is, often times, not necessary,** as there is an auto-select mechanism for those times when only one selection may move in a given direction. For example, cpana never needs a selection (and, btw, it can be solved in 26 moves!).

Be aware that move counts for a given puzzle may differ according to how they are counted. Many puzzzlers count a compound move with a single piece as one move. Here, it is not.

===============================================================
### Seven, A2Z (c7.adb, caz.adb)

c7 (flat7) is a flat representation of a 3D 2x2x2 cube with one cubelet missing that allows sliding permutations.  There are two 2x2 layers. Here, the elements are labelled 1..7.

caz (flatAZ) is a flat representation of a 3x3x3 cube with one cubelet missing that allows sliding permutations.  Here, there are three 3x3 layers. The elements are labelled with the english alphabet.

Flat7 & FlatAZ, are my own creations. They are 2-dimensional versions of my 3D, OpenGL "Rufas Cube" puzzles, available at:  https://sourceforge.net/projects/rufascube/


Both the "caz" and "c7" puzzles work the same:

* note the original order, and blank location;
* mix;
* then restore.

A character in an adjacent row, column, or layer may be moved to the empty space using the keyboard.

Pressing the (home) key on a typical keyboard produces the character 'H'.  So assuming that (home)=>'H', (end)=>'F', (up)=>'A', etc...
the KEY MAPPING follows:

* (1)..(5): mix;  higher values are more difficult.
* (up),(lf),(dn),(rt): move north, west, south, east
* (i),(j),(k),(l): move north, west, south, east
* (w),(a),(s),(d): move north, west, south, east
* (home),(end): move up one layer, down one layer
* (\\),(/): [backslash=]move up one layer, [forwardslash=]down one layer
* (-),(+): move up one layer, down one layer
* (?): help
* (q): quit



===============================================================

### sokoban (csok.adb)
There are now two character sets possible that are toggled with the (c)-key.

Move the pusher ( <> or @ ) with the arrow keys in order to push all the boxes ( [] or $ ) onto the goals ( :: or . ) in which case they look like ( {} or asterisk ).  Various other functions available on the help screen.  Includes a very large family of puzzle files.

Three [external] sokoban solvers named iplr3r, ibox3r, & hbox4  are available.  The command line is "solver-name puzzle-file-name level-number-to-solve".  The solvers print solution-strings to the terminal screen.

There are many cases the first two solvers cannot handle, but they are pretty good at solving smaller puzzles, particularly the more dense ones. Hbox4 is the most capable.

Three time-limited-to-10-second solvers are embedded into csok.  At any time you may press the (=)-key to see if the solver #1 can help you.  If so, you will be prompted to keep pressing that same key to proceed toward a solution.  No prompt means either the present state is unsolvable, or merely that the embedded algorithm failed.  Similarly, the (.)-key initiates solver #2; and the (,)-key initiates solver #3. These can give you a headstart toward a correct solution by limited use of this feature.  Once you think you can solve it yourself, stop using the solver and proceed manually.  This really helps when you cannot see what your next move should be.


### HoleInOne (chio.adb, chio4.adb)
Move the red 2x2 'a' block into the center of the four L-shaped corner pieces.

### Nine (c9.adb)
Reverse the order of the numbered blocks with assorted shapes. First version begins with blocks in order. Second begins with blocks in reverse order. Has solver.

===============================================================
## Setup & Running:

SliderPuzzles is a stand-alone application.
Ncurses is NOT needed; there are no prerequisites.

Mac users see "osx-setup.txt".
Windows users see "windows-setup.txt".

Unzip the archive.  On Windows, 7z [www.7-zip.org] works well for this.
The proper command to extract the archive and maintain the directory structure is "7z x filename".

Open a commandline terminal, and cd to the game directory.

Your keyboard should have a short key-delay and fast repeat rate.

Minimize the size of your terminal window to 60x25...

Then enlarge the Font so that the window fills your monitor.

To launch the puzzle selector App, depending on your system, type:

* winSlide.bat (win64)
* macSlide.sh (OSX)
* gnuSlide.sh (linux)

Note that any individual app may still be executed from the directory appropriate to your O.S.  For example, on Windows you can CD to bin\win\ and then type "csok" to run Sokoban.



### OSX caveat
The prebuilt OSX executables require version 10.13 (sep2017) or newer.

===========================================================================
## Compiler Scripts
There are 3 scripts, winbuildall.bat for Windows, lbuildall.sh for Linux, and obuildall.sh for OS-X.  They differ in where the executables are put.  With so many different precompiled binaries for each OS, there would be too much clutter if they were all put into the same place, particularly since windows needs colocated DLLs.

These build scripts work for GNU Ada [with its own g++].
See ./alternateBuildScripts/ for more examples.

The latest scripts have elliminated the need to use the "gnatcoll" library simply by compiling from source 3 additional tiny files, a small subset of gnatcoll, that are actually used.

Final note:  the latest OSX script does not use Xcode, only GNU Ada & GNU g++.

==========================================================================
## Build Instructions:
Remember that prebuilt executables are already included. But, if you want or need to rebuild...


To get a recent Ada compiler;  eg. GNU-Ada...try this source:

https://github.com/alire-project/GNAT-FSF-builds/releases


Manually install GNU Ada.  If you don't like my key-mappings, edit the code as you like.

Next, edit the scripts wincmp.bat, lcmp.sh or ocmp.sh so that the path to gnatmake is correct.  These scripts streamline the build process by allowing auxilliary files to be neatly hidden in subdirectories.

Windows users please read gnuAdaOnWindows.txt.

Then type "[win/l/o]buildall" to create new command-line executables for your system. ( win for Windows, l for Linux, o for OSX). 

There are NO other 3rd party libraries or tools required to build.




---------------------------------------------------------------

## What is special about this project?...freedom...portability

* uses the Ada programming language and the freely-available GNU compiler.
* runs on Macs running OSX, or PCs running Windows or Linux;
* uses only free open source software [F.O.S.S] tools & libraries;
* portable, transparent code, easy to modify, rebuild;
* uses a cross-platform implementation of OpenAL-Audio, adaptable by any Ada application that needs sounds & music-loops with a simple interface.
* pure minimalism:  no graphics, just colored ASCII characters, keyboard, & sound;
* Ncurses is <u>not</u> required.

Open source Ada developers are welcome to help improve or extend this app.
Developer or not, send comments, suggestions or questions to:
fastrgv@gmail.com


---------------------------------------------------------------


## License:

SliderPuzzles is covered by the GNU GPL v3 as indicated in the sources:

 Copyright (C) 2022  <fastrgv@gmail.com>

 This program is free software: you can redistribute it and/or modify
 it under the terms of the GNU General Public License as published by
 the Free Software Foundation, either version 3 of the License, or
 (at your option) any later version.

 This program is distributed in the hope that it will be useful,
 but WITHOUT ANY WARRANTY; without even the implied warranty of
 MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
 GNU General Public License for more details.

 You may read the full text of the GNU General Public License
 at <http://www.gnu.org/licenses/>.


----------------------------------------------
## Other Credits and Thanks:
Serhiy Grabarchuk and Peter Grabarchuk for their "Hole in One", "Hole in One plus 4", and "Nine" puzzles.

Nick Baxter, J.H.Conway, Jim Lewis, Bob Henderson, Gil Dogon, Ed Pegg Jr., J.I. Wiley, J.H. Fleming, C. L. Diamond, Sam Loyd, H. E. Dudeney, E. B. Escott, Nob Yoshigahara, James W. Stephens for the classic sliders.


----------------------------------------------
### SoundFiles (wav)
Fanfare/Applause and UFO sounds are from freesound.org and are covered by the Creative Commons CC0 Public License documented in the accompanying file ./docs/creativeCommonsCC0.txt. A few have a CC-by-3.0 license and are accompanied by a text file with the attribution.

The remaining sounds are public domain.
See also: ./sounds/licenses-sound-data.txt.

It is my intention to use media with copyrights or licenses that are compatible with GPLv3. Please notify me if you believe there is an incompatibility, and it will be removed; eg a CC-by-NC license is NOT GPL compatible.




----------------------------------------------
## Download Sites for all my games:
* https://github.com/fastrgv?tab=repositories
* https://www.indiedb.com/members/fastrgv/games
* https://fastrgv.itch.io
* https://sourceforge.net/u/fastrgv/profile/
* https://gamejolt.com/@fastrgv/games


## Video BlockSlider Autosolve:
* https://youtu.be/dD3VGbXv3ng


--------------------------------------------------
## Some Earlier Revision History:

**ver 2.5.2 -- 22oct2022**
* Added 16 annoying block sliders that are small, yet quite challenging.
* Improved traffic-rush by presenting puzzles in order, from easy to hard;
* Similarly improved Klotski-sliders by sorting puzzles from easy to hard; also added Quzzle, Quzzle-Killer puzzles near the difficult end of the scale.
* Improved documentation.

**ver 2.5.1 -- 26sep2022**
* Simplified Win64 build; using new stand-alone GNU Ada compiler.
* Removed Win32 build because embedded sokoban solvers need maximal memory.
* Removed all gnatcoll libraries by compiling from source the tiny subset needed.

**ver 2.5.0 -- 20sep2022**
* Restored Win64 build, now using MSYS2 & mingw64 on Windows.
* Still deliver Win32 build, also.

**ver 2.4.1 -- 16sep22**
* Removed Win64 build.
* Now using GNU Ada rather than defunct AdaCore compiler.

**ver 2.4.0 -- 23dec21**
* Updated gnatcoll libraries on OSX & w32; removed unused libgpr.a.
* All "assets", including datafiles & soundfiles, now have licenses compatible with the GPLv3 license.

**ver 2.3.9 -- 05nov21**
* Added example script to build using Gnu/Gnat.
* Refined libraries and build scripts.
* Replaced libgnatcoll.a with one from GitHub.

**ver 2.3.8 -- 21oct21**
* Besides Win64, there is now a Win32 build, to support older platforms.
* Improved adaOpenAL binding code.

**ver 2.3.7 -- 18oct21**
* Eliminated anomalous clutter in nexus selection app;


