cmake_minimum_required(VERSION 3.8.0...4.0.2)
project(compile_test VERSION 0.1.0 LANGUAGES C CXX)

set(CMAKE_CXX_STANDARD 17)

set(CMAKE_CXX_FLAGS_SAN "${CMAKE_CXX_FLAGS_DEBUG} -fsanitize=undefined -fsanitize=address")

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

if(NOT CMAKE_BUILD_TYPE )
    set(CMAKE_BUILD_TYPE "Debug")
endif()

message(STATUS "BUILD TYPE : ${CMAKE_BUILD_TYPE}")

include_directories(include)

add_subdirectory(src)
