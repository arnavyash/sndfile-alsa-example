# (c) Arnav Yash Chandra 2020.
# Distributed under the Boost Software License, Version 1.0.
# (See accompanying file LICENSE or copy at
# https://www.boost.org/LICENSE_1_0.txt)

cmake_minimum_required(VERSION 3.12)

project(sndfile-alsa-example 
  VERSION 0.1
  DESCRIPTION "Example that uses libsndfile and ALSA to play sound files."
  LANGUAGES C
)

# append <project-root>/cmake to CMAKE_MODULE_PATH to
# help CMake find the Find*.cmake files.
list(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake/modules")

add_subdirectory(src)

## add a target executable `sndfile-alsa` to the project
#add_executable(sndfile-alsa sndfile-alsa.c)
#
## add libasound as a dependency to the target `sndfile-alsa`
#find_package(ALSA REQUIRED)
#if (ALSA_FOUND)
#  target_include_directories(sndfile-alsa PUBLIC ${ALSA_INCLUDE_DIRS})
#  target_link_libraries(sndfile-alsa ${ALSA_LIBRARIES})
#endif(ALSA_FOUND)
#
## add libsndfile as a dependency to the target `sndfile-alsa`
#find_package(SNDFILE REQUIRED)
#if (SNDFILE_FOUND)
#  target_include_directories(sndfile-alsa PUBLIC ${SNDFILE_INCLUDE_DIRS})
#  target_link_libraries(sndfile-alsa ${SNDFILE_LIBRARIES})
#endif(SNDFILE_FOUND)
#
## Instructions for helping CMake determine where to install
## the targets
#include(GNUInstallDirs)
#install(TARGETS sndfile-alsa RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR})
#
