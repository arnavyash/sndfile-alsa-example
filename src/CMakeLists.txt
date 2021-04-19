# SPDX-FileCopyrightText: 2021 arnavyc
# 
# SPDX-License-Identifier: 0BSD
# 
# Distributed under the BSD Zero Clause License
# (See accompanying file LICENSE)

# add a target executable `sndfile-alsa` to the project
add_executable(sndfile-alsa sndfile-alsa.c)

# add libasound as a dependency to the target `sndfile-alsa`
find_package(ALSA REQUIRED)
if (ALSA_FOUND)
  target_include_directories(sndfile-alsa PUBLIC ${ALSA_INCLUDE_DIRS})
  target_link_libraries(sndfile-alsa ${ALSA_LIBRARIES})
endif(ALSA_FOUND)

# add libsndfile as a dependency to the target `sndfile-alsa`
find_package(SNDFILE REQUIRED)
if (SNDFILE_FOUND)
  target_include_directories(sndfile-alsa PUBLIC ${SNDFILE_INCLUDE_DIRS})
  target_link_libraries(sndfile-alsa ${SNDFILE_LIBRARIES})
endif(SNDFILE_FOUND)

# Instructions for helping CMake determine where to install
# the targets
include(GNUInstallDirs)
install(TARGETS sndfile-alsa RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR})

