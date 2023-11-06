cmake_minimum_required(VERSION 3.10)
project (lib_test VERSION 0.0.1 LANGUAGES CXX)
set(CMAKE_CXX_STANDARD 20)
include(FetchContent)


add_library(lib_test STATIC ${CMAKE_SOURCE_DIR}src/)


target_include_directories(lib_test PUBLIC include)
