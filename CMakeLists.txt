cmake_minimum_required(VERSION 3.17)

project(ci_test VERSION 1.0.0 LANGUAGES CXX)

add_executable(${PROJECT_NAME})


set(CMAKE_CXX_STANDARD 17)

target_sources(${PROJECT_NAME}
    PRIVATE
        main.cpp
)

# Set default compile flags for GCC
if(CMAKE_COMPILER_IS_GNUCXX)
    message(STATUS "GCC detected, adding compile flags")
    target_compile_options(${PROJECT_NAME}
        PRIVATE
            -Wall
            -Wextra
    )
endif(CMAKE_COMPILER_IS_GNUCXX)


set_target_properties(
    ${PROJECT_NAME} PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "../"
)


