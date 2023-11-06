cmake_minimum_required(VERSION 3.10)
project (lib_test_project VERSION 0.0.1 LANGUAGES CXX)
set(CMAKE_CXX_STANDARD 20)

      

file(GLOB_RECURSE SOURCES RELATIVE ${CMAKE_SOURCE_DIR}
  "include/**.h"
  "include/**.hpp"
  "src/**.cpp"
  "src/**.c"
  )
      
include(FetchContent)

    

add_library(lib_test STATIC ${SOURCES})


target_include_directories(lib_test PUBLIC include)
