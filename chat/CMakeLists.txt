cmake_minimum_required(VERSION 2.8.12)

project(Chat)

option(CHAT_WITH_CONAN "Use conan" ON)
if(CHAT_WITH_CONAN)
    include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
    conan_basic_setup(TARGETS)
endif()

set(CHAT_SAY_SOURCE_PATH "" CACHE PATH "Path to FiberBlob source")
if(CHAT_SAY_SOURCE_PATH)
    add_subdirectory(${CHAT_SAY_SOURCE_PATH} Say)
endif()

set(CHAT_HELLO_SOURCE_PATH "" CACHE PATH "Path to FiberBlob source")
if(CHAT_HELLO_SOURCE_PATH)
    add_subdirectory(${CHAT_HELLO_SOURCE_PATH} Hello)
endif()

add_subdirectory(src)

