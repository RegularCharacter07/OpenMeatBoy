add_executable (OpenMeatBoy "OpenMeatBoy.cpp" "OpenMeatBoy.h")

find_package(SDL3 CONFIG REQUIRED)
target_link_libraries(OpenMeatBoy PRIVATE SDL3::SDL3)

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET OpenMeatBoy PROPERTY CXX_STANDARD 20)
endif()