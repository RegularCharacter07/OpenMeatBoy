cmake_minimum_required(VERSION 3.25)
project(OpenMeatBoy VERSION 0.1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

option(SMB_BUILD_TESTS "Build tests" ON)
option(SMB_BUILD_MODS  "Build mods" ON)

find_package(OpenGL REQUIRED)
add_subdirectory(external/SDL3)
add_subdirectory(external/glm)
add_subdirectory(external/glad)

add_subdirectory(engine)
add_subdirectory(game)

if(SMB_BUILD_TESTS)
    enable_testing()
    add_subdirectory(tests)
endif()

if(SMB_BUILD_MODS)
    add_subdirectory(mods)
endif()