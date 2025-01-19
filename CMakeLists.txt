cmake_minimum_required(VERSION 3.30)

project(ImGui LANGUAGES CXX)

set(IMGUI_SOURCES
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui_demo.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui_draw.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui_tables.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui_widgets.cpp
)

add_library(ImGui STATIC ${IMGUI_SOURCES})

target_include_directories(ImGui PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}
)

target_compile_features(ImGui PUBLIC cxx_std_17)