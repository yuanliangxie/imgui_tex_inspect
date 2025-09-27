

find_package(OpenGL REQUIRED)

add_library(imgui_tex_inspect_lib
        backends/tex_inspect_opengl.cpp
        imgui_tex_inspect.cpp
        imgui_tex_inspect_demo.cpp
        imgui_tex_inspect_internal.h
)

target_include_directories(imgui_tex_inspect_lib PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/backends
        ${CMAKE_CURRENT_SOURCE_DIR}
)

target_link_libraries(imgui_tex_inspect_lib PUBLIC
        imgui
        stb_image
        OpenGL::GL
        glad
)