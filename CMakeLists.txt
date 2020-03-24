cmake_minimum_required(VERSION 2.8)
project(OouraFFT)

########################################################################
# select the release build type by default to get optimization flags
########################################################################
if(NOT CMAKE_BUILD_TYPE)
   set(CMAKE_BUILD_TYPE "Release")
   message(STATUS "Build type not specified: defaulting to release.")
endif(NOT CMAKE_BUILD_TYPE)


add_library(OouraFFT STATIC
  fft4g.c #fft4g.h 
)

target_include_directories(OouraFFT PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})

set_property(TARGET OouraFFT APPEND PROPERTY INTERFACE_INCLUDE_DIRECTORIES
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
)

#target_link_libraries(OouraFFT m)
