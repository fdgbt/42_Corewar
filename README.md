# 42_corewar
This project aims to create a virtual arena where 1 to 4 champions (programmable bots) fight to the death.  

It is sub-divided in 3 parts:
- The champion, coded in a simplistic assembly-like language, allowing the use of various strategy.
- The Assembler, a program to compile the champions in Bytes, following a determined format that is required by the Arena.
- The Virtual Machine, the Arena that will handle the fight and display the status informations.

This is a group project with 4 developers.

## Example

## Expected Result

## Install
Create or update the "corewar" and "asm" programs from sources.
```
make
```

## Reinstall
Recompile completely the both programs.
```
make re
```

## Clean
Delete object files created during installation.
```
make clean
```

## Uninstall
Delete object files but also the compiled programs.  
It will not affect the source code.
```
make fclean
```

## Usage

Firstly, use the assembler to compile the champions in ".cor" format:
```
./asm vm_champs/champs/examples/bee_gees.s vm_champs/champs/examples/bigzork.s vm_champs/champs/examples/helltrain.s vm_champs/champs/examples/turtle.s
```

Start the virtual machine (arena) without graphic mode:
```
./corewar vm_champs/champs/examples/bee_gees.cor vm_champs/champs/examples/bigzork.cor vm_champs/champs/examples/helltrain.cor vm_champs/champs/examples/turtle.cor
```

Start the virtual machine (arena) with internal graphic mode (debug):
```
./corewar vm_champs/champs/examples/bee_gees.cor vm_champs/champs/examples/bigzork.cor vm_champs/champs/examples/helltrain.cor vm_champs/champs/examples/turtle.cor -bc
```

Start the virtual machine (arena) with external graphic mode (Corewar Visualiser):
```
cd /src/visu
../../corewar ../../vm_champs/champs/examples/bee_gees.cor ../../vm_champs/champs/examples/bigzork.cor ../../vm_champs/champs/examples/helltrain.cor ../../vm_champs/champs/examples/turtle.cor -x | python3 cor_visu.py -py3
```
