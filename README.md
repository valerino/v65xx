# v65xx
my MOS 6502/6510/65xxx emulator/interpreter!

## features
* clean code
    * since i myself am a newbie in writing emulators, i've explicitly choosen to prefer clean to performant code!
* cycle accurate
* built-in debugger
    * call _step()_ with _debugging=true_ (and possibly with _forceDebugging=true_ to interrupt while running, i.e. with an hotkey)
    * while in debugging mode use _'h'_ for help on commands
    * [debugger in action (during development of http://github.com/valerino/vc64-emu)](https://twitter.com/valerino/status/1090800442378985478?s=20)

## build
~~~
git clone https://github.com/valerino/v65xx
cd v65xx

# clone also the following repo
# (no submodules on purpose, they're evil and just add complexity, period.)
git clone https://github.com/valerino/emushared

# cd into emushared, follow build instructions in its README.md (including setting up environment variables)

# get back to v65xx folder and build
mkdir build && cd build
cmake ..
make

# setup environment variables to be used in external projects
export V65XX_INCLUDE_PATH=/path/to/v65xx
export V65XX_LIB_PATH=/path/to/v65xx/build
~~~

## sample usage
[my proof of concept c64 emulator](https://github.com/valerino/vc64-emu)

## STATUS
* emulates all documented and undocumented (to test) opcodes
* passes the [Klaus's functional tests](https://github.com/Klaus2m5/6502_65C02_functional_tests) from 6502.org (provided in this repo)!
  * call _reset(true)_ after constructing the cpu object to load the functional tests into the emulated memory.

## references
* http://archive.6502.org/datasheets/mos_6510_mpu.pdf
* http://archive.6502.org/datasheets/rockwell_r650x_r651x.pdf (rockwell 65xx, clearer version of the original above)
* http://www.atarihq.com/danb/files/64doc.txt
* http://www.oxyron.de/html/opcodes02.html
* https://www.masswerk.at/6502/6502_instruction_set.html
* https://wiki.nesdev.com/w/index.php/Status_flags
* http://www.6502.org/tutorials/decimal_mode.html
* http://www.6502.org/tutorials/6502opcodes.html
* http://obelisk.me.uk/6502/reference.html
* http://www.thealmightyguru.com/Games/Hacking/Wiki/index.php/6502_Opcodes
* http://www.ffd2.com/fridge/docs/6502-NMOS.extra.opcodes (_best source for undocumented instructions implementation!_)
