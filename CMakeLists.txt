cmake_minimum_required(VERSION 2.8)
project( ProjectName )
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake/Modules/")

SET(CUSTOM_COMPILER_FLAGS "-std=c++11 -stdlib=libstdc++")

SET( CMAKE_CXX_FLAGS  "${CMAKE_CXX_FLAGS} ${CUSTOM_COMPILER_FLAGS}")
SET( CMAKE_EXE_LINKER_FLAGS  "${CMAKE_EXE_LINKER_FLAGS} ${CUSTOM_COMPILER_FLAGS}" )


#dynamically get gtest
include( cmake/Modules/gtest.cmake )
include_directories( ${GTEST_INCLUDE_DIR} )

# Set BOOST_ROOT environment variable to point to your local Boost dir.
find_package( Boost REQUIRED )
include_directories( ${Boost_INCLUDE_DIR} )


add_subdirectory( src )
add_subdirectory( test )
