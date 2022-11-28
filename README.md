# 42_corewar
This project aims to create a virtual arena where 2-4 champions (programmable bots) fight to the death.  

This project is sub-divided in 3 parts:
- The champion, coded in a simplistic assembly-like language, allowing the use of various strategy.
- The Assembler, a program to compile the champions in Bytes, following a determined format that is required by the Arena.
- The Virtual Machine, the Arena that will handle the fight and display the status informations.

This is a group project with 4 developers (all from 42).

## Example

## Expected Result

## Install
Create or update the "lem-in" program from sources.
```
make
```

## Reinstall
Recompile completely the program.
```
make re
```

## Clean
Delete object files created during installation.
```
make clean
```

## Uninstall
Delete object files but also the compiled program.  
It will not affect the source code.
```
make fclean
```

## Usage
```
./lem-in < maps/valid/subject7
```
