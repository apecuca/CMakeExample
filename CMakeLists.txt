# Set the minimum version of CMake that can be used
# $ cmake --version
# make --version
cmake_minimum_required (VERSION 3.5)

# Set project name
project (CMakeExample)

# Enable Hot Reload for MSVC compilers if supported.
if (POLICY CMP0141)
  cmake_policy(SET CMP0141 NEW)
  set(CMAKE_MSVC_DEBUG_INFORMATION_FORMAT "$<IF:$<AND:$<C_COMPILER_ID:MSVC>,$<CXX_COMPILER_ID:MSVC>>,$<$<CONFIG:Debug,RelWithDebInfo>:EditAndContinue>,$<$<CONFIG:Debug,RelWithDebInfo>:ProgramDatabase>>")
endif()

# Add executables to project
add_executable(CMakeExample 
	src/main.cpp
)

# Set the directories that will be included in the build command
target_include_directories(CMakeExample
	PRIVATE
		${PROJECT_SOURCE_DIR}/include
)