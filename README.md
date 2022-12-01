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

The second goal is to faithfully reproduce the behavior of the "master" assembler (asm).  
This "master" assembler is also available in the "vm_champs" folder.  

The third goal is to create a new champion ("zkiller"), his only prerequisite is to beat the "Zork" champion.  
All available champions are located in the "vm_champs/champs" folder.

The last objective is to create a beautiful visualiser to display the memory in a (relatively) human-understandable way.  
Usually the visualiser is part of the virtual machine, but in our case it is external as it has been designed with Python.  

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

## Viewer
A unique visualisator "Corewar Visualizer" has been developed for this project.  
This program has the particularity to be created with the Python language.  

The following packages must be installed on your system before to use the visualisator:  
- python3
- pip3

If necessary, you can use the "Homebrew" package manager to install them.  
Homebrew was originally designed to simplify the installation process on MacOs (indeed, there is a majority of Mac at 42).  
The use of Homebrew is facultative as you can install "python" and "pip3" on your own way, depending of your OS.  
```
brew install python
brew install pip3
```

Then, use the python3 official package manager "pip3" to install the "pygame" module:
```
pip3 install pygame
```

You can now combine the "Corewar Vizualizer" with the "Corewar" program:

```
cd /src/visu
```
```
../../corewar ../../vm_champs/champs/examples/turtle.cor -x | python3 cor_visu.py -py3
```

**Tips:**  
- [ESC]	Quit
- [SPACE]	Play / Pause
- [<-]	Previous cycle / step
- [->]	Next cycle / step
- [+]	Speed up
- [-]	Speed down
- [H]	Hide / Show data
- [S]	Mute / Unmute

## MAN (complete user manual)
```
./asm -h
./corewar -h
```

## Screenshots
![Capture d’écran du 2022-12-01 17-41-39](https://user-images.githubusercontent.com/52746061/205109970-fad21801-880f-405a-a67e-75259f7205af.png)  
![visual](https://user-images.githubusercontent.com/52746061/205045905-dd153138-ada2-470f-abf4-13ff34325556.gif)  
![Capture5](https://user-images.githubusercontent.com/52746061/205120425-a5088635-602a-4dfe-b51b-d9c774d4055f.png)  
![Capture4](https://user-images.githubusercontent.com/52746061/205120218-e7c73211-4f85-488f-9746-23ebe0e7438a.png)  

## Notes
This is a group project made by 4 developers.

## Keywords
Compilation  
Simplistic virtual machine  
Simplistic assembly-like language  
Visual rendering  
