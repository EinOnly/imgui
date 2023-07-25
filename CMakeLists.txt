cmake_minimum_required(VERSION 2.20)
project(IMGUI CXX)

# include(FindCPPSources)

# set(SOURCE_DIR_IMGUI ${PROJECT_SOURCE_DIR})

# find_cpp_sources(CPP_SOURCES "${SOURCE_DIR_IMGUI}")

# message("ImGui Src ##############################")
# string(REPLACE ";" "\n" MY_LIST "${CPP_SOURCES}")
# foreach(item IN LISTS MY_LIST)
#   message("${item}")
# endforeach()
# message("ImGui Src ##############################")


# add_library(imgui SHARED ${CPP_SOURCES})
# target_include_directories( imgui PUBLIC  ${PROJECT_SOURCE_DIR} )

add_library(imgui STATIC ${PROJECT_SOURCE_DIR}/imgui.cpp
                         ${PROJECT_SOURCE_DIR}/imgui_draw.cpp
                         ${PROJECT_SOURCE_DIR}/imgui_demo.cpp
                         ${PROJECT_SOURCE_DIR}/imgui_tables.cpp
                         ${PROJECT_SOURCE_DIR}/imgui_widgets.cpp

                         ${PROJECT_SOURCE_DIR}/backends/imgui_impl_glfw.cpp
                         )
target_include_directories( imgui PUBLIC  ${PROJECT_SOURCE_DIR}
                                             ${PROJECT_SOURCE_DIR}/backens

)

target_link_libraries( imgui PRIVATE glfw )