cmake_minimum_required(VERSION 2.8.12)

project(Chat)

add_library(chat chat.cpp)

if(NOT TARGET hello::hello)
    find_package(hello REQUIRED)
endif()
target_link_libraries(chat hello::hello)

add_executable(app app.cpp)

target_link_libraries(app chat)
