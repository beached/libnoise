cmake_minimum_required(VERSION 3.16 )
project(noise
        VERSION "1.0.0"
        DESCRIPTION ""
        LANGUAGES C CXX)

set ( LIBNOISE_VERSION "1.0.0-cmake" )

option(BUILD_SHARED_LIBS "Build shared libraries for libnoise" ON)
option(BUILD_LIBNOISE_DOCUMENTATION "Create doxygen documentation for developers" OFF)
option(BUILD_LIBNOISE_UTILS "Build utility functions for use with libnoise" ON)
option(BUILD_LIBNOISE_EXAMPLES "Build libnoise examples" ON)

message(STATUS "CMAKE_INSTALL_BINDIR : " ${CMAKE_INSTALL_BINDIR})
message(STATUS "CMAKE_INSTALL_LIBDIR : " ${CMAKE_INSTALL_LIBDIR})

add_subdirectory(src)

if (BUILD_LIBNOISE_UTILS)
	add_subdirectory(noiseutils)
endif()

if (BUILD_LIBNOISE_EXAMPLES)
	add_subdirectory(examples)
endif()

add_subdirectory(doc)

#add_subdirectory(samples)
