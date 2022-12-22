cmake_minimum_required(VERSION 3.25)

project(testcase1)

add_library(testcase1 src/message.cpp)

if (WIN32)
    target_compile_definitions(testcase1
        PRIVATE
            -D_WIN32_WINNT=0x0601
    )
endif()

target_precompile_headers(testcase1
    PRIVATE
        <iostream>)

set_target_properties(testcase1
    PROPERTIES
        CXX_STANDARD 23
        CXX_STANDARD_REQUIRED ON
)