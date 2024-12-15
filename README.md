# CMake Example
## Introduction
This is a very short project I did with the objective of learning how to use CMake. This is knowledge that'll help me in current and future projects. <br/>
Building this project displays a little message directed to CMake :)

Project file tree:
```
.
├── CMakeLists.txt
├── include
│   └── Hello.hpp
└── src
    ├── main.cpp
    └── App.cpp
    └── App.hpp
```

## Building
Below is the step-by-step of building and running the application with CMake.

1. Create the build directory in the root folder of the project <br/>
``$ mkdir build``

2. Navigate to the build directory <br/>
``$ cd build``

3.  Configure the project and generate a native build system <br/>
``$ cmake ..``

5.  Call that build system to actually compile/link the project <br/>
``$ make``

6.  Try to use the created executable <br/>
``$ ./CMakeExample``

| Note  | On Windows, CMake generates a MSVC solution by default, so you'll need to add `-G "Unix Makefiles"` to the CMake line on step 3. |
| :- |:-|

### If you made changes to the code and want to build again
The last build configuration is saved, so you can skip the folder creation and follow the steps below.

1. Navigate to the build folder
2. Run ``$ cmake ..``, even if you are on Windows
3. Run ``$ make``
4. Open the executable with ``$ ./CMakeExample``

## Sources
[CMake documentation](https://cmake.org/cmake/help/latest/guide/tutorial/A%20Basic%20Starting%20Point.html) </br>
[Problem with running on windows](https://stackoverflow.com/questions/39643291/make-without-makefile-after-cmake) </br>
[CMake Examples](https://github.com/ttroy50/cmake-examples) </br>
