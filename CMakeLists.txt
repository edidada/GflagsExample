cmake_minimum_required(VERSION 3.13)
project(GflagsExample)

set(CMAKE_CXX_STANDARD 11)

add_executable(GflagsExample gflags_test.cc gflags_test1.cpp)