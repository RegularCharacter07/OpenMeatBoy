file(GLOB_RECURSE SOURCES main.cpp)

add_executable(OpenMeatBoy ${SOURCES})

target_include_directories(OpenMeatBoy PUBLIC ../include)

target_link_libraries(OpenMeatBoy
    PRIVATE
    SDL3::SDL3
    OpenGL::GL
    glad
    glm::glm
)