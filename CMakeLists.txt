# Set the minimum version of CMake that can be used.
# $ cmake --version
cmake_minimum_required (VERSION 3.5)

# Set project name.
project (CMakeExample)

# Enable Hot Reload for MSVC compilers if supported.
if (POLICY CMP0141)
  cmake_policy(SET CMP0141 NEW)
  set(CMAKE_MSVC_DEBUG_INFORMATION_FORMAT "$<IF:$<AND:$<C_COMPILER_ID:MSVC>,$<CXX_COMPILER_ID:MSVC>>,$<$<CONFIG:Debug,RelWithDebInfo>:EditAndContinue>,$<$<CONFIG:Debug,RelWithDebInfo>:ProgramDatabase>>")
endif()

# Search the directory tree for all the files that match the pattern.
# This is an alternative to individually setting all the files with set(source).
file (GLOB_RECURSE sources src/*.cpp src/*.hpp)
#file (GLOB_RECURSE data resources/*)

# Add the data to the project.
add_executable(CMakeExample ${sources})
#add_executable(CMakeExample ${sources} ${data})

# Include files in these directories in the build command.
target_include_directories(CMakeExample PUBLIC
	${PROJECT_SOURCE_DIR}/include
)