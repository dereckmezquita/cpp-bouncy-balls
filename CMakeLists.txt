cmake_minimum_required(VERSION 3.23)
project(cpp_bouncy_balls)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++17")

set(
    SOURCE_FILES
        main.cpp
        src/physics/Vec2.cpp
        src/physics/Vec2.h
        src/physics/Ball.cpp
        src/physics/Ball.h
)

add_executable(cpp_bouncy_balls ${SOURCE_FILES})

# Find SFML with capitalized component names
find_package(SFML 3.0 COMPONENTS Graphics Window Audio Network REQUIRED)

# Add include directories
include_directories(${SFML_INCLUDE_DIRS})

# Link against SFML libraries with namespace
target_link_libraries(cpp_bouncy_balls SFML::Graphics SFML::Window SFML::Network SFML::Audio)