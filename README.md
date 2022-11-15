# Constant searcher

I got fed up with searching all around the internet for constants for windows reverse engineering, so I parsed the windows headers and put them all in a single file.

## How to use

Grep for whatever you want to search in defines.h

For more convenience, edit ./find-windows-definition with the path to this repository and add it to your path.

## How I compiled this

in C:\Windows\Program Files (x86)\Windows Kits\Include, execute the following:

    rg -o -I "^#define +[A-Z_]+ +0x\d+\s*" | sed -E 's/#define +//' > defines.h

This uses RipGrep to search for all definitions that map a macro to an integer.
