cmake_minimum_required(VERSION 3.0.0)
project(main VERSION 0.1.0 LANGUAGES C CXX)

include(CTest)
enable_testing()

include_directories(
    ${CMAKE_SOURCE_DIR}/lib/inc
)


link_directories(
    ${CMAKE_SOURCE_DIR}/lib
)

add_executable(main main.cpp)

target_link_libraries(main add)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
