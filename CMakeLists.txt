cmake_minimum_required(VERSION 3.10)
project(curses-tui)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g")

file (GLOB INCLUDE "include")
include_directories(${INCLUDE})

file(GLOB SOURCES "source/*.cpp")

add_executable(tui_test source/TUI.cpp source/Focus.cpp source/Misc_functions.cpp 
               source/Animations.cpp source/Timer.cpp TUI_test.cpp)


target_link_libraries(tui_test PRIVATE ncurses)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/build)
