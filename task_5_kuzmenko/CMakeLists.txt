cmake_minimum_required(VERSION 3.2)

project(Simple_sieve LANGUAGES CXX)
set(CMAKE_CXX_STANDARD 11) # set standard to 11 (we use auto, chrono and uint32_t so we nead at least C++ 11)

if(NOT CMAKE_BUILD_TYPE) # if CMAKE_BUILD_TYPE is undefined
    set(CMAKE_BUILD_TYPE Release) # set it to Release
endif()

#set(CMAKE_CXX_FLAGS "-Wall -Wextra -pedantic") # Set flags for compilation (applied both to Release and Debug or any other type). NOTE: this flags are g++ specific.
set(CMAKE_CXX_FLAGS_DEBUG "-Og -g -DDEBUG") # Set additional flags for Debug builds. NOTE: this flags are g++ specific.
#set(CMAKE_CXX_FLAGS_RELEASE "-Ofast -DNDEBUG -march=native") # Set additional flags for Release builds. NOTE: this flags are g++ specific.

add_executable(main main.cpp list.cpp list.h)

enable_testing()
add_test(NAME test_list COMMAND ./main test_file)