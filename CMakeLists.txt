cmake_minimum_required(VERSION 3.18)

project("portaudio-playground" C)

SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -static")

find_package(portaudio 19 EXACT REQUIRED) # PATHS "P:\\Downloads\\cpp-libraries\\portaudio\\build\\cmake\\portaudio")

IF(portaudio_FOUND)
    message(STATUS "YES")
ELSE(portaudio_FOUND)
    message(STATUS "NO")
ENDIF(portaudio_FOUND)

add_executable(${PROJECT_NAME}
    "src/main.c"
    "src/vu-meter.c"
    "src/vu-meter.h"
)

target_link_libraries(${PROJECT_NAME} portaudio_static)
