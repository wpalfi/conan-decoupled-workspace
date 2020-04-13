cmake_minimum_required(VERSION 2.8.12)

project(Hello)

add_library(hello hello.cpp)
target_include_directories(hello PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

add_library(hello::hello ALIAS hello)

if(NOT TARGET say::say)
    find_package(say REQUIRED)
endif()
target_link_libraries(hello say::say)
