# Copyright 2016 Boise State University.  All rights reserved.
# Use of this source code is governed by a BSD-style
# license that can be found in the LICENSE file.

cmake_minimum_required(VERSION 2.8.8)

include_directories(sqlite)
include_directories(filter)

add_subdirectory(sqlite)
add_subdirectory(filter)

add_executable(bcal bcal.c
               $<TARGET_OBJECTS:filter>)

target_link_libraries(bcal ${GDAL_LIBRARY})
