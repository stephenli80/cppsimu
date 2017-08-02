cmake_minimum_required(VERSION 3.7)
project(cppsimu)

set(CMAKE_CXX_STANDARD 11)

set(SOURCE_FILES
        src/folly/io/async/AsyncUDPSocket.cpp
        src/folly/io/async/AsyncUDPSocket.h src/agv/agvsimu.cpp)

add_executable(cppsimu ${SOURCE_FILES})