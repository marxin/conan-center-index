cmake_minimum_required(VERSION 3.15)
project(test_package LANGUAGES CXX)

find_package(gperftools REQUIRED CONFIG)

add_executable(${PROJECT_NAME} test_package.cpp)
target_link_libraries(${PROJECT_NAME} PRIVATE gperftools::gperftools)

add_executable(${PROJECT_NAME}_minimal test_package.cpp)
target_link_libraries(${PROJECT_NAME}_minimal PRIVATE gperftools::tcmalloc_minimal)
