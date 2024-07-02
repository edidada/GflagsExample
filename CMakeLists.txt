cmake_minimum_required(VERSION 3.13)
project(GflagsExample)

set(CMAKE_CXX_STANDARD 11)

add_executable(gflags_test gflags_test.cc)
add_executable(gflags_test1 gflags_test1.cpp)

if(UNIX AND NOT APPLE)
    # Linux
    # Check for specific distributions
    if(EXISTS "/etc/os-release")
        file(READ "/etc/os-release" OS_RELEASE_CONTENT)
        string(FIND "${OS_RELEASE_CONTENT}" "ID=ubuntu" UBUNTU_FOUND)
        string(FIND "${OS_RELEASE_CONTENT}" "ID=debian" DEBIAN_FOUND)
        string(FIND "${OS_RELEASE_CONTENT}" "ID=centos" CENTOS_FOUND)

        if(NOT ${UBUNTU_FOUND} EQUAL -1)
            target_link_libraries(gflags_test libgflags.so)
            target_link_libraries(gflags_test1 libgflags.so)
        elseif(NOT ${DEBIAN_FOUND} EQUAL -1)
            message(STATUS "Running on Debian")
        elseif(NOT ${CENTOS_FOUND} EQUAL -1)
            message(STATUS "Running on CentOS")
        else()
            message(STATUS "Running on an unknown Unix-like system")
        endif()
    else()
        message(WARNING "Unable to detect Linux distribution: /etc/os-release not found")
    endif()
elseif(APPLE)
    # macOS
    message(STATUS "This is macOS")
elseif(WIN32)
    # Windows
    message(STATUS "This is Windows")
else()
    message(FATAL_ERROR "Unsupported operating system")
endif()