cmake_minimum_required(VERSION 3.10)
project(turbo-base64)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

list(APPEND SOURCES "turbob64c.c" "turbob64d.c" "turbob64v128.c")
if(NOT MSVC)
    list (APPEND SOURCES "turbob64v256.c")
endif()
set(HEADERS "turbob64.h" "turbob64_.h")

add_library(turbo-base64 ${SOURCES} ${HEADERS})
if(NOT MSVC)
    target_compile_options(turbo-base64 PUBLIC "-mavx2")
endif()
