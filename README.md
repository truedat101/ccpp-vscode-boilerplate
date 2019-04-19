# Overview

The goal of this repository is to allow anyone to quickly migrate over from Visual Studio to VSCode, and take advantage of the debugger and IDE.

## Required Software

- VSCode : https://code.visualstudio.com
- Modules for VSCode
- C/C++ for VSCode https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools#review-details
- Native Debug: https://marketplace.visualstudio.com/items?itemName=webfreak.debug#review-details
- C/C++ Advanced Lint (clang) https://marketplace.visualstudio.com/items?itemName=jbenden.c-cpp-flylint&ssr=false
- cmake

## Building

- mkdir build && cd build && cmake ..
- To build a debug release: cmake -DCMAKE_BUILD_TYPE=Debug ..
- make (on windows, one would simply run cmake --build .. --config Debug --target ccpp-vscode )

## One Time Setup

To setup debugging, you need to do a few more things. Edit your .vscode/launch.json (in the project). You can edit the various launch configurations here. This is confusing to me because a ton of launch configurations. I'm not an expert on this. However, the simplest thing to do is list your binary exe name in the right place. Obviously for Linux vs OS X or Win, you might need some different launch configurations.
- To debug: (1) click the Debug icon, (2) Select a run configuration, (3) and then click |> run. If you have set breakpoints, great. Otherwise, the program will run and possibly exit. Set some variables or expressions too.

In order to use the Debugger, you will need to add one or more launch configurations per project.  This involves (1) switching to the debugger view.  

![Image of a the debugger view button](https://user-images.githubusercontent.com/64202/56433897-5fddf700-6287-11e9-9d2d-720bba18c92a.png)

Once in the debugger view, you need to add a launch configuration.  To do so, (2) click on the launch config drop down and select "Add Configuration".
![Image of a the debugger configurations](https://user-images.githubusercontent.com/64202/56433917-6d937c80-6287-11e9-8ec4-df5933f6b3fd.png)

Adding a debug configuration (3) selecxting a new configuration.  The recommendation is to use the C/C++ launch (gdb) configuration.  Click on the launch or attach configuration.  You must fill in your program to launch.  And you should specify args[] as comma seperated strings ["-x", "-y", "-Dtrue"] (for example).

![Image of choosing a configuration](https://user-images.githubusercontent.com/64202/56433930-7a17d500-6287-11e9-9f60-711fe152e433.png)

Click save.  You have a good configuration hopefully.  If at first you have trouble, you can always go back to this json file to edit your config.  NOTE: You can have multiple launch configurations.  For example, you may use diferent arguments, or you may have a different approach for launching, or you might use different binaries.

## Debugging

![Image of choosing a configuration](https://user-images.githubusercontent.com/64202/56433922-7421f400-6287-11e9-8f3e-e8d995b58245.png)

- select the gdb launch configuration next to the green Run button on the top task bar
- Click on the green Run button in the debug view.  
- You should now be able to step through your program using the traditional debugger step into/step over/step back/continue/stop commands.
- Note: You must set breakpoints in your code if you want to debug.  Also, set watches in the variables.


## Further resources

- Read up on the more complete instructions at code-debug plugin by WebFreak001: https://github.com/WebFreak001/code-debug
