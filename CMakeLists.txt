cmake_minimum_required(VERSION 3.0.0)
project(restbedtestfrontpageexampleserver VERSION 0.1.0)

include(CTest)
enable_testing()

add_executable(restbedtestfrontpageexampleserver main.cpp)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)

# Setup
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(CMAKE_BINARY_DIR "./build")
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR})
set(LIBRARY_OUTPUT_PATH ${CMAKE_BINARY_DIR})

# FD Variables
set(FDRService_VERSION_MAJOR 1)
set(FDRService_VERSION_MINOR 0)

set(FDRService_INCLUDE_DIR "./include")
set(FDRService_SOURCE_DIR "./src")

# RestBED
set(RESTBED_ROOT "/home/mfchrist/cernbox/restbedtests/restbed/distribution")
set(RESTBED_INCLUDE_DIR "${RESTBED_ROOT}/include")
set(RESTBED_LIBRARY_DIR "${RESTBED_ROOT}/library")

# find all libraries
file(GLOB_RECURSE RESTBED_LIBRARY_FILES
    "${RESTBED_LIBRARY_DIR}/*.a"
)

include_directories(${RESTBED_INCLUDE_DIR})

# find project source files
file(GLOB_RECURSE FDRService_FILES
    "${FDRService_INCLUDE_DIR}/*.h"
    "${FDRService_INCLUDE_DIR}/*.hpp"
    "${FDRService_SOURCE_DIR}/*.c"
    "${FDRService_SOURCE_DIR}/*.cpp"
)
    $(RM) $(OBJECTS) $(EXECUTABLE)