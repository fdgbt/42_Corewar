# 42_corewar
This project aims to create a virtual machine (arena) where 1 to 4 champions (programmable bots) fight to the death.  

It is sub-divided in 4 parts:
- The champion, coded in a simplistic assembly-like language, allowing the use of several strategies.
- The Assembler, a program to compile the champions in Bytes, following a custom format that is required by the Virtual Machine.
- The Virtual Machine, also called the Arena, that will handle the fight and display the result.
- The Visualiser, displaying the battlefield: the state of the RAM memory.

## Example

Initially, Core War is a 1984 programming game created by D. G. Jones and A. K. Dewdney in which two or more battle programs (called "warriors") compete for control of a virtual computer.  
More information: https://en.wikipedia.org/wiki/Core_War

- 42 Event: Corewar Championship 2018 https://www.youtube.com/watch?v=R-OkYyzp-DI
- 42 Event: Corewar Championship 2017 https://www.youtube.com/watch?v=A8DPfQL3uO0

## Expected Result
The main goal of this project is to faithfully reproduce the behavior of the "master" virtual machine (corewar).  
This "master" virtual machine is available in the "vm_champs" folder.  

The second goal of this project is to faithfully reproduce the behavior of the "master" assembler (asm).  
This "master" assembler is also available in the "vm_champs" folder.  

The third goal is to create a new champion ("zkiller"), his only prerequisite is to beat the "Zork" champion.  
All available champions are located in the "vm_champs/champs" folder.

The last objective is to create a beautiful visualiser to display the fights in a (relatively) human-understandable way.  
Usually the visualiser is part of the virtual machine, but in our case it is external as it has been designed with "Python".  

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
```
```
../../corewar ../../vm_champs/champs/examples/bee_gees.cor ../../vm_champs/champs/examples/bigzork.cor ../../vm_champs/champs/examples/helltrain.cor ../../vm_champs/champs/examples/turtle.cor -x | python3 cor_visu.py -py3
```

## MAN (complete user manual)
```
./asm -h
./corewar -h
```

## Screenshots
![visual](https://user-images.githubusercontent.com/52746061/205045905-dd153138-ada2-470f-abf4-13ff34325556.gif)

## Notes
This is a group project with 4 developers.

## Keywords
Compilation  
Simplistic virtual machine  
Simplistic assembly-like language  
Visual rendering  
