cmake_minimum_required(VERSION 3.10)
project(turbo-base64)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

set(SOURCES "turbob64c.c" "turbob64d.c" "turbob64sse.c" "turbob64avx2.c")

add_library(turbo-base64 ${SOURCES})
target_compile_options(turbo-base64 PUBLIC "-mavx2")