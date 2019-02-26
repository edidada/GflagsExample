cmake_minimum_required(VERSION 3.13)
project(GflagsExample)

set(CMAKE_CXX_STANDARD 11)

add_executable(gflags_test gflags_test.cc)
add_executable(gflags_test1 gflags_test1.cpp)

target_link_libraries(gflags_test libgflags.so)
target_link_libraries(gflags_test1 libgflags.so)