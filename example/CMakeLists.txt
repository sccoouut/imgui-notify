cmake_minimum_required(VERSION 3.0)

project(imgui-notify_example LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED YES)
set(CMAKE_CXX_EXTENSIONS NO)

file(GLOB_RECURSE ${PROJECT_NAME}_LIST
        "${CMAKE_CURRENT_SOURCE_DIR}/*.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/*.cc"
        "${CMAKE_CURRENT_SOURCE_DIR}/*.cxx"
        "${CMAKE_CURRENT_SOURCE_DIR}/*.cpp"
        )
file(GLOB_RECURSE ${PROJECT_NAME}_LIST_H
        "${CMAKE_CURRENT_SOURCE_DIR}/*.h"
        "${CMAKE_CURRENT_SOURCE_DIR}/*.hh"
        "${CMAKE_CURRENT_SOURCE_DIR}/*.hxx"
        "${CMAKE_CURRENT_SOURCE_DIR}/*.hpp"
        )

add_executable(${PROJECT_NAME}
        ${${PROJECT_NAME}_LIST}
        ${${PROJECT_NAME}_LIST_H}
        )

target_compile_definitions(${PROJECT_NAME} PUBLIC
        "ImTextureID=ImU64"
        "_UNICODE"
        "UNICODE"
        )

target_link_libraries(${PROJECT_NAME} PUBLIC
        d3d12
        d3dcompiler
        dxgi

        imgui-notify
        )