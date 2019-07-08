cmake_minimum_required(VERSION 3.4.1)

set(CMAKE_VERBOSE_MAKEFILE on)
set(can_use_assembler TRUE)
enable_language(ASM)

set(SOURCES)
file(GLOB_RECURSE SOURCES "*.c")

add_library(dk-blur-lib SHARED ${SOURCES})

set(libs)
list(APPEND libs
	jnigraphics
    android
    log
)

target_link_libraries(dk-blur-lib ${libs})
