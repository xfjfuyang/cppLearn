cmake_minimum_required(VERSION 3.26)
project(cppLearn)

set(CMAKE_CXX_STANDARD 17)

set(gtest_path  ${CMAKE_SOURCE_DIR}/../../../googletest)

message(STATUS ${CMAKE_BUILD_RPATH})


add_subdirectory(${gtest_path} ${CMAKE_BUILD_RPATH}/gtest)

add_executable(cppLearn main.cpp
        include/comm.h)


target_include_directories(cppLearn PUBLIC
    ${CMAKE_SOURCE_DIR}/include
)

target_link_libraries(cppLearn PRIVATE
    gtest
    gmock
)
