Fix area resources
~~~~~~~~~~~~~~~~~~

Version:  1.0
Author:   Argent77

Download: https://github.com/Argent77/A7-BiffedAreasFix/releases

Overview
~~~~~~~~

A troubleshooting mod for original BG2 games (SoA, ToB, BGT, or Tutu) that attempts to fix crashes
caused by new or modified areas that still reference unpatched game resources.

The error message for these types of crashes is:

ASSERTION FAILED!
File: ChDimm.cpp
Line: 7641

Exp: pBiffHeader->dwFileType != mmioFOURCC('B', 'I', 'F', 'C')


Components
~~~~~~~~~~

The mod offers several different options how to fix this issue.

1. Fix areas by placing only WAV files in the override folder (recommended)

This option should fix crashes in most cases. It will copy all sound files that are referenced by
areas into the override folder of the game.


2. Fix areas by placing all except TIS files in the override folder

As option 1, but will also place BMP, MOS and WED files that are associated with areas into the
override folder of the game. All of these files require little disk space.


3. Fix areas by placing all files in the override folder (requires lots of disk space)

As option 1 or 2, but will also place TIS files that are associated with areas into the override
folder of the game. Choose this option only if the first two options don't work, since it requires
much more disk space.


4. Fix areas by decompressing compressed BIFF files (requires lots of disk space)

Use this option only as a last resort. It destructively decompresses all compressed BIFF files of
the game which should fix crashes if the first three options don't work.

On a standard BG2 installation this option requires about 1 GB additional disk space, but may
require a total of 2 or 3 GB disk space during the decompression operation.

IMPORTANT: This option is not registered in the WeiDU.log and can therefore not be reverted!
           It is strongly recommended to make a backup of the game directory first.


Information for modders
~~~~~~~~~~~~~~~~~~~~~~~

The WeiDU script file "a7_area_references.tpa" in the lib folder of the mod can be used to help
detecting referenced in your own mod.

Simply include the script file in your own WeiDU script and call the action function "a7#get_are_resources"
to collect all resources referenced by your ARE files in an associative array. The resulting array
can then be used in subsequent operations.

More details about available parameters and return values can be found in the library file itself.
The main script of this mod shows several examples how this function can be used.


Credits
~~~~~~~

Coding and testing: Argent77


Changelog
~~~~~~~~~

1.0
- Initial release
