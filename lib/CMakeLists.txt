cmake_minimum_required(VERSION 3.0.0)
project(add VERSION 0.1.0 LANGUAGES C CXX)

include(CTest)
enable_testing()


include_directories(
    ${CMAKE_SOURCE_DIR}/lib/inc
)

add_library(add SHARED ${CMAKE_SOURCE_DIR}/lib/src/add.cpp ${CMAKE_SOURCE_DIR}/lib/inc/add.h)

set_target_properties(add PROPERTIES LIBRARY_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/lib)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
