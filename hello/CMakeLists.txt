cmake_minimum_required(VERSION 2.8.12)

project(Hello)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup(TARGETS)

#Could use add_subdirectory instead of using conan package
#(conan workspace should generate this)
#
#   add_subdirectory(../say/src say)

add_subdirectory(src)
