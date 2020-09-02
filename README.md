
# Custom CPU Architecture

This project is neither finished nor stable.

This project holds material about a custom-built 8-bit CPU architecture with a 12-bit instruction set.
It is built for educational purposes only and doesn't hold any real value other than its simplicity and ease of implementation.

# Circuit
The circuit is built using Logisim. Any version based on the original software will do.
You will find the model under ```simulation/model.circ```

# Assembler
An assembly language and an assembler have been built to make this computer programmable.
The language is composed of 4 instructions :
- write: Writes an 8-bit value into the R3 register.
- move: Moves a value from one register to another.
- jump: Jumps to the provided ROM address (10-bit).
- if jump: If the if register is set to 1, jumps to the specified value, otherwise don't.

# Macros
In order to make writting program easier, a macro language has been implemented.
For the list of macro avaible, please take a look in macro.awk.
This list is subject to change.
There are currently macros for easier comparaison, addition and multiplication between registers.

# Installation
The transpiler and the macro engine are written in awk. Make sure to have it installed.
Note: some linux distribution in their stable branch ship with a non POSIX-compliant version of mawk. If you are concerned make sure to install gawk as an alternative.
For windows users you might want to consider this [port](http://gnuwin32.sourceforge.net/packages/gawk.htm).
If you use macros you will need to pass your source file throught macro.awk, then through transpiler.awk.
If you are on a UNIX-based OS you should consider using the ```assemble.sh``` script that will build your source under ```build/```.
Note that you will need to have xxd installed if you want a binary version to be generated.


To load a program, open the ```Program Counter``` sub-circuit, clear the ROM and load the ```.img``` file created by the transpiler into the ROM.
Go back to the main circuit, turn on and off the reset button and enable ticking or tick manually if you want to debug.

# Further work
Creating a higher-level language for easier programming.

# Bugs
When successively writting and moving, some registers tend to take arbitrary values related to previous instruction codes.

# Untested
The RAM has not been tested yet.
It might not load or output values correctly.
