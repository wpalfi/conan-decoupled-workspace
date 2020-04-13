cmake_minimum_required(VERSION 2.8.12)

project(Hello)

option(HELLO_WITH_CONAN "Use conan" ON)
if(HELLO_WITH_CONAN)
    include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
    conan_basic_setup(TARGETS)
else()
    add_subdirectory(../say/src say) # could use e.g. cache variable for path in real world
endif()

add_subdirectory(src)
