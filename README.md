# Overview

The goal of this repository is to allow anyone to quickly migrate over from Visual Studio to VSCode, and take advantage of the debugger and IDE.

## Required Software

- VSCode : https://code.visualstudio.com
- Modules for VSCode:
-- C/C++ for VSCode https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools#review-details
-- Native Debug: https://marketplace.visualstudio.com/items?itemName=webfreak.debug#review-details
-- C/C++ Advanced Lint (clang) https://marketplace.visualstudio.com/items?itemName=jbenden.c-cpp-flylint&ssr=false
- cmake

## Building

- mkdir build && cd build && cmake ..
- To build a debug release: cmake -DCMAKE_BUILD_TYPE=Debug ..
- make (on windows, one would simply run cmake --build .. --config Debug --target ccpp-vscode )

## Debugging

- To build: ctrl-shift-b. Select build.
- To run: ctrl-shift-b. Select run (name of your exe)
- To setup debugging, you need to do a few more things. Edit your .vscode/launch.json (in the project). You can edit the various launch configurations here. This is confusing to me because a ton of launch configurations. I'm not an expert on this. However, the simplest thing to do is list your binary exe name in the right place. Obviously for Linux vs OS X or Win, you might need some different launch configurations.
- To debug: (1) click the Debug icon, (2) Select a run configuration, (3) and then click |> run. If you have set breakpoints, great. Otherwise, the program will run and possibly exit. Set some variables or expressions too.