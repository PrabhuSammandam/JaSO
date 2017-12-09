cmake_minimum_required(VERSION 3.7)

project(simpleserver)

# Set the output folder where your program will be created
set(CMAKE_BINARY_DIR ${CMAKE_SOURCE_DIR}/bin)
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR})
set(LIBRARY_OUTPUT_PATH ${CMAKE_BINARY_DIR})

# The following folder will be included
include_directories(../JaCoAPCore/code/inc ../JaCoAPCore/code/port)

#However, the file(GLOB...) allows for wildcard additions:
#file(GLOB SOURCES "*.cpp")

set (SOURCES ServerExample.cpp  ServerDataChannel.cpp)
set ( PROJECT_LINK_LIBS libjacoapcore.a libws2_32.a)
link_directories( ../JaCoAPCore/code/bin )

add_executable(simpleserver ${SOURCES})
target_link_libraries(simpleserver ${PROJECT_LINK_LIBS} )

