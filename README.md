# CMake Example
## Introduction
This is a very short project I did with the objective of learning how to use CMake. This is knowledge that'll help me in current and future projects. <br/>
Building this project displays a little message directed to CMake :)

The files in this project include:
```bash
$ tree
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
Below is the expected output of generating makefiles with CMake and compiling with MinGW. <br/>
If you want, you can use a different compiler, but you'll need to specify the generator in the cmake command. I used MinGW because it's easier to setup and it hasn't let me down yet.

```bash
$ mkdir build

$ cd build

$ cmake .. -G "MinGW Makefiles"
-- The C compiler identification is GNU 6.3.0
-- The CXX compiler identification is GNU 6.3.0
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: C:/MinGW/bin/gcc.exe - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: C:/MinGW/bin/c++.exe - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Configuring done (2.2s)
-- Generating done (0.0s)
-- Build files have been written to: /home/dev/projects/CMakeExample/build

$ mingw32-make
[ 33%] Building CXX object CMakeFiles/CMakeExample.dir/src/App.cpp.obj
[ 66%] Building CXX object CMakeFiles/CMakeExample.dir/src/main.cpp.obj
[100%] Linking CXX executable CMakeExample.exe
[100%] Built target CMakeExample

$ ./CMakeExample.exe
Hello CMake!!
It's nice to finally understand you :)
```

| Note  | On Windows, CMake generates a MSVC solution by default, so if you want to use a different generator, you need to specify in the cmake command. For example, for the MinGW generator, add `-G "Unix Makefiles"` to the command. |
| :- |:-|

## Sources
[CMake documentation](https://cmake.org/cmake/help/latest/guide/tutorial/A%20Basic%20Starting%20Point.html) </br>
[Problem with running on windows](https://stackoverflow.com/questions/39643291/make-without-makefile-after-cmake) </br>
[CMake Examples](https://github.com/ttroy50/cmake-examples) </br>
