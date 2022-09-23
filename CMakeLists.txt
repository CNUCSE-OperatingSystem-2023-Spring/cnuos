cmake_minimum_required(VERSION 3.22.0)
project(cnuos
    VERSION 1.0.0
    LANGUAGES C)

set(target "cnuos")
set(arch   "aarch64-linux")

set(CMAKE_C_STANDARD 11)
set(CMAKE_C_IMPLICIT_LINK_LIBRARIES "")
set(CMAKE_C_IMPLICIT_LINK_DIRECTORIES "")

file(GLOB_RECURSE
    src
        CONFIGURE_DEPENDS
            ${CMAKE_CURRENT_SOURCE_DIR}/src/*.c
            ${CMAKE_CURRENT_SOURCE_DIR}/src/**/*.c
            ${CMAKE_CURRENT_SOURCE_DIR}/src/**/**/*.c
)

target_sources(
    ${target} PRIVATE ${src}
)

target_include_directories(
    ${target} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include
)
