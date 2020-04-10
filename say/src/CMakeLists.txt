cmake_minimum_required(VERSION 2.8.12)

project(Say)

add_library(say say.cpp)
target_include_directories(say PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

add_library(say::say ALIAS say)
