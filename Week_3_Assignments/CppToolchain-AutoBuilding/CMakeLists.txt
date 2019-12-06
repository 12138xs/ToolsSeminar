cmake_minimum_required(VERSION 3.10)
project(PROJECT)

option(TEST3 "Build the project using TEST3" OFF)
option(TEST2 "Build the project using TEST2" OFF)
option(TEST1 "Build the project using TEST1" OFF)

if(TEST1)
  add_definitions(-D TEST1)
elseif(TEST2)
  add_definitions(-D TEST2)
elseif(TEST3)
  add_definitions(-D TEST3)
endif()

include_directories(include)
link_directories(lib)
link_libraries(libstest.a)

add_executable(display display.cpp mesh.cpp)
target_link_libraries(display libstest.a -lGL -lglut -lGLU)
