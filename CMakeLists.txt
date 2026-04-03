cmake_minimum_required(VERSION 3.20)
project(OpenMeatBoy)

set(CMAKE_CXX_STANDARD 20)

find_package(OpenGL REQUIRED)
find_package(SDL3 REQUIRED)
find_package(glm REQUIRED)
add_library(glad external/glad/src/glad.c)
target_include_directories(glad PUBLIC external/glad/include)

add_subdirectory(src)