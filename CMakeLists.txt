cmake_minimum_required(VERSION 3.21)
project(GDStreamChat VERSION 1.0.0)

add_library(${PROJECT_NAME} SHARED
    src/main.cpp
)

if (NOT DEFINED ENV{GEODE_SDK})
    message(FATAL_ERROR "GEODE_SDK environment variable is not set. Install Geode SDK and configure the project through its template workflow.")
endif()

add_subdirectory($ENV{GEODE_SDK} ${CMAKE_BINARY_DIR}/geode-sdk)
setup_geode_mod(${PROJECT_NAME})
