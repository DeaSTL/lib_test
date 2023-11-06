# CMakeLists.txt

# Set the minimum required CMake version
cmake_minimum_required(VERSION 3.12)

# Project name
project(MyLibrary)

# Define the source files for your library
set(SOURCE_FILES
    src/lib-test.cpp
    include/lib-test.hpp
)

# Create the static library
add_library(lib_test STATIC ${SOURCE_FILES})

# Specify include directories for your library if needed
target_include_directories(lib_test PUBLIC include)

# You can also set compile options if necessary
# target_compile_options(lib_test PRIVATE -Wall -Wextra)

# Optionally, you can install the library and header files
install(TARGETS lib_test
    ARCHIVE DESTINATION lib
)

install(DIRECTORY include/
    DESTINATION include
)
