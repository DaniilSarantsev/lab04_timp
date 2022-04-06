cmake_minimum_required(VERSION 3.10)
project(solver_app)
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
add_executable(solver_app equation.cpp)

add_library(${PROJECT_NAME}_lib STATIC ${CMAKE_CURRENT_SOURCE_DIR}/../solver_lib/solver.cpp
        ${CMAKE_CURRENT_SOURCE_DIR}/../solver_lib/solver.h)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib)
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib formatter_ex)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../solver_lib)


target_link_libraries(${PROJECT_NAME} formatter_ex solver_lib)
