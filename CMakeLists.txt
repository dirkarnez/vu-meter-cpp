cmake_minimum_required(VERSION 3.18)

project(portaudio-playground C)

SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -static")

SET(BUILD_SHARED_LIBS OFF)

find_package(PortAudio REQUIRED PATHS "P:\\Downloads\\cpp-libraries\\portaudio\\build\\cmake\\portaudio")

IF(PortAudio_FOUND)
    message(STATUS "YES")
ELSE(PortAudio_FOUND)
    message(STATUS "NO")
ENDIF(PortAudio_FOUND)

add_executable(${PROJECT_NAME}
    "src/main.c"
)

target_link_libraries(${PROJECT_NAME} PortAudio)
