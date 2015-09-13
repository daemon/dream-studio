cmake_minimum_required(VERSION 2.6)
project(DREAM_STUDIO)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

set(CMAKE_CXX_FLAGS "-g -Wall -std=c++11")
set(sqlite3_DIR "${CMAKE_SOURCE_DIR}/cmake_modules")
find_package(sqlite3)

if (SQLITE3_FOUND)
  ADD_DEFINITIONS(-DWITH_SQLITE)
  include_directories(SQLITE3_INCLUDE_DIR)
endif (SQLITE3_FOUND)

add_subdirectory(src)