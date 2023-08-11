cmake_minimum_required(VERSION 3.9)
project(AV1 C CXX)

set(ROOT "${CMAKE_CURRENT_SOURCE_DIR}")
set(CONFIG_DIR "${CMAKE_CURRENT_BINARY_DIR}")

# Set g++ as the C++ compiler and gcc as the C compiler
set(CMAKE_C_COMPILER gcc)
set(CMAKE_CXX_COMPILER g++)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include_directories(${ROOT}/third_party)
include_directories(${ROOT}/src)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -O2 -Wall")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O2 -Wall")

file(GLOB_RECURSE SOURCE_FILES "${ROOT}/src/*.cc")
add_executable(av1_encoder ${SOURCE_FILES})
