(re)Learning how to program an Amiga after a 20 year break
==========================================================
introduction
------------
This repo contains example programs I have written as I re-learn how to program an amiga.  The programs are written in assembler and directly access the hardware. The target is an Amiga 500 (my long lost friend). Currently I do not own an amiga, so I can only test using UAE, so it's possible they will not work on the real hardware.

Don't use this as an amiga programming guide. I don't do things the "correct" way. There are heaps of great guides out there if you want to do things the right way.

documentation
-------------
Most of the sites I have used during the learning process:
* [68000 instructions](http://68k.hax.com/)
* [vasm documentation](http://sun.hasenbraten.de/vasm/release/vasm.html)
* [vlink documentation (PDF)](http://sun.hasenbraten.de/vlink/release/vlink.pdf)
* [amiga registers](http://amigadev.elowar.com/read/ADCD_2.1/Hardware_Manual_guide/node0060.html)
* [amiga hardware reference manual](http://amigadev.elowar.com/read/ADCD_2.1/Hardware_Manual_guide/node0000.html)
* [amiga rkm devices manual](http://amigadev.elowar.com/read/ADCD_2.1/Devices_Manual_guide/node0000.html)
* [coppershade.org downloads](http://coppershade.org/articles/More!/Downloads/)
* [copper timing details](http://coppershade.org/articles/AMIGA/Agnus/Copper:_Exact_WAIT_Timing/)
* [coding forum](http://ada.untergrund.net/?p=boardforums&forum=4)
* [coding forum](http://eab.abime.net/forumdisplay.php?f=112)

cross development environment
-----------------------------

These examples are developed on a mac using [cahirwpz's](https://github.com/cahirwpz) AmigaOS cross compiler for Linux / MacOSX / Windows.

   https://github.com/cahirwpz/amigaos-cross-toolchain

The support tools I have developed have additional requirements which you may not have on your system.

For a dump of what I did to install them see [installing the cross development environment](doc/BuildingCrossDev.md)

building
--------

Build all examples by running ``make`` at the top level directory.

Each example will have an ADF file in it's ``bin`` directory.  These files can be loaded directly as DF0: on [FS-UAE](http://fs-uae.net/) or [Scripted Amiga Emulator](http://scriptedamigaemulator.net/) using the AROS ROM.

Individual examples can be built by entering the directory and running make:

  ```
# cd 001.simple_image
# make
```

tools
-----
The following cross development tools have been developed to support the examples:

* [imagecon](tools/imagecon)
* [makeadf](tools/makeadf)

Each tool has a test to check if any changes you have made have broken basic functionality:

  ```
# cd tools/imagecon
# make test
______  ___   _____ _____ ___________
| ___ \/ _ \ /  ___/  ___|  ___|  _  \
| |_/ / /_\ \\ `--.\ `--.| |__ | | | |
|  __/|  _  | `--. \`--. \  __|| | | |
| |   | | | |/\__/ /\__/ / |___| |/ /
\_|   \_| |_/\____/\____/\____/|___/
#
```

or test all by running  ``make test`` at the top level

license
-------
Some of the code I have included in this repository is copyright by various authors and provided under various licenses. Copyright notices are preseved where possible.

Some of the tools use GPL licensed libraries which would mean they could only be distributed under the conditions of the respective version of the GPL.

All code without a copyright notice is probably in the public domain.
