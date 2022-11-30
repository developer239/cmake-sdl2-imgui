cmake_minimum_required(VERSION 3.23)
project(CMake_SDL2_ImGui)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED true)

add_executable(CMake_SDL2_ImGui main.cpp)

## SDL

list(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake/sdl2)

find_package(SDL2 REQUIRED)
find_package(SDL2_ttf REQUIRED)
find_package(SDL2_image REQUIRED)
find_package(SDL2_mixer REQUIRED)

target_link_libraries(${PROJECT_NAME} PUBLIC SDL2::SDL2 SDL2::TTF
        SDL2::Image SDL2::Mixer)

## ImGui

list(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake/imgui)

find_package(Imgui REQUIRED)

target_link_libraries(${PROJECT_NAME} PUBLIC Imgui)
