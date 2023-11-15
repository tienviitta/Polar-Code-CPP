cmake_minimum_required(VERSION 3.18...3.22)

# Project
project(pccpp
    VERSION 0.0.1
    DESCRIPTION "Polar FEC Studies and Libraries"
    LANGUAGES CXX
)

# Define the minimum C++ standard that is required
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

if(MSVC)
    add_compile_options(/W4 /WX)
else()
    add_compile_options(-Wall -Wextra -pedantic -Werror)
endif()

add_executable(pccpp
    src/pccpp.cpp
    src/polar.cpp
    src/polar.h
)

set_property(TARGET pccpp PROPERTY C_STANDARD 20)
set_property(TARGET pccpp PROPERTY C_STANDARD_REQUIRED ON)
target_link_libraries(pccpp PRIVATE m)
