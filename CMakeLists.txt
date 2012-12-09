cmake_minimum_required(VERSION 2.8)

project(libga CXX)
set(libga_VERSION_MAJOR 0) 
set(libga_VERSION_MINOR 1) 

set(INCLUDE_DIRS inc)
include_directories(${INCLUDE_DIRS})

set(GCC_CFLAGS -std=c++11 -Wall -Wextra -Werror --pedantic)
set(VS_CFLAGS /Wall /warnaserror)

if(CMAKE_COMPILER_IS_GNUCXX)
    set(CFLAGS ${GCC_CFLAGS})
elseif(MSVC)
    set(CFLAGS ${VS_CFLAGS})
endif(CMAKE_COMPILER_IS_GNUCXX)

# for Visual Studio folders
file(GLOB INCLUDE_FILES "${INCLUDE_DIRS}/*.h")
source_group(headers\\ga FILES ${INCLUDE_FILES})

add_subdirectory(inc)
add_subdirectory(src)
