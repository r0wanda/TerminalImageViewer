cmake_minimum_required(VERSION 3.23)

project(TerminalImageViewer LANGUAGES CXX)

add_executable(tiv_bin)
add_library(tiv)

target_compile_options(tiv PRIVATE -O2 -std=c++17 -Wall -Wextra -fexceptions)
set(THREADS_PREFER_PTHREAD_FLAG ON)
find_package(Threads REQUIRED)
find_package(ZLIB REQUIRED)
find_package(PNG REQUIRED)

target_sources(tiv
    PRIVATE
        src/main.cpp
		src/poddy.cpp
		src/poddy.hpp
)


target_link_libraries(tiv PRIVATE Threads::Threads PNG::PNG)
