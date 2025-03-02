![screenshot](https://github.com/fastrgv/SliderPuzzles/blob/main/hio.png)
![screenshot](https://github.com/fastrgv/SliderPuzzles/blob/main/rush.png)

### Download all source code, resources & binaries in the following 7-zip file:

https://github.com/fastrgv/SliderPuzzles/releases/download/v2.6.3/slpuz1jan25.7z


* On OSX, Keka works well for 7Z files. The command-line for Keka is:
	* /Applications/Keka.app/Contents/MacOS/Keka --cli 7z x (filename.7z)




#### Note to github downloaders: Please ignore the "Source code" zip & tar.gz files. (They are auto-generated by GitHub). Click on the large 7z file under releases to download all source & binaries (Windows & Linux). Type "7z x filename" to extract the archive. Then you can compile your own binaries, or use the pre-built ones provided.











# SliderPuzzles with Sound


## What's new:



**ver 2.6.4 --3mar2025**

* Updated & improved 3 solvers used within csok;


**ver 2.6.3 --01jan2025**

* Updated embedded solver hbox in csok.
* Added ">","<" keys to adjust csok-solver timeout (10-sec increments)

## More change-history at end of file



===============================================================
## Introduction

SliderPuzzles is a collection of retro puzzles with sound that runs in a commandline terminal on Windows, OSX, and most any Linux distro.

-----------------------------------------------------------
Featuring

	* live solvers promote learning with less frustration
	* no installation
	* no dependencies (Ncurses not needed)
	* simply unzip in your Downloads directory, or any other writeable directory, and run;
	* or unzip onto a USB flash drive [w/same file format] and run.
-----------------------------------------------------------

### Details

The 7zip command to extract the archive and maintain the directory structure is "7z x filename".

* Windows versions use runtime-priority control for arcade-level response.

Rebuildable using the free GNU Ada compiler.

Includes 12 puzzle games that use ascii characters only:  rush-hour, klotski, flat7, flatAZ, sokoban, hole-in-one, hole-in-one+4, nine, dirty-dozen, panama, annoying-sliders.

See the image "./puzzles.png" for a visual of some of the available puzzzles.

All puzzles can be called directly from the command line; e.g.

* bin\win\csok.exe	(sokoban from base dir)
* csok.exe				(sokoban from ~\bin\win\ dir)

but it is more convenient to use the selector app, thusly:

* winSlide.bat			(Win64)
* gnuSlide.sh			(linux)
* macSlide.sh			(OSX)

Use the keyboard arrow keys to highlight the desired game, then press the (enter)-key.

* Windows users note: Using linux executables under WSL [Windows Subsystem for Linux] is not supported. Instead, you should use the windows versions because extraordinary measures have been taken to achieve arcade-level response.

* Similarly, linux users cannot use wine to run Windows executables, with this particular App.

If an older Linux system complains that /dev/dsp/ cannot be opened, prepend the command with "padsp".

EG:  "padsp (ExeName)"




### For Maximal Enjoyment...
Keyboard setup can be very important for playability.  You should have a very short key-delay and fast repeat rate setting when running the arcade games. The normal settings are fine for puzzles.

Screen setup is important, too...

**Terminal size required:**

	* 60x25

It is recommended to resize your terminal window; then enlarge the font until the window just barely fits your computer screen.

===========================================================================

### Common KeyMappings

* (up),(lf),(dn),(rt): move north, west, south, east (see ~/docs/KeyboardMoves.txt) 
* (i),(j),(k),(l): move north, west, south, east
* (w),(a),(s),(d): move north, west, south, east
* (?): help
* (q): quit
* (=): AutoSolve; step-by-step
* (+): next puzzle
* (-): previous puzzle
* (r): reset



### TrafficRush (crush.adb)
Colored, non-graphical Traffic-Rush puzzle game designed to run in a terminal window.

Horizontal and vertical strings of letters represent cars and trucks in a crowded parking garage.  The objective is to move them around lengthwise in order to be able to get red car "a" to the exit, which is either at the right or top of the garage.  Note that the last digits in each puzzle name represents the minimum number of moves to win.

A stand alone autosolver, bfsr, is provided, but now, an autosolver is embedded into this game.  At any time you may press the (=)-key to begin stepping toward a solution.

I created about 20% of these rush-puzzles (filenames that end "my.rush"), including the most difficult one "zzzz_89my.rush".



### BlockSliders [cslid], DirtyDozen [cdd], AnnoyingSliders [cann]
Colored, non-graphical Block Slider puzzle games designed to run in a terminal window.
In these 3, an UpperCase letter helps distinguish a 1x1 block.

Colored blocks of letters can be moved horizontally or vertically wherever there is space.  Often, the objective is to move the red block to a specified goal position. Sometimes the goal is to swap the positions of two blocks.

A stand alone autosolver, bfsa, is provided, but now, a "live" autosolver is embedded into these games.  At any time you may press the (=)-key to begin stepping toward a solution.

In cann (AnnoyingSliders) you must type "0" to restart it, since "r" is reserved to mean "red"; also the ijkl movement keys are disabled since the letter "k" is used for the color black.

Extra key functions for these 3 blocksliders only:  

* (.) save current CFG
* (/) restore saved CFG


For those times when a solution seems impossible, the more difficult puzzle families have an AutoSolver function using the (=)-key to step closer towards the solution:  crush, cslid, cdd, and cann.  

### Advice to improve puzzle-solving skills:  
Remember that you can **stop** using the autosolvers at any time and try to manually solve the puzzle from a configuration that is a few steps closer to the solution. And because these solvers are "live", you can **resume** using the autosolvers at any time if you get stuck again. Each time you resume, you might need to wait a few seconds for the solver to complete its search.


### Gameplay: crush, cslid, cann (annoying-sliders)


First, one selects a vehicle or block by typing its identifier letter.  Then use the arrow keys to move it.  Note that **manual selection is, often times, not necessary,** as there is an auto-select mechanism for those times when only one selection may move in a given direction. For example, cpana never needs a selection (and, btw, it can be solved in 26 moves!).

Be aware that move counts for a given puzzle may differ according to how they are counted. Many puzzlers count a compound move with a single piece as one move. Here, no.

===============================================================
### flat7, flatAZ (c7.adb, caz.adb)

c7 (flat7) is a flat representation of a 3D 2x2x2 cube with one cubelet missing that allows sliding permutations.  There are two 2x2 layers. Here, the elements are labelled 1..7.

caz (flatAZ) is a flat representation of a 3x3x3 cube with one cubelet missing that allows sliding permutations.  Here, there are three 3x3 layers. The elements are labelled with the english alphabet.

Flat7 & FlatAZ, are my own creations. They are 2-dimensional versions of my 3D, OpenGL "Rufas Cube" puzzles, available at:  https://sourceforge.net/projects/rufascube/


Both the "caz" and "c7" puzzles work the same:

* note the original order, and blank location;
* mix;
* then restore.

A character in an adjacent row, column, or layer may be moved to the empty space using the keyboard.

The KEY MAPPINGS for these 2 puzzles:

* (1)..(5): mix;  higher values are more difficult.
* (up),(lf),(dn),(rt): move north, west, south, east
* (i),(j),(k),(l): move north, west, south, east
* (w),(a),(s),(d): move north, west, south, east
* (home),(end): move up one layer, down one layer
* (backslash),(slash): move up one layer, down one layer
* (-),(+): move up one layer, down one layer
* (?): help
* (q): quit
* (=): AutoSolve


#### AutoSolvers Note

One of the slowest is in caz(FlatAZ), which can take up to 10 seconds to find the solution to a level 5 shuffle. When it has finished, it will display the remaining steps as you continue to press the equal-key (=).

The c9 solver is also very slow. It can take over 15 seconds.



===============================================================

### sokoban (csok.adb)
There are now two character sets possible that are toggled with the (c)-key.

Move the pusher ( <> or @ ) with the arrow keys in order to push all the boxes ( [] or $ ) onto the goals ( :: or . ) in which case they look like ( {} or asterisk ).  Various other functions available on the help screen.  Includes a very large family of puzzle files.

Three [external] sokoban solvers named iplr3r, ibox3r, & hbox  are available.  The command line is "solver-name puzzle-file-name level-number-to-solve".  The solvers print solution-strings to the terminal screen.

Be aware that sokoban puzzles are very much more difficult to solve than all the others, so many are not solvable, even without a time limit.

There are many cases the first two solvers cannot handle, but they are pretty good at solving smaller puzzles, particularly the more dense ones. Hbox is the most capable.

Three time-limited-to-10-second solvers are embedded into csok.  At any time you may press the (=)-key to see if the solver #1 can help you.  If so, you will be prompted to keep pressing that same key to proceed toward a solution.  No prompt means either the present state is unsolvable, or merely that the embedded algorithm failed.  Similarly, the (.)-key initiates solver #2; and the (,)-key initiates solver #3. These can give you a headstart toward a correct solution by limited use of this feature.  Once you think you can solve it yourself, stop using the solver and proceed manually.  This really helps when you cannot see what your next move should be.

Note: all 3 solvers can fail if the puzzle is difficult or too large (256 or more valid puzzle positions).

The default **timeout** used by embedded solvers is adjustable using the (>)-key or (<)-key to increment or decrement by 10 seconds per press. This is the time to wait for the internal autosolvers before giving up. The default is 10 seconds.

Also, the default **method** used by embedded solver Hbox [ (.)-key ] can now be reset using a numeric (k)-key, where k is 0..5.

#### 10 method options [0..9] for hbox:

* 0 "quickest" using 6 heuristics+inertia
* 1 "move-efficient" +inertia
* 2 suppress hungarian estimator (for dense puzzles)
* 3 like 0 but single-step
* 4 like 0 but using only 5-heuristics

* 5 like 0 but using 1-heuristic (meth10)
* 6 like 1 but using 1-heuristic (meth11)
* 7 like 2 but using 1-heuristic (meth12)
* 8 like 3 but using 1-heuristic (meth13)
* 9 like 4 but using 1-heuristic (meth14)

For further details see:

* https://sourceforge.net/projects/hbox4/			(4 is not a typo)


solver-key summary:

* (.)		initiate hbox
* (,)		initiate ibox
* (=)		initiate iplr

* (>)		increment timeout by 10 sec
* (<)		decrement timeout by 10 sec

* (0..9)	set default solution method for Hbox




### HoleInOne/HoleInOne+4 (chio.adb/chio4.adb)
Move the red 2x2 'a' block into the center of the four L-shaped corner pieces.

### Nine (c9.adb)
Reverse the order of the numbered blocks with assorted shapes. First version begins with blocks in order. Second begins with blocks in reverse order. Has **very slow** solver.

===============================================================
## Setup & Running:

SliderPuzzles is a stand-alone application.
Ncurses is NOT needed; there are no prerequisites.

Mac/OSX users see "osx-setup.txt".

Windows users see "windows-setup.txt". Works on both Win10 & Win11.

Unzip the archive.  

* On Linux & Windows, 7z [www.7-zip.org] works well for this. The proper command to extract the archive and maintain the directory structure is "7z x filename".

* On OSX, Keka works well for 7Z files. The command-line for Keka is:
	* /Applications/Keka.app/Contents/MacOS/Keka --cli 7z x (filename.7z)


Open a commandline terminal, and cd to the game directory.

Your keyboard should have a short key-delay and fast repeat rate.

Minimize the size of your terminal window to 60x25...

Then enlarge the Font so that the window fills your monitor.

To launch the puzzle selector App, depending on your system, type:

* winSlide.bat (win64: win10+win11)
* macSlide.sh (OSX)
* gnuSlide.sh (linux)  [ ognuSlide.sh works on old linux versions ]

Note that any individual app may still be executed from the directory appropriate to your O.S.  For example, on Windows you can CD to bin\win\ and then type "csok" to run Sokoban.



===========================================================================
## Compiler Scripts
There are 3 sets of scripts included.  They differ in where the executables are put.  With many different precompiled binaries for each OS, there would be too much clutter if they were all put into the same place, particularly since windows needs colocated DLLs.

These build scripts work for GNU Ada [with its own g++].

The latest scripts have elliminated the need to use the "gnatcoll" library simply by compiling from source 3 additional tiny files, a small subset of gnatcoll, that are actually used.

==========================================================================
## Build Instructions:
Remember that prebuilt executables are already included. But, if you want or need to rebuild...


To get a recent Ada compiler;  eg. GNU-Ada...try this source:

https://github.com/alire-project/GNAT-FSF-builds/releases


Manually install GNU Ada.  

Next, edit the scripts wincmp.bat, lcmp.sh or ocmp.sh so that the path to gnatmake is correct.  These scripts streamline the build process by allowing auxilliary files to be neatly hidden in subdirectories.

Windows users please read gnuAdaOnWindows.txt.

* winbuildall.bat (Windows)
* obuildall.sh (OSX)
* lbuildall.sh (linux)

There are NO other 3rd party libraries or tools required to build.




---------------------------------------------------------------

## What is special about this project?...freedom...portability

* uses the Ada programming language and the freely-available GNU compiler.
* runs on PCs running Windows, OSX or Linux;
* uses only free open source software [F.O.S.S] tools & libraries;
* portable, transparent code, easy to modify, rebuild;
* uses a cross-platform implementation of OpenAL-Audio, adaptable by any Ada application that needs sounds & music-loops with a simple interface.
* pure minimalism:  no graphics, just colored ASCII characters, keyboard, & sound;
* Ncurses is <u>not</u> required.

I am short of testers, and would appreciate any feedback...
Open source Ada developers are welcome to help improve or extend this app.
Developer or not, send comments, suggestions or questions to:
fastrgv@gmail.com



## Some of my other puzzle apps.

* Two of these puzzles, Flat7 & FlatAZ, are my own creations. They are 2-dimensional versions of my 3D, OpenGL "Rufas Cube" puzzles, available at:  https://sourceforge.net/projects/rufascube/

* Many of these 2D slider puzzles are also available in OpenGL-graphical form at: https://sourceforge.net/projects/rufasslider/

* Also using OpenGL graphics, I have created some 3D slider puzzles that run on Windows, OSX, and Linux. It is available at: https://sourceforge.net/projects/reliquarium/


---------------------------------------------------------------


## License:

SliderPuzzles is covered by the GNU GPL v3 as indicated in the sources:

 Copyright (C) 2025  <fastrgv@gmail.com>

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

Nick Baxter, J.H.Conway, Jim Lewis, Bob Henderson, Gil Dogon, Ed Pegg Jr., J.I. Wiley, J.H. Fleming, C. L. Diamond, Sam Loyd, H. E. Dudeney, E. B. Escott, Nob Yoshigahara, James W. Stephens, & Neil Bickford for the classic sliders.


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


**ver 2.6.2 --16dec2024**
* All block sliders (cslid,cann,cdd) now capitalize letters that represent 1x1 blocks.
* Block sliders cdd, cann & cslid now permit saving/restoring puzzle state using "."/":" keys.
* Annoying-sliders cannot permit using the ijkl-keys for movement because the k-key is used to select a black colored block.
* Updated hbox4 to hbox5.
* Updated embedded hbox5 solver to csok.

**ver 2.6.1 --26feb2024**
* Updated [embedded+external] hbox4 with memory checks.
* Updated OpenAL sound code.
* Corrected display logic of annoying sliders goal-dots.
* Other code improvements.

**ver 2.6.0 --4jan2024**
* Fixed some errors; improved sokoban solvers, external and embedded (csok).
* Repaired csok single-file-mode [user given file+MxLev+Lev].

**ver 2.5.9 -- 6nov23**
* Improved/generalized OSX build scripts.
* Repaired TrafficRush [crush] autosolver problem.

**ver 2.5.8 -- 13oct23**
* Added warning if window is too small.

**ver 2.5.7 -- 06oct23**
* Restored OSX build for the command line (without a bundle) .

**ver 2.5.6 -- 24sep23**
* Improved TrafficRush (crush) with exit animation & sound.
* Added 5 more Annoying Sliders that are seriously difficult.

**ver 2.5.5 -- 07dec2022**
* Further improvements in autosolvers for c7 & caz.
* Improved sokoban (csok).

**ver 2.5.4 -- 15nov2022**
* Regrouped these slider puzzles together just for retro-puzzle fans.
* Greatly improved autosolvers for c7, caz.

**ver 2.5.3 -- 05nov2022**
* Created & enabled embedded "live" solvers for the annoying-sliders and panama apps.
* Improved robustness of all embedded solvers.
* Improved feedback messages in puzzles.
* Fixed a serious error in the sliding block puzzles that caused flickering on Windows.

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


