cmake_minimum_required(VERSION 3.22.1)
project("glover_port")

add_definitions(-D__ANDROID__ -DENABLE_PC_MENU)

file(GLOB_RECURSE GAME_SOURCES "*.cpp" "*.c")

add_library(main SHARED ${GAME_SOURCES})

target_link_libraries(
    main
    GLESv2
    EGL
    log
    android
    z
    m
)
