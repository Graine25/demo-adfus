# adfus - ReXGlue Recompiled Project
#
# This file is yours to edit. 'rexglue migrate' will NOT overwrite it.
# SDK boilerplate lives in generated/rexglue.cmake.

cmake_minimum_required(VERSION 3.25)
set(adfus_LANGUAGES CXX)
if(APPLE)
    list(APPEND adfus_LANGUAGES OBJC OBJCXX)
endif()
project(adfus LANGUAGES ${adfus_LANGUAGES})

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include(generated/rexglue.cmake)

# Sources
set(adfus_SOURCES
    src/main.cpp
)

if(WIN32)
    add_executable(adfus WIN32 ${adfus_SOURCES})
else()
    add_executable(adfus ${adfus_SOURCES})
endif()

rexglue_setup_target(adfus)

