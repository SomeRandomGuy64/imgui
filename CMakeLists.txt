cmake_minimum_required(VERSION 3.30)

project(ImGui LANGUAGES CXX)

set(IMGUI_SOURCES
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui_demo.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui_draw.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui_tables.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui_widgets.cpp
)

set(IMGUI_HEADERS
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui.h
    ${CMAKE_CURRENT_SOURCE_DIR}/imconfig.h
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui_internal.h
    ${CMAKE_CURRENT_SOURCE_DIR}/imstb_rectpack.h
    ${CMAKE_CURRENT_SOURCE_DIR}/imstb_textedit.h
    ${CMAKE_CURRENT_SOURCE_DIR}/imstb_truetype.h
)

set(IMGUI_BACKEND_SOURCES
    ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_dx11.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_dx11.h
    ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_dx12.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_dx12.h
    ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_metal.h
    ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_metal.mm
    ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_opengl3.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_opengl3.h
    ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_opengl3_loader.h
    ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_sdl3.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_sdl3.h
    ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_vulkan.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_vulkan.h
    ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_wgpu.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_wgpu.h
    ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_win32.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_win32.h
)

add_library(ImGui STATIC ${IMGUI_SOURCES} ${IMGUI_BACKEND_SOURCES})

target_include_directories(ImGui PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_CURRENT_SOURCE_DIR}/backends
)

target_compile_features(ImGui PUBLIC cxx_std_17)