cmake_minimum_required(VERSION 3.10)

project(hello_world_with_formatter_ex)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_executable(${PROJECT_NAME} hello_world.cpp)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib)

find_library(formatter_ex NAMES libformatter_ex.a PATHS ${CMAKE_CURRENT_SOURCE_DIR}/formatter_ex_lib)
find_library(formatter NAMES libformatter.a PATHS ${CMAKE_CURRENT_SOURCE_DIR}/formatter_lib)

target_link_libraries(${PROJECT_NAME} formatter_ex)

