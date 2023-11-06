cmake_minimum_required(VERSION 3.10)
project (lib-test VERSION 0.0.1 LANGUAGES CXX)
set(CMAKE_CXX_STANDARD 20)

      

file(GLOB_RECURSE SOURCES RELATIVE ${CMAKE_SOURCE_DIR}
  "include/**.h"
  "include/**.hpp"
  "src/**.cpp"
  "src/**.c"
  )
      
include(FetchContent)

if(RELEASE EQUAL 1)
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O2 -Wextra -Wpedantic -Wall")
  add_definitions(-DRELEASE)
else()
  add_definitions(-DDEBUG)
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g -O0 -Wextra -Wpedantic -Wall")
  if(TEST_MODE EQUAL 1)
  endif()
endif()
     
add_library(lib-test-lib STATIC ${SOURCES})


target_include_directories(lib-test-lib PUBLIC include)
