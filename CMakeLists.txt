cmake_minimum_required(VERSION 3.20)
project(OpenMeatBoy)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

file(GLOB_RECURSE SOURCES "src/*.cpp")

add_executable(OpenMeatBoy ${SOURCES})

target_include_directories(OpenMeatBoy PRIVATE include)