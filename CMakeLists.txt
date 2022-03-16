cmake_minimum_required(VERSION 3.0)

project(imgui-notify LANGUAGES CXX)

option(${PROJECT_NAME}_BUILD_EXAMPLE "Build an example" OFF)

add_library(${PROJECT_NAME} INTERFACE)

target_include_directories(${PROJECT_NAME} INTERFACE
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
    $<INSTALL_INTERFACE:include>
    )

if (${PROJECT_NAME}_BUILD_EXAMPLE)
    add_subdirectory(example)
endif ()
