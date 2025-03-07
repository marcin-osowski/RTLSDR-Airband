cmake_minimum_required (VERSION 3.1)
project (RTLSDR-Airband CXX)

set (RTL_AIRBAND_VERSION_MAJOR 4)
set (RTL_AIRBAND_VERSION_MINOR 1)
set (RTL_AIRBAND_VERSION_PATCH 1)
set (RTL_AIRBAND_VERSION "${RTL_AIRBAND_VERSION_MAJOR}.${RTL_AIRBAND_VERSION_MINOR}.${RTL_AIRBAND_VERSION_PATCH}")

set (CMAKE_CXX_STANDARD 11)
set (CXX_STANDARD_REQUIRED ON)
set (CMAKE_CXX_EXTENSIONS OFF)
set (CMAKE_COMPILE_WARNING_AS_ERROR ON)

if(NOT CMAKE_BUILD_TYPE)
   set(CMAKE_BUILD_TYPE Release)
   message(STATUS "Build type not specified: defaulting to Release")
endif(NOT CMAKE_BUILD_TYPE)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra")
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -Og -DDEBUG")

if(DEBUG_SQUELCH)
   set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -DDEBUG_SQUELCH")
endif()

add_subdirectory (src)

