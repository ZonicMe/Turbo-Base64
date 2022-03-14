cmake_minimum_required(VERSION 3.10)
project(turbo-base64)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

set(SOURCES "turbob64c.c" "turbob64d.c" "turbob64v128.c" "turbob64v256.c")
set(HEADERS "turbob64.h" "turbob64_.h")

add_library(turbo-base64 ${SOURCES} ${HEADERS})
target_compile_options(turbo-base64 PUBLIC "-mavx2")
